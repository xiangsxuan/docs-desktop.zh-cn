---
title: 图形界面的结构
ms.date: 03/30/2017
helpviewer_keywords:
- GDI+, using managed interface
- graphics [Windows Forms], class structure
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
ms.openlocfilehash: d3b16249b6bae4a113661f5a3a47097046ba20f1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970786"
---
# <a name="structure-of-the-graphics-interface"></a>图形界面的结构
GDI + 的托管类接口包含大约60类、50枚举和8个结构。 <xref:System.Drawing.Graphics>类是 GDI + 功能的核心，它是实际绘制线条、曲线、图形、图像和文本的类。  
  
## <a name="important-classes"></a>重要的类  
 许多类与类一起使用 <xref:System.Drawing.Graphics> 。 例如， <xref:System.Drawing.Graphics.DrawLine%2A> 方法接收一个 <xref:System.Drawing.Pen> 对象，该对象包含要绘制的线条的属性 (颜色、宽度、虚线样式和类似) 。 <xref:System.Drawing.Graphics.FillRectangle%2A>方法可以接收指向对象的指针 <xref:System.Drawing.Drawing2D.LinearGradientBrush> ，该对象与 <xref:System.Drawing.Graphics> 对象配合使用来填充渐变颜色的矩形。 <xref:System.Drawing.Font> 和 <xref:System.Drawing.StringFormat> 对象会影响 <xref:System.Drawing.Graphics> 对象绘制文本的方式。 <xref:System.Drawing.Drawing2D.Matrix>对象存储和操作对象的世界变换 <xref:System.Drawing.Graphics> ，该对象用于旋转、缩放和翻转图像。  
  
 GDI + 提供几个结构 (例如，、 <xref:System.Drawing.Rectangle> <xref:System.Drawing.Point> 和 <xref:System.Drawing.Size>) 用于组织图形数据。 此外，某些类主要用作结构化数据类型。 例如， <xref:System.Drawing.Imaging.BitmapData> 类是类的帮助程序 <xref:System.Drawing.Bitmap> ， <xref:System.Drawing.Drawing2D.PathData> 类是类的帮助器 <xref:System.Drawing.Drawing2D.GraphicsPath> 。  
  
 GDI + 定义多个枚举，这是相关常量的集合。 例如， <xref:System.Drawing.Drawing2D.LineJoin> 枚举包含元素 <xref:System.Drawing.Drawing2D.LineJoin.Bevel> 、 <xref:System.Drawing.Drawing2D.LineJoin.Miter> 和 <xref:System.Drawing.Drawing2D.LineJoin.Round> ，它们指定可用于联接两行的样式。  
  
## <a name="see-also"></a>另请参阅

- [图形概述](graphics-overview-windows-forms.md)
- [关于 GDI+ 托管代码](about-gdi-managed-code.md)
- [使用托管图形类](using-managed-graphics-classes.md)
