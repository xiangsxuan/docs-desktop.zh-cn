---
title: 如何：在 Viewport3D 中进行命中测试
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D visuals [WPF], hit-testing for
- hit tests [WPF], for 3D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: 34bc86349332293e40aca5743cbabb2a48634da6
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972683"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a><span data-ttu-id="30109-102">如何：在 Viewport3D 中进行命中测试</span><span class="sxs-lookup"><span data-stu-id="30109-102">How to: Hit Test in a Viewport3D</span></span>

<span data-ttu-id="30109-103">此示例演示如何在中对三维视觉对象进行命中测试 <xref:System.Windows.Controls.Viewport3D> 。</span><span class="sxs-lookup"><span data-stu-id="30109-103">This example shows how to hit test for 3D Visuals in a <xref:System.Windows.Controls.Viewport3D>.</span></span>

<span data-ttu-id="30109-104">由于 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 返回2d 和3d 信息，因此可能会循环访问测试结果以只读取3d 结果。</span><span class="sxs-lookup"><span data-stu-id="30109-104">Because <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> returns 2D and 3D information, it is possible to iterate through the test results to read only 3D results.</span></span>

[!code-csharp[HitTest3D#HitTest3D3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
[!code-vb[HitTest3D#HitTest3D3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]

<span data-ttu-id="30109-105"><xref:System.Windows.Media.HitTestResultBehavior>以下代码中的用于确定如何处理命中测试结果。</span><span class="sxs-lookup"><span data-stu-id="30109-105">The <xref:System.Windows.Media.HitTestResultBehavior> in the following code determines how the hit test results are processed.</span></span> <span data-ttu-id="30109-106">`UpdateResultInfo` 和 `UpdateMaterial` 是本地定义的方法。</span><span class="sxs-lookup"><span data-stu-id="30109-106">`UpdateResultInfo` and `UpdateMaterial` are locally defined methods.</span></span>

[!code-csharp[HitTest3D#HitTest3D3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
[!code-vb[HitTest3D#HitTest3D3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]
