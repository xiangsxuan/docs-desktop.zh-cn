---
title: 鼠标捕获
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: 10583f074831b16dce3c713b4ac9a76c7005c9f5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972730"
---
# <a name="mouse-capture-in-windows-forms"></a>Windows 窗体中的鼠标捕获
*鼠标捕获* 指的是控件使用所有鼠标输入的命令。 当控件已捕获鼠标时，它将接收鼠标输入，无论指针是否在其边框内。  
  
## <a name="setting-mouse-capture"></a>设置鼠标捕获  
 在 Windows 窗体当用户在控件上按下鼠标按钮时，由控件捕获鼠标，而当用户释放鼠标按钮时，鼠标由控件释放。  
  
 <xref:System.Windows.Forms.Control.Capture%2A>类的属性 <xref:System.Windows.Forms.Control> 指定控件是否已捕获鼠标。 若要确定控件何时失去了鼠标捕获，请处理 <xref:System.Windows.Forms.Control.MouseCaptureChanged> 事件。  
  
 只有前景窗口才能捕获鼠标。 当后台窗口尝试捕获鼠标时，窗口仅接收鼠标指针位于窗口可见部分内时发生的鼠标事件的消息。 此外，即使前景窗口已捕获鼠标，用户仍可以单击其他窗口，使其成为前台。 捕获鼠标时，快捷键不起作用。  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体应用程序中的鼠标输入](mouse-input-in-a-windows-forms-application.md)
