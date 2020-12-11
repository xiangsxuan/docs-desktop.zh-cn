---
title: 如何：编码和解码 GIF 图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding GIF images [WPF]
- encoding image formats [WPF]
- decoding GIF images [WPF]
- decoding image formats [WPF]
- GIF decoding [WPF]
- GIF encoding [WPF]
ms.assetid: 9cdd9ec7-71eb-444b-b9e3-991958461163
ms.openlocfilehash: ec509a03d95e5f72af0b1f362e253799b07edc1f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973472"
---
# <a name="how-to-encode-and-decode-a-gif-image"></a><span data-ttu-id="2aadc-102">如何：编码和解码 GIF 图像</span><span class="sxs-lookup"><span data-stu-id="2aadc-102">How to: Encode and Decode a GIF Image</span></span>
<span data-ttu-id="2aadc-103">下面的示例演示如何使用特定和对象对图形交换格式进行解码和编码 (GIF) <xref:System.Windows.Media.Imaging.GifBitmapDecoder> 图像 <xref:System.Windows.Media.Imaging.GifBitmapEncoder> 。</span><span class="sxs-lookup"><span data-stu-id="2aadc-103">The following examples show how to decode and encode a Graphics Interchange Format (GIF) image using the specific <xref:System.Windows.Media.Imaging.GifBitmapDecoder> and <xref:System.Windows.Media.Imaging.GifBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2aadc-104">示例</span><span class="sxs-lookup"><span data-stu-id="2aadc-104">Example</span></span>  
 <span data-ttu-id="2aadc-105">此示例演示如何使用从对 GIF 图像进行解码 <xref:System.Windows.Media.Imaging.GifBitmapDecoder> <xref:System.IO.FileStream> 。</span><span class="sxs-lookup"><span data-stu-id="2aadc-105">This example demonstrates how to decode a GIF image using a <xref:System.Windows.Media.Imaging.GifBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="2aadc-106">示例</span><span class="sxs-lookup"><span data-stu-id="2aadc-106">Example</span></span>  
 <span data-ttu-id="2aadc-107">此示例演示如何使用将编码为 <xref:System.Windows.Media.Imaging.BitmapSource> GIF 图像 <xref:System.Windows.Media.Imaging.GifBitmapEncoder> 。</span><span class="sxs-lookup"><span data-stu-id="2aadc-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a GIF image using a <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="2aadc-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2aadc-108">See also</span></span>

- [<span data-ttu-id="2aadc-109">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="2aadc-109">Imaging Overview</span></span>](imaging-overview.md)
