---
title: 如何：创建路径渐变
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- path gradients [Windows Forms], creating
- gradients [Windows Forms], creating path
- graphics paths [Windows Forms], creating gradient
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
ms.openlocfilehash: cf4dc558c008fb8adfc327a6a894a428e985df03
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970644"
---
# <a name="how-to-create-a-path-gradient"></a><span data-ttu-id="92b2d-102">如何：创建路径渐变</span><span class="sxs-lookup"><span data-stu-id="92b2d-102">How to: Create a Path Gradient</span></span>
<span data-ttu-id="92b2d-103"><xref:System.Drawing.Drawing2D.PathGradientBrush>利用类，您可以自定义使用渐变颜色填充形状的方式。</span><span class="sxs-lookup"><span data-stu-id="92b2d-103">The <xref:System.Drawing.Drawing2D.PathGradientBrush> class allows you to customize the way you fill a shape with gradually changing colors.</span></span> <span data-ttu-id="92b2d-104">例如，可以为路径中心指定一种颜色，并为路径边界指定另一种颜色。</span><span class="sxs-lookup"><span data-stu-id="92b2d-104">For example, you can specify one color for the center of a path and another color for the boundary of a path.</span></span> <span data-ttu-id="92b2d-105">还可以为路径边界上多个点的每个点指定单独的颜色。</span><span class="sxs-lookup"><span data-stu-id="92b2d-105">You can also specify separate colors for each of several points along the boundary of a path.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="92b2d-106">在 GDI + 中，路径是由对象维护的一系列直线和曲线 <xref:System.Drawing.Drawing2D.GraphicsPath> 。</span><span class="sxs-lookup"><span data-stu-id="92b2d-106">In GDI+, a path is a sequence of lines and curves maintained by a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="92b2d-107">有关 GDI + 路径的详细信息，请参阅 [GDI + 中的图形路径](graphics-paths-in-gdi.md) 和 [构造和绘制路径](constructing-and-drawing-paths.md)。</span><span class="sxs-lookup"><span data-stu-id="92b2d-107">For more information about GDI+ paths, see [Graphics Paths in GDI+](graphics-paths-in-gdi.md) and [Constructing and Drawing Paths](constructing-and-drawing-paths.md).</span></span>  

<span data-ttu-id="92b2d-108">本文中的示例是从控件的事件处理程序调用的方法 <xref:System.Windows.Forms.Control.Paint> 。</span><span class="sxs-lookup"><span data-stu-id="92b2d-108">The examples in this article are methods that are called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a><span data-ttu-id="92b2d-109">使用路径渐变填充椭圆</span><span class="sxs-lookup"><span data-stu-id="92b2d-109">To fill an ellipse with a path gradient</span></span>  
  
