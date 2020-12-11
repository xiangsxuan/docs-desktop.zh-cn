---
title: 如何：枚举 Visual 的绘图内容
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 25aa0c3706005c1e16cedd7e06914db764545ebb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973758"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="f5ca8-102">如何：枚举 Visual 的绘图内容</span><span class="sxs-lookup"><span data-stu-id="f5ca8-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="f5ca8-103"><xref:System.Windows.Media.Drawing>对象提供用于枚举的内容的对象模型 <xref:System.Windows.Media.Visual> 。</span><span class="sxs-lookup"><span data-stu-id="f5ca8-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5ca8-104">示例</span><span class="sxs-lookup"><span data-stu-id="f5ca8-104">Example</span></span>  
 <span data-ttu-id="f5ca8-105">下面的示例使用 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 方法来检索 <xref:System.Windows.Media.DrawingGroup> 的值 <xref:System.Windows.Media.Visual> 并对其进行枚举。</span><span class="sxs-lookup"><span data-stu-id="f5ca8-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5ca8-106">枚举视觉对象的内容时，您是在检索 <xref:System.Windows.Media.Drawing> 对象，而不是以矢量图形指令列表的形式呈现数据。</span><span class="sxs-lookup"><span data-stu-id="f5ca8-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="f5ca8-107">有关详细信息，请参阅 [WPF 图形呈现概述](wpf-graphics-rendering-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f5ca8-107">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="f5ca8-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5ca8-108">See also</span></span>

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="f5ca8-109">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="f5ca8-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="f5ca8-110">WPF 图形呈现疑难解答</span><span class="sxs-lookup"><span data-stu-id="f5ca8-110">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
