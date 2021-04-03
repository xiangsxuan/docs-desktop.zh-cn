---
title: 如何：将几何图形用作参数的命中测试
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 8bed7784b00f49178c9a87def74b62f7ce620ec7
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972682"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a><span data-ttu-id="eb93f-102">如何：将几何图形用作参数的命中测试</span><span class="sxs-lookup"><span data-stu-id="eb93f-102">How to: Hit Test Using Geometry as a Parameter</span></span>
<span data-ttu-id="eb93f-103">此示例演示如何使用 <xref:System.Windows.Media.Geometry> 作为命中测试参数对视觉对象执行命中测试。</span><span class="sxs-lookup"><span data-stu-id="eb93f-103">This example shows how to perform a hit test on a visual object using a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb93f-104">示例</span><span class="sxs-lookup"><span data-stu-id="eb93f-104">Example</span></span>  
 <span data-ttu-id="eb93f-105">下面的示例演示如何为方法设置使用的命中测试 <xref:System.Windows.Media.GeometryHitTestParameters> <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 。</span><span class="sxs-lookup"><span data-stu-id="eb93f-105">The following example shows how to set up a hit test using <xref:System.Windows.Media.GeometryHitTestParameters> for the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="eb93f-106"><xref:System.Windows.Point>传递给方法的值 `OnMouseDown` 用于创建对象，以便 <xref:System.Windows.Media.Geometry> 扩展命中测试的范围。</span><span class="sxs-lookup"><span data-stu-id="eb93f-106">The <xref:System.Windows.Point> value that is passed to the `OnMouseDown` method is used to create a <xref:System.Windows.Media.Geometry> object in order to expand the range of the hit test.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <span data-ttu-id="eb93f-107">的 <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> 属性 <xref:System.Windows.Media.GeometryHitTestResult> 提供有关使用 <xref:System.Windows.Media.Geometry> 作为命中测试参数的命中测试结果的信息。</span><span class="sxs-lookup"><span data-stu-id="eb93f-107">The <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property of <xref:System.Windows.Media.GeometryHitTestResult> provides information about the results of a hit test that uses a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span> <span data-ttu-id="eb93f-108">下图演示了命中测试几何图形（蓝色圆圈）与目标视觉对象（红色正方形）的呈现内容之间的关系。</span><span class="sxs-lookup"><span data-stu-id="eb93f-108">The following illustration shows the relationship between the hit test geometry (the blue circle) and the rendered content of the target visual object (the red square).</span></span>  
  
 ![显示命中测试中使用的 System.windows.media.geometryhittestresult.intersectiondetail 的关系图。](./media/how-to-hit-test-using-geometry-as-a-parameter/intersectiondetail-hit-test.png)  
  
 <span data-ttu-id="eb93f-110">下面的示例演示如何在用作命中测试参数时实现命中测试回调 <xref:System.Windows.Media.Geometry> 。</span><span class="sxs-lookup"><span data-stu-id="eb93f-110">The following example shows how to implement a hit test callback when a <xref:System.Windows.Media.Geometry> is used as a hit test parameter.</span></span> <span data-ttu-id="eb93f-111">`result`参数转换为，以便 <xref:System.Windows.Media.GeometryHitTestResult> 检索属性的值 <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> 。</span><span class="sxs-lookup"><span data-stu-id="eb93f-111">The `result` parameter is cast to a <xref:System.Windows.Media.GeometryHitTestResult> in order to retrieve the value of the <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property.</span></span> <span data-ttu-id="eb93f-112">属性值允许你确定 <xref:System.Windows.Media.Geometry> 命中测试参数是完全或部分包含在命中测试目标的呈现内容中。</span><span class="sxs-lookup"><span data-stu-id="eb93f-112">The property value allows you to determine if the <xref:System.Windows.Media.Geometry> hit test parameter is fully or partially contained within the rendered content of the hit test target.</span></span> <span data-ttu-id="eb93f-113">在本示例中，示例代码仅将命中测试结果添加到完全包含在目标边界中的视觉对象的列表中。</span><span class="sxs-lookup"><span data-stu-id="eb93f-113">In this case, the sample code is only adding hit test results to the list for visuals that are fully contained within the target boundary.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
> <span data-ttu-id="eb93f-114"><xref:System.Windows.Media.HitTestResult>当交集详细信息为时，不应调用回调 <xref:System.Windows.Media.IntersectionDetail.Empty> 。</span><span class="sxs-lookup"><span data-stu-id="eb93f-114">The <xref:System.Windows.Media.HitTestResult> callback should not be called when the intersection detail is <xref:System.Windows.Media.IntersectionDetail.Empty>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb93f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb93f-115">See also</span></span>

- [<span data-ttu-id="eb93f-116">可视化层中的命中测试</span><span class="sxs-lookup"><span data-stu-id="eb93f-116">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="eb93f-117">对视觉对象中的几何图形进行命中测试</span><span class="sxs-lookup"><span data-stu-id="eb93f-117">Hit Test Geometry in a Visual</span></span>](how-to-hit-test-geometry-in-a-visual.md)