- <span data-ttu-id="92b2d-110">下面的示例使用路径渐变画笔填充椭圆。</span><span class="sxs-lookup"><span data-stu-id="92b2d-110">The following example fills an ellipse with a path gradient brush.</span></span> <span data-ttu-id="92b2d-111">中心颜色设置为蓝色，边界颜色设置为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="92b2d-111">The center color is set to blue and the boundary color is set to aqua.</span></span> <span data-ttu-id="92b2d-112">下图显示了实心椭圆。</span><span class="sxs-lookup"><span data-stu-id="92b2d-112">The following illustration shows the filled ellipse.</span></span>  
  
     ![渐变路径填充椭圆。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     <span data-ttu-id="92b2d-114">默认情况下，路径渐变画笔不会延伸到路径边界之外。</span><span class="sxs-lookup"><span data-stu-id="92b2d-114">By default, a path gradient brush does not extend outside the boundary of the path.</span></span> <span data-ttu-id="92b2d-115">如果使用路径渐变画笔来填充超出路径边界的图形，则不会填充路径之外的屏幕区域。</span><span class="sxs-lookup"><span data-stu-id="92b2d-115">If you use the path gradient brush to fill a figure that extends beyond the boundary of the path, the area of the screen outside the path will not be filled.</span></span>  
  
     <span data-ttu-id="92b2d-116">下图显示了将以下代码中的调用更改为时所发生的情况 <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)` ：</span><span class="sxs-lookup"><span data-stu-id="92b2d-116">The following illustration shows what happens if you change the <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> call in the following code to `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`:</span></span>  
  
     ![超出路径边界的渐变路径已扩展。](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     <span data-ttu-id="92b2d-118">前面的代码示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> e，后者是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="92b2d-118">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> e, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
### <a name="to-specify-points-on-the-boundary"></a><span data-ttu-id="92b2d-119">指定边界上的点</span><span class="sxs-lookup"><span data-stu-id="92b2d-119">To specify points on the boundary</span></span>  
  
- <span data-ttu-id="92b2d-120">下面的示例从星形路径构造路径渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="92b2d-120">The following example constructs a path gradient brush from a star-shaped path.</span></span> <span data-ttu-id="92b2d-121">该代码设置 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> 属性，该属性将星形质心的颜色设置为红色。</span><span class="sxs-lookup"><span data-stu-id="92b2d-121">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> property, which sets the color at the centroid of the star to red.</span></span> <span data-ttu-id="92b2d-122">然后，该代码设置 <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> 属性，以指定 (存储在数组中的 `colors` 各个点) 的各种颜色 `points` 。</span><span class="sxs-lookup"><span data-stu-id="92b2d-122">Then the code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> property to specify various colors (stored in the `colors` array) at the individual points in the `points` array.</span></span> <span data-ttu-id="92b2d-123">最后一个代码语句用路径渐变画笔填充星形路径。</span><span class="sxs-lookup"><span data-stu-id="92b2d-123">The final code statement fills the star-shaped path with the path gradient brush.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- <span data-ttu-id="92b2d-124">下面的示例在代码中绘制路径渐变，而不包含 <xref:System.Drawing.Drawing2D.GraphicsPath> 对象。</span><span class="sxs-lookup"><span data-stu-id="92b2d-124">The following example draws a path gradient without a <xref:System.Drawing.Drawing2D.GraphicsPath> object in the code.</span></span> <span data-ttu-id="92b2d-125"><xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A>该示例中的特定构造函数接收一个点数组，但不需要 <xref:System.Drawing.Drawing2D.GraphicsPath> 对象。</span><span class="sxs-lookup"><span data-stu-id="92b2d-125">The particular <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> constructor in the example receives an array of points but does not require a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="92b2d-126">另请注意， <xref:System.Drawing.Drawing2D.PathGradientBrush> 用于填充矩形，而不是路径。</span><span class="sxs-lookup"><span data-stu-id="92b2d-126">Also, note that the <xref:System.Drawing.Drawing2D.PathGradientBrush> is used to fill a rectangle, not a path.</span></span> <span data-ttu-id="92b2d-127">该矩形大于用于定义画笔的闭合路径，因此画笔不绘制其中的某些矩形。</span><span class="sxs-lookup"><span data-stu-id="92b2d-127">The rectangle is larger than the closed path used to define the brush, so some of the rectangle is not painted by the brush.</span></span> <span data-ttu-id="92b2d-128">下图显示了矩形 (虚线) 以及由路径渐变画笔绘制的矩形部分：</span><span class="sxs-lookup"><span data-stu-id="92b2d-128">The following illustration shows the rectangle (dotted line) and the portion of the rectangle painted by the path gradient brush:</span></span>
  
     ![由路径渐变画笔绘制的渐变部分。](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a><span data-ttu-id="92b2d-130">自定义路径渐变</span><span class="sxs-lookup"><span data-stu-id="92b2d-130">To customize a path gradient</span></span>  
  
- <span data-ttu-id="92b2d-131">自定义路径渐变画笔的一种方法是设置其 <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="92b2d-131">One way to customize a path gradient brush is to set its <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> property.</span></span> <span data-ttu-id="92b2d-132">焦点缩放指定位于主路径内的内部路径。</span><span class="sxs-lookup"><span data-stu-id="92b2d-132">The focus scales specify an inner path that lies inside the main path.</span></span> <span data-ttu-id="92b2d-133">中心颜色在内部路径内的任何位置显示，而不是仅在中心点显示。</span><span class="sxs-lookup"><span data-stu-id="92b2d-133">The center color is displayed everywhere inside that inner path rather than only at the center point.</span></span>  
  
     <span data-ttu-id="92b2d-134">下面的示例基于椭圆形路径创建路径渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="92b2d-134">The following example creates a path gradient brush based on an elliptical path.</span></span> <span data-ttu-id="92b2d-135">该代码将边界颜色设置为蓝色，将中心颜色设置为浅绿色，然后使用路径渐变画笔填充椭圆路径。</span><span class="sxs-lookup"><span data-stu-id="92b2d-135">The code sets the boundary color to blue, sets the center color to aqua, and then uses the path gradient brush to fill the elliptical path.</span></span>  
  
     <span data-ttu-id="92b2d-136">接下来，代码设置路径渐变画笔的聚焦缩放。</span><span class="sxs-lookup"><span data-stu-id="92b2d-136">Next, the code sets the focus scales of the path gradient brush.</span></span> <span data-ttu-id="92b2d-137">X 焦点刻度设置为0.3，而 y 焦点刻度设置为0.8。</span><span class="sxs-lookup"><span data-stu-id="92b2d-137">The x focus scale is set to 0.3, and the y focus scale is set to 0.8.</span></span> <span data-ttu-id="92b2d-138">此代码将调用 <xref:System.Drawing.Graphics.TranslateTransform%2A> 对象的方法， <xref:System.Drawing.Graphics> 以便随后调用以 <xref:System.Drawing.Graphics.FillPath%2A> 填充位于第一个椭圆右侧的椭圆。</span><span class="sxs-lookup"><span data-stu-id="92b2d-138">The code calls the <xref:System.Drawing.Graphics.TranslateTransform%2A> method of a <xref:System.Drawing.Graphics> object so that the subsequent call to <xref:System.Drawing.Graphics.FillPath%2A> fills an ellipse that sits to the right of the first ellipse.</span></span>  
  
     <span data-ttu-id="92b2d-139">若要查看焦点刻度的效果，请设想一个小椭圆与主椭圆共享其中心。</span><span class="sxs-lookup"><span data-stu-id="92b2d-139">To see the effect of the focus scales, imagine a small ellipse that shares its center with the main ellipse.</span></span> <span data-ttu-id="92b2d-140">小型 (内部) 椭圆是指围绕其中心) 水平方向缩放的主要椭圆， (水平方向为0.3，垂直方向为0.8。</span><span class="sxs-lookup"><span data-stu-id="92b2d-140">The small (inner) ellipse is the main ellipse scaled (about its center) horizontally by a factor of 0.3 and vertically by a factor of 0.8.</span></span> <span data-ttu-id="92b2d-141">从外部椭圆的边界移到内部椭圆的边界时，颜色将从蓝色逐渐变为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="92b2d-141">As you move from the boundary of the outer ellipse to the boundary of the inner ellipse, the color changes gradually from blue to aqua.</span></span> <span data-ttu-id="92b2d-142">从内部椭圆的边界移到共享中心时，颜色将保持浅绿色。</span><span class="sxs-lookup"><span data-stu-id="92b2d-142">As you move from the boundary of the inner ellipse to the shared center, the color remains aqua.</span></span>  
  
     <span data-ttu-id="92b2d-143">下图显示以下代码的输出。</span><span class="sxs-lookup"><span data-stu-id="92b2d-143">The following illustration shows the output of the following code.</span></span> <span data-ttu-id="92b2d-144">左侧的椭圆仅在中心点处为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="92b2d-144">The ellipse on the left is aqua only at the center point.</span></span> <span data-ttu-id="92b2d-145">右侧的椭圆在内部路径内的任何位置都为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="92b2d-145">The ellipse on the right is aqua everywhere inside the inner path.</span></span>  
  
 ![焦点刻度的渐变效果](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a><span data-ttu-id="92b2d-147">自定义内插</span><span class="sxs-lookup"><span data-stu-id="92b2d-147">To customize with interpolation</span></span>  
  
- <span data-ttu-id="92b2d-148">自定义路径渐变画笔的另一种方法是指定插值颜色数组和内插位置数组。</span><span class="sxs-lookup"><span data-stu-id="92b2d-148">Another way to customize a path gradient brush is to specify an array of interpolation colors and an array of interpolation positions.</span></span>  
  
     <span data-ttu-id="92b2d-149">下面的示例基于三角形创建路径渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="92b2d-149">The following example creates a path gradient brush based on a triangle.</span></span> <span data-ttu-id="92b2d-150">此代码将 <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> 路径渐变画笔的属性设置为指定一组插值色数组， (深绿色、浅绿色、蓝色) 和 (0，0.25，1) 的内插位置数组。</span><span class="sxs-lookup"><span data-stu-id="92b2d-150">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> property of the path gradient brush to specify an array of interpolation colors (dark green, aqua, blue) and an array of interpolation positions (0, 0.25, 1).</span></span> <span data-ttu-id="92b2d-151">从三角形的边界向中心点移动时，颜色将从深绿色逐渐变为浅绿色，然后从浅绿色变为蓝色。</span><span class="sxs-lookup"><span data-stu-id="92b2d-151">As you move from the boundary of the triangle to the center point, the color changes gradually from dark green to aqua and then from aqua to blue.</span></span> <span data-ttu-id="92b2d-152">从深绿色到浅绿色的更改发生在从深绿色到蓝色的距离的25%。</span><span class="sxs-lookup"><span data-stu-id="92b2d-152">The change from dark green to aqua happens in 25 percent of the distance from dark green to blue.</span></span>  
  
     <span data-ttu-id="92b2d-153">下图显示了用自定义路径渐变画笔填充的三角形。</span><span class="sxs-lookup"><span data-stu-id="92b2d-153">The following illustration shows the triangle filled with the custom path gradient brush.</span></span>  
  
     ![用自定义路径渐变画笔填充的三角形。](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a><span data-ttu-id="92b2d-155">设置中心点</span><span class="sxs-lookup"><span data-stu-id="92b2d-155">To set the center point</span></span>  
  
- <span data-ttu-id="92b2d-156">默认情况下，路径渐变画笔的中心点位于用于构造画笔的路径的质心上。</span><span class="sxs-lookup"><span data-stu-id="92b2d-156">By default, the center point of a path gradient brush is at the centroid of the path used to construct the brush.</span></span> <span data-ttu-id="92b2d-157">您可以通过设置类的属性来更改中心点的位置 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> <xref:System.Drawing.Drawing2D.PathGradientBrush> 。</span><span class="sxs-lookup"><span data-stu-id="92b2d-157">You can change the location of the center point by setting the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property of the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
     <span data-ttu-id="92b2d-158">下面的示例基于椭圆创建路径渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="92b2d-158">The following example creates a path gradient brush based on an ellipse.</span></span> <span data-ttu-id="92b2d-159">椭圆的中心位于 (70，35) ，但路径渐变画笔的中心点设置为 (120，40) 。</span><span class="sxs-lookup"><span data-stu-id="92b2d-159">The center of the ellipse is at (70, 35), but the center point of the path gradient brush is set to (120, 40).</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     <span data-ttu-id="92b2d-160">下图显示了轨迹渐变画笔的实心椭圆和中心点：</span><span class="sxs-lookup"><span data-stu-id="92b2d-160">The following illustration shows the filled ellipse and the center point of the path gradient brush:</span></span>  
  
     ![带有填充椭圆和中心点的渐变路径。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- <span data-ttu-id="92b2d-162">可以将路径渐变画笔的中心点设置为用于构造画笔的路径之外的位置。</span><span class="sxs-lookup"><span data-stu-id="92b2d-162">You can set the center point of a path gradient brush to a location outside the path that was used to construct the brush.</span></span> <span data-ttu-id="92b2d-163">下面的示例将替换调用以在 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> 前面的代码中设置属性。</span><span class="sxs-lookup"><span data-stu-id="92b2d-163">The following example replaces the call to set the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property in the preceding code.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     <span data-ttu-id="92b2d-164">下图显示了此更改的输出：</span><span class="sxs-lookup"><span data-stu-id="92b2d-164">The following illustration shows the output with this change:</span></span>  
  
     ![中心点在路径外的渐变路径。](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     <span data-ttu-id="92b2d-166">在上图中，椭圆最右侧的点不是纯蓝色的 (虽然它们非常接近) 。</span><span class="sxs-lookup"><span data-stu-id="92b2d-166">In the preceding illustration, the points at the far right of the ellipse are not pure blue (although they are very close).</span></span> <span data-ttu-id="92b2d-167">渐变中的颜色的位置为，即填充达到 (145，35) 的点，其中颜色将为纯蓝色 (0，0，255) 。</span><span class="sxs-lookup"><span data-stu-id="92b2d-167">The colors in the gradient are positioned as if the fill reached the point (145, 35) where the color would be pure blue (0, 0, 255).</span></span> <span data-ttu-id="92b2d-168">但填充永远不会达到 (145，35) ，因为路径渐变画笔仅在其路径内绘制。</span><span class="sxs-lookup"><span data-stu-id="92b2d-168">But the fill never reaches (145, 35) because a path gradient brush paints only inside its path.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="92b2d-169">编译代码</span><span class="sxs-lookup"><span data-stu-id="92b2d-169">Compiling the Code</span></span>  
 <span data-ttu-id="92b2d-170">前面的示例旨在与 Windows 窗体一起使用，并且它们需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="92b2d-170">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92b2d-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92b2d-171">See also</span></span>

- [<span data-ttu-id="92b2d-172">使用渐变画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="92b2d-172">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
