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
# <a name="how-to-use-a-cached-element-as-a-brush"></a>如何：使用缓存的元素作为画笔
使用 <xref:System.Windows.Media.BitmapCacheBrush> 类来有效地重复使用缓存的元素。 若要缓存元素，请创建类的新实例， <xref:System.Windows.Media.BitmapCache> 并将其分配给该元素的 <xref:System.Windows.UIElement.CacheMode%2A> 属性。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何重用缓存的元素。 缓存元素是 <xref:System.Windows.Controls.Image> 显示大图像的控件。 通过 <xref:System.Windows.Controls.Image> 使用类将控件缓存为位图 <xref:System.Windows.Media.BitmapCache> ，并通过将缓存分配给来重复使用缓存 <xref:System.Windows.Media.BitmapCacheBrush> 。 画笔将分配给第二十五个按钮的背景，以显示高效重复使用。  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [如何：通过缓存元素来改善呈现性能](how-to-improve-rendering-performance-by-caching-an-element.md)
