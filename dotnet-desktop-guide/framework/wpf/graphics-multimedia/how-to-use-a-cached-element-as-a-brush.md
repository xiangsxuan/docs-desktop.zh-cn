---
title: 如何：使用缓存的元素作为画笔
ms.date: 03/30/2017
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
ms.openlocfilehash: 78df242c7f00b69e36ea4ab6751f51509d9e2220
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973772"
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a><span data-ttu-id="e6c69-102">如何：使用缓存的元素作为画笔</span><span class="sxs-lookup"><span data-stu-id="e6c69-102">How to: Use a Cached Element as a Brush</span></span>
<span data-ttu-id="e6c69-103">使用 <xref:System.Windows.Media.BitmapCacheBrush> 类来有效地重复使用缓存的元素。</span><span class="sxs-lookup"><span data-stu-id="e6c69-103">Use the <xref:System.Windows.Media.BitmapCacheBrush> class to reuse a cached element efficiently.</span></span> <span data-ttu-id="e6c69-104">若要缓存元素，请创建类的新实例， <xref:System.Windows.Media.BitmapCache> 并将其分配给该元素的 <xref:System.Windows.UIElement.CacheMode%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="e6c69-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6c69-105">示例</span><span class="sxs-lookup"><span data-stu-id="e6c69-105">Example</span></span>  
 <span data-ttu-id="e6c69-106">下面的代码示例演示如何重用缓存的元素。</span><span class="sxs-lookup"><span data-stu-id="e6c69-106">The following code example shows how to reuse a cached element.</span></span> <span data-ttu-id="e6c69-107">缓存元素是 <xref:System.Windows.Controls.Image> 显示大图像的控件。</span><span class="sxs-lookup"><span data-stu-id="e6c69-107">The cached element is an <xref:System.Windows.Controls.Image> control that displays a large image.</span></span> <span data-ttu-id="e6c69-108">通过 <xref:System.Windows.Controls.Image> 使用类将控件缓存为位图 <xref:System.Windows.Media.BitmapCache> ，并通过将缓存分配给来重复使用缓存 <xref:System.Windows.Media.BitmapCacheBrush> 。</span><span class="sxs-lookup"><span data-stu-id="e6c69-108">The <xref:System.Windows.Controls.Image> control is cached as a bitmap by using the <xref:System.Windows.Media.BitmapCache> class, and the cache is reused by assigning it to a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span> <span data-ttu-id="e6c69-109">画笔将分配给第二十五个按钮的背景，以显示高效重复使用。</span><span class="sxs-lookup"><span data-stu-id="e6c69-109">The brush is assigned to the background of twenty-five buttons to show efficient reuse.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="e6c69-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6c69-110">See also</span></span>

- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="e6c69-111">如何：通过缓存元素来改善呈现性能</span><span class="sxs-lookup"><span data-stu-id="e6c69-111">How to: Improve Rendering Performance by Caching an Element</span></span>](how-to-improve-rendering-performance-by-caching-an-element.md)
