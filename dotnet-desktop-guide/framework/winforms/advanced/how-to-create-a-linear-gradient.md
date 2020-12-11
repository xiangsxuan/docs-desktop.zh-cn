---
title: 如何：创建线性渐变
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: e55d27b454579268658192ae56daa52e0b28bb83
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970653"
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="8a16b-102">如何：创建线性渐变</span><span class="sxs-lookup"><span data-stu-id="8a16b-102">How to: Create a Linear Gradient</span></span>
<span data-ttu-id="8a16b-103">GDI + 提供水平、垂直和对角线线性渐变。</span><span class="sxs-lookup"><span data-stu-id="8a16b-103">GDI+ provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="8a16b-104">默认情况下，线性渐变中的颜色会统一发生变化。</span><span class="sxs-lookup"><span data-stu-id="8a16b-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="8a16b-105">但是，您可以自定义线性渐变，以便以非均匀方式更改颜色。</span><span class="sxs-lookup"><span data-stu-id="8a16b-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  

> [!NOTE]
> <span data-ttu-id="8a16b-106">本文中的示例是从控件的事件处理程序调用的方法 <xref:System.Windows.Forms.Control.Paint> 。</span><span class="sxs-lookup"><span data-stu-id="8a16b-106">The examples in this article are methods that are called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  

