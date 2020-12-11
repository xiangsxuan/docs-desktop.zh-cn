---
title: 演练：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
ms.openlocfilehash: d71534bed0af142ff71ba9a0c01207b2c72a6d6a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972866"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>演练：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体

<xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间支持多文档界面 (MDI) 应用程序，而 <xref:System.Windows.Forms.MenuStrip> 控件支持菜单合并。 MDI 窗体还可支持 <xref:System.Windows.Forms.ToolStrip> 控件。

本演练演示如何使用 <xref:System.Windows.Forms.ToolStripPanel> 带有 MDI 窗体的控件。 此窗体还支持菜单与子菜单合并。 此演练演示了下列任务：

- 创建 Windows 窗体项目。

- 创建窗体的主菜单。 菜单的实际名称将有所不同。

- 将 <xref:System.Windows.Forms.ToolStripPanel> 控件添加到 " **工具箱**"。

- 创建子窗体。

- <xref:System.Windows.Forms.ToolStripPanel>按 z 顺序排列控件。

完成后，将拥有一个支持菜单合并和可移动控件的 MDI 窗体 <xref:System.Windows.Forms.ToolStrip> 。

若要将本主题中的代码复制为单个列表，请参阅 [如何：创建具有菜单合并和 ToolStrip 控件的 MDI 窗体](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。

## <a name="prerequisites"></a>先决条件

需要 Visual Studio 才能完成此演练。

## <a name="create-the-project"></a>创建项目

1. 在 Visual Studio 中，创建名为 **system.windows.forms.toolstrip.mdiform** (文件 "   >  **新建**  >  **项目**" "  >  **Visual c #** " 或 " **Visual Basic**  >  **经典桌面**  >  **Windows 窗体应用程序**) " 的 Windows 应用程序项目

2. 在 Windows 窗体设计器中，选择窗体。

3. 在属性窗口中，将的值设置 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 为 `true` 。

## <a name="create-the-main-menu"></a>创建主菜单

父 MDI 窗体包含主菜单。 主菜单中有一个名为 **Window** 的菜单项。 通过 " **窗口** " 菜单项，可以创建子窗体。 子窗体中的菜单项将合并到主菜单。

1. 从 " **工具箱**" 中，将 <xref:System.Windows.Forms.MenuStrip> 控件拖到窗体上。

2. 将添加 <xref:System.Windows.Forms.ToolStripMenuItem> 到 <xref:System.Windows.Forms.MenuStrip> 控件并将其命名为 " **窗口**"。

3. 选择 <xref:System.Windows.Forms.MenuStrip> 控件。

4. 在属性窗口中，将属性的值设置 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 为 `ToolStripMenuItem1` 。

5. 将子项添加到 " **窗口** " 菜单项，然后将子项命名为 " **新**"。

6. 在“属性”窗口中，单击“事件”。

7. 双击该 <xref:System.Windows.Forms.ToolStripItem.Click> 事件。

     Windows 窗体设计器生成事件的事件处理程序 <xref:System.Windows.Forms.ToolStripItem.Click> 。

8. 将以下代码插入到事件处理程序中。

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a>将 ToolStripPanel 控件添加到工具箱

使用 <xref:System.Windows.Forms.MenuStrip> 带有 MDI 窗体的控件时，必须具有 <xref:System.Windows.Forms.ToolStripPanel> 控件。 必须将控件添加 <xref:System.Windows.Forms.ToolStripPanel> 到 " **工具箱** "，才能在 WINDOWS 窗体设计器中生成 MDI 窗体。

1. 打开 " **工具箱**"，然后单击 " **所有 Windows 窗体** " 选项卡以显示可用的 Windows 窗体控件。

2. 右键单击以打开快捷菜单，然后选择 " **选择项**"。

3. 在 " **选择工具箱项** " 对话框中，在 " **名称** " 列中向下滚动，直到找到 **ToolStripPanel**。

4. 选中 " **ToolStripPanel**" 复选框，然后单击 **"确定"**。

     <xref:System.Windows.Forms.ToolStripPanel>控件将出现在 **工具箱** 中。

## <a name="create-a-child-form"></a>创建子窗体

在此过程中，您将定义一个具有自己的控件的单独的子窗体类 <xref:System.Windows.Forms.MenuStrip> 。 此窗体的菜单项与父窗体的菜单项合并。

1. 向项目中添加一个名为的新窗体 `ChildForm` 。

     有关详细信息，请参阅 [如何：将 Windows 窗体添加到项目](/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100))。

2. 从 " **工具箱**" 中，将 <xref:System.Windows.Forms.MenuStrip> 控件拖动到子窗体上。

3. 单击 <xref:System.Windows.Forms.MenuStrip> 控件的设计器操作标志符号 (![ 小型黑色箭头 ](./media/designer-actions-glyph.gif)) ，然后选择 " **编辑项**"。

4. 在 " **项集合编辑器** " 对话框中，将一个 <xref:System.Windows.Forms.ToolStripMenuItem> 名为 **ChildMenuItem** 的新添加到子菜单中。

     有关详细信息，请参阅 [ToolStrip 项集合编辑器](/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100))。

## <a name="test-the-form"></a>测试窗体

1. 按 **F5** 编译并运行您的窗体。

2. 单击 " **窗口** " 菜单项以打开菜单，然后单击 " **新建**"。

     在窗体的 MDI 工作区中创建一个新的子窗体。 子窗体的菜单与主菜单合并在一起。

3. 关闭子窗体。

     子窗体的菜单将从主菜单中删除。

