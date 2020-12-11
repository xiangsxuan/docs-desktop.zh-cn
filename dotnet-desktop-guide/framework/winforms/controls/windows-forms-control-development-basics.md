---
title: 控件开发基础知识
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
ms.openlocfilehash: fab0a76e2f9fdb7e2f89e9d6a10dd9c522a6d8e1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973045"
---
# <a name="windows-forms-control-development-basics"></a>Windows 窗体控件开发基础知识
Windows 窗体控件是直接或间接从派生的类 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。 以下列表描述了用于开发 Windows 窗体控件的常见方案：  
  
- 组合现有控件以创作复合控件。  
  
     复合控件封装可作为控件重复使用的用户界面。 复合控件的一个示例是包含一个文本框和一个 "重置" 按钮的控件。 可视化设计器为创建复合控件提供了丰富的支持。 若要创作复合控件，请从派生 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType> 。 基类 <xref:System.Windows.Forms.UserControl> 为子控件提供了键盘路由，并使子控件可以作为组工作。 有关详细信息，请参阅[开发复合 Windows 窗体控件](developing-a-composite-windows-forms-control.md)。  
  
- 扩展现有控件以便对其进行自定义或将其添加到其功能。  
  
     不能更改其颜色的按钮以及具有其他属性（用于跟踪单击次数）的按钮是扩展控件的示例。 您可以通过从该控件派生并重写或添加属性、方法和事件来自定义任何 Windows 窗体控件。  
  
- 创作不会合并或扩展现有控件的控件。  
  
     在此方案中，从基类派生控件 <xref:System.Windows.Forms.Control> 。 你可以添加，还可以重写基类的属性、方法和事件。 若要开始操作，请参阅 [如何：开发简单的 Windows 窗体控件](how-to-develop-a-simple-windows-forms-control.md)。  
  
 Windows 窗体控件的基类 <xref:System.Windows.Forms.Control> 提供了在基于 Windows 的客户端应用程序中进行可视化显示所需的管道。 <xref:System.Windows.Forms.Control> 提供窗口句柄，处理消息路由，并提供鼠标和键盘事件以及许多其他用户界面事件。 它提供高级布局，并具有特定于可视显示的属性，例如、、、 <xref:System.Windows.Forms.Control.ForeColor%2A> <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Control.Height%2A> <xref:System.Windows.Forms.Control.Width%2A> 等。 此外，它还提供与 ActiveX 控件的安全、线程支持和互操作性。 由于基类提供了大量基础结构，因此使开发自己的 Windows 窗体控件变得相对简单。  
  
## <a name="see-also"></a>另请参阅

- [如何：开发简单的 Windows 窗体控件](how-to-develop-a-simple-windows-forms-control.md)
- [开发复合 Windows 窗体控件](developing-a-composite-windows-forms-control.md)
- [如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)
- [各种自定义控件](varieties-of-custom-controls.md)
