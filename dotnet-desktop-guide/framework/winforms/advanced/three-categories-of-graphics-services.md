---
title: 图形服务的三个类别
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: fa7391ef0f7170ddb9d9d24aa5a1a03635bf46e0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970772"
---
# <a name="three-categories-of-graphics-services"></a>图形服务的三个类别
Windows 窗体中的图形产品分为以下三大类：  
  
- 二维 (二维) 向量图形  
  
- 映像  
  
- 版式  
  
## <a name="2d-vector-graphics"></a>2D 向量图形  
 二维向量图形（如直线、曲线和图形）是由坐标系统上的点集指定的基元。 例如，直线由其两个端点指定，矩形由一个点指定，该点提供其左上角的位置和一对数字，提供其宽度和高度。 简单路径由由直线连接的点数组指定。 贝塞尔样条是由四个控制点指定的复杂曲线。  
  
 GDI + 提供类和结构，它们存储有关基元本身的信息、存储有关如何绘制基元的信息的类以及实际执行绘图的类。 例如， <xref:System.Drawing.Rectangle> 结构存储一个矩形的位置和大小; <xref:System.Drawing.Pen> 类存储有关线条颜色、线条宽度和线条样式的信息; <xref:System.Drawing.Graphics> 类具有用于绘制线条、矩形、路径和其他图形的方法。 还有多个 <xref:System.Drawing.Brush> 类存储有关如何用颜色或模式填充闭合图形和路径的信息。  
  
 可以在图元文件中记录一系列图形命令的矢量图像。 GDI + 提供 <xref:System.Drawing.Imaging.Metafile> 用于记录、显示和保存图元文件的类。 使用 <xref:System.Drawing.Imaging.MetafileHeader> 和 <xref:System.Drawing.Imaging.MetaHeader> 类，可以检查存储在图元文件头中的数据。  
  
## <a name="imaging"></a>映像  
 某些类型的图片难以或不可能以矢量图形的技术来显示。 例如，工具栏按钮上的图片和显示为图标的图片难于指定为直线和曲线的集合。 更多的棒球体育场的高分辨率数字照片甚至更难使用矢量技术进行创建。 此类型的图像存储为位图，位图是表示屏幕上各个点的颜色的数字数组。 GDI + 提供了 <xref:System.Drawing.Bitmap> 用于显示、操作和保存位图的类。  
  
## <a name="typography"></a>版式  
 版式是指各种字体、大小和样式的文本显示。 GDI + 为此复杂任务提供广泛支持。 GDI + 中的新增功能之一是子像素抗锯齿，这为在 LCD 屏幕上呈现的文本提供更平滑的外观。  
  
 此外，Windows 窗体还提供了在其类中绘制具有 GDI 功能的文本的选项 <xref:System.Windows.Forms.TextRenderer> 。  
  
## <a name="see-also"></a>另请参阅

- [图形概述](graphics-overview-windows-forms.md)
- [关于 GDI+ 托管代码](about-gdi-managed-code.md)
- [使用托管图形类](using-managed-graphics-classes.md)
