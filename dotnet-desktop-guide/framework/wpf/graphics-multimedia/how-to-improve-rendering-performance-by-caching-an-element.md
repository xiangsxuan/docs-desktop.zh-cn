---
title: 如何：通过缓存元素来改善呈现性能
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: 118e8b0cca52c44788c9d5b291d710f765e7af2a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972680"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a><span data-ttu-id="af820-102">如何：通过缓存元素来改善呈现性能</span><span class="sxs-lookup"><span data-stu-id="af820-102">How to: Improve Rendering Performance by Caching an Element</span></span>
<span data-ttu-id="af820-103">使用 <xref:System.Windows.Media.BitmapCache> 类提高复杂的呈现性能 <xref:System.Windows.UIElement> 。</span><span class="sxs-lookup"><span data-stu-id="af820-103">Use the <xref:System.Windows.Media.BitmapCache> class to improve rendering performance of a complex <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="af820-104">若要缓存元素，请创建类的新实例， <xref:System.Windows.Media.BitmapCache> 并将其分配给该元素的 <xref:System.Windows.UIElement.CacheMode%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="af820-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span> <span data-ttu-id="af820-105">你可以 <xref:System.Windows.Media.BitmapCache> 在中有效地重复使用 <xref:System.Windows.Media.BitmapCacheBrush> 。</span><span class="sxs-lookup"><span data-stu-id="af820-105">You can reuse a <xref:System.Windows.Media.BitmapCache> efficiently in a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af820-106">示例</span><span class="sxs-lookup"><span data-stu-id="af820-106">Example</span></span>  
 <span data-ttu-id="af820-107">下面的代码示例演示如何创建一个复杂的元素并将其缓存为位图，这可提高对该元素进行动画处理时的性能。</span><span class="sxs-lookup"><span data-stu-id="af820-107">The following code example shows how to create a complex element and cache it as a bitmap, which improves performance when the element is animated.</span></span> <span data-ttu-id="af820-108">元素是一个画布，其中包含具有多个顶点的形状几何。</span><span class="sxs-lookup"><span data-stu-id="af820-108">The element is a canvas that holds shape geometries with many vertices.</span></span> <span data-ttu-id="af820-109">将 <xref:System.Windows.Media.BitmapCache> 具有默认值的分配给 <xref:System.Windows.UIElement.CacheMode%2A> 画布的，而动画显示缓存位图的平滑缩放。</span><span class="sxs-lookup"><span data-stu-id="af820-109">A <xref:System.Windows.Media.BitmapCache> with default values is assigned to the <xref:System.Windows.UIElement.CacheMode%2A> of the canvas, and an animation shows the smooth scaling of the cached bitmap.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a><span data-ttu-id="af820-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af820-110">See also</span></span>

- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="af820-111">如何：使用缓存的元素作为画笔</span><span class="sxs-lookup"><span data-stu-id="af820-111">How to: Use a Cached Element as a Brush</span></span>](how-to-use-a-cached-element-as-a-brush.md)
