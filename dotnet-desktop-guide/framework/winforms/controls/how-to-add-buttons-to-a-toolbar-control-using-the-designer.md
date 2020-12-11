---
title: 如何：使用设计器向 ToolBar 控件添加按钮
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
ms.openlocfilehash: 4d7a49633599aabc96153e4793e50c1a4d6d092d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971280"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>如何：使用设计器向 ToolBar 控件添加按钮

> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。

控件的一个组成部分 <xref:System.Windows.Forms.ToolBar> 是您向其中添加的按钮。 可以使用这些命令来轻松访问菜单命令或，也可以将其放置在应用程序的用户界面的另一个区域中，向用户提供菜单结构中不存在的命令。

下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.ToolBar> 。 有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

### <a name="to-add-buttons-at-design-time"></a>在设计时添加按钮

1. 选择 <xref:System.Windows.Forms.ToolBar> 控件。

2. 在 "**属性**" 窗口中，单击 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 属性以将其选中， 然后单击 " ![ Visual) Studio 属性窗口中的省略号按钮" ( ... ) " (的省略号按钮， ](./media/visual-studio-ellipsis-button.png) 以打开" **ToolBarButton 集合编辑器**"。

3. 使用 " **添加** " 和 " **删除** " 按钮可在控件中添加和删除按钮 <xref:System.Windows.Forms.ToolBar> 。

4. 在编辑器右侧窗格中显示的 " **属性** " 窗口中，配置各个按钮的属性。 下表显示要考虑的一些重要属性。

    |属性|描述|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|设置要显示在下拉工具栏按钮中的菜单。 工具栏按钮的 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 属性必须设置为 <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton> 。 此属性采用类的实例 <xref:System.Windows.Forms.ContextMenu> 作为引用。|
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|设置是否部分推送切换样式的工具栏按钮。 工具栏按钮的 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 属性必须设置为 <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> 。|
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|设置切换样式的工具栏按钮当前是否处于按下状态。 工具栏按钮的 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 属性必须设置为 <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> 或 <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton> 。|
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|设置工具栏按钮的样式。 必须是枚举中的值之一 <xref:System.Windows.Forms.ToolBarButtonStyle> 。|
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|按钮显示的文本字符串。|
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|作为按钮的工具提示显示的文本。|

5. 单击 **"确定"** 以关闭对话框并创建指定的面板。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolBar>
- [如何：定义工具栏按钮的图标](how-to-define-an-icon-for-a-toolbar-button.md)
- [如何：触发工具栏按钮的菜单事件](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [ToolBar 控件概述](toolbar-control-overview-windows-forms.md)
- [ToolBar 控件](toolbar-control-windows-forms.md)
