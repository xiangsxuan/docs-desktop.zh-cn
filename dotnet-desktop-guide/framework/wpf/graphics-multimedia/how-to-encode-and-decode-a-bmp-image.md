---
title: 如何：编码和解码 BMP 图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding BMP images [WPF]
- BMP encoding [WPF]
- decoding BMP images [WPF]
- encoding image formats [WPF]
- BMP decoding [WPF]
- decoding image formats [WPF]
ms.assetid: feb5ef27-28ac-40ab-bfc2-e0456990d32c
ms.openlocfilehash: 7d3520a1b1913fe68fedb0ea9d76cc138ed661c4
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973310"
---
# <a name="how-to-encode-and-decode-a-bmp-image"></a><span data-ttu-id="ebea3-102">如何：编码和解码 BMP 图像</span><span class="sxs-lookup"><span data-stu-id="ebea3-102">How to: Encode and Decode a BMP Image</span></span>
<span data-ttu-id="ebea3-103">下面的示例演示如何使用特定和对象对位图 (BMP) 图像进行解码和 <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> 编码 <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> 。</span><span class="sxs-lookup"><span data-stu-id="ebea3-103">The following examples show how to decode and encode a bitmap (BMP) image using the specific <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebea3-104">示例</span><span class="sxs-lookup"><span data-stu-id="ebea3-104">Example</span></span>  
 <span data-ttu-id="ebea3-105">此示例演示如何使用从中解码 BMP 图像 <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> <xref:System.Uri> 。</span><span class="sxs-lookup"><span data-stu-id="ebea3-105">This example demonstrates how to decode a BMP image using a <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="ebea3-106">示例</span><span class="sxs-lookup"><span data-stu-id="ebea3-106">Example</span></span>  
 <span data-ttu-id="ebea3-107">此示例演示如何使用将编码为 <xref:System.Windows.Media.Imaging.BitmapSource> BMP 图像 <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> 。</span><span class="sxs-lookup"><span data-stu-id="ebea3-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a BMP image using a <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="ebea3-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebea3-108">See also</span></span>

- [<span data-ttu-id="ebea3-109">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="ebea3-109">Imaging Overview</span></span>](imaging-overview.md)
