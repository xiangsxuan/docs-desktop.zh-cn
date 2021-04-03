---
title: 如何：将 Visual 编码为图像文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: 193b6a14e404d32bb49d6e0ef3cbd513166bcce2
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974098"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a>如何：将 Visual 编码为图像文件
此示例演示如何 <xref:System.Windows.Media.Visual> 使用和将对象编码到图像文件中 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> <xref:System.Windows.Media.Imaging.PngBitmapEncoder> 。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Media.DrawingVisual>是使用创建的 <xref:System.Windows.Media.Imaging.BitmapImage> ，并 <xref:System.Windows.Media.FormattedText> 呈现给 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 。 然后，将使用呈现的位图来创建一个， <xref:System.Windows.Media.Imaging.BitmapFrame> 它将添加到 <xref:System.Windows.Media.Imaging.PngBitmapEncoder> 以创建新的便携式网络图形 (PNG) 文件。  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <xref:System.Windows.Media.Imaging.PngBitmapEncoder>在此示例中使用了，但任何派生 <xref:System.Windows.Media.Imaging.BitmapEncoder> 对象均可用于创建图像文件。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.DrawingContext>
- [图像处理概述](imaging-overview.md)
- [Drawing 对象概述](drawing-objects-overview.md)
- [使用 DrawingVisual 对象](using-drawingvisual-objects.md)
