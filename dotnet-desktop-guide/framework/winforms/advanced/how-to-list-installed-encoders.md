---
title: 如何：列出已安装的编码器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: 2634dd96b3aa5edcecde092919eb328b7f3dadc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971691"
---
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="675c2-102">如何：列出已安装的编码器</span><span class="sxs-lookup"><span data-stu-id="675c2-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="675c2-103">你可能需要列出计算机上可用的图像编码器，以确定应用程序是否可以保存到特定的图像文件格式。</span><span class="sxs-lookup"><span data-stu-id="675c2-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="675c2-104"><xref:System.Drawing.Imaging.ImageCodecInfo>类提供 <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> 静态方法，以便您可以确定哪些图像编码器可用。</span><span class="sxs-lookup"><span data-stu-id="675c2-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <span data-ttu-id="675c2-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> 返回对象的数组 <xref:System.Drawing.Imaging.ImageCodecInfo> 。</span><span class="sxs-lookup"><span data-stu-id="675c2-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="675c2-106">示例</span><span class="sxs-lookup"><span data-stu-id="675c2-106">Example</span></span>  
 <span data-ttu-id="675c2-107">下面的代码示例输出安装的编码器及其属性值的列表。</span><span class="sxs-lookup"><span data-stu-id="675c2-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="675c2-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="675c2-108">Compiling the Code</span></span>  
 <span data-ttu-id="675c2-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="675c2-109">This example requires:</span></span>  
  
- <span data-ttu-id="675c2-110">Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="675c2-110">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="675c2-111">一个 <xref:System.Windows.Forms.PaintEventArgs> ，它是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="675c2-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="675c2-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="675c2-112">See also</span></span>

- [<span data-ttu-id="675c2-113">如何：列出已安装的解码器</span><span class="sxs-lookup"><span data-stu-id="675c2-113">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)
- [<span data-ttu-id="675c2-114">在托管 GDI+ 中使用图像编码器和解码器</span><span class="sxs-lookup"><span data-stu-id="675c2-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
