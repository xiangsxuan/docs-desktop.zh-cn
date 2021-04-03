---
title: 如何：创建和使用画布
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
ms.openlocfilehash: c9ee49327b6490df094e84b4227ea0fb2e757c4d
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972901"
---
# <a name="how-to-create-and-use-a-canvas"></a><span data-ttu-id="0b5e5-102">如何：创建和使用画布</span><span class="sxs-lookup"><span data-stu-id="0b5e5-102">How to: Create and Use a Canvas</span></span>
<span data-ttu-id="0b5e5-103">此示例演示如何创建和使用的实例 <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="0b5e5-103">This example shows how to create and use an instance of <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b5e5-104">示例</span><span class="sxs-lookup"><span data-stu-id="0b5e5-104">Example</span></span>  
 <span data-ttu-id="0b5e5-105">下面的示例通过使用的和方法显式定位两个 <xref:System.Windows.Controls.TextBlock> 元素 <xref:System.Windows.Controls.Canvas.SetTop%2A> <xref:System.Windows.Controls.Canvas.SetLeft%2A> <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="0b5e5-105">The following example explicitly positions two <xref:System.Windows.Controls.TextBlock> elements by using the <xref:System.Windows.Controls.Canvas.SetTop%2A> and <xref:System.Windows.Controls.Canvas.SetLeft%2A> methods of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="0b5e5-106">该示例还将 <xref:System.Windows.Controls.Control.Background%2A> 的颜色分配 `LightSteelBlue` 给 <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="0b5e5-106">The example also assigns a <xref:System.Windows.Controls.Control.Background%2A> color of `LightSteelBlue` to the <xref:System.Windows.Controls.Canvas>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b5e5-107">当你使用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 来放置 <xref:System.Windows.Controls.TextBlock> 元素时，请使用 <xref:System.Windows.Controls.Canvas.Top%2A> 和 <xref:System.Windows.Controls.Canvas.Left%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="0b5e5-107">When you use [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] to position <xref:System.Windows.Controls.TextBlock> elements, use the <xref:System.Windows.Controls.Canvas.Top%2A> and <xref:System.Windows.Controls.Canvas.Left%2A> properties.</span></span>  
  
 [!code-csharp[CanvasCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0b5e5-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b5e5-108">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [<span data-ttu-id="0b5e5-109">面板概述</span><span class="sxs-lookup"><span data-stu-id="0b5e5-109">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="0b5e5-110">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="0b5e5-110">How-to Topics</span></span>](canvas-how-to-topics.md)
