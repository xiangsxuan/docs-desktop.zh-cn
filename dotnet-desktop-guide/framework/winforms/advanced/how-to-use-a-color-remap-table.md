---
title: 如何：使用颜色重新映射表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 360ec30563ee5001d784dc7c4ccdb50563867c29
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971395"
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="5d810-102">如何：使用颜色重新映射表</span><span class="sxs-lookup"><span data-stu-id="5d810-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="5d810-103">重新映射是指根据颜色重新映射表转换图像中的颜色的过程。</span><span class="sxs-lookup"><span data-stu-id="5d810-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="5d810-104">颜色重新映射表是对象的数组 <xref:System.Drawing.Imaging.ColorMap> 。</span><span class="sxs-lookup"><span data-stu-id="5d810-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="5d810-105"><xref:System.Drawing.Imaging.ColorMap>数组中的每个对象都有一个 <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> 属性和一个 <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="5d810-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="5d810-106">当 GDI + 绘制图像时，图像的每个像素都将与旧颜色数组进行比较。</span><span class="sxs-lookup"><span data-stu-id="5d810-106">When GDI+ draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="5d810-107">如果像素的颜色与旧颜色匹配，则其颜色将更改为相应的新颜色。</span><span class="sxs-lookup"><span data-stu-id="5d810-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="5d810-108">仅为呈现更改颜色，在或对象) 中存储的图像本身 (颜色值 <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> 不会更改。</span><span class="sxs-lookup"><span data-stu-id="5d810-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="5d810-109">若要绘制重映射的图像，请初始化 <xref:System.Drawing.Imaging.ColorMap> 对象的数组。</span><span class="sxs-lookup"><span data-stu-id="5d810-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="5d810-110">将该数组传递给 <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> 对象的方法 <xref:System.Drawing.Imaging.ImageAttributes> ，然后将该对象传递 <xref:System.Drawing.Imaging.ImageAttributes> 给对象的 <xref:System.Drawing.Graphics.DrawImage%2A> 方法 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="5d810-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d810-111">示例</span><span class="sxs-lookup"><span data-stu-id="5d810-111">Example</span></span>  
 <span data-ttu-id="5d810-112">下面的示例 <xref:System.Drawing.Image> 从文件 RemapInput.bmp 创建对象。</span><span class="sxs-lookup"><span data-stu-id="5d810-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="5d810-113">此代码创建由单个对象组成的颜色重新映射表 <xref:System.Drawing.Imaging.ColorMap> 。</span><span class="sxs-lookup"><span data-stu-id="5d810-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="5d810-114"><xref:System.Drawing.Imaging.ColorMap.OldColor%2A>对象的属性 `ColorRemap` 为红色， <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> 属性为蓝色。</span><span class="sxs-lookup"><span data-stu-id="5d810-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="5d810-115">此图像绘制一次，无需重新映射，一次是重新映射。</span><span class="sxs-lookup"><span data-stu-id="5d810-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="5d810-116">重新映射过程会将所有红色像素变为蓝色。</span><span class="sxs-lookup"><span data-stu-id="5d810-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="5d810-117">下图显示左侧的原始图像和右侧重新映射后的图像。</span><span class="sxs-lookup"><span data-stu-id="5d810-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 ![显示原始图像和重新映射映像的屏幕截图。](./media/how-to-use-a-color-remap-table/original-image-remap-colors.png)  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5d810-119">编译代码</span><span class="sxs-lookup"><span data-stu-id="5d810-119">Compiling the Code</span></span>  
 <span data-ttu-id="5d810-120">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="5d810-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d810-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d810-121">See also</span></span>

- [<span data-ttu-id="5d810-122">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="5d810-122">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="5d810-123">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="5d810-123">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
