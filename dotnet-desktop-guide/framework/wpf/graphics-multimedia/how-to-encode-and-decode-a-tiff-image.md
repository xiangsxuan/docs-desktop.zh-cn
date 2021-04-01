---
title: 如何：编码和解码 TIFF 图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TIFF encoding [WPF]
- encoding TIFF images [WPF]
- encoding image formats [WPF]
- decoding TIFF images [WPF]
- decoding image formats [WPF]
- TIFF decoding [WPF]
ms.assetid: 1dfe3209-fc73-40e6-ad1c-71c1c58b3364
ms.openlocfilehash: 173a30e785b16a3617b82b771c463083356d6e6e
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973510"
---
# <a name="how-to-encode-and-decode-a-tiff-image"></a><span data-ttu-id="099c8-102">如何：编码和解码 TIFF 图像</span><span class="sxs-lookup"><span data-stu-id="099c8-102">How to: Encode and Decode a TIFF Image</span></span>
<span data-ttu-id="099c8-103">下面的示例演示如何使用特定和对象对标记图像文件格式进行解码和编码 (TIFF) <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> 图像 <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> 。</span><span class="sxs-lookup"><span data-stu-id="099c8-103">The following examples show how to decode and encode a Tagged Image File Format (TIFF) image using the specific <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> and <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="099c8-104">示例</span><span class="sxs-lookup"><span data-stu-id="099c8-104">Example</span></span>  
 <span data-ttu-id="099c8-105">此示例演示如何使用从对 TIFF 图像进行解码 <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> <xref:System.Uri> 。</span><span class="sxs-lookup"><span data-stu-id="099c8-105">This example demonstrates how to decode a TIFF image using a <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#1)]
 [!code-csharp[TiffBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#1)]
 [!code-vb[TiffBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="099c8-106">示例</span><span class="sxs-lookup"><span data-stu-id="099c8-106">Example</span></span>  
 <span data-ttu-id="099c8-107">此示例演示如何使用将编码为 <xref:System.Windows.Media.Imaging.BitmapSource> TIFF 图像 <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> 。</span><span class="sxs-lookup"><span data-stu-id="099c8-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a TIFF image using a <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#4)]
 [!code-csharp[TiffBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#4)]
 [!code-vb[TiffBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="099c8-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="099c8-108">See also</span></span>

- [<span data-ttu-id="099c8-109">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="099c8-109">Imaging Overview</span></span>](imaging-overview.md)
