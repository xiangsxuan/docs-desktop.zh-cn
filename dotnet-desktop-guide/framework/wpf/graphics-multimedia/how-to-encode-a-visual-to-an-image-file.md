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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974098"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="61328-102">如何：将 Visual 编码为图像文件</span><span class="sxs-lookup"><span data-stu-id="61328-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="61328-103">此示例演示如何 <xref:System.Windows.Media.Visual> 使用和将对象编码到图像文件中 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> <xref:System.Windows.Media.Imaging.PngBitmapEncoder> 。</span><span class="sxs-lookup"><span data-stu-id="61328-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61328-104">示例</span><span class="sxs-lookup"><span data-stu-id="61328-104">Example</span></span>  
 <span data-ttu-id="61328-105"><xref:System.Windows.Media.DrawingVisual>是使用创建的 <xref:System.Windows.Media.Imaging.BitmapImage> ，并 <xref:System.Windows.Media.FormattedText> 呈现给 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 。</span><span class="sxs-lookup"><span data-stu-id="61328-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="61328-106">然后，将使用呈现的位图来创建一个， <xref:System.Windows.Media.Imaging.BitmapFrame> 它将添加到 <xref:System.Windows.Media.Imaging.PngBitmapEncoder> 以创建新的便携式网络图形 (PNG) 文件。</span><span class="sxs-lookup"><span data-stu-id="61328-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new Portable Network Graphics (PNG) file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="61328-107"><xref:System.Windows.Media.Imaging.PngBitmapEncoder>在此示例中使用了，但任何派生 <xref:System.Windows.Media.Imaging.BitmapEncoder> 对象均可用于创建图像文件。</span><span class="sxs-lookup"><span data-stu-id="61328-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61328-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61328-108">See also</span></span>

- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="61328-109">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="61328-109">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="61328-110">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="61328-110">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="61328-111">使用 DrawingVisual 对象</span><span class="sxs-lookup"><span data-stu-id="61328-111">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
