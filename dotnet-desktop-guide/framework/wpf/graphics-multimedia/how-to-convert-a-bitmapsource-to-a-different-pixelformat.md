---
title: 如何：将 BitmapSource 转换为另一种 PixelFormat
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BitmapSource objects [WPF], converting to indexed pixel format
- converting images [WPF]
- converting [WPF], BitmapSource objects to indexed pixel formats
- converting [WPF], BitmapSource objects to palettized pixel format
- BitmapSource objects [WPF], converting to palettized pixel format
ms.assetid: cd9df1e4-d5dc-4f57-b67b-4ec67e086b33
ms.openlocfilehash: ea042599369da8435198e4206f89f3fa356a80c2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973528"
---
# <a name="how-to-convert-a-bitmapsource-to-a-different-pixelformat"></a>如何：将 BitmapSource 转换为另一种 PixelFormat
此示例演示如何 <xref:System.Windows.Media.Imaging.BitmapSource> 使用将 () 中的对象转换 <xref:System.Windows.Media.Imaging.BitmapImage> 为其他对象 <xref:System.Windows.Media.PixelFormat> <xref:System.Windows.Media.Imaging.FormatConvertedBitmap> 。  
  
## <a name="example"></a>示例  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#PixelFormatConversion](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/PixelFormatsExample.cs#pixelformatconversion)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#PixelFormatConversion](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/PixelFormatsExample.vb#pixelformatconversion)]  
  
## <a name="see-also"></a>另请参阅

- [图像处理概述](imaging-overview.md)
