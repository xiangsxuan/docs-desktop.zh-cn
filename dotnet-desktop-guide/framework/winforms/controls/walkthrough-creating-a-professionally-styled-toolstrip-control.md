---
title: 演练：创建具有专业样式的 ToolStrip 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
ms.openlocfilehash: 3fd9175f47f9f1b35743dc69b462227fdfafe55d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972867"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a>演练：创建具有专业样式的 ToolStrip 控件

可以 <xref:System.Windows.Forms.ToolStrip> 通过编写自己的从类型派生的类，为应用程序的控件指定专业外观和行为 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 。

本演练演示如何使用 <xref:System.Windows.Forms.ToolStrip> 控件来创建与 Microsoft® Outlook®提供的 **导航窗格** 类似的复合控件。 此演练演示了下列任务：

- 创建 Windows 控件库项目。

- 设计 System.windows.forms.toolstrip.stackview 控件。

- 实现自定义呈现器。

完成后，将拥有一个可重复使用的自定义客户端控件，该控件具有专业外观 Microsoft Office® XP 控件。

若要将本主题中的代码复制为单个列表，请参阅 [如何：创建具有专业样式的 ToolStrip 控件](how-to-create-a-professionally-styled-toolstrip-control.md)。

## <a name="prerequisites"></a>先决条件

需要 Visual Studio 才能完成此演练。

## <a name="create-the-control-library-project"></a>创建控件库项目

1. 在 Visual Studio 中，创建一个名为的新 Windows 控件库项目 `StackViewLibrary` 。

2. 在 **解决方案资源管理器** 中，通过删除名为 "UserControl1.cs" 或 "UserControl1" 的源文件来删除项目的默认控件，具体取决于你选择的语言。

     有关详细信息，请参阅 [如何：删除、删除和排除项](/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))。

3. 向 <xref:System.Windows.Forms.UserControl> **StackViewLibrary** 项目添加一个新项。 为新的源文件指定基名称 `StackView` 。

## <a name="design-the-stackview-control"></a>设计 System.windows.forms.toolstrip.stackview 控件

`StackView`控件是具有一个子控件的复合控件 <xref:System.Windows.Forms.ToolStrip> 。 有关复合控件的详细信息，请参阅 [各种自定义控件](varieties-of-custom-controls.md)。

1. 从 " **工具箱**" 中，将 <xref:System.Windows.Forms.ToolStrip> 控件拖动到设计图面。

2. 在 " **属性** " 窗口中， <xref:System.Windows.Forms.ToolStrip> 根据下表设置控件的属性。

    |属性|值|
    |--------------|-----------|
    |名称|`stackStrip`|
    |CanOverflow|`false`|
    |程序坞|<xref:System.Windows.Forms.DockStyle.Bottom>|
    |字体|`Tahoma, 10pt, style=Bold`|
    |GripStyle|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|
    |LayoutStyle|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|
    |填充|`0, 7, 0, 0`|
    |RenderMode|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|

3. 在 Windows 窗体设计器中，单击 <xref:System.Windows.Forms.ToolStrip> 控件的 " **添加** " 按钮，并将添加 <xref:System.Windows.Forms.ToolStripButton> 到 `stackStrip` 控件。

4. 在 " **属性** " 窗口中， <xref:System.Windows.Forms.ToolStripButton> 根据下表设置控件的属性。

    |属性|值|
    |--------------|-----------|
    |名称|`mailStackButton`|
    |CheckOnClick|true|
    |CheckState|<xref:System.Windows.Forms.CheckState.Checked>|
    |System.windows.forms.toolstripitem.displaystyle|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|
    |ImageAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|
    |ImageScaling|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|
    |ImageTransparentColor|`238, 238, 238`|
    |Margin|`0, 0, 0, 0`|
    |填充|`3, 3, 3, 3`|
    |文本|**信**|
    |TextAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|

5. 对其他三个控件重复步骤 7 <xref:System.Windows.Forms.ToolStripButton> 。

     将控件命名为 `calendarStackButton` 、 `contactsStackButton` 和 `tasksStackButton` 。 分别将属性的值设置 <xref:System.Windows.Forms.Control.Text%2A> 为 " **日历**"、" **联系人**" 和 " **任务**"。

## <a name="handle-events"></a>处理事件

为了使控件正常运行，两个事件很重要 `StackView` 。 处理 <xref:System.Windows.Forms.UserControl.Load> 事件以正确定位控件。 处理 <xref:System.Windows.Forms.ToolStripItem.Click> 每个的事件 <xref:System.Windows.Forms.ToolStripButton> ，以使 `StackView` 控件状态行为与控件相似 <xref:System.Windows.Forms.RadioButton> 。

