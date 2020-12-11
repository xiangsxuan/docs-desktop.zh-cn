---
title: 如何：旋转颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971673"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="986c8-102">如何：旋转颜色</span><span class="sxs-lookup"><span data-stu-id="986c8-102">How to: Rotate Colors</span></span>
<span data-ttu-id="986c8-103">在四维颜色空间中，旋转难于可视化。</span><span class="sxs-lookup"><span data-stu-id="986c8-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="986c8-104">通过同意使其中一个颜色组件保持固定，我们可以更轻松地可视化旋转。</span><span class="sxs-lookup"><span data-stu-id="986c8-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="986c8-105">假设我们同意在 1 (完全不透明的) 保持 alpha 分量固定。</span><span class="sxs-lookup"><span data-stu-id="986c8-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="986c8-106">然后，可以使用红色、绿色和蓝色轴直观显示三维颜色空间，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="986c8-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 ![显示用红色、绿色和蓝色轴旋转的插图。](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 <span data-ttu-id="986c8-108">颜色可被视为3D 空间中的点。</span><span class="sxs-lookup"><span data-stu-id="986c8-108">A color can be thought of as a point in 3D space.</span></span> <span data-ttu-id="986c8-109">例如，点 (1，0，0，0) 空间表示红色， (0，1，0) 空间中的点表示绿色。</span><span class="sxs-lookup"><span data-stu-id="986c8-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="986c8-110">下图显示了在 Red-Green 平面中，如何将颜色 (1，0，0) 旋转到60度。</span><span class="sxs-lookup"><span data-stu-id="986c8-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="986c8-111">可以将平面中平行于 Red-Green 平面的旋转视为围绕蓝色轴旋转。</span><span class="sxs-lookup"><span data-stu-id="986c8-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 ![显示有关蓝色轴旋转的插图。](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 <span data-ttu-id="986c8-113">下图显示了如何初始化颜色矩阵，以便对三个坐标轴 (红、绿、蓝) 的每个轴进行旋转：</span><span class="sxs-lookup"><span data-stu-id="986c8-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue):</span></span>  
  
 ![初始化颜色矩阵以执行关于三个轴的旋转。](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a><span data-ttu-id="986c8-115">示例</span><span class="sxs-lookup"><span data-stu-id="986c8-115">Example</span></span>  
 <span data-ttu-id="986c8-116">下面的示例使用一个图像，该图像是 (1，0，0.6) 的所有颜色，并对蓝色轴应用60度旋转。</span><span class="sxs-lookup"><span data-stu-id="986c8-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="986c8-117">旋转角度在平行于 red 绿色平面的平面中进行扫描。</span><span class="sxs-lookup"><span data-stu-id="986c8-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="986c8-118">下图显示左侧的原始图像和右侧的彩色旋转图像：</span><span class="sxs-lookup"><span data-stu-id="986c8-118">The following illustration shows the original image on the left and the color-rotated image on the right:</span></span>  
  
 ![显示原始图像和彩色旋转图像的插图。](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 <span data-ttu-id="986c8-120">下图显示了在以下代码中执行的颜色旋转的可视化效果：</span><span class="sxs-lookup"><span data-stu-id="986c8-120">The following illustration shows a visualization of the color rotation performed in the following code:</span></span>
  
 ![显示颜色旋转的可视化效果的图例。](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="986c8-122">编译代码</span><span class="sxs-lookup"><span data-stu-id="986c8-122">Compiling the Code</span></span>  
 <span data-ttu-id="986c8-123">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="986c8-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="986c8-124">替换 `RotationInput.bmp` 为在系统中有效的图像文件名和路径。</span><span class="sxs-lookup"><span data-stu-id="986c8-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="986c8-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="986c8-125">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="986c8-126">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="986c8-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="986c8-127">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="986c8-127">Recoloring Images</span></span>](recoloring-images.md)
