---
title: GDI+ 中的画笔和实心形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [Windows Forms], GDI+
- filled shapes [Windows Forms], GDI+
- shapes [Windows Forms], GDI+
- GDI+, brushes
- GDI+, filled shapes
- gradient brushes
- brushes [Windows Forms], gradient
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
ms.openlocfilehash: 45ef0b5920e43300e047d363149ea10a7833477b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970361"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a>GDI+ 中的画笔和实心形状
闭合形状（如矩形或椭圆）由轮廓和内部组成。 使用笔绘制轮廓，并使用画笔填充内部。 Gdi + 提供了多个用于填充闭合形状的内部的画笔类： <xref:System.Drawing.SolidBrush> 、 <xref:System.Drawing.Drawing2D.HatchBrush> 、、 <xref:System.Drawing.TextureBrush> <xref:System.Drawing.Drawing2D.LinearGradientBrush> 和 <xref:System.Drawing.Drawing2D.PathGradientBrush> 。 所有这些类都继承自 <xref:System.Drawing.Brush> 类。 下图显示了使用纯色画笔填充的矩形以及用阴影画笔填充的椭圆。  
  
 ![实心形状](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")  
  
## <a name="solid-brushes"></a>纯色画笔  
 若要填充闭合的形状，需要 <xref:System.Drawing.Graphics> 类和的实例 <xref:System.Drawing.Brush> 。 类的实例 <xref:System.Drawing.Graphics> 提供了方法（如 <xref:System.Drawing.Graphics.FillRectangle%2A> 和）， <xref:System.Drawing.Graphics.FillEllipse%2A> 以及 <xref:System.Drawing.Brush> 存储填充的特性，如颜色和模式。 <xref:System.Drawing.Brush>作为一个自变量传递给 fill 方法。 下面的代码示例演示如何使用纯红色填充椭圆。  
  
 [!code-csharp[LinesCurvesAndShapes#121](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
> 在前面的示例中，画笔的类型为 <xref:System.Drawing.SolidBrush> ，它继承自 <xref:System.Drawing.Brush> 。  
  
## <a name="hatch-brushes"></a>阴影画笔  
 使用阴影画笔填充形状时，需要指定前景色、背景色和阴影样式。 前景色是阴影的颜色。  
  
 [!code-csharp[LinesCurvesAndShapes#122](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 GDI + 提供的阴影样式超过50个;下图中显示的三个样式为 <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal> 、 <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal> 和 <xref:System.Drawing.Drawing2D.HatchStyle.Cross> 。  
  
 ![实心形状](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")  
  
## <a name="texture-brushes"></a>纹理画笔  
 使用纹理画笔，可以使用位图中存储的模式来填充形状。 例如，假设下面的图片存储在名为的磁盘文件中 `MyTexture.bmp` 。  
  
 ![实心形状](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")  
  
 下面的代码示例演示如何通过重复存储在中的图片来填充椭圆 `MyTexture.bmp` 。  
  
 [!code-csharp[LinesCurvesAndShapes#123](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 下图显示了实心椭圆。  
  
 ![实心形状](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")  
  
## <a name="gradient-brushes"></a>渐变画笔  
 GDI + 提供了两种类型的渐变画笔：线性和路径。 您可以使用线性渐变画笔来填充形状，颜色在水平、垂直或对角移动时逐渐变化。 下面的代码示例演示如何使用水平渐变画笔（当您从椭圆的左边缘向右边缘移动时，使用从蓝色到绿色的更改）填充椭圆。  
  
 [!code-csharp[LinesCurvesAndShapes#124](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 下图显示了实心椭圆。  
  
 ![实心形状](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")  
  
 可以将路径渐变画笔配置为在从形状的中心向边缘移动时更改颜色。  
  
 ![实心形状](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")  
  
 路径渐变画笔非常灵活。 在下图中，用于填充三角形的渐变画笔在顶点处逐步变化为三种不同颜色中的每一种颜色。  
  
 ![实心形状](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>
- <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [直线、曲线和图形](lines-curves-and-shapes.md)
- [如何：在 Windows 窗体上绘制实心矩形](how-to-draw-a-filled-rectangle-on-a-windows-form.md)
- [如何：在 Windows 窗体上绘制实心椭圆](how-to-draw-a-filled-ellipse-on-a-windows-form.md)
