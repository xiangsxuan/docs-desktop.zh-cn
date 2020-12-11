---
title: HelpProvider 组件概述
ms.date: 03/30/2017
f1_keywords:
- HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
ms.openlocfilehash: 74d35dfa39a605cb1e1e85cc3aeda834e1c60669
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971519"
---
# <a name="helpprovider-component-overview-windows-forms"></a>HelpProvider 组件概述（Windows 窗体）
Windows 窗体 [HelpProvider](helpprovider-component-windows-forms.md) 组件用于将 html Help 1.x 帮助文件 (与 Html 帮助讨论会一起生成的 .chm 文件或与您的 Windows 应用程序) 的 .htm 文件相关联。 可以通过多种方式提供帮助：  
  
- 为 Windows 窗体上的控件提供上下文相关帮助。  
  
- 在特定对话框或对话框中的特定控件上提供区分上下文的帮助。  
  
- 在特定区域中打开帮助文件，例如目录表、索引或搜索函数的主页。  
  
## <a name="using-the-help-provider"></a>使用帮助提供程序  
 将 <xref:System.Windows.Forms.HelpProvider> 组件添加到 Windows 窗体后，窗体上的其他控件就可以公开组件的 "帮助" 属性 <xref:System.Windows.Forms.HelpProvider> 。 这使您能够为 Windows 窗体上的控件提供帮助。 您可以使用属性将帮助文件与 <xref:System.Windows.Forms.HelpProvider> 组件相关联 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 。 您可以通过调用 <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> 并提供指定控件的枚举中的值来指定提供的帮助的类型 <xref:System.Windows.Forms.HelpNavigator> 。 可以通过调用方法为帮助提供关键字或主题 <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> 。  
  
 （可选）若要将特定帮助字符串与另一个控件关联，请使用 <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> 方法。 当控件具有焦点时，如果用户按 F1 键，则使用此方法与控件相关联的字符串将显示在弹出窗口中。  
  
 如果尚未 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 设置，则必须使用 <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> 提供帮助文本。 如果同时设置了 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 和帮助字符串，则基于的帮助 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 将优先。  
  
> [!NOTE]
> 在 <xref:System.Windows.Forms.Help.ShowHelp%2A> 控件的方法或属性中指定帮助文件的路径时，使用相对路径可能会遇到问题 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> <xref:System.Windows.Forms.HelpProvider> 。 因此，请务必使用绝对文件路径来指定帮助文件。  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体应用程序中的帮助系统](../advanced/help-systems-in-windows-forms-applications.md)
