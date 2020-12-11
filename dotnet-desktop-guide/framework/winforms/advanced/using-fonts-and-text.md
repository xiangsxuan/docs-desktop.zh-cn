---
title: 使用字体和文本
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: 73a4af5fe7367e777fcb83af8c84c09be91e5b1e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971581"
---
# <a name="using-fonts-and-text"></a>使用字体和文本
GDI + 和 GDI 提供了几个用于在 Windows 窗体上绘制文本的类。 GDI + <xref:System.Drawing.Graphics> 类有几种方法可用于 <xref:System.Drawing.Graphics.DrawString%2A> 指定文本的各种功能，如位置、边框、字体和格式。 此外，还可以使用类提供的静态和方法来绘制文本和使用 GDI 来度量文本 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> `TextRenderer` 。 GDI 方法还允许您指定位置、字体和格式。 您可以选择用于文本呈现的 GDI 或 GDI +;但是，GDI 通常提供更好的性能和更准确的文本测量。 用于文本呈现的其他类包括 `FontFamily` 、、 `Font` <xref:System.Drawing.StringFormat> 和 `TextFormatFlags` 。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：构造字体系列和字体](how-to-construct-font-families-and-fonts.md)  
 演示如何创建 `Font` 和 `FontFamily` 对象。  
  
 [如何：在指定位置绘制文本](how-to-draw-text-at-a-specified-location.md)  
 介绍如何使用 GDI + 和 GDI 在特定位置绘制文本。  
  
 [如何：在矩形中绘制换行文本](how-to-draw-wrapped-text-in-a-rectangle.md)  
 介绍如何使用 GDI + 和 GDI 在矩形中绘制文本。  
  
 [如何：用 GDI 绘制文本](how-to-draw-text-with-gdi.md)  
 演示如何使用 GDI 来绘制文本。  
  
 [如何：对齐绘制的文本](how-to-align-drawn-text.md)  
 演示如何设置 GDI + 和 GDI 文本的格式。  
  
 [如何：创建垂直文本](how-to-create-vertical-text.md)  
 描述如何用 GDI + 绘制垂直对齐的文本。  
  
 [如何：在绘制的文本中设置制表位](how-to-set-tab-stops-in-drawn-text.md)  
 演示如何用 tab 键在 GDI + 中绘制文本。  
  
 [如何：枚举已安装的字体](how-to-enumerate-installed-fonts.md)  
 说明如何列出已安装字体的名称。  
  
 [如何：创建专用的字体集合](how-to-create-a-private-font-collection.md)  
 描述如何创建 <xref:System.Drawing.Text.PrivateFontCollection> 对象。  
  
 [如何：获取字体规格](how-to-obtain-font-metrics.md)  
 演示如何获取字体规格，如单元上升和下降。  
  
 [如何：对文本使用抗锯齿效果](how-to-use-antialiasing-with-text.md)  
 说明如何在绘制文本时使用抗锯齿。  
  
## <a name="reference"></a>参考  
 <xref:System.Drawing.Font>  
 描述此类，并包含指向其所有成员的链接。  
  
 <xref:System.Drawing.FontFamily>  
 描述此类，并包含指向其所有成员的链接。  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 描述此类，并包含指向其所有成员的链接。  
  
 <xref:System.Windows.Forms.TextRenderer>  
 描述此类，并包含指向其所有成员的链接。  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 描述此类，并包含指向其所有成员的链接。
