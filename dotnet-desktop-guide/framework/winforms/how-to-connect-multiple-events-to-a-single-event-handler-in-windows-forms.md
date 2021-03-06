---
title: 如何：将多个事件连接到单个事件处理程序
description: '了解如何通过使用 c # 中属性窗口的事件视图，在 Windows 窗体中将多个事件连接到单个事件处理程序。'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
ms.openlocfilehash: cca85c223b46d9a82dbc3e34e3377fb83c075959
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970267"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a>如何：将多个事件连接到 Windows 窗体中的单个事件处理程序
在应用程序设计中，你可能会发现需要对多个事件使用单个事件处理程序，或者有多个事件执行相同的过程。 例如，如果菜单命令与窗体上的按钮公开相同的功能，则它通常是一种功能强大的时间保护程序。 为此，可以使用 c # 中的属性窗口的 "事件" 视图，或者使用 " `Handles` Visual Basic 代码编辑器" 中的 "关键字" 和 " **类名** " 和 " **方法名称** " 下拉框。  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a>在 Visual Basic 中将多个事件连接到单个事件处理程序  
  
1. 右键单击窗体，然后选择 " **查看代码**"。  
  
2. 从 " **类名称** " 下拉框中，选择一个要具有事件处理程序句柄的控件。  
  
3. 从 " **方法名称** " 下拉框中，选择希望事件处理程序处理的事件之一。  
  
4. 代码编辑器将插入相应的事件处理程序，并将插入点定位到方法中。 在下面的示例中，它是 <xref:System.Windows.Forms.Control.Click> 控件的事件 <xref:System.Windows.Forms.Button> 。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. 向子句附加要处理的其他事件 `Handles` 。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. 将相应代码添加到事件处理程序。  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a>将多个事件连接到 C 中的单个事件处理程序\#
  
1. 选择要将事件处理程序连接到的控件。  
  
2. 在属性窗口中，单击 " **事件** " 按钮 (![事件 "按钮](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")) "。  
  
3. 单击要处理的事件的名称。  
  
4. 在 "事件名称" 旁边的 "值" 部分中，单击下拉按钮以显示与要处理的事件的方法签名匹配的现有事件处理程序的列表。  
  
5. 从列表中选择相应的事件处理程序。  
  
     代码将添加到窗体中，以将事件绑定到现有的事件处理程序。  
  
## <a name="see-also"></a>另请参阅

- [在 Windows 窗体中创建事件处理程序](creating-event-handlers-in-windows-forms.md)
- [事件处理程序概述](event-handlers-overview-windows-forms.md)
