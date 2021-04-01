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
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a>如何：将几何图形用作参数的命中测试
此示例演示如何使用 <xref:System.Windows.Media.Geometry> 作为命中测试参数对视觉对象执行命中测试。  
  
## <a name="example"></a>示例  
 下面的示例演示如何为方法设置使用的命中测试 <xref:System.Windows.Media.GeometryHitTestParameters> <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 。 <xref:System.Windows.Point>传递给方法的值 `OnMouseDown` 用于创建对象，以便 <xref:System.Windows.Media.Geometry> 扩展命中测试的范围。  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 的 <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> 属性 <xref:System.Windows.Media.GeometryHitTestResult> 提供有关使用 <xref:System.Windows.Media.Geometry> 作为命中测试参数的命中测试结果的信息。 下图演示了命中测试几何图形（蓝色圆圈）与目标视觉对象（红色正方形）的呈现内容之间的关系。  
  
 ![显示命中测试中使用的 System.windows.media.geometryhittestresult.intersectiondetail 的关系图。](./media/how-to-hit-test-using-geometry-as-a-parameter/intersectiondetail-hit-test.png)  
  
 下面的示例演示如何在用作命中测试参数时实现命中测试回调 <xref:System.Windows.Media.Geometry> 。 `result`参数转换为，以便 <xref:System.Windows.Media.GeometryHitTestResult> 检索属性的值 <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> 。 属性值允许你确定 <xref:System.Windows.Media.Geometry> 命中测试参数是完全或部分包含在命中测试目标的呈现内容中。 在本示例中，示例代码仅将命中测试结果添加到完全包含在目标边界中的视觉对象的列表中。  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
> <xref:System.Windows.Media.HitTestResult>当交集详细信息为时，不应调用回调 <xref:System.Windows.Media.IntersectionDetail.Empty> 。  
  
## <a name="see-also"></a>请参阅

- [可视化层中的命中测试](hit-testing-in-the-visual-layer.md)
- [对视觉对象中的几何图形进行命中测试](how-to-hit-test-geometry-in-a-visual.md)
