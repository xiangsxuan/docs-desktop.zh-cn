---
title: 使用渐变画笔填充形状
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 7ff555ba4fd81e9123e5f9e9feed38a0ec9d0a08
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971580"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a><span data-ttu-id="d746b-102">使用渐变画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="d746b-102">Using a Gradient Brush to Fill Shapes</span></span>
<span data-ttu-id="d746b-103">您可以使用渐变画笔来填充渐变颜色的形状。</span><span class="sxs-lookup"><span data-stu-id="d746b-103">You can use a gradient brush to fill a shape with a gradually changing color.</span></span> <span data-ttu-id="d746b-104">例如，您可以使用水平渐变填充具有颜色的形状，该颜色在从形状的左边缘向右边缘移动时逐渐变化。</span><span class="sxs-lookup"><span data-stu-id="d746b-104">For example, you can use a horizontal gradient to fill a shape with color that changes gradually as you move from the left edge of the shape to the right edge.</span></span> <span data-ttu-id="d746b-105">假设有一个矩形，左边缘为黑色 (由红色、绿色和蓝色分量0、0、0) 和右边缘表示， (由255，0，0) 表示。</span><span class="sxs-lookup"><span data-stu-id="d746b-105">Imagine a rectangle with a left edge that is black (represented by red, green, and blue components 0, 0, 0) and a right edge that is red (represented by 255, 0, 0).</span></span> <span data-ttu-id="d746b-106">如果矩形为256像素宽，则给定像素的红色分量将比它左侧像素的红色分量大1。</span><span class="sxs-lookup"><span data-stu-id="d746b-106">If the rectangle is 256 pixels wide, the red component of a given pixel will be one greater than the red component of the pixel to its left.</span></span> <span data-ttu-id="d746b-107">行中最左边的像素具有颜色分量 (0，0，0) ，第二个像素 (1，0，0) ，第三个像素具有 (2，0，0) ，依此类推，直到到达最右边的像素，其中颜色分量 (255，0，0) 。</span><span class="sxs-lookup"><span data-stu-id="d746b-107">The leftmost pixel in a row has color components (0, 0, 0), the second pixel has (1, 0, 0), the third pixel has (2, 0, 0), and so on, until you get to the rightmost pixel, which has color components (255, 0, 0).</span></span> <span data-ttu-id="d746b-108">这些插值颜色值构成了颜色渐变。</span><span class="sxs-lookup"><span data-stu-id="d746b-108">These interpolated color values make up the color gradient.</span></span>  
  
 <span data-ttu-id="d746b-109">当水平、垂直或平行于指定的斜线时，线性渐变会改变颜色。</span><span class="sxs-lookup"><span data-stu-id="d746b-109">A linear gradient changes color as you move horizontally, vertically, or parallel to a specified slanted line.</span></span> <span data-ttu-id="d746b-110">移动路径的内部和边界时，路径渐变会改变颜色。</span><span class="sxs-lookup"><span data-stu-id="d746b-110">A path gradient changes color as you move about the interior and boundary of a path.</span></span> <span data-ttu-id="d746b-111">您可以自定义路径渐变以实现各种效果。</span><span class="sxs-lookup"><span data-stu-id="d746b-111">You can customize path gradients to achieve a wide variety of effects.</span></span>  
  
 <span data-ttu-id="d746b-112">下图显示了使用线性渐变画笔填充的矩形，并使用路径渐变画笔填充了椭圆：</span><span class="sxs-lookup"><span data-stu-id="d746b-112">The following illustration shows a rectangle filled with a linear gradient brush and an ellipse filled with a path gradient brush:</span></span>  
  
 ![使用带有椭圆的渐变画笔填充的矩形。](./media/using-a-gradient-brush-to-fill-shapes/rectangle-ellipse-gradient-brush.png)  
  
## <a name="in-this-section"></a><span data-ttu-id="d746b-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="d746b-114">In This Section</span></span>  
 [<span data-ttu-id="d746b-115">如何：创建线性渐变</span><span class="sxs-lookup"><span data-stu-id="d746b-115">How to: Create a Linear Gradient</span></span>](how-to-create-a-linear-gradient.md)  
 <span data-ttu-id="d746b-116">演示如何使用类创建线性渐变 <xref:System.Drawing.Drawing2D.LinearGradientBrush> 。</span><span class="sxs-lookup"><span data-stu-id="d746b-116">Shows how to create a linear gradient using the <xref:System.Drawing.Drawing2D.LinearGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="d746b-117">如何：创建路径渐变</span><span class="sxs-lookup"><span data-stu-id="d746b-117">How to: Create a Path Gradient</span></span>](how-to-create-a-path-gradient.md)  
 <span data-ttu-id="d746b-118">描述如何使用类创建路径渐变 <xref:System.Drawing.Drawing2D.PathGradientBrush> 。</span><span class="sxs-lookup"><span data-stu-id="d746b-118">Describes how to create a path gradient using the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="d746b-119">如何：对渐变应用 gamma 矫正</span><span class="sxs-lookup"><span data-stu-id="d746b-119">How to: Apply Gamma Correction to a Gradient</span></span>](how-to-apply-gamma-correction-to-a-gradient.md)  
 <span data-ttu-id="d746b-120">说明如何对渐变画笔使用伽玛更正。</span><span class="sxs-lookup"><span data-stu-id="d746b-120">Explains how to use gamma correction with a gradient brush.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d746b-121">参考</span><span class="sxs-lookup"><span data-stu-id="d746b-121">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="d746b-122">包含此类的说明，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="d746b-122">Contains a description of this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="d746b-123">包含此类的说明，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="d746b-123">Contains a description of this class and has links to all of its members.</span></span>
