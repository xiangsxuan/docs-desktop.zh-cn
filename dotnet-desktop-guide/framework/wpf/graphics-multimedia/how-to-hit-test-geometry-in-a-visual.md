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
# <a name="how-to-hit-test-geometry-in-a-visual"></a><span data-ttu-id="645ed-102">如何：对 Visual 中的几何图形进行命中测试</span><span class="sxs-lookup"><span data-stu-id="645ed-102">How to: Hit Test Geometry in a Visual</span></span>
<span data-ttu-id="645ed-103">此示例演示如何对由一个或多个对象组成的视觉对象执行命中测试 <xref:System.Windows.Media.Geometry> 。</span><span class="sxs-lookup"><span data-stu-id="645ed-103">This example shows how to perform a hit test on a visual object that is composed of one or more <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="645ed-104">示例</span><span class="sxs-lookup"><span data-stu-id="645ed-104">Example</span></span>  
 <span data-ttu-id="645ed-105">下面的示例演示如何 <xref:System.Windows.Media.DrawingGroup> 从使用方法的视觉对象中检索 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 。</span><span class="sxs-lookup"><span data-stu-id="645ed-105">The following example shows how to retrieve the <xref:System.Windows.Media.DrawingGroup> from a visual object that uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method.</span></span> <span data-ttu-id="645ed-106">然后，将对中的每个绘图的呈现内容执行命中测试 <xref:System.Windows.Media.DrawingGroup> ，以确定命中了哪个几何图形。</span><span class="sxs-lookup"><span data-stu-id="645ed-106">A hit test is then performed on the rendered content of each drawing in the <xref:System.Windows.Media.DrawingGroup> to determine which geometry was hit.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="645ed-107">在大多数情况下，可以使用 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 方法来确定某个点是否与视觉对象的任何呈现内容相交。</span><span class="sxs-lookup"><span data-stu-id="645ed-107">In most cases, you would use the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method to determine whether a point intersects any of the rendered content of a visual.</span></span>  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <span data-ttu-id="645ed-108"><xref:System.Windows.Media.Geometry.FillContains%2A>方法是一个重载的方法，它允许使用指定的或进行命中测试 <xref:System.Windows.Point> <xref:System.Windows.Media.Geometry> 。</span><span class="sxs-lookup"><span data-stu-id="645ed-108">The <xref:System.Windows.Media.Geometry.FillContains%2A> method is an overloaded method that allows you to hit test by using a specified <xref:System.Windows.Point> or <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="645ed-109">绘制几何图形时，笔画可以延伸到填充边界之外。</span><span class="sxs-lookup"><span data-stu-id="645ed-109">If a geometry is stroked, the stroke can extend outside the fill bounds.</span></span> <span data-ttu-id="645ed-110">在这种情况下，除了之外，您可能还需要调用 <xref:System.Windows.Media.Geometry.StrokeContains%2A> <xref:System.Windows.Media.Geometry.FillContains%2A> 。</span><span class="sxs-lookup"><span data-stu-id="645ed-110">In which case, you may want to call <xref:System.Windows.Media.Geometry.StrokeContains%2A> in addition to <xref:System.Windows.Media.Geometry.FillContains%2A>.</span></span>  
  
 <span data-ttu-id="645ed-111">还可以提供 <xref:System.Windows.Media.ToleranceType> 用于贝塞尔平展用途的。</span><span class="sxs-lookup"><span data-stu-id="645ed-111">You can also provide a <xref:System.Windows.Media.ToleranceType> that is used for the purposes of Bezier flattening.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="645ed-112">此示例并未考虑可能应用到几何图形中的任何变形或剪裁。</span><span class="sxs-lookup"><span data-stu-id="645ed-112">This sample does not take into account any transforms or clipping that may be applied to the geometry.</span></span> <span data-ttu-id="645ed-113">此外，此示例不会使用已设置样式的控件，因为这种控件没有与它直接关联的绘图。</span><span class="sxs-lookup"><span data-stu-id="645ed-113">In addition, this sample will not work with a styled control, since it does not have any drawings directly associated with it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="645ed-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="645ed-114">See also</span></span>

- [<span data-ttu-id="645ed-115">可视化层中的命中测试</span><span class="sxs-lookup"><span data-stu-id="645ed-115">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="645ed-116">对用作参数的几何图形进行命中测试</span><span class="sxs-lookup"><span data-stu-id="645ed-116">Hit Test Using Geometry as a Parameter</span></span>](how-to-hit-test-using-geometry-as-a-parameter.md)
