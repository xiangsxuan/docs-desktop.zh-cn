---
title: 如何：通过避免自动缩放来改善性能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
ms.openlocfilehash: dd1a1545dce33de1ce11938db8495ebf311dadda
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971443"
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a><span data-ttu-id="92e31-102">如何：通过避免自动缩放来改善性能</span><span class="sxs-lookup"><span data-stu-id="92e31-102">How to: Improve Performance by Avoiding Automatic Scaling</span></span>
<span data-ttu-id="92e31-103">GDI + 可以在绘图时自动缩放图像，这会降低性能。</span><span class="sxs-lookup"><span data-stu-id="92e31-103">GDI+ may automatically scale an image as you draw it, which would decrease performance.</span></span> <span data-ttu-id="92e31-104">或者，您可以通过将目标矩形的尺寸传递给方法来控制图像的缩放 <xref:System.Drawing.Graphics.DrawImage%2A> 。</span><span class="sxs-lookup"><span data-stu-id="92e31-104">Alternatively, you can control the scaling of the image by passing the dimensions of the destination rectangle to the <xref:System.Drawing.Graphics.DrawImage%2A> method.</span></span>  
  
 <span data-ttu-id="92e31-105">例如，以下对方法的调用 <xref:System.Drawing.Graphics.DrawImage%2A> 指定 (50，30) 的左上角，但不指定目标矩形。</span><span class="sxs-lookup"><span data-stu-id="92e31-105">For example, the following call to the <xref:System.Drawing.Graphics.DrawImage%2A> method specifies an upper-left corner of (50, 30) but does not specify a destination rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 <span data-ttu-id="92e31-106">尽管这是最简单的方法版本 <xref:System.Drawing.Graphics.DrawImage%2A> ，但它不一定是最有效的方法。</span><span class="sxs-lookup"><span data-stu-id="92e31-106">Although this is the easiest version of the <xref:System.Drawing.Graphics.DrawImage%2A> method in terms of the number of required arguments, it is not necessarily the most efficient.</span></span> <span data-ttu-id="92e31-107">如果 GDI + 使用的分辨率通常 (每英寸96点) 不同于存储在对象中的分辨率 <xref:System.Drawing.Image> ，则 <xref:System.Drawing.Graphics.DrawImage%2A> 方法将缩放图像。</span><span class="sxs-lookup"><span data-stu-id="92e31-107">If the resolution used by GDI+ (usually 96 dots per inch) is different from the resolution stored in the <xref:System.Drawing.Image> object, then the <xref:System.Drawing.Graphics.DrawImage%2A> method will scale the image.</span></span> <span data-ttu-id="92e31-108">例如，假设对象的 <xref:System.Drawing.Image> 宽度为216像素，存储的水平分辨率值为每英寸72点。</span><span class="sxs-lookup"><span data-stu-id="92e31-108">For example, suppose an <xref:System.Drawing.Image> object has a width of 216 pixels and a stored horizontal resolution value of 72 dots per inch.</span></span> <span data-ttu-id="92e31-109">由于216/72 是3， <xref:System.Drawing.Graphics.DrawImage%2A> 将缩放图像，使其宽度为3英寸，分辨率为每英寸96点。</span><span class="sxs-lookup"><span data-stu-id="92e31-109">Because 216/72 is 3, <xref:System.Drawing.Graphics.DrawImage%2A> will scale the image so that it has a width of 3 inches at a resolution of 96 dots per inch.</span></span> <span data-ttu-id="92e31-110">也就是说， <xref:System.Drawing.Graphics.DrawImage%2A> 将显示宽度为 96x3 = 288 像素的图像。</span><span class="sxs-lookup"><span data-stu-id="92e31-110">That is, <xref:System.Drawing.Graphics.DrawImage%2A> will display an image that has a width of 96x3 = 288 pixels.</span></span>  
  
 <span data-ttu-id="92e31-111">即使屏幕分辨率不同于每英寸96点，GDI + 也可能缩放图像，就像屏幕分辨率是每英寸96点。</span><span class="sxs-lookup"><span data-stu-id="92e31-111">Even if your screen resolution is different from 96 dots per inch, GDI+ will probably scale the image as if the screen resolution were 96 dots per inch.</span></span> <span data-ttu-id="92e31-112">这是因为 GDI + <xref:System.Drawing.Graphics> 对象与设备上下文相关联，当 GDI + 查询屏幕分辨率的设备上下文时，结果通常为96，而不考虑实际屏幕分辨率。</span><span class="sxs-lookup"><span data-stu-id="92e31-112">That is because a GDI+ <xref:System.Drawing.Graphics> object is associated with a device context, and when GDI+ queries the device context for the screen resolution, the result is usually 96, regardless of the actual screen resolution.</span></span> <span data-ttu-id="92e31-113">可以通过在方法中指定目标矩形来避免自动缩放 <xref:System.Drawing.Graphics.DrawImage%2A> 。</span><span class="sxs-lookup"><span data-stu-id="92e31-113">You can avoid automatic scaling by specifying the destination rectangle in the <xref:System.Drawing.Graphics.DrawImage%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92e31-114">示例</span><span class="sxs-lookup"><span data-stu-id="92e31-114">Example</span></span>  
 <span data-ttu-id="92e31-115">下面的示例将同一图像绘制两次。</span><span class="sxs-lookup"><span data-stu-id="92e31-115">The following example draws the same image twice.</span></span> <span data-ttu-id="92e31-116">在第一种情况下，不指定目标矩形的宽度和高度，并且自动缩放图像。</span><span class="sxs-lookup"><span data-stu-id="92e31-116">In the first case, the width and height of the destination rectangle are not specified, and the image is automatically scaled.</span></span> <span data-ttu-id="92e31-117">在第二种情况下，将目标矩形) 的宽度和高度 (指定为与原始图像的宽度和高度相同。</span><span class="sxs-lookup"><span data-stu-id="92e31-117">In the second case, the width and height (measured in pixels) of the destination rectangle are specified to be the same as the width and height of the original image.</span></span> <span data-ttu-id="92e31-118">下图显示了呈现两次的图像：</span><span class="sxs-lookup"><span data-stu-id="92e31-118">The following illustration shows the image rendered twice:</span></span>  
  
 ![显示具有缩放纹理的图像的屏幕截图。](./media/how-to-improve-performance-by-avoiding-automatic-scaling/two-scaled-texture-images.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="92e31-120">编译代码</span><span class="sxs-lookup"><span data-stu-id="92e31-120">Compiling the Code</span></span>  
 <span data-ttu-id="92e31-121">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="92e31-121">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="92e31-122">将 Texture.jpg 替换为在系统中有效的映像名称和路径。</span><span class="sxs-lookup"><span data-stu-id="92e31-122">Replace Texture.jpg with an image name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92e31-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92e31-123">See also</span></span>

- [<span data-ttu-id="92e31-124">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="92e31-124">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="92e31-125">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="92e31-125">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
