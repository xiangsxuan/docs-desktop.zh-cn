---
title: 如何：用图像纹理填充形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: 42c456137f84c6fa657ba5a09727eae052a45376
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971702"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="8ada3-102">如何：用图像纹理填充形状</span><span class="sxs-lookup"><span data-stu-id="8ada3-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="8ada3-103">通过使用 <xref:System.Drawing.Image> 类和类，您可以使用纹理填充闭合形状 <xref:System.Drawing.TextureBrush> 。</span><span class="sxs-lookup"><span data-stu-id="8ada3-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ada3-104">示例</span><span class="sxs-lookup"><span data-stu-id="8ada3-104">Example</span></span>  
 <span data-ttu-id="8ada3-105">下面的示例使用图像填充椭圆。</span><span class="sxs-lookup"><span data-stu-id="8ada3-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="8ada3-106">代码构造 <xref:System.Drawing.Image> 对象，然后将该对象的地址 <xref:System.Drawing.Image> 作为参数传递给 <xref:System.Drawing.TextureBrush.%23ctor%2A> 构造函数。</span><span class="sxs-lookup"><span data-stu-id="8ada3-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="8ada3-107">第三个语句缩放图像，第四条语句用缩放图像的重复副本填充椭圆。</span><span class="sxs-lookup"><span data-stu-id="8ada3-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="8ada3-108">在下面的代码中， <xref:System.Drawing.TextureBrush.Transform%2A> 属性包含在绘制图像之前应用于该图像的转换。</span><span class="sxs-lookup"><span data-stu-id="8ada3-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="8ada3-109">假设原始图像的宽度为640像素，高度为480像素。</span><span class="sxs-lookup"><span data-stu-id="8ada3-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="8ada3-110">该转换通过设置水平和垂直缩放值将图像收缩为75×75。</span><span class="sxs-lookup"><span data-stu-id="8ada3-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8ada3-111">在下面的示例中，图像大小为75×75，椭圆大小为150×250。</span><span class="sxs-lookup"><span data-stu-id="8ada3-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="8ada3-112">由于图像小于它所填充的椭圆，因此椭圆与图像平铺。</span><span class="sxs-lookup"><span data-stu-id="8ada3-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="8ada3-113">平铺意味着在达到形状边界之前，图像将水平和垂直地重复。</span><span class="sxs-lookup"><span data-stu-id="8ada3-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="8ada3-114">有关平铺的详细信息，请参阅 [如何：使用图像平铺形状](how-to-tile-a-shape-with-an-image.md)。</span><span class="sxs-lookup"><span data-stu-id="8ada3-114">For more information about tiling, see [How to: Tile a Shape with an Image](how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8ada3-115">编译代码</span><span class="sxs-lookup"><span data-stu-id="8ada3-115">Compiling the Code</span></span>  
 <span data-ttu-id="8ada3-116">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="8ada3-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ada3-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ada3-117">See also</span></span>

- [<span data-ttu-id="8ada3-118">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="8ada3-118">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
