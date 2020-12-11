---
title: Windows 窗体应用中的用户输入
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
ms.openlocfilehash: 8e82276f14519c4ef54948744c93014232bdff52
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973353"
---
# <a name="user-input-in-a-windows-forms-application"></a>Windows 窗体应用程序中的用户输入
在 Windows 窗体中，将用户输入以 Windows 消息形式发送到应用程序。 一系列可重写的方法在应用程序、窗体和控件级别处理这些消息。 当这些方法接收鼠标和键盘消息时，它们会引发可处理的事件以获取有关鼠标或键盘输入的信息。 在许多情况下，Windows 窗体应用程序只需处理这些事件就能处理所有用户输入。 在其他情况下，应用程序可能需要重写处理消息的方法之一，以便在应用程序、窗体或控件接收特定消息之前截获该消息。  
  
## <a name="mouse-and-keyboard-events"></a>鼠标和键盘事件  
 所有 Windows 窗体控件将继承与鼠标和键盘输入相关的一组事件。 例如，控件可以处理 <xref:System.Windows.Forms.Control.KeyPress> 事件以确定所按下的键的字符代码，或控件可以处理 <xref:System.Windows.Forms.Control.MouseClick> 事件以确定鼠标单击的位置。 有关鼠标和键盘事件的详细信息，请参阅[在 Windows 窗体中](mouse-events-in-windows-forms.md)[使用键盘事件](using-keyboard-events.md)和鼠标事件。  
  
## <a name="methods-that-process-user-input-messages"></a>处理用户输入消息的方法  
 窗体和控件可以访问 <xref:System.Windows.Forms.IMessageFilter> 接口和一组可重写的方法，这些方法在消息队列中的不同点处理 Windows 消息。 这些方法都有一个 <xref:System.Windows.Forms.Message> 参数，用于封装 Windows 消息的低级详细信息。 您可以实现或重写这些方法来检查消息，然后使用消息或将消息传递到消息队列中的下一个使用者。 下表显示了处理 Windows 窗体中所有 Windows 消息的方法。  
  
|方法|说明|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|此方法会截获排队 (也称为在应用程序级别) Windows 消息已发布。|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|此方法在处理之前，在窗体和控件级别截获 Windows 消息。|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|此方法在窗体和控件级别处理 Windows 消息。|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|此方法在窗体和控件级别执行 Windows 消息的默认处理。 这会提供窗口的最小功能。|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|此方法在处理消息后，在窗体和控件级别截获这些消息。 <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage>若要调用此方法，必须设置样式位。|  
  
 键盘和鼠标消息也由一组特定于这些类型消息的可重写方法来处理。 有关详细信息，请参阅 [键盘输入的工作](how-keyboard-input-works.md) 原理以及 [鼠标输入在 Windows 窗体中的工作](how-mouse-input-works-in-windows-forms.md)方式。  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体中的用户输入](user-input-in-windows-forms.md)
- [Windows 窗体应用程序中的键盘输入](keyboard-input-in-a-windows-forms-application.md)
- [Windows 窗体应用程序中的鼠标输入](mouse-input-in-a-windows-forms-application.md)
