---
title: 如何：列出已安装的解码器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: 961862d6212b7e76812fc222d3a99f08528d9a16
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971440"
---
# <a name="how-to-list-installed-decoders"></a><span data-ttu-id="52e90-102">如何：列出已安装的解码器</span><span class="sxs-lookup"><span data-stu-id="52e90-102">How to: List Installed Decoders</span></span>
<span data-ttu-id="52e90-103">你可能需要列出计算机上可用的图像解码器，以确定应用程序是否可以读取特定的图像文件格式。</span><span class="sxs-lookup"><span data-stu-id="52e90-103">You may want to list the image decoders available on a computer, to determine whether your application can read a particular image file format.</span></span> <span data-ttu-id="52e90-104"><xref:System.Drawing.Imaging.ImageCodecInfo>类提供 <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> 静态方法，以便您可以确定可用的图像解码器。</span><span class="sxs-lookup"><span data-stu-id="52e90-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> static methods so that you can determine which image decoders are available.</span></span> <span data-ttu-id="52e90-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> 返回对象的数组 <xref:System.Drawing.Imaging.ImageCodecInfo> 。</span><span class="sxs-lookup"><span data-stu-id="52e90-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52e90-106">示例</span><span class="sxs-lookup"><span data-stu-id="52e90-106">Example</span></span>  
 <span data-ttu-id="52e90-107">下面的代码示例输出已安装的解码器及其属性值的列表。</span><span class="sxs-lookup"><span data-stu-id="52e90-107">The following code example outputs the list of installed decoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#2](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="52e90-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="52e90-108">Compiling the Code</span></span>  
 <span data-ttu-id="52e90-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="52e90-109">This example requires:</span></span>  
  
- <span data-ttu-id="52e90-110">Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="52e90-110">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="52e90-111">一个 <xref:System.Windows.Forms.PaintEventArgs> ，它是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="52e90-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e90-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52e90-112">See also</span></span>

- [<span data-ttu-id="52e90-113">如何：列出已安装的编码器</span><span class="sxs-lookup"><span data-stu-id="52e90-113">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="52e90-114">在托管 GDI+ 中使用图像编码器和解码器</span><span class="sxs-lookup"><span data-stu-id="52e90-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
