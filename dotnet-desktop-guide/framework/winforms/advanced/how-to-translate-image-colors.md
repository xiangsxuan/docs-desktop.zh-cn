---
title: 如何：转换图像颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: fb9ec30c06740214b8dc6b65d32eba4e2920c89b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971647"
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="5ae07-102">如何：转换图像颜色</span><span class="sxs-lookup"><span data-stu-id="5ae07-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="5ae07-103">翻译会将一个值添加到四个颜色组件中的一个或多个。</span><span class="sxs-lookup"><span data-stu-id="5ae07-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="5ae07-104">下表给出了表示翻译的颜色矩阵条目。</span><span class="sxs-lookup"><span data-stu-id="5ae07-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="5ae07-105">要转换的组件</span><span class="sxs-lookup"><span data-stu-id="5ae07-105">Component to be translated</span></span>|<span data-ttu-id="5ae07-106">矩阵条目</span><span class="sxs-lookup"><span data-stu-id="5ae07-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="5ae07-107">Red</span><span class="sxs-lookup"><span data-stu-id="5ae07-107">Red</span></span>|<span data-ttu-id="5ae07-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="5ae07-108">[4][0]</span></span>|  
|<span data-ttu-id="5ae07-109">绿色</span><span class="sxs-lookup"><span data-stu-id="5ae07-109">Green</span></span>|<span data-ttu-id="5ae07-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="5ae07-110">[4][1]</span></span>|  
|<span data-ttu-id="5ae07-111">蓝色</span><span class="sxs-lookup"><span data-stu-id="5ae07-111">Blue</span></span>|<span data-ttu-id="5ae07-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="5ae07-112">[4][2]</span></span>|  
|<span data-ttu-id="5ae07-113">Alpha</span><span class="sxs-lookup"><span data-stu-id="5ae07-113">Alpha</span></span>|<span data-ttu-id="5ae07-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="5ae07-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5ae07-115">示例</span><span class="sxs-lookup"><span data-stu-id="5ae07-115">Example</span></span>  
 <span data-ttu-id="5ae07-116">下面的示例 <xref:System.Drawing.Image> 从文件 ColorBars.bmp 构造对象。</span><span class="sxs-lookup"><span data-stu-id="5ae07-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="5ae07-117">然后，代码将0.75 添加到图像中每个像素的红色部分。</span><span class="sxs-lookup"><span data-stu-id="5ae07-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="5ae07-118">原始图像与变换后的图像一起绘制。</span><span class="sxs-lookup"><span data-stu-id="5ae07-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="5ae07-119">下图显示左侧的原始图像和右侧已转换的图像：</span><span class="sxs-lookup"><span data-stu-id="5ae07-119">The following illustration shows the original image on the left and the transformed image on the right:</span></span>  
  
 ![原始图像和转换图像的屏幕截图。](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 <span data-ttu-id="5ae07-121">下表列出了红色转换前后四个条形的颜色矢量。</span><span class="sxs-lookup"><span data-stu-id="5ae07-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="5ae07-122">请注意，由于颜色分量的最大值为1，第二行中的红色部分不会更改。</span><span class="sxs-lookup"><span data-stu-id="5ae07-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="5ae07-123"> (同样，颜色分量的最小值为0。 ) </span><span class="sxs-lookup"><span data-stu-id="5ae07-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="5ae07-124">原始</span><span class="sxs-lookup"><span data-stu-id="5ae07-124">Original</span></span>|<span data-ttu-id="5ae07-125">已转换</span><span class="sxs-lookup"><span data-stu-id="5ae07-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="5ae07-126">黑色 (0，0，0，1) </span><span class="sxs-lookup"><span data-stu-id="5ae07-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="5ae07-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae07-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="5ae07-128">红色 (1，0，0，1) </span><span class="sxs-lookup"><span data-stu-id="5ae07-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="5ae07-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae07-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="5ae07-130">绿色 (0，1，0，1) </span><span class="sxs-lookup"><span data-stu-id="5ae07-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="5ae07-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae07-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="5ae07-132">Blue (0，0，1，1) </span><span class="sxs-lookup"><span data-stu-id="5ae07-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="5ae07-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae07-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5ae07-134">编译代码</span><span class="sxs-lookup"><span data-stu-id="5ae07-134">Compiling the Code</span></span>  
 <span data-ttu-id="5ae07-135">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="5ae07-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="5ae07-136">替换 `ColorBars.bmp` 为在系统中有效的图像文件名和路径。</span><span class="sxs-lookup"><span data-stu-id="5ae07-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ae07-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ae07-137">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="5ae07-138">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="5ae07-138">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="5ae07-139">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="5ae07-139">Recoloring Images</span></span>](recoloring-images.md)
