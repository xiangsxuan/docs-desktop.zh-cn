---
title: 如何：将图像作为缩略图加载
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
ms.openlocfilehash: a5b2f4b7de52203ded711e9e829886a5c25c6067
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972679"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a>如何：将图像作为缩略图加载
下面的示例演示如何以 <xref:System.Windows.Controls.Image> 缩略图的形式加载以节省应用程序内存。  
  
## <a name="example"></a>示例  
 下面的示例 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> 在中设置的属性 <xref:System.Windows.Media.Imaging.BitmapImage> [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 以减少加载图像所需的内存。  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>示例  
 下面的示例 <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> <xref:System.Windows.Media.Imaging.BitmapImage> 在代码中设置的属性以减少加载图像所需的内存。  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>另请参阅

- [图像处理概述](imaging-overview.md)
