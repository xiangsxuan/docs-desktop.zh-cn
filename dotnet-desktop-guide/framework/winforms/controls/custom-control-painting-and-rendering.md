---
title: 自定义控件的绘制和呈现
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: 14abac5678bfffa3cdb61307fd3cb54681c82a99
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970152"
---
# <a name="custom-control-painting-and-rendering"></a>自定义控件的绘制和呈现
控件的自定义绘制是 .NET Framework 容易实现的众多复杂任务之一。 创作自定义控件时，有许多有关控件图形外观的选项。 如果要创作从继承的控件 `Control` ，则必须提供使控件呈现其图形表示形式的代码。 如果要通过从继承 `UserControl` ，或从某个 Windows 窗体控件继承来创建用户控件，则可以重写标准图形表示形式，并提供您自己的图形代码。 如果要为创作控件提供自定义呈现 `UserControl` ，则选项会变得更有限，但仍允许控件和应用程序的各种图形化可能性。  
  
## <a name="in-this-section"></a>本节内容  
 [呈现 Windows 窗体控件](rendering-a-windows-forms-control.md)  
 演示如何对显示控件的逻辑进行编程。  
  
 [用户描述的控件](user-drawn-controls.md)  
 概述编写和重写控件的呈现代码所涉及的步骤。  
  
 [构成控件](constituent-controls.md)  
 介绍如何实现用户控件和窗体中构成控件的自定义呈现代码。  
  
 [如何：使控件在运行时不可见](how-to-make-your-control-invisible-at-run-time.md)  
 演示如何使用 <xref:System.Windows.Forms.Control.Visible%2A> 属性隐藏和显示控件。  
  
 [如何：使控件拥有透明背景](how-to-give-your-control-a-transparent-background.md)  
 演示如何使用 <xref:System.Windows.Forms.Control.SetStyle%2A> 方法创建不透明、透明或部分透明的背景色。  
  
 [使用视觉样式呈现控件](rendering-controls-with-visual-styles.md)  
 演示如何在支持视觉样式的操作系统中使用视觉样式呈现控件。  
  
## <a name="reference"></a>参考  
 <xref:System.Windows.Forms.Control>  
 对此类进行描述，并提供指向其所有成员的链接。  
  
 <xref:System.Windows.Forms.UserControl>  
 对此类进行描述，并提供指向其所有成员的链接。  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 描述此方法。  
  
## <a name="related-sections"></a>相关章节  
 [如何：创建用于绘制的 Graphics 对象](../advanced/how-to-create-graphics-objects-for-drawing.md)  
 介绍 Visual Studio 中的 GDI + 图形功能，并提供指向详细信息的链接。  
  
 [各种自定义控件](varieties-of-custom-controls.md)  
 介绍可以创作的自定义控件类型。
