---
title: 如何：旋转、反射和倾斜图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 80ac92d545d9be7a4a611038eaaadbbdbe2e8ecf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971420"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a><span data-ttu-id="f6f8c-102">如何：旋转、反射和倾斜图像</span><span class="sxs-lookup"><span data-stu-id="f6f8c-102">How to: Rotate, Reflect, and Skew Images</span></span>
<span data-ttu-id="f6f8c-103">可以通过指定原始图像左上角、右上角和左下角的目标点来旋转、反射和倾斜图像。</span><span class="sxs-lookup"><span data-stu-id="f6f8c-103">You can rotate, reflect, and skew an image by specifying destination points for the upper-left, upper-right, and lower-left corners of the original image.</span></span> <span data-ttu-id="f6f8c-104">三个目标点确定将原始矩形图像映射到平行四边形的仿射转换。</span><span class="sxs-lookup"><span data-stu-id="f6f8c-104">The three destination points determine an affine transformation that maps the original rectangular image to a parallelogram.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6f8c-105">示例</span><span class="sxs-lookup"><span data-stu-id="f6f8c-105">Example</span></span>  
 <span data-ttu-id="f6f8c-106">例如，假设原始图像是一个矩形，左上角的 (0，0) ，右上角的 (100，0) ，左下角位于 (0，50) 。</span><span class="sxs-lookup"><span data-stu-id="f6f8c-106">For example, suppose the original image is a rectangle with upper-left corner at (0, 0), upper-right corner at (100, 0), and lower-left corner at (0, 50).</span></span> <span data-ttu-id="f6f8c-107">现在假设你将这三个点映射到目标点，如下所示。</span><span class="sxs-lookup"><span data-stu-id="f6f8c-107">Now suppose you map those three points to destination points as follows.</span></span>  
  
|<span data-ttu-id="f6f8c-108">原始点</span><span class="sxs-lookup"><span data-stu-id="f6f8c-108">Original point</span></span>|<span data-ttu-id="f6f8c-109">目标点</span><span class="sxs-lookup"><span data-stu-id="f6f8c-109">Destination point</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="f6f8c-110">左上 (0，0) </span><span class="sxs-lookup"><span data-stu-id="f6f8c-110">Upper-left (0, 0)</span></span>|<span data-ttu-id="f6f8c-111">(200, 20)</span><span class="sxs-lookup"><span data-stu-id="f6f8c-111">(200, 20)</span></span>|  
|<span data-ttu-id="f6f8c-112">右上 (100，0) </span><span class="sxs-lookup"><span data-stu-id="f6f8c-112">Upper-right (100, 0)</span></span>|<span data-ttu-id="f6f8c-113">(110, 100)</span><span class="sxs-lookup"><span data-stu-id="f6f8c-113">(110, 100)</span></span>|  
|<span data-ttu-id="f6f8c-114">左下 (0，50) </span><span class="sxs-lookup"><span data-stu-id="f6f8c-114">Lower-left (0, 50)</span></span>|<span data-ttu-id="f6f8c-115">(250, 30)</span><span class="sxs-lookup"><span data-stu-id="f6f8c-115">(250, 30)</span></span>|  
  
 <span data-ttu-id="f6f8c-116">下图显示了原始图像和映射到平行四边形的图像。</span><span class="sxs-lookup"><span data-stu-id="f6f8c-116">The following illustration shows the original image and the image mapped to the parallelogram.</span></span> <span data-ttu-id="f6f8c-117">原始图像已被扭曲、反射、旋转和平移。</span><span class="sxs-lookup"><span data-stu-id="f6f8c-117">The original image has been skewed, reflected, rotated, and translated.</span></span> <span data-ttu-id="f6f8c-118">沿原始图像上边缘的 x 轴映射到通过 (200，20) 和 (110，100) 运行的行。</span><span class="sxs-lookup"><span data-stu-id="f6f8c-118">The x-axis along the top edge of the original image is mapped to the line that runs through (200, 20) and (110, 100).</span></span> <span data-ttu-id="f6f8c-119">沿原始图像左边缘的 y 轴映射到通过 (200，20) 和 (250，30) 运行的行。</span><span class="sxs-lookup"><span data-stu-id="f6f8c-119">The y-axis along the left edge of the original image is mapped to the line that runs through (200, 20) and (250, 30).</span></span>  
  
 ![原始图像和映射到平行四边形的图像。](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-illustration.gif)  
  
 <span data-ttu-id="f6f8c-121">下图显示了应用于照片图像的类似转换：</span><span class="sxs-lookup"><span data-stu-id="f6f8c-121">The following illustration shows a similar transformation applied to a photographic image:</span></span>  
  
 ![Climber 和映射到平行四边形的图片的图片。](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-photo.png)  
  
 <span data-ttu-id="f6f8c-123">下图显示了应用于图元文件的类似转换：</span><span class="sxs-lookup"><span data-stu-id="f6f8c-123">The following illustration shows a similar transformation applied to a metafile:</span></span>  
  
 ![映射到平行四边形的形状和文本的插图。](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-metafile.png)  
  
 <span data-ttu-id="f6f8c-125">下面的示例生成第一个图中显示的图像。</span><span class="sxs-lookup"><span data-stu-id="f6f8c-125">The following example produces the images shown in the first illustration.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f6f8c-126">编译代码</span><span class="sxs-lookup"><span data-stu-id="f6f8c-126">Compiling the Code</span></span>  
 <span data-ttu-id="f6f8c-127">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="f6f8c-127">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f6f8c-128">请确保将替换为在 `Stripes.bmp` 系统中有效的图像的路径。</span><span class="sxs-lookup"><span data-stu-id="f6f8c-128">Make sure to replace `Stripes.bmp` with the path to an image that is valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6f8c-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6f8c-129">See also</span></span>

- [<span data-ttu-id="f6f8c-130">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="f6f8c-130">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
