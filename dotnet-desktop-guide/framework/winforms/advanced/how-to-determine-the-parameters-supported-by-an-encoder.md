---
title: 如何：确定编码器支持的参数
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 3e5345180e0ff3321b9ef0b885b836d3e9456f28
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970313"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="10b0b-102">如何：确定编码器支持的参数</span><span class="sxs-lookup"><span data-stu-id="10b0b-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="10b0b-103">你可以调整图像参数，如质量和压缩级别，但你必须知道给定图像编码器支持哪些参数。</span><span class="sxs-lookup"><span data-stu-id="10b0b-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="10b0b-104"><xref:System.Drawing.Image>类提供方法， <xref:System.Drawing.Image.GetEncoderParameterList%2A> 以便您可以确定特定编码器支持的图像参数。</span><span class="sxs-lookup"><span data-stu-id="10b0b-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="10b0b-105">使用 GUID 指定编码器。</span><span class="sxs-lookup"><span data-stu-id="10b0b-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="10b0b-106"><xref:System.Drawing.Image.GetEncoderParameterList%2A>方法返回对象的数组 <xref:System.Drawing.Imaging.EncoderParameter> 。</span><span class="sxs-lookup"><span data-stu-id="10b0b-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10b0b-107">示例</span><span class="sxs-lookup"><span data-stu-id="10b0b-107">Example</span></span>  
 <span data-ttu-id="10b0b-108">下面的示例代码输出 JPEG 编码器支持的参数。</span><span class="sxs-lookup"><span data-stu-id="10b0b-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="10b0b-109">使用类概述中的参数类别列表和关联 Guid <xref:System.Drawing.Imaging.Encoder> 来确定每个参数的类别。</span><span class="sxs-lookup"><span data-stu-id="10b0b-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="10b0b-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="10b0b-110">Compiling the Code</span></span>  
 <span data-ttu-id="10b0b-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="10b0b-111">This example requires:</span></span>  
  
- <span data-ttu-id="10b0b-112">Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="10b0b-112">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="10b0b-113">一个 <xref:System.Windows.Forms.PaintEventArgs> ，它是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="10b0b-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10b0b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10b0b-114">See also</span></span>

- [<span data-ttu-id="10b0b-115">如何：列出已安装的编码器</span><span class="sxs-lookup"><span data-stu-id="10b0b-115">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="10b0b-116">位图类型</span><span class="sxs-lookup"><span data-stu-id="10b0b-116">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="10b0b-117">在托管 GDI+ 中使用图像编码器和解码器</span><span class="sxs-lookup"><span data-stu-id="10b0b-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
