---
title: 如何：编码和解码 JPEG 图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding image formats [WPF]
- decoding JPEG images [WPF]
- encoding JPEG images [WPF]
- decoding image formats [WPF]
- JPEG decoding [WPF]
- JPEG encoding [WPF]
ms.assetid: b8cfde37-9f68-4911-a05e-51d8d7bdec7b
ms.openlocfilehash: 0f64ef8537f22ea996cbcf274885de1f3968267a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974097"
---
# <a name="how-to-encode-and-decode-a-jpeg-image"></a><span data-ttu-id="2e58d-102">如何：编码和解码 JPEG 图像</span><span class="sxs-lookup"><span data-stu-id="2e58d-102">How to: Encode and decode a JPEG image</span></span>

<span data-ttu-id="2e58d-103">下面的示例演示如何使用特定和对象对 JPEG 图像进行解码和 <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> 编码 <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> 。</span><span class="sxs-lookup"><span data-stu-id="2e58d-103">The following examples show how to decode and encode a JPEG image using the specific <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> and <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> objects.</span></span>  
  
## <a name="example---decode-a-jpeg-image"></a><span data-ttu-id="2e58d-104">示例-解码 JPEG 图像</span><span class="sxs-lookup"><span data-stu-id="2e58d-104">Example - Decode a JPEG image</span></span>

<span data-ttu-id="2e58d-105">此示例演示如何使用从中解码 JPEG 图像 <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> <xref:System.IO.FileStream> 。</span><span class="sxs-lookup"><span data-stu-id="2e58d-105">This example demonstrates how to decode a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#1)]
[!code-csharp[JpegBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#1)]
[!code-vb[JpegBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#1)]  
  
## <a name="example---encode-a-jpeg-image"></a><span data-ttu-id="2e58d-106">示例-对 JPEG 图像进行编码</span><span class="sxs-lookup"><span data-stu-id="2e58d-106">Example - Encode a JPEG image</span></span>

<span data-ttu-id="2e58d-107">此示例演示如何使用将编码为 <xref:System.Windows.Media.Imaging.BitmapSource> JPEG 图像 <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> 。</span><span class="sxs-lookup"><span data-stu-id="2e58d-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#4)]
[!code-csharp[JpegBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#4)]
[!code-vb[JpegBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="2e58d-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e58d-108">See also</span></span>

- [<span data-ttu-id="2e58d-109">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="2e58d-109">Imaging Overview</span></span>](imaging-overview.md)
