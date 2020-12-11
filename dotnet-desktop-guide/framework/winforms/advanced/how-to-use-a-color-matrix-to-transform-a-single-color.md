---
title: 如何：使用颜色矩阵对单色进行转换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 2df74e022b842f7e5c9ff80f6aeddfce51af5eab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971652"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a><span data-ttu-id="b41d8-102">如何：使用颜色矩阵对单色进行转换</span><span class="sxs-lookup"><span data-stu-id="b41d8-102">How to: Use a Color Matrix to Transform a Single Color</span></span>
<span data-ttu-id="b41d8-103">GDI + 提供 <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> 用于存储和操作图像的和类。</span><span class="sxs-lookup"><span data-stu-id="b41d8-103">GDI+ provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="b41d8-104"><xref:System.Drawing.Image> 和 <xref:System.Drawing.Bitmap> 对象将每个像素的颜色存储为32位数字：对于红色、绿色、蓝色和 alpha 分别使用8位。</span><span class="sxs-lookup"><span data-stu-id="b41d8-104"><xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects store the color of each pixel as a 32-bit number: 8 bits each for red, green, blue, and alpha.</span></span> <span data-ttu-id="b41d8-105">这四个组件都是0到255之间的一个数字，0表示没有强度，255表示完全强度。</span><span class="sxs-lookup"><span data-stu-id="b41d8-105">Each of the four components is a number from 0 through 255, with 0 representing no intensity and 255 representing full intensity.</span></span> <span data-ttu-id="b41d8-106">Alpha 分量指定颜色的透明度：0表示完全透明，255表示完全不透明。</span><span class="sxs-lookup"><span data-stu-id="b41d8-106">The alpha component specifies the transparency of the color: 0 is fully transparent, and 255 is fully opaque.</span></span>  
  
 <span data-ttu-id="b41d8-107">颜色矢量是 (红、绿、蓝、alpha) 形式的4元组。</span><span class="sxs-lookup"><span data-stu-id="b41d8-107">A color vector is a 4-tuple of the form (red, green, blue, alpha).</span></span> <span data-ttu-id="b41d8-108">例如，颜色向量 (0，255，0，255) 表示不透明的颜色，该颜色没有红色或蓝色，但以完全强度显示绿色。</span><span class="sxs-lookup"><span data-stu-id="b41d8-108">For example, the color vector (0, 255, 0, 255) represents an opaque color that has no red or blue, but has green at full intensity.</span></span>  
  
 <span data-ttu-id="b41d8-109">表示颜色的另一种约定使用数字1来表示完全强度。</span><span class="sxs-lookup"><span data-stu-id="b41d8-109">Another convention for representing colors uses the number 1 for full intensity.</span></span> <span data-ttu-id="b41d8-110">使用该约定，上一段中所述的颜色将由向量 (0，1，0，1) 表示。</span><span class="sxs-lookup"><span data-stu-id="b41d8-110">Using that convention, the color described in the preceding paragraph would be represented by the vector (0, 1, 0, 1).</span></span> <span data-ttu-id="b41d8-111">GDI + 执行颜色转换时，使用1作为完整强度的约定。</span><span class="sxs-lookup"><span data-stu-id="b41d8-111">GDI+ uses the convention of 1 as full intensity when it performs color transformations.</span></span>  
  
 <span data-ttu-id="b41d8-112">您可以通过将颜色向量与4×4矩阵相乘，将线性转换 (旋转、缩放和 like) 应用于颜色矢量。</span><span class="sxs-lookup"><span data-stu-id="b41d8-112">You can apply linear transformations (rotation, scaling, and the like) to color vectors by multiplying the color vectors by a 4×4 matrix.</span></span> <span data-ttu-id="b41d8-113">但是，不能使用4×4矩阵 (非线性) 执行转换。</span><span class="sxs-lookup"><span data-stu-id="b41d8-113">However, you cannot use a 4×4 matrix to perform a translation (nonlinear).</span></span> <span data-ttu-id="b41d8-114">如果添加了一个虚拟的第五个坐标 (例如，数字 1) 每个颜色向量，则可以使用5×5矩阵应用线性转换和转换的任意组合。</span><span class="sxs-lookup"><span data-stu-id="b41d8-114">If you add a dummy fifth coordinate (for example, the number 1) to each of the color vectors, you can use a 5×5 matrix to apply any combination of linear transformations and translations.</span></span> <span data-ttu-id="b41d8-115">由线性转换后跟平移的转换称为仿射转换。</span><span class="sxs-lookup"><span data-stu-id="b41d8-115">A transformation consisting of a linear transformation followed by a translation is called an affine transformation.</span></span>  
  
 <span data-ttu-id="b41d8-116">例如，假设你想要从 (0.2、0.0、0.4、1.0) 的颜色开始，并应用以下转换：</span><span class="sxs-lookup"><span data-stu-id="b41d8-116">For example, suppose you want to start with the color (0.2, 0.0, 0.4, 1.0) and apply the following transformations:</span></span>  
  
1. <span data-ttu-id="b41d8-117">双红色分量</span><span class="sxs-lookup"><span data-stu-id="b41d8-117">Double the red component</span></span>  
  
