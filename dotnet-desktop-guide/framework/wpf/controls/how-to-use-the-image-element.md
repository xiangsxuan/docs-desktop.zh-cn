---
title: 如何：使用 Image 元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
ms.openlocfilehash: e267aec4d8a1632f77d756bd94d077efcbb2e10c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972990"
---
# <a name="how-to-use-the-image-element"></a>如何：使用 Image 元素
此示例演示如何使用元素在应用程序中包括图像 <xref:System.Windows.Controls.Image> 。  
  
## <a name="example"></a>示例  
 下面的示例演示如何呈现宽为 200 像素的图像。 在此 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 示例中，同时使用特性语法和属性标记语法来定义图像。 有关特性语法和属性语法的详细信息，请参阅[依赖属性概述](../advanced/dependency-properties-overview.md)。 <xref:System.Windows.Media.Imaging.BitmapImage>用于定义图像的源数据，并为属性标记语法示例显式定义了。 此外，的将 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 设置为与 <xref:System.Windows.Media.Imaging.BitmapImage> 的相同宽度 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Controls.Image> 。 这样做是为了确保呈现图像所使用的内存量最小。  
  
> [!NOTE]
> 通常，如果要指定呈现的图像的大小，请仅指定 <xref:System.Windows.FrameworkElement.Width%2A> 或， <xref:System.Windows.FrameworkElement.Height%2A> 而不是两者。 如果仅指定一个，则会保持图像的纵横比。 否则，图像可能会出现意外的拉伸或扭曲。 若要控制图像的拉伸行为，请使用 <xref:System.Windows.Controls.Image.Stretch%2A> 和 <xref:System.Windows.Controls.Image.StretchDirection%2A> 属性。  
  
> [!NOTE]
> 当使用或指定映像的大小时 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> ，还应将 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 或设置 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> 为相同的大小。  
  
 <xref:System.Windows.Controls.Image.Stretch%2A>属性确定如何拉伸图像源以填充图像元素。 有关详细信息，请参见 <xref:System.Windows.Media.Stretch> 枚举。  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>示例  
 以下示例演示如何使用代码呈现宽度为 200 像素的图像。  
  
> [!NOTE]
> 设置 <xref:System.Windows.Media.Imaging.BitmapImage> 属性必须在 <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> 和块中完成 <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> 。  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>另请参阅

- [图像处理概述](../graphics-multimedia/imaging-overview.md)
