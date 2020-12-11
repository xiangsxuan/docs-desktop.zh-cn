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
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a>如何：通过缓存元素来改善呈现性能
使用 <xref:System.Windows.Media.BitmapCache> 类提高复杂的呈现性能 <xref:System.Windows.UIElement> 。 若要缓存元素，请创建类的新实例， <xref:System.Windows.Media.BitmapCache> 并将其分配给该元素的 <xref:System.Windows.UIElement.CacheMode%2A> 属性。 你可以 <xref:System.Windows.Media.BitmapCache> 在中有效地重复使用 <xref:System.Windows.Media.BitmapCacheBrush> 。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何创建一个复杂的元素并将其缓存为位图，这可提高对该元素进行动画处理时的性能。 元素是一个画布，其中包含具有多个顶点的形状几何。 将 <xref:System.Windows.Media.BitmapCache> 具有默认值的分配给 <xref:System.Windows.UIElement.CacheMode%2A> 画布的，而动画显示缓存位图的平滑缩放。  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [如何：使用缓存的元素作为画笔](how-to-use-a-cached-element-as-a-brush.md)