1. 在 Windows 窗体设计器中，选择 `StackView` 控件。

2. 在“属性”窗口中，单击“事件”。

3. 双击 Load 事件以生成 `StackView_Load` 事件处理程序。

4. 在 `StackView_Load` 事件处理程序中，复制并粘贴以下代码。

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]

5. 在 Windows 窗体设计器中，选择 `mailStackButton` 控件。

6. 在“属性”窗口中，单击“事件”。

7. 双击 "Click" 事件。

     Windows 窗体设计器生成 `mailStackButton_Click` 事件处理程序。

8. 将 `mailStackButton_Click` 事件处理程序重命名为 `stackButton_Click` 。

     有关详细信息，请参阅 [重命名代码符号重构](/visualstudio/ide/reference/rename)。

9. 将以下代码插入到 `stackButton_Click` 事件处理程序中。

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]

10. 在 Windows 窗体设计器中，选择 `calendarStackButton` 控件。

11. 在 " **属性** " 窗口中，将 Click 事件设置为 `stackButton_Click` 事件处理程序。

12. 对和控件重复步骤10和 `contactsStackButton` 11 `tasksStackButton` 。

## <a name="define-icons"></a>定义图标

每个 `StackView` 按钮都有一个关联的图标。 为方便起见，每个图标都表示为 Base64 编码的字符串，该字符串在从其创建之前进行反序列化 <xref:System.Drawing.Bitmap> 。 在生产环境中，将位图数据存储为资源，并在 Windows 窗体设计器中显示图标。 有关详细信息，请参阅 [如何：将背景图像添加到 Windows 窗体](/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100))。

1. 在代码编辑器中，将以下代码插入到 `StackView` 类定义中。 此代码初始化图标的位图 <xref:System.Windows.Forms.ToolStripButton> 。

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]

2. `InitializeImages`在类构造函数中添加对方法的调用 `StackView` 。

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="implement-a-custom-renderer"></a>实现自定义呈现器

您可以自定义控件的大多数元素 `StackView` ，实现从类派生的类 <xref:System.Windows.Forms.ToolStripRenderer> 。 在此过程中，您将实现一个 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 类，该类自定义手柄并绘制控件的渐变背景 <xref:System.Windows.Forms.ToolStripButton> 。

1. 将以下代码插入 `StackView` 控件定义。

     这是类的定义 `StackRenderer` ，它将重写 <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip> 、 <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder> 和 <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> 方法以生成自定义外观。

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]

2. 在 `StackView` 控件的构造函数中，创建类的新实例， `StackRenderer` 并将此实例分配给 `stackStrip` 控件的 <xref:System.Windows.Forms.ToolStrip.Renderer%2A> 属性。

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="test-the-stackview-control"></a>测试 System.windows.forms.toolstrip.stackview 控件

`StackView`控件派生自 <xref:System.Windows.Forms.UserControl> 类。 因此，可以用 **UserControl 测试容器** 测试控件。 有关详细信息，请参阅 [如何：测试 UserControl 的 Run-Time 行为](how-to-test-the-run-time-behavior-of-a-usercontrol.md)。

1. 按 **F5** 生成项目并启动 " **UserControl 测试容器**"。

2. 将指针移到控件的按钮上 `StackView` ，然后单击按钮以查看其所选状态的外观。

## <a name="next-steps"></a>后续步骤

在本演练中，您已创建了一个可重用的自定义客户端控件，并具有 Office XP 控件的专业外观。 可以将 <xref:System.Windows.Forms.ToolStrip> 控件系列用于许多其他用途：

- 为控件创建快捷菜单 <xref:System.Windows.Forms.ContextMenuStrip> 。 有关详细信息，请参阅 [ContextMenu 组件概述](contextmenu-component-overview-windows-forms.md)。

- 使用自动填充的标准菜单创建窗体。 有关详细信息，请参阅 [演练：向窗体提供标准菜单项](walkthrough-providing-standard-menu-items-to-a-form.md)。

- 使用停靠控件 (MDI) 窗体创建多文档界面 <xref:System.Windows.Forms.ToolStrip> 。 有关详细信息，请参阅 [如何：创建具有菜单合并和 ToolStrip 控件的 MDI 窗体](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [ToolStrip 控件](toolstrip-control-windows-forms.md)
- [如何：向窗体提供标准菜单项](how-to-provide-standard-menu-items-to-a-form.md)