<span data-ttu-id="8a16b-107">下面的示例使用水平线性渐变画笔填充线条、椭圆和矩形。</span><span class="sxs-lookup"><span data-stu-id="8a16b-107">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
<span data-ttu-id="8a16b-108"><xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A>构造函数接收四个参数：两个点和两种颜色。</span><span class="sxs-lookup"><span data-stu-id="8a16b-108">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="8a16b-109">第一个点 (0，10) 与第一种彩色 (红色) ，第二个点 (200，10) 与第二种颜色 (蓝色) 关联。</span><span class="sxs-lookup"><span data-stu-id="8a16b-109">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="8a16b-110">正如您所料，从 (0、10) 绘制到 (200，10) 将从红色逐渐变为蓝色。</span><span class="sxs-lookup"><span data-stu-id="8a16b-110">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="8a16b-111"> (0，10) 和 (200，10) 点的数十不重要。</span><span class="sxs-lookup"><span data-stu-id="8a16b-111">The 10s in the points (0, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="8a16b-112">重要的是，这两个点具有相同的第二个坐标：连接它们的线是水平的。</span><span class="sxs-lookup"><span data-stu-id="8a16b-112">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="8a16b-113">当水平坐标从0到200时，椭圆和矩形还会从红色逐渐变为蓝色。</span><span class="sxs-lookup"><span data-stu-id="8a16b-113">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="8a16b-114">下图显示了线条、椭圆和矩形。</span><span class="sxs-lookup"><span data-stu-id="8a16b-114">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="8a16b-115">请注意，当水平坐标超过200时，颜色渐变会重复自身。</span><span class="sxs-lookup"><span data-stu-id="8a16b-115">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 ![线条、椭圆和使用颜色渐变填充的矩形。](./media/how-to-create-a-linear-gradient/gradient-line-ellipse-rectangle.png)  
  
## <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="8a16b-117">使用水平线性渐变</span><span class="sxs-lookup"><span data-stu-id="8a16b-117">To use horizontal linear gradients</span></span>  
  
- <span data-ttu-id="8a16b-118">分别在第三个和第四个参数中传递不透明的蓝和蓝蓝。</span><span class="sxs-lookup"><span data-stu-id="8a16b-118">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="8a16b-119">在前面的示例中，当你从0的水平坐标移动到200的水平坐标时，颜色组件会线性变化。</span><span class="sxs-lookup"><span data-stu-id="8a16b-119">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="8a16b-120">例如，第一个坐标为介于0到200之间的点，其蓝色分量为介于0到255之间。</span><span class="sxs-lookup"><span data-stu-id="8a16b-120">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 <span data-ttu-id="8a16b-121">使用 GDI + 可以调整颜色不同于渐变边缘的方式。</span><span class="sxs-lookup"><span data-stu-id="8a16b-121">GDI+ allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="8a16b-122">假设要创建一个渐变画笔，使其根据下表从黑色更改为红色。</span><span class="sxs-lookup"><span data-stu-id="8a16b-122">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="8a16b-123">水平坐标</span><span class="sxs-lookup"><span data-stu-id="8a16b-123">Horizontal coordinate</span></span>|<span data-ttu-id="8a16b-124">RGB 组件</span><span class="sxs-lookup"><span data-stu-id="8a16b-124">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="8a16b-125">0</span><span class="sxs-lookup"><span data-stu-id="8a16b-125">0</span></span>|<span data-ttu-id="8a16b-126">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="8a16b-126">(0, 0, 0)</span></span>|  
|<span data-ttu-id="8a16b-127">40</span><span class="sxs-lookup"><span data-stu-id="8a16b-127">40</span></span>|<span data-ttu-id="8a16b-128">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="8a16b-128">(128, 0, 0)</span></span>|  
|<span data-ttu-id="8a16b-129">200</span><span class="sxs-lookup"><span data-stu-id="8a16b-129">200</span></span>|<span data-ttu-id="8a16b-130">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="8a16b-130">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="8a16b-131">请注意，当水平坐标只是从0到200的20% 时，红色部分为半度。</span><span class="sxs-lookup"><span data-stu-id="8a16b-131">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="8a16b-132">下面的示例将 <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> 属性设置为将三个相对强度与三个相对位置相关联。</span><span class="sxs-lookup"><span data-stu-id="8a16b-132">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> property to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="8a16b-133">如上表所示，0.5 的相对强度与0.2 的相对位置相关联。</span><span class="sxs-lookup"><span data-stu-id="8a16b-133">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="8a16b-134">代码使用渐变画笔填充椭圆和矩形。</span><span class="sxs-lookup"><span data-stu-id="8a16b-134">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="8a16b-135">下图显示了生成的椭圆形和矩形。</span><span class="sxs-lookup"><span data-stu-id="8a16b-135">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 ![用水平渐变填充的椭圆和矩形。](./media/how-to-create-a-linear-gradient/gradient-ellipse-rectangle.png)  

## <a name="to-customize-linear-gradients"></a><span data-ttu-id="8a16b-137">自定义线性渐变</span><span class="sxs-lookup"><span data-stu-id="8a16b-137">To customize linear gradients</span></span>  
  
- <span data-ttu-id="8a16b-138">将不透明的黑色和不透明红分别作为第三个和第四个参数传递。</span><span class="sxs-lookup"><span data-stu-id="8a16b-138">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="8a16b-139">以上示例中的渐变是水平的;也就是说，当沿任意水平线条移动时，颜色会逐渐变化。</span><span class="sxs-lookup"><span data-stu-id="8a16b-139">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="8a16b-140">还可以定义垂直渐变和对角渐变。</span><span class="sxs-lookup"><span data-stu-id="8a16b-140">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="8a16b-141">下面的示例将 (0，0) 的点和 (200，100) 传递到 <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> 构造函数。</span><span class="sxs-lookup"><span data-stu-id="8a16b-141">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="8a16b-142">蓝色与 (0，0) 相关联，绿色与 (200，100) 关联。</span><span class="sxs-lookup"><span data-stu-id="8a16b-142">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="8a16b-143">带有笔宽度 10) 的线条 (，并使用线性渐变画笔填充椭圆。</span><span class="sxs-lookup"><span data-stu-id="8a16b-143">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="8a16b-144">下图显示了线条和椭圆。</span><span class="sxs-lookup"><span data-stu-id="8a16b-144">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="8a16b-145">请注意，当沿与通过 (0，0) 和 (200，100) 的直线传递的任何直线移动时，椭圆中的颜色会逐渐变化。</span><span class="sxs-lookup"><span data-stu-id="8a16b-145">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 ![用对角颜色渐变填充的线条和椭圆。](./media/how-to-create-a-linear-gradient/gradient-line-ellipse.png)  
  
## <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="8a16b-147">创建对角方向线性渐变</span><span class="sxs-lookup"><span data-stu-id="8a16b-147">To create diagonal linear gradients</span></span>  
  
- <span data-ttu-id="8a16b-148">分别以第三个和第四个参数的形式传入不透明蓝色和不透明绿色。</span><span class="sxs-lookup"><span data-stu-id="8a16b-148">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="8a16b-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a16b-149">See also</span></span>

- [<span data-ttu-id="8a16b-150">使用渐变画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="8a16b-150">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
- [<span data-ttu-id="8a16b-151">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="8a16b-151">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
