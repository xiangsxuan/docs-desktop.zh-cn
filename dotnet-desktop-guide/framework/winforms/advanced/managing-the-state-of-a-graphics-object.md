---
title: 管理 Graphics 对象的状态
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: d1e7e6eac775ca779fb68605adcc9bc2b9915e49
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971377"
---
# <a name="managing-the-state-of-a-graphics-object"></a>管理 Graphics 对象的状态
<xref:System.Drawing.Graphics>类是 GDI + 的核心。 若要绘制任何内容，可以获取 <xref:System.Drawing.Graphics> 对象，设置其属性，并调用其方法 <xref:System.Drawing.Graphics.DrawLine%2A> 、 <xref:System.Drawing.Graphics.DrawImage%2A> 、和， <xref:System.Drawing.Graphics.DrawString%2A> 如) 。  
  
 下面的示例调用 <xref:System.Drawing.Graphics.DrawRectangle%2A> 对象的方法 <xref:System.Drawing.Graphics> 。 传递给方法的第一个参数 <xref:System.Drawing.Graphics.DrawRectangle%2A> 是 <xref:System.Drawing.Pen> 对象。  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a>图形状态  
 <xref:System.Drawing.Graphics>对象不仅仅提供绘图方法，如 <xref:System.Drawing.Graphics.DrawLine%2A> 和 <xref:System.Drawing.Graphics.DrawRectangle%2A> 。 <xref:System.Drawing.Graphics>对象还维持了图形状态，可分为以下几类：  
  
- 质量设置  
  
- 转换  
  
- 剪辑区域  
  
### <a name="quality-settings"></a>质量设置  
 <xref:System.Drawing.Graphics>对象具有多个属性，这些属性影响绘制的项的质量。 例如， <xref:System.Drawing.Graphics.TextRenderingHint%2A> 如果将任何) 应用于文本，可以将属性设置为指定消除锯齿的类型 (。 影响质量的其他属性包括 <xref:System.Drawing.Graphics.SmoothingMode%2A> 、 <xref:System.Drawing.Graphics.CompositingMode%2A> 、 <xref:System.Drawing.Graphics.CompositingQuality%2A> 和 <xref:System.Drawing.Graphics.InterpolationMode%2A> 。  
  
 下面的示例绘制两个椭圆，其中一个平滑模式设置为， <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> 一个设置为平滑模式 <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed> ：  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a>转换  
 <xref:System.Drawing.Graphics>对象维护 (世界和页面) 的两个转换，这些转换应用于该对象绘制的所有项 <xref:System.Drawing.Graphics> 。 任何仿射转换都可以存储在世界变换中。 仿射转换包括缩放、旋转、反射、倾斜和平移。 页面转换可用于缩放和更改单位 (例如，将像素改为英寸) 。 有关详细信息，请参阅 [坐标系统和转换](coordinate-systems-and-transformations.md)。  
  
 下面的示例设置对象的世界转换和页转换 <xref:System.Drawing.Graphics> 。 世界变换设置为30度旋转。 设置页转换，以便将传递给第二个的坐标 <xref:System.Drawing.Graphics.DrawEllipse%2A> 视为毫米而不是像素。 此代码对方法进行两次相同的调用 <xref:System.Drawing.Graphics.DrawEllipse%2A> 。 世界转换应用于第一次 <xref:System.Drawing.Graphics.DrawEllipse%2A> 调用， (世界和页面) 的转换都应用于第二次 <xref:System.Drawing.Graphics.DrawEllipse%2A> 调用。  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 下图显示了这两个椭圆。 请注意，30度的旋转大约是 (工作区左上角的坐标系统的原点) ，而不是椭圆的中心。 另请注意，对于第一个椭圆，笔宽度1表示1个像素，第二个椭圆为1毫米。  
  
 ![显示两个椭圆的插图：旋转和笔宽度。](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a>剪辑区域  
 <xref:System.Drawing.Graphics>对象维护一个适用于该对象绘制的所有项的剪辑区域 <xref:System.Drawing.Graphics> 。 可以通过调用方法设置剪辑区域 <xref:System.Drawing.Graphics.SetClip%2A> 。  
  
 下面的示例通过构造两个矩形的并集来创建一个加号区域。 该区域被指定为对象的剪辑区域 <xref:System.Drawing.Graphics> 。 然后，该代码将绘制两个限制为剪辑区域内部的行。  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 下图显示了剪切的行：  
  
 ![显示受限制的剪辑区域的关系图。](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [使用嵌套的 Graphics 容器](using-nested-graphics-containers.md)
