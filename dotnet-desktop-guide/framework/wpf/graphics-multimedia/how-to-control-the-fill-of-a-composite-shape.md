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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973530"
---
# <a name="how-to-control-the-fill-of-a-composite-shape"></a><span data-ttu-id="dd0b0-102">如何：控制复合形状的填充</span><span class="sxs-lookup"><span data-stu-id="dd0b0-102">How to: Control the Fill of a Composite Shape</span></span>

<span data-ttu-id="dd0b0-103"><xref:System.Windows.Media.GeometryGroup.FillRule%2A>或的属性 <xref:System.Windows.Media.GeometryGroup> <xref:System.Windows.Media.PathGeometry> 指定一个 "规则"，组合形状使用该 "规则" 来确定给定点是否为几何图形的一部分。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-103">The <xref:System.Windows.Media.GeometryGroup.FillRule%2A> property of a <xref:System.Windows.Media.GeometryGroup> or a <xref:System.Windows.Media.PathGeometry>, specifies a "rule" which the composite shape uses to determine whether a given point is part of the geometry.</span></span> <span data-ttu-id="dd0b0-104">有两个可能的值 <xref:System.Windows.Media.FillRule> ： <xref:System.Windows.Media.FillRule.EvenOdd> 和 <xref:System.Windows.Media.FillRule.Nonzero> 。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-104">There are two possible values for <xref:System.Windows.Media.FillRule>: <xref:System.Windows.Media.FillRule.EvenOdd> and <xref:System.Windows.Media.FillRule.Nonzero>.</span></span> <span data-ttu-id="dd0b0-105">以下各节将介绍如何使用这两个规则。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-105">The following sections will describe how to use these two rules.</span></span>

<span data-ttu-id="dd0b0-106">**EvenOdd：** 此规则通过从一点向任意方向绘制一条射向无穷远的射线，然后计算给定形状中与该射线相交的路径段的数量，从而确定该点是否位于填充区域中。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-106">**EvenOdd:** This rule determines whether a point is in the fill region by drawing a ray from that point to infinity in any direction and counting the number of path segments within the given shape that the ray crosses.</span></span> <span data-ttu-id="dd0b0-107">如果此数目为奇数，那么该点则在内部；如果为偶数，则该点在外部。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-107">If this number is odd, the point is inside; if even, the point is outside.</span></span>

<span data-ttu-id="dd0b0-108">例如，下面的 XAML 创建复合形状，其中包含一系列同心圆环 (目标) ，其 <xref:System.Windows.Media.GeometryGroup.FillRule%2A> 设置为 <xref:System.Windows.Media.FillRule.EvenOdd> 。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-108">For example, the XAML below creates a composite shape made up of a series of concentric rings (target) with a <xref:System.Windows.Media.GeometryGroup.FillRule%2A> set to <xref:System.Windows.Media.FillRule.EvenOdd>.</span></span>

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleEvenOddValue](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillruleevenoddvalue)]

<span data-ttu-id="dd0b0-109">下图显示在上一个示例中创建的形状。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-109">The following illustration shows the shape created in the previous example.</span></span>

![由带有交替颜色的系列同心圆环组成的圆。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-property.png)

<span data-ttu-id="dd0b0-111">在上图中，请注意，不会填写中心和第三环。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-111">In the previous illustration, notice that the center and third ring are not filled.</span></span> <span data-ttu-id="dd0b0-112">这是因为射线是从穿过偶数段的这两个环中的点绘制的。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-112">This is because a ray drawn from any point within either of those two rings passes through an even number of segments.</span></span> <span data-ttu-id="dd0b0-113">请参阅下图：</span><span class="sxs-lookup"><span data-stu-id="dd0b0-113">See the following illustration:</span></span>

![显示在圆圈中绘制的 EvenOdd 光线的关系图。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-rays.png)

<span data-ttu-id="dd0b0-115">**NonZero：** 此规则通过从一点向任意方向绘制一条射向无穷远的射线，并检查一段形状与射线相交的位置，从而确定该点是否位于路径的填充区域。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-115">**NonZero:** This rule determines whether a point is in the fill region of the path by drawing a ray from that point to infinity in any direction and then examining the places where a segment of the shape crosses the ray.</span></span> <span data-ttu-id="dd0b0-116">从零计数开始，从左到右每次添加与射线相交的一个段，然后从右到左每次减去与射线相交的一个路径段。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-116">Starting with a count of zero, add one each time a Segment crosses the ray from left to right and subtract one each time a path segment crosses the ray from right to left.</span></span> <span data-ttu-id="dd0b0-117">在对交叉点进行计数后，如果结果为零，那么该点则位于路径外。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-117">After counting the crossings, if the result is zero then the point is outside the path.</span></span> <span data-ttu-id="dd0b0-118">否则，该点则在路径内。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-118">Otherwise, it is inside.</span></span>

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValueEllipseGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovalueellipsegeometry)]

<span data-ttu-id="dd0b0-119">使用前面的示例，的值将 <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.GeometryGroup.FillRule%2A> 提供以下图作为结果：</span><span class="sxs-lookup"><span data-stu-id="dd0b0-119">Using the previous example, a value of <xref:System.Windows.Media.FillRule.Nonzero> for <xref:System.Windows.Media.GeometryGroup.FillRule%2A> gives the following illustration as a result:</span></span>

![由一系列同心圆环组成的圆，它们都用相同的颜色填充。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-nonzero.png)

