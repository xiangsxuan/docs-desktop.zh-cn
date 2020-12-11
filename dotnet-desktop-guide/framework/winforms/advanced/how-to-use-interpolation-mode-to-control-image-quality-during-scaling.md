---
title: 如何：在缩放期间使用内插模式控制图像质量
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: ab0ff93b3ee26467c0de448efd31b698167f95c2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971637"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a><span data-ttu-id="fef4e-102">如何：在缩放期间使用内插模式控制图像质量</span><span class="sxs-lookup"><span data-stu-id="fef4e-102">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>
<span data-ttu-id="fef4e-103">对象的内插模式 <xref:System.Drawing.Graphics> 影响 GDI + 缩放 (拉伸和收缩) 图像的方式。</span><span class="sxs-lookup"><span data-stu-id="fef4e-103">The interpolation mode of a <xref:System.Drawing.Graphics> object influences the way GDI+ scales (stretches and shrinks) images.</span></span> <span data-ttu-id="fef4e-104"><xref:System.Drawing.Drawing2D.InterpolationMode>枚举定义了几种内插模式，其中的一些模式显示在下面的列表中：</span><span class="sxs-lookup"><span data-stu-id="fef4e-104">The <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration defines several interpolation modes, some of which are shown in the following list:</span></span>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 <span data-ttu-id="fef4e-105">若要拉伸图像，必须将原始图像中的每个像素映射到较大图像中的一组像素。</span><span class="sxs-lookup"><span data-stu-id="fef4e-105">To stretch an image, each pixel in the original image must be mapped to a group of pixels in the larger image.</span></span> <span data-ttu-id="fef4e-106">若要收缩图像，必须将原始图像中的像素组映射到较小图像中的单个像素。</span><span class="sxs-lookup"><span data-stu-id="fef4e-106">To shrink an image, groups of pixels in the original image must be mapped to single pixels in the smaller image.</span></span> <span data-ttu-id="fef4e-107">执行这些映射的算法的有效性决定了缩放图像的质量。</span><span class="sxs-lookup"><span data-stu-id="fef4e-107">The effectiveness of the algorithms that perform these mappings determines the quality of a scaled image.</span></span> <span data-ttu-id="fef4e-108">生成高质量缩放图像的算法往往需要更长的处理时间。</span><span class="sxs-lookup"><span data-stu-id="fef4e-108">Algorithms that produce higher-quality scaled images tend to require more processing time.</span></span> <span data-ttu-id="fef4e-109">在上面的列表中，是最高 <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> 质量的模式，并且 <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> 是最高质量的模式。</span><span class="sxs-lookup"><span data-stu-id="fef4e-109">In the preceding list, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> is the lowest-quality mode and <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> is the highest-quality mode.</span></span>  
  
 <span data-ttu-id="fef4e-110">若要设置内插模式，请将枚举的一个成员分配 <xref:System.Drawing.Drawing2D.InterpolationMode> 给 <xref:System.Drawing.Graphics.InterpolationMode%2A> 对象的属性 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="fef4e-110">To set the interpolation mode, assign one of the members of the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to the <xref:System.Drawing.Graphics.InterpolationMode%2A> property of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fef4e-111">示例</span><span class="sxs-lookup"><span data-stu-id="fef4e-111">Example</span></span>  
 <span data-ttu-id="fef4e-112">下面的示例绘制一个图像，然后使用三个不同的内插模式缩小图像。</span><span class="sxs-lookup"><span data-stu-id="fef4e-112">The following example draws an image and then shrinks the image with three different interpolation modes.</span></span>  
  
 <span data-ttu-id="fef4e-113">下图显示了原始图像和三个较小的图像。</span><span class="sxs-lookup"><span data-stu-id="fef4e-113">The following illustration shows the original image and the three smaller images.</span></span>  
  
 ![显示带有各种内插设置的图像的屏幕截图。](./media/how-to-use-interpolation-mode-to-control-image-quality-during-scaling/varied-interpolation-settings.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fef4e-115">编译代码</span><span class="sxs-lookup"><span data-stu-id="fef4e-115">Compiling the Code</span></span>  
 <span data-ttu-id="fef4e-116">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="fef4e-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef4e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fef4e-117">See also</span></span>

- [<span data-ttu-id="fef4e-118">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="fef4e-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="fef4e-119">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="fef4e-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
