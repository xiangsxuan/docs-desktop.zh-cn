---
title: 如何：从 Visual 创建位图
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: a622d99f7c477f8654526ed399f1eb37288682fe
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973523"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a>如何：从 Visual 创建位图
此示例演示如何从创建位图 <xref:System.Windows.Media.Visual> 。 <xref:System.Windows.Media.DrawingVisual>使用呈现 <xref:System.Windows.Media.FormattedText> 。 然后，将 <xref:System.Windows.Media.Visual> 呈现到 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 创建给定文本的位图。  
  
## <a name="example"></a>示例  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.DrawingContext>
- [图像处理概述](imaging-overview.md)
- [Drawing 对象概述](drawing-objects-overview.md)
- [使用 DrawingVisual 对象](using-drawingvisual-objects.md)
