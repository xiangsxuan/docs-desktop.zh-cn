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
# <a name="how-to-create-a-path-gradient"></a>如何：创建路径渐变
<xref:System.Drawing.Drawing2D.PathGradientBrush>利用类，您可以自定义使用渐变颜色填充形状的方式。 例如，可以为路径中心指定一种颜色，并为路径边界指定另一种颜色。 还可以为路径边界上多个点的每个点指定单独的颜色。  
  
> [!NOTE]
> 在 GDI + 中，路径是由对象维护的一系列直线和曲线 <xref:System.Drawing.Drawing2D.GraphicsPath> 。 有关 GDI + 路径的详细信息，请参阅 [GDI + 中的图形路径](graphics-paths-in-gdi.md) 和 [构造和绘制路径](constructing-and-drawing-paths.md)。  

本文中的示例是从控件的事件处理程序调用的方法 <xref:System.Windows.Forms.Control.Paint> 。  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>使用路径渐变填充椭圆  
  
- 下面的示例使用路径渐变画笔填充椭圆。 中心颜色设置为蓝色，边界颜色设置为浅绿色。 下图显示了实心椭圆。  
  
     ![渐变路径填充椭圆。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     默认情况下，路径渐变画笔不会延伸到路径边界之外。 如果使用路径渐变画笔来填充超出路径边界的图形，则不会填充路径之外的屏幕区域。  
  
     下图显示了将以下代码中的调用更改为时所发生的情况 <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)` ：  
  
     ![超出路径边界的渐变路径已扩展。](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     前面的代码示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> e，后者是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
### <a name="to-specify-points-on-the-boundary"></a>指定边界上的点  
  
- 下面的示例从星形路径构造路径渐变画笔。 该代码设置 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> 属性，该属性将星形质心的颜色设置为红色。 然后，该代码设置 <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> 属性，以指定 (存储在数组中的 `colors` 各个点) 的各种颜色 `points` 。 最后一个代码语句用路径渐变画笔填充星形路径。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- 下面的示例在代码中绘制路径渐变，而不包含 <xref:System.Drawing.Drawing2D.GraphicsPath> 对象。 <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A>该示例中的特定构造函数接收一个点数组，但不需要 <xref:System.Drawing.Drawing2D.GraphicsPath> 对象。 另请注意， <xref:System.Drawing.Drawing2D.PathGradientBrush> 用于填充矩形，而不是路径。 该矩形大于用于定义画笔的闭合路径，因此画笔不绘制其中的某些矩形。 下图显示了矩形 (虚线) 以及由路径渐变画笔绘制的矩形部分：
  
     ![由路径渐变画笔绘制的渐变部分。](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>自定义路径渐变  
  
- 自定义路径渐变画笔的一种方法是设置其 <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> 属性。 焦点缩放指定位于主路径内的内部路径。 中心颜色在内部路径内的任何位置显示，而不是仅在中心点显示。  
  
     下面的示例基于椭圆形路径创建路径渐变画笔。 该代码将边界颜色设置为蓝色，将中心颜色设置为浅绿色，然后使用路径渐变画笔填充椭圆路径。  
  
     接下来，代码设置路径渐变画笔的聚焦缩放。 X 焦点刻度设置为0.3，而 y 焦点刻度设置为0.8。 此代码将调用 <xref:System.Drawing.Graphics.TranslateTransform%2A> 对象的方法， <xref:System.Drawing.Graphics> 以便随后调用以 <xref:System.Drawing.Graphics.FillPath%2A> 填充位于第一个椭圆右侧的椭圆。  
  
     若要查看焦点刻度的效果，请设想一个小椭圆与主椭圆共享其中心。 小型 (内部) 椭圆是指围绕其中心) 水平方向缩放的主要椭圆， (水平方向为0.3，垂直方向为0.8。 从外部椭圆的边界移到内部椭圆的边界时，颜色将从蓝色逐渐变为浅绿色。 从内部椭圆的边界移到共享中心时，颜色将保持浅绿色。  
  
     下图显示以下代码的输出。 左侧的椭圆仅在中心点处为浅绿色。 右侧的椭圆在内部路径内的任何位置都为浅绿色。  
  
 ![焦点刻度的渐变效果](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>自定义内插  
  
- 自定义路径渐变画笔的另一种方法是指定插值颜色数组和内插位置数组。  
  
     下面的示例基于三角形创建路径渐变画笔。 此代码将 <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> 路径渐变画笔的属性设置为指定一组插值色数组， (深绿色、浅绿色、蓝色) 和 (0，0.25，1) 的内插位置数组。 从三角形的边界向中心点移动时，颜色将从深绿色逐渐变为浅绿色，然后从浅绿色变为蓝色。 从深绿色到浅绿色的更改发生在从深绿色到蓝色的距离的25%。  
  
     下图显示了用自定义路径渐变画笔填充的三角形。  
  
     ![用自定义路径渐变画笔填充的三角形。](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>设置中心点  
  
- 默认情况下，路径渐变画笔的中心点位于用于构造画笔的路径的质心上。 您可以通过设置类的属性来更改中心点的位置 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> <xref:System.Drawing.Drawing2D.PathGradientBrush> 。  
  
     下面的示例基于椭圆创建路径渐变画笔。 椭圆的中心位于 (70，35) ，但路径渐变画笔的中心点设置为 (120，40) 。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     下图显示了轨迹渐变画笔的实心椭圆和中心点：  
  
     ![带有填充椭圆和中心点的渐变路径。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- 可以将路径渐变画笔的中心点设置为用于构造画笔的路径之外的位置。 下面的示例将替换调用以在 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> 前面的代码中设置属性。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     下图显示了此更改的输出：  
  
     ![中心点在路径外的渐变路径。](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     在上图中，椭圆最右侧的点不是纯蓝色的 (虽然它们非常接近) 。 渐变中的颜色的位置为，即填充达到 (145，35) 的点，其中颜色将为纯蓝色 (0，0，255) 。 但填充永远不会达到 (145，35) ，因为路径渐变画笔仅在其路径内绘制。  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它们需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- [使用渐变画笔填充形状](using-a-gradient-brush-to-fill-shapes.md)
