---
title: ToolBar 控件概述
ms.date: 03/30/2017
f1_keywords:
- ToolBar
helpviewer_keywords:
- toolbars [Windows Forms], about toolbars
- ToolBar control [Windows Forms], about ToolBar controls
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
ms.openlocfilehash: f364e052258703331496f8103b48953a90aa3a9b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971742"
---
# <a name="toolbar-control-overview-windows-forms"></a>ToolBar 控件概述（Windows 窗体）
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。  
  
 Windows 窗体 <xref:System.Windows.Forms.ToolBar> 控件在窗体上用作可显示下拉菜单的行的控件条以及可激活命令的位图按钮。 因此，单击工具栏按钮相当于选择菜单命令。 可将按钮配置为以普通按钮、下拉菜单或分隔符等形式显示和表现。 通常，工具栏包含对应于应用程序菜单结构中的项的按钮和菜单，提供对应用程序最常用的函数和命令的快速访问。  
  
## <a name="working-with-the-toolbar-control"></a>使用 ToolBar 控件  
 <xref:System.Windows.Forms.ToolBar>控件通常沿其父窗口的顶部 "停靠"，但也可停靠到窗口的任何一侧。 用户将鼠标指针指向工具栏按钮时，工具栏可以显示工具提示。 工具提示是一个小型弹出式窗口，用以简述按钮或菜单的用途。 若要显示工具提示， <xref:System.Windows.Forms.ToolBar.ShowToolTips%2A> 属性必须设置为 `true` 。  
  
> [!NOTE]
> 某些应用程序具有与工具栏非常类似的控件，这些控件可“浮动”在应用程序窗口之上并可重新定位。 Windows 窗体 ToolBar 控件不能执行这些操作。  
  
 当 <xref:System.Windows.Forms.ToolBar.Appearance%2A> 属性设置为时 <xref:System.Windows.Forms.ToolBarAppearance> ，工具栏按钮将显示为凸起和三维。 您可以将 <xref:System.Windows.Forms.ToolBar.Appearance%2A> 工具栏的属性设置为， <xref:System.Windows.Forms.ToolBarAppearance> 以使工具栏及其按钮具有平面外观。 鼠标指针移动到平面按钮时，该按钮的外观变为三维形状。 可使用分隔符将工具栏按钮划分成多个逻辑组。 分隔符是属性设置为的工具栏按钮 <xref:System.Windows.Forms.ToolBarButton.Style%2A> <xref:System.Windows.Forms.ToolBarButtonStyle> 。 它在工具栏上显示为空白。 工具栏以平面方式显示时，按钮分隔符在按钮之间显示为直线而不是空白。  
  
 <xref:System.Windows.Forms.ToolBar>控件允许您通过将 <xref:System.Windows.Forms.Button> 对象添加到集合来创建工具栏 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 。 您可以使用集合编辑器向控件添加按钮 <xref:System.Windows.Forms.ToolBar> ; 每个对象都 <xref:System.Windows.Forms.Button> 应分配文本或图像，不过您可以同时分配这两个对象。 图像由关联的 [ImageList](imagelist-component-windows-forms.md) 组件提供。 在运行时，可以 <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection> 使用和方法从中添加或删除按钮 <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A> <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A> 。 若要对的按钮进行编程 <xref:System.Windows.Forms.ToolBar> ，请使用类的属性将代码添加到 <xref:System.Windows.Forms.ToolBar.ButtonClick> 的事件 <xref:System.Windows.Forms.ToolBar> ， <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> 以确定单击了哪个按钮。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolBar>
- [ToolBar 控件](toolbar-control-windows-forms.md)
- [如何：向 ToolBar 控件添加按钮](how-to-add-buttons-to-a-toolbar-control.md)
- [如何：定义工具栏按钮的图标](how-to-define-an-icon-for-a-toolbar-button.md)
- [如何：触发工具栏按钮的菜单事件](how-to-trigger-menu-events-for-toolbar-buttons.md)