<span data-ttu-id="dd0b0-121">如图所示，所有环都已填充。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-121">As you can see, all the rings are filled.</span></span> <span data-ttu-id="dd0b0-122">这是因为所有段按同一方向运行，因此从任一点绘制的射线将与一个或多个段相交，并且交点总数不会等于零。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-122">This is because all the segments are running in the same direction and so a ray drawn from any point will cross one or more segments and the sum of the crossings will not equal zero.</span></span> <span data-ttu-id="dd0b0-123">例如，在下图中，红色箭头表示段的绘制方向，白色箭头表示从最内部环中的点运行的任意射线。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-123">For example, in the following illustration, the red arrows represent the direction the segments are drawn and the white arrow represents an arbitrary ray running from a point in the innermost ring.</span></span> <span data-ttu-id="dd0b0-124">从零值开始，对于该射线相交的每个段，会加值“1”，因为从左到右该段与该射线相交。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-124">Starting with a value of zero, for each segment that the ray crosses, a value of one is added because the segment crosses the ray from left to right.</span></span>

![显示 FillRule 属性值等于非零值的关系图。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-equal-nonzero.png)

<span data-ttu-id="dd0b0-126">为了更好地演示规则行为， <xref:System.Windows.Media.FillRule.Nonzero> 需要在不同方向上以不同方向运行的更复杂的形状。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-126">To better demonstrate the behavior of <xref:System.Windows.Media.FillRule.Nonzero> rule a more complex shape with segments running in different directions is required.</span></span> <span data-ttu-id="dd0b0-127">下面的 XAML 代码创建了与前面的示例类似的形状，只不过它是使用创建的， <xref:System.Windows.Media.PathGeometry> 而 <xref:System.Windows.Media.EllipseGeometry> 后者创建四条同心圆圆弧，而不是完全闭合同心圆。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-127">The XAML code below creates a similar shape as the previous example except that it is created with a <xref:System.Windows.Media.PathGeometry> rather then a <xref:System.Windows.Media.EllipseGeometry> which creates four concentric arcs rather then fully closed concentric circles.</span></span>

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValuePathGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovaluepathgeometry)]

<span data-ttu-id="dd0b0-128">下图显示在上一个示例中创建的形状。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-128">The following illustration shows the shape created in the previous example.</span></span>

![一个圆，由一条序列同心圆，其交替颜色包含第三个弧线（未填充）。](./media/how-to-control-the-fill-of-a-composite-shape/pathgeometry-concentric-arcs.png)

<span data-ttu-id="dd0b0-130">请注意，自中心数起的第三条弧未填充。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-130">Notice that the third arc from the center is not filled.</span></span> <span data-ttu-id="dd0b0-131">下图显示了这种情况的原因。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-131">The following illustration shows why this is.</span></span> <span data-ttu-id="dd0b0-132">在图中，红色箭头表示绘制段的方向。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-132">In the illustration, the red arrows represent the direction the segments are drawn.</span></span> <span data-ttu-id="dd0b0-133">两个白色箭头表示以“未填充”区域中的某个点为起点绘制的任意两条射线。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-133">The two white arrows represent two arbitrary rays that move out from a point in the "non-filled" region.</span></span> <span data-ttu-id="dd0b0-134">如图所示，与给定射线路径中的段相交的该射线值的总和为零。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-134">As can be seen from the illustration, the sum of the values from a given ray crossing the segments in its path is zero.</span></span> <span data-ttu-id="dd0b0-135">如上文所定义，总和为零意味着该点不是几何图形的一部分（也不是填充的一部分），而总和 *不* 为零（包括负值）意味着该点是几何图形的一部分。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-135">As defined above, a sum of zero means that the point is not part of the geometry (not part of the fill) while a sum that is *not* zero, including a negative value, is part of the geometry.</span></span>

![显示任意光线跨越段的关系图。](./media/how-to-control-the-fill-of-a-composite-shape/arbitrary-ray-cross-segment.png)

> [!NOTE]
> <span data-ttu-id="dd0b0-137">出于的目的 <xref:System.Windows.Media.FillRule> ，所有形状都被视为已关闭。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-137">For the purposes of <xref:System.Windows.Media.FillRule>, all shapes are considered closed.</span></span> <span data-ttu-id="dd0b0-138">如果段中存在间隙，请绘制用于闭合该段的假想线。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-138">If there is a gap in a segment, draw an imaginary line to close it.</span></span> <span data-ttu-id="dd0b0-139">在以上示例中，环中存在多个较小间隙。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-139">In the example above, there are small gaps in the rings.</span></span> <span data-ttu-id="dd0b0-140">考虑到这一点，人们可能希望穿过间隙的射线产生不同的结果，然后射线在另一个方向上运行。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-140">Given this, one might expect a ray that runs through the gap to give a different result then a ray running in another direction.</span></span> <span data-ttu-id="dd0b0-141">下面是其中一个间隙的放大插图和 "虚构段" (段，为应用 <xref:System.Windows.Media.FillRule> 关闭它的) 而绘制。</span><span class="sxs-lookup"><span data-stu-id="dd0b0-141">Below is an enlarged illustration of one of these gaps and the "imaginary segment" (segment that is drawn for purposes of applying the <xref:System.Windows.Media.FillRule>) that closes it.</span></span>

![显示始终关闭的 FillRule 段的关系图。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-closed-segments.png)

## <a name="example"></a><span data-ttu-id="dd0b0-143">示例</span><span class="sxs-lookup"><span data-stu-id="dd0b0-143">Example</span></span>

## <a name="see-also"></a><span data-ttu-id="dd0b0-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd0b0-144">See also</span></span>

- [<span data-ttu-id="dd0b0-145">创建复合形状</span><span class="sxs-lookup"><span data-stu-id="dd0b0-145">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="dd0b0-146">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="dd0b0-146">Geometry Overview</span></span>](geometry-overview.md)
