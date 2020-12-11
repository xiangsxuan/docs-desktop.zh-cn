---
title: 如何：在 Windows 窗体上创建 Windows 资源管理器样式的界面
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 34a5cd735c350688d9e83003806668e213932c85
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972057"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a>如何：在 Windows 窗体上创建 Windows 资源管理器样式的界面
Windows 资源管理器是应用程序的一个常见用户界面选项，因为它已做好了准备。

 Windows 资源管理器本质上是 <xref:System.Windows.Forms.TreeView> 控件和 <xref:System.Windows.Forms.ListView> 控件在单独的面板上。 可以通过拆分器调整面板的大小。 这种控件排列对于显示和浏览信息非常有效。

 以下步骤演示如何在类似 Windows 资源管理器的窗体中排列控件。 它们不显示如何添加 Windows 资源管理器应用程序的文件浏览功能。

## <a name="to-create-a-windows-explorer-style-windows-form"></a>创建 Windows 资源管理器样式的 Windows 窗体

1. 创建新的 Windows 应用程序项目 (**文件**"  >  **新建**  >  **项目**" "  >  **Visual c #** " 或 " **Visual Basic**  >  **经典桌面**  >  **Windows 窗体应用程序**) "。

2. 从 **工具箱**：

    1. 将 <xref:System.Windows.Forms.SplitContainer> 控件拖到窗体上。

    2. 将 <xref:System.Windows.Forms.TreeView> 控件拖入 **SplitterPanel1** (<xref:System.Windows.Forms.SplitContainer> 标记为 **Panel1**) 的控件的面板。

    3. 将 <xref:System.Windows.Forms.ListView> 控件拖入 **SplitterPanel2** (<xref:System.Windows.Forms.SplitContainer> 标记为 **Panel2**) 的控件的面板。

3. 按住 CTRL 键并依次单击所有三个控件以将其选中。 选择 <xref:System.Windows.Forms.SplitContainer> 控件时，请单击拆分条，而不是面板。

    > [!NOTE]
    > 不要使用 "**编辑**" 菜单上的 "**全选**" 命令。 如果这样做，下一步中所需的属性将不会显示在 " **属性** " 窗口中。

4. 在“属性”  窗口中，将 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>。

5. 按 F5 运行该应用程序。

     该窗体显示两个部分的用户界面，与 Windows 资源管理器类似。

    > [!NOTE]
    > 拖动拆分器时，面板会调整其自身大小。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.SplitContainer>
- [如何：使用 Windows 窗体创建多窗格用户界面](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [如何：定义拆分窗口中的大小调整和定位行为](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [如何：水平拆分窗口](how-to-split-a-window-horizontally.md)
- [SplitContainer 控件](splitcontainer-control-windows-forms.md)
