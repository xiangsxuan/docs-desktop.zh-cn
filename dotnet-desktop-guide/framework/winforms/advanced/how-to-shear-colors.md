---
title: 如何：切变颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971412"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="a4366-102">如何：切变颜色</span><span class="sxs-lookup"><span data-stu-id="a4366-102">How to: Shear Colors</span></span>
<span data-ttu-id="a4366-103">切变按与其他颜色组件成比例的比例增加或减少颜色成分。</span><span class="sxs-lookup"><span data-stu-id="a4366-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="a4366-104">例如，请考虑一个转换，其中红色组件会增加蓝色分量值的一半。</span><span class="sxs-lookup"><span data-stu-id="a4366-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="a4366-105">在这种转换下，0.2、0.5、1) 的颜色 ( (0.7，0.5，1) 。</span><span class="sxs-lookup"><span data-stu-id="a4366-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="a4366-106">新的红色分量为 0.2 + (1/2) # B2 1) = 0.7。</span><span class="sxs-lookup"><span data-stu-id="a4366-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4366-107">示例</span><span class="sxs-lookup"><span data-stu-id="a4366-107">Example</span></span>  
 <span data-ttu-id="a4366-108">下面的示例 <xref:System.Drawing.Image> 从文件 ColorBars4.bmp 构造对象。</span><span class="sxs-lookup"><span data-stu-id="a4366-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="a4366-109">然后，该代码将上一段中所述的切变转换应用于图像中的每个像素。</span><span class="sxs-lookup"><span data-stu-id="a4366-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="a4366-110">下图显示左侧的原始图像和右侧剪切的图像：</span><span class="sxs-lookup"><span data-stu-id="a4366-110">The following illustration shows the original image on the left and the sheared image on the right:</span></span>
  
 ![具有彩色条带线的两个正方形，用于说明原始图像和剪切图像。](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 <span data-ttu-id="a4366-112">下表列出了切变转换前后四个条形的颜色矢量。</span><span class="sxs-lookup"><span data-stu-id="a4366-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="a4366-113">原始</span><span class="sxs-lookup"><span data-stu-id="a4366-113">Original</span></span>|<span data-ttu-id="a4366-114">剪切</span><span class="sxs-lookup"><span data-stu-id="a4366-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="a4366-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="a4366-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="a4366-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="a4366-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="a4366-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="a4366-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="a4366-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="a4366-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="a4366-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="a4366-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="a4366-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="a4366-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="a4366-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="a4366-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="a4366-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="a4366-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a4366-123">编译代码</span><span class="sxs-lookup"><span data-stu-id="a4366-123">Compiling the Code</span></span>  
 <span data-ttu-id="a4366-124">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="a4366-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="a4366-125">替换 `ColorBars.bmp` 为在系统中有效的图像名称和路径。</span><span class="sxs-lookup"><span data-stu-id="a4366-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4366-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4366-126">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="a4366-127">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="a4366-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="a4366-128">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="a4366-128">Recoloring Images</span></span>](recoloring-images.md)
