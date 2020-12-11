---
title: 帮助系统
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
ms.openlocfilehash: 07e13ff35de49ae3ec7591544b1c9353ba4bb378
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970806"
---
# <a name="help-systems-in-windows-forms-applications"></a>Windows 窗体应用程序中的帮助系统
作为应用程序开发人员，作为应用程序开发人员，最重要的礼节之一就是提供有帮助的帮助系统。 在这种情况下，它们会在出现混乱或 disoriented 的情况下打开。 使用 [HelpProvider 组件](../controls/helpprovider-component-windows-forms.md)，可以轻松地在基于 Windows 的应用程序中提供帮助系统。  
  
## <a name="different-types-of-help"></a>不同类型的帮助  
 Windows 窗体 <xref:System.Windows.Forms.HelpProvider> 组件用于将基于 Windows 的应用程序与 HTML Help 1.x 帮助文件（HTML Help Workshop 生成的 .chm 文件，或 .htm 文件）关联。 <xref:System.Windows.Forms.HelpProvider>组件可用于为 Windows 窗体或特定控件上的控件提供区分上下文的帮助。 此外，该 <xref:System.Windows.Forms.HelpProvider> 组件还可以在特定区域（如目录的主页、索引或搜索功能）打开帮助文件。 有关组件的常规信息 <xref:System.Windows.Forms.HelpProvider> ，请参阅 [HelpProvider 组件概述](../controls/helpprovider-component-overview-windows-forms.md)。 有关如何使用 <xref:System.Windows.Forms.HelpProvider> 组件显示 Windows 窗体上的弹出帮助的信息，请参阅 [如何：显示弹出帮助](how-to-display-pop-up-help.md)。 有关使用 <xref:System.Windows.Forms.ToolTip> 组件显示特定于控件的帮助的信息，请参阅 [使用工具提示的控件帮助](control-help-using-tooltips.md)。  
  
 可以通过 HTML 帮助讨论会生成 HTML Help 1.x 文件。 有关 HTML 帮助的详细信息，请参阅 MSDN 中的 "HTML 帮助讨论会" 或其他 "HTML 帮助" 主题。  
  
## <a name="see-also"></a>另请参阅

- [在 Windows 窗体中集成用户帮助](integrating-user-help-in-windows-forms.md)
- [HelpProvider 组件](../controls/helpprovider-component-windows-forms.md)
- [ToolTip 组件](../controls/tooltip-component-windows-forms.md)
- [Windows 窗体概述](../windows-forms-overview.md)
- [Windows 窗体](../index.yml)