2. <span data-ttu-id="b41d8-118">向红色、绿色和蓝色分量添加0。2</span><span class="sxs-lookup"><span data-stu-id="b41d8-118">Add 0.2 to the red, green, and blue components</span></span>  
  
 <span data-ttu-id="b41d8-119">下面的矩阵乘法将按列出的顺序执行转换对。</span><span class="sxs-lookup"><span data-stu-id="b41d8-119">The following matrix multiplication will perform the pair of transformations in the order listed.</span></span>  
  
 ![转换乘法矩阵的屏幕截图。](./media/how-to-use-a-color-matrix-to-transform-a-single-color/multiplication-color-matrix.gif)
  
 <span data-ttu-id="b41d8-121">颜色矩阵的元素按行和 then 列索引 (从零开始) 。</span><span class="sxs-lookup"><span data-stu-id="b41d8-121">The elements of a color matrix are indexed (zero-based) by row and then column.</span></span> <span data-ttu-id="b41d8-122">例如，matrix M 的第五行和第三列中的条目由 M [4] [2] 表示。</span><span class="sxs-lookup"><span data-stu-id="b41d8-122">For example, the entry in the fifth row and third column of matrix M is denoted by M[4][2].</span></span>  
  
 <span data-ttu-id="b41d8-123">下) 图中显示的5×5恒等矩阵 (，其中每个对角线都为1，而其他位置为0。</span><span class="sxs-lookup"><span data-stu-id="b41d8-123">The 5×5 identity matrix (shown in the following illustration) has 1s on the diagonal and 0s everywhere else.</span></span> <span data-ttu-id="b41d8-124">如果用恒等矩阵乘以颜色向量，则颜色矢量不会改变。</span><span class="sxs-lookup"><span data-stu-id="b41d8-124">If you multiply a color vector by the identity matrix, the color vector does not change.</span></span> <span data-ttu-id="b41d8-125">形成颜色转换的矩阵的一种简便方法是从标识矩阵开始，并进行少量的更改，以生成所需的转换。</span><span class="sxs-lookup"><span data-stu-id="b41d8-125">A convenient way to form the matrix of a color transformation is to start with the identity matrix and make a small change that produces the desired transformation.</span></span>  
  
 ![颜色转换的5x5 标识矩阵的屏幕截图。](./media/how-to-use-a-color-matrix-to-transform-a-single-color/5x5-identity-matrix-color-transformation.gif)  
  
 <span data-ttu-id="b41d8-127">有关矩阵和转换的更多详细讨论，请参阅 [坐标系统和转换](coordinate-systems-and-transformations.md)。</span><span class="sxs-lookup"><span data-stu-id="b41d8-127">For a more detailed discussion of matrices and transformations, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b41d8-128">示例</span><span class="sxs-lookup"><span data-stu-id="b41d8-128">Example</span></span>  
 <span data-ttu-id="b41d8-129">下面的示例使用一个图像，该图像的颜色为0.2、0.0、0.4、1.0)  (，并应用上述段落中描述的转换。</span><span class="sxs-lookup"><span data-stu-id="b41d8-129">The following example takes an image that is all one color (0.2, 0.0, 0.4, 1.0) and applies the transformation described in the preceding paragraphs.</span></span>  
  
 <span data-ttu-id="b41d8-130">下图显示左侧的原始图像和右侧的变换后的图像。</span><span class="sxs-lookup"><span data-stu-id="b41d8-130">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 ![左侧的紫色方块和右侧的 fuchsia 方块。](./media/how-to-use-a-color-matrix-to-transform-a-single-color/color-transformation.png)  
  
 <span data-ttu-id="b41d8-132">以下示例中的代码使用以下步骤来执行重新着色：</span><span class="sxs-lookup"><span data-stu-id="b41d8-132">The code in the following example uses the following steps to perform the recoloring:</span></span>  
  
1. <span data-ttu-id="b41d8-133">初始化 <xref:System.Drawing.Imaging.ColorMatrix> 对象。</span><span class="sxs-lookup"><span data-stu-id="b41d8-133">Initialize a <xref:System.Drawing.Imaging.ColorMatrix> object.</span></span>  
  
2. <span data-ttu-id="b41d8-134">创建一个 <xref:System.Drawing.Imaging.ImageAttributes> 对象，并将该 <xref:System.Drawing.Imaging.ColorMatrix> 对象传递给 <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> 对象的方法 <xref:System.Drawing.Imaging.ImageAttributes> 。</span><span class="sxs-lookup"><span data-stu-id="b41d8-134">Create an <xref:System.Drawing.Imaging.ImageAttributes> object and pass the <xref:System.Drawing.Imaging.ColorMatrix> object to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object.</span></span>  
  
3. <span data-ttu-id="b41d8-135">将 <xref:System.Drawing.Imaging.ImageAttributes> 对象传递给 <xref:System.Drawing.Graphics.DrawImage%2A> 对象的方法 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="b41d8-135">Pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b41d8-136">编译代码</span><span class="sxs-lookup"><span data-stu-id="b41d8-136">Compiling the Code</span></span>  
 <span data-ttu-id="b41d8-137">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="b41d8-137">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b41d8-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b41d8-138">See also</span></span>

- [<span data-ttu-id="b41d8-139">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="b41d8-139">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="b41d8-140">坐标系和坐标转换</span><span class="sxs-lookup"><span data-stu-id="b41d8-140">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
