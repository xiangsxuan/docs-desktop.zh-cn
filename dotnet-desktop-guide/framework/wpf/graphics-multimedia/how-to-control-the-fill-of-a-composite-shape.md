---
title: 如何：控制复合形状的填充
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], composite [WPF], controlling fill
- composite shapes [WPF], controlling fill
- graphics [WPF], composite shapes
- fill [WPF], controlling
ms.assetid: c1c94575-9eca-48a5-a49a-2ec65259f229
ms.openlocfilehash: 89f69d392e8838af99538c759a2f06453e1bcd60
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973530"
---
# <a name="how-to-control-the-fill-of-a-composite-shape"></a>如何：控制复合形状的填充

<xref:System.Windows.Media.GeometryGroup.FillRule%2A>或的属性 <xref:System.Windows.Media.GeometryGroup> <xref:System.Windows.Media.PathGeometry> 指定一个 "规则"，组合形状使用该 "规则" 来确定给定点是否为几何图形的一部分。 有两个可能的值 <xref:System.Windows.Media.FillRule> ： <xref:System.Windows.Media.FillRule.EvenOdd> 和 <xref:System.Windows.Media.FillRule.Nonzero> 。 以下各节将介绍如何使用这两个规则。

**EvenOdd：** 此规则通过从一点向任意方向绘制一条射向无穷远的射线，然后计算给定形状中与该射线相交的路径段的数量，从而确定该点是否位于填充区域中。 如果此数目为奇数，那么该点则在内部；如果为偶数，则该点在外部。

例如，下面的 XAML 创建复合形状，其中包含一系列同心圆环 (目标) ，其 <xref:System.Windows.Media.GeometryGroup.FillRule%2A> 设置为 <xref:System.Windows.Media.FillRule.EvenOdd> 。

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleEvenOddValue](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillruleevenoddvalue)]

下图显示在上一个示例中创建的形状。

![由带有交替颜色的系列同心圆环组成的圆。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-property.png)

在上图中，请注意，不会填写中心和第三环。 这是因为射线是从穿过偶数段的这两个环中的点绘制的。 请参阅下图：

![显示在圆圈中绘制的 EvenOdd 光线的关系图。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-rays.png)

**NonZero：** 此规则通过从一点向任意方向绘制一条射向无穷远的射线，并检查一段形状与射线相交的位置，从而确定该点是否位于路径的填充区域。 从零计数开始，从左到右每次添加与射线相交的一个段，然后从右到左每次减去与射线相交的一个路径段。 在对交叉点进行计数后，如果结果为零，那么该点则位于路径外。 否则，该点则在路径内。

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValueEllipseGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovalueellipsegeometry)]

使用前面的示例，的值将 <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.GeometryGroup.FillRule%2A> 提供以下图作为结果：

![由一系列同心圆环组成的圆，它们都用相同的颜色填充。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-nonzero.png)

如图所示，所有环都已填充。 这是因为所有段按同一方向运行，因此从任一点绘制的射线将与一个或多个段相交，并且交点总数不会等于零。 例如，在下图中，红色箭头表示段的绘制方向，白色箭头表示从最内部环中的点运行的任意射线。 从零值开始，对于该射线相交的每个段，会加值“1”，因为从左到右该段与该射线相交。

![显示 FillRule 属性值等于非零值的关系图。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-equal-nonzero.png)

为了更好地演示规则行为， <xref:System.Windows.Media.FillRule.Nonzero> 需要在不同方向上以不同方向运行的更复杂的形状。 下面的 XAML 代码创建了与前面的示例类似的形状，只不过它是使用创建的， <xref:System.Windows.Media.PathGeometry> 而 <xref:System.Windows.Media.EllipseGeometry> 后者创建四条同心圆圆弧，而不是完全闭合同心圆。

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValuePathGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovaluepathgeometry)]

下图显示在上一个示例中创建的形状。

![一个圆，由一条序列同心圆，其交替颜色包含第三个弧线（未填充）。](./media/how-to-control-the-fill-of-a-composite-shape/pathgeometry-concentric-arcs.png)

请注意，自中心数起的第三条弧未填充。 下图显示了这种情况的原因。 在图中，红色箭头表示绘制段的方向。 两个白色箭头表示以“未填充”区域中的某个点为起点绘制的任意两条射线。 如图所示，与给定射线路径中的段相交的该射线值的总和为零。 如上文所定义，总和为零意味着该点不是几何图形的一部分（也不是填充的一部分），而总和 *不* 为零（包括负值）意味着该点是几何图形的一部分。

![显示任意光线跨越段的关系图。](./media/how-to-control-the-fill-of-a-composite-shape/arbitrary-ray-cross-segment.png)

> [!NOTE]
> 出于的目的 <xref:System.Windows.Media.FillRule> ，所有形状都被视为已关闭。 如果段中存在间隙，请绘制用于闭合该段的假想线。 在以上示例中，环中存在多个较小间隙。 考虑到这一点，人们可能希望穿过间隙的射线产生不同的结果，然后射线在另一个方向上运行。 下面是其中一个间隙的放大插图和 "虚构段" (段，为应用 <xref:System.Windows.Media.FillRule> 关闭它的) 而绘制。

![显示始终关闭的 FillRule 段的关系图。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-closed-segments.png)

## <a name="example"></a>示例

## <a name="see-also"></a>另请参阅

- [创建复合形状](how-to-create-a-composite-shape.md)
- [Geometry 概述](geometry-overview.md)