4. 单击 " **新建** " 多次。

     子窗体自动列在 " **窗口** " 菜单项下，因为 <xref:System.Windows.Forms.MenuStrip> 分配了控件的 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 属性。

## <a name="add-toolstrip-support"></a>添加 ToolStrip 支持

在此过程中，您将向 <xref:System.Windows.Forms.ToolStrip> MDI 父窗体添加四个控件。 每个 <xref:System.Windows.Forms.ToolStrip> 控件都将添加 <xref:System.Windows.Forms.ToolStripPanel> 到控件内，该控件停靠到窗体的边缘。

1. 从 " **工具箱**" 中，将 <xref:System.Windows.Forms.ToolStripPanel> 控件拖到窗体上。

2. <xref:System.Windows.Forms.ToolStripPanel>选中控件后，双击 <xref:System.Windows.Forms.ToolStrip> **工具箱** 中的控件。

     <xref:System.Windows.Forms.ToolStrip>在控件中创建控件 <xref:System.Windows.Forms.ToolStripPanel> 。

3. 选择 <xref:System.Windows.Forms.ToolStripPanel> 控件。

4. 在属性窗口中，将控件的属性值更改 <xref:System.Windows.Forms.Control.Dock%2A> 为 <xref:System.Windows.Forms.DockStyle.Left> 。

     <xref:System.Windows.Forms.ToolStripPanel>控件停靠在主菜单下的窗体的左侧。 根据控件调整 MDI 客户端区域大小 <xref:System.Windows.Forms.ToolStripPanel> 。

5. 重复步骤1到4。

     将新 <xref:System.Windows.Forms.ToolStripPanel> 控件停靠到窗体的顶部。

     <xref:System.Windows.Forms.ToolStripPanel>控件停靠在主菜单下，而位于第一个控件的右侧 <xref:System.Windows.Forms.ToolStripPanel> 。 此步骤说明了正确定位控件时 z 顺序的重要性 <xref:System.Windows.Forms.ToolStripPanel> 。

6. 对两个以上的控件重复步骤1到 4 <xref:System.Windows.Forms.ToolStripPanel> 。

     将新 <xref:System.Windows.Forms.ToolStripPanel> 控件停靠到窗体的右侧和底部。

## <a name="arrange-toolstrippanel-controls-by-z-order"></a>按 Z 顺序排列 ToolStripPanel 控件

停靠 <xref:System.Windows.Forms.ToolStripPanel> 控件在 MDI 窗体上的位置由该控件在 z 顺序中的位置确定。 您可以轻松地在 "文档大纲" 窗口中排列控件的 z 顺序。

1. 在 " **视图** " 菜单上，单击 " **其他窗口**"，然后单击 " **文档大纲**"。

     <xref:System.Windows.Forms.ToolStripPanel>前面的过程中的控件排列是非标准的。 这是因为 z 顺序不正确。 使用 "文档大纲" 窗口可以更改控件的 z 顺序。

2. 在 "文档大纲" 窗口中，选择 " **ToolStripPanel4**"。

3. 重复单击向下箭头按钮，直到 **ToolStripPanel4** 位于列表底部。

     **ToolStripPanel4** 控件停靠在窗体底部的其他控件下。

4. 选择 **ToolStripPanel2**。

5. 单击向下箭头按钮一次，将控件置于列表中的第三位。

     **ToolStripPanel2** 控件停靠在窗体的顶部，位于主菜单的下方和其他控件的上方。

6. 在 " **文档大纲** " 窗口中选择各个控件，并将它们移动到 z 顺序中的不同位置。 请注意 z 顺序对停靠控件位置的影响。 使用 CTRL + Z 或 "**编辑**" 菜单上的 "**撤消**" 可撤消更改。

## <a name="checkpoint---test-your-form"></a>检查点-测试窗体

1. 按 **F5** 编译并运行您的窗体。

2. 单击控件的手柄 <xref:System.Windows.Forms.ToolStrip> ，将控件拖动到窗体上的不同位置。

     可以将 <xref:System.Windows.Forms.ToolStrip> 一个控件从一个 <xref:System.Windows.Forms.ToolStripPanel> 控件拖动到另一个控件。

## <a name="next-steps"></a>后续步骤

在本演练中，您已创建了一个具有 <xref:System.Windows.Forms.ToolStrip> 控件和菜单合并的 MDI 父窗体。 可以将 <xref:System.Windows.Forms.ToolStrip> 控件系列用于许多其他用途：

- 为控件创建快捷菜单 <xref:System.Windows.Forms.ContextMenuStrip> 。 有关详细信息，请参阅 [ContextMenu 组件概述](contextmenu-component-overview-windows-forms.md)。

- 创建了一个带有自动填充的标准菜单的窗体。 有关详细信息，请参阅 [演练：向窗体提供标准菜单项](walkthrough-providing-standard-menu-items-to-a-form.md)。

- 为 <xref:System.Windows.Forms.ToolStrip> 控件指定专业外观。 有关详细信息，请参阅 [如何：为应用程序设置 ToolStrip 呈现](how-to-set-the-toolstrip-renderer-for-an-application.md)器。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [如何：创建 MDI 父窗体](../advanced/how-to-create-mdi-parent-forms.md)
- [如何：创建 MDI 子窗体](../advanced/how-to-create-mdi-child-forms.md)
- [如何：将 MenuStrip 插入 MDI 下拉菜单](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [ToolStrip 控件](toolstrip-control-windows-forms.md)
