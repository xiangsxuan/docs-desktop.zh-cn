---
title: 如何：对 Visual 中的几何图形进行命中测试
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: 52b9b99b0af38d797e4a3c98dc0979211c930c1f
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972684"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>如何：对 Visual 中的几何图形进行命中测试
此示例演示如何对由一个或多个对象组成的视觉对象执行命中测试 <xref:System.Windows.Media.Geometry> 。  
  
## <a name="example"></a>示例  
 下面的示例演示如何 <xref:System.Windows.Media.DrawingGroup> 从使用方法的视觉对象中检索 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 。 然后，将对中的每个绘图的呈现内容执行命中测试 <xref:System.Windows.Media.DrawingGroup> ，以确定命中了哪个几何图形。  
  
> [!NOTE]
> 在大多数情况下，可以使用 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 方法来确定某个点是否与视觉对象的任何呈现内容相交。  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <xref:System.Windows.Media.Geometry.FillContains%2A>方法是一个重载的方法，它允许使用指定的或进行命中测试 <xref:System.Windows.Point> <xref:System.Windows.Media.Geometry> 。 绘制几何图形时，笔画可以延伸到填充边界之外。 在这种情况下，除了之外，您可能还需要调用 <xref:System.Windows.Media.Geometry.StrokeContains%2A> <xref:System.Windows.Media.Geometry.FillContains%2A> 。  
  
 还可以提供 <xref:System.Windows.Media.ToleranceType> 用于贝塞尔平展用途的。  
  
> [!NOTE]
> 此示例并未考虑可能应用到几何图形中的任何变形或剪裁。 此外，此示例不会使用已设置样式的控件，因为这种控件没有与它直接关联的绘图。  
  
## <a name="see-also"></a>另请参阅

- [可视化层中的命中测试](hit-testing-in-the-visual-layer.md)
- [对用作参数的几何图形进行命中测试](how-to-hit-test-using-geometry-as-a-parameter.md)
