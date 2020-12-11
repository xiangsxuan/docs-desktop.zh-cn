---
title: 如何：显示弹出帮助
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: a3b40f49119fcf7900f1f0c8b77c5d83fe81144c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970312"
---
# <a name="how-to-display-pop-up-help"></a>如何：显示弹出帮助

在 Windows 窗体上显示帮助的一种方法是通过 " **帮助** " 按钮，该按钮位于标题栏右侧，可通过属性进行访问 <xref:System.Windows.Forms.Form.HelpButton%2A> 。 此类型的“帮助”显示非常适用于对话框。 使用 <xref:System.Windows.Forms.Form.ShowDialog%2A> 方法适度显示的对话框在获取外部帮助系统时会遇到问题，因为必须先关闭模型对话框后才能切换到另一个窗口。 此外，使用 " **帮助** " 按钮时，标题栏中不显示 " **最小化** " 按钮或 " **最大化** " 按钮。 这是标准的对话框约定，而窗体通常具有 **最小化** 和 **最大化** 按钮。

您还可以使用该 <xref:System.Windows.Forms.HelpProvider> 组件将控件链接到帮助系统中的文件，即使您已经实现了弹出式帮助也是如此。 有关详细信息，请参阅 [在 Windows 应用程序中提供帮助](how-to-provide-help-in-a-windows-application.md)。

## <a name="display-pop-up-help"></a>显示弹出帮助

1. 在 Visual Studio 中，将 " [HelpProvider](../controls/helpprovider-component-windows-forms.md) " 组件从 "工具箱" 拖到窗体上。

   它将显示在 Windows 窗体设计器底部的任务栏中。

2. 在“属性”窗口，将 <xref:System.Windows.Forms.Form.HelpButton%2A> 属性设置为 `true`。 这将在窗体的标题栏右侧显示带问号的按钮。

3. 为了显示 <xref:System.Windows.Forms.Form.HelpButton%2A>，必须将窗体的 <xref:System.Windows.Forms.Form.MinimizeBox%2A> 和 <xref:System.Windows.Forms.Form.MaximizeBox%2A> 属性设置为 `false`，将 <xref:System.Windows.Forms.Form.ControlBox%2A> 属性设置为 `true` 以及将 <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 属性设置为下列值之一：<xref:System.Windows.Forms.FormBorderStyle.FixedSingle>、<xref:System.Windows.Forms.FormBorderStyle.Fixed3D>、<xref:System.Windows.Forms.FormBorderStyle.FixedDialog> 或 <xref:System.Windows.Forms.FormBorderStyle.Sizable>。

4. 选择想在你的窗体上显示帮助的控件，然后在“属性”窗口设置“帮助”字符串。 这是将在类似于 [工具提示](../controls/tooltip-component-windows-forms.md)的窗口中显示的文本字符串。

5. 按 F5 。

6. 在标题栏上按 " **帮助** " 按钮，然后单击要在其上设置帮助字符串的控件。

## <a name="see-also"></a>另请参阅

- [使用工具提示的控件帮助](control-help-using-tooltips.md)
- [在 Windows 窗体中集成用户帮助](integrating-user-help-in-windows-forms.md)
- [Windows 窗体](../index.yml)
