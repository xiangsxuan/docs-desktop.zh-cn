---
title: 如何：使用设计器定义工具栏按钮的图标
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 49e93f12bebbf409e6b3a06634556b9103c85f44
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971215"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>如何：使用设计器定义工具栏按钮的图标

> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。

<xref:System.Windows.Forms.ToolBar> 按钮能够显示它们中的图标，用户可以轻松识别。 这是通过向组件添加图像 <xref:System.Windows.Forms.ImageList> 并将其与控件相关联实现的 <xref:System.Windows.Forms.ToolBar> 。

下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含 <xref:System.Windows.Forms.ToolBar> 控件和组件的窗体 <xref:System.Windows.Forms.ImageList> 。 有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>在设计时设置工具栏按钮的图标

1. 向组件添加映像 <xref:System.Windows.Forms.ImageList> 。 有关详细信息，请参阅 [如何：在设计器中添加或删除 ImageList 映像](how-to-add-or-remove-imagelist-images-with-the-designer.md)。

2. 选择 <xref:System.Windows.Forms.ToolBar> 窗体上的控件。

3. 在 " **属性** " 窗口中，将 <xref:System.Windows.Forms.ToolBar> 控件的 <xref:System.Windows.Forms.ToolBar.ImageList%2A> 属性设置为 <xref:System.Windows.Forms.ImageList> 组件。

4. 单击 <xref:System.Windows.Forms.ToolBar> 控件的 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 属性以将其选中，然后单击省略号按钮 (省略号 ![ 按钮 ( ...) 属性窗口 ) ， ](./media/visual-studio-ellipsis-button.png) 以打开 **ToolBarButton 集合编辑器**。

5. 使用 " **添加** " 按钮可将按钮添加到 <xref:System.Windows.Forms.ToolBar> 控件。

6. 在 **ToolBarButton 集合编辑器** 右侧窗格中显示的 "**属性**" 窗口中，将 <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> 每个工具栏按钮的属性设置为列表中的某个值，该列表是从添加到组件的图像中提取的 <xref:System.Windows.Forms.ImageList> 。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolBar>
- [如何：触发工具栏按钮的菜单事件](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [ToolBar 控件](toolbar-control-windows-forms.md)
- [ImageList 组件](imagelist-component-windows-forms.md)
