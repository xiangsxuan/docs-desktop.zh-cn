---
title: ToolStrip 控件体系结构
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
ms.openlocfilehash: d0a1441e9bae8d2c1f938e7399c11e736708da4d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973081"
---
# <a name="toolstrip-control-architecture"></a>ToolStrip 控件体系结构

<xref:System.Windows.Forms.ToolStrip>和 <xref:System.Windows.Forms.ToolStripItem> 类提供了一个灵活、可扩展的系统来显示工具栏、状态和菜单项。 这些类都包含在 <xref:System.Windows.Forms> 命名空间中，并且通常以 "ToolStrip" 前缀命名， (如 <xref:System.Windows.Forms.ToolStripOverflow>) 或带有 "停车" 后缀 (如 <xref:System.Windows.Forms.MenuStrip>) 。

## <a name="toolstrip"></a>ToolStrip

以下主题描述 <xref:System.Windows.Forms.ToolStrip> 和派生自它的控件。

<xref:System.Windows.Forms.ToolStrip> 是、和的抽象基类 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ContextMenuStrip> 。 以下对象模型显示了 <xref:System.Windows.Forms.ToolStrip> 继承层次结构。

![显示 ToolStrip 对象模型的关系图。](./media/toolstrip-control-architecture/toolstrip-object-model.gif)

你可以通过集合访问中的所有项 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip.Items%2A> 。 你可以通过集合访问中的所有项 <xref:System.Windows.Forms.ToolStripDropDownItem> <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> 。 在从派生的类中 <xref:System.Windows.Forms.ToolStrip> ，还可以使用 <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> 属性来仅访问当前显示的那些项。 这些是当前不在溢出菜单中的项。

以下各项专用于 <xref:System.Windows.Forms.ToolStripSystemRenderer> 在所有方向上无缝使用和 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 。 默认情况下，它们在设计时可用于 <xref:System.Windows.Forms.ToolStrip> 控件：

- <xref:System.Windows.Forms.ToolStripButton>

- <xref:System.Windows.Forms.ToolStripSeparator>

- <xref:System.Windows.Forms.ToolStripLabel>

- <xref:System.Windows.Forms.ToolStripDropDownButton>

- <xref:System.Windows.Forms.ToolStripSplitButton>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="menustrip"></a>MenuStrip

<xref:System.Windows.Forms.MenuStrip> 是取代的顶级容器 <xref:System.Windows.Forms.MainMenu> 。 它还提供了键处理和多个文档界面 (MDI) 功能。 功能 <xref:System.Windows.Forms.ToolStripDropDownItem> 和一起 <xref:System.Windows.Forms.ToolStripMenuItem> 工作， <xref:System.Windows.Forms.MenuStrip> 尽管它们是从派生的 <xref:System.Windows.Forms.ToolStripItem> 。

以下各项专用于 <xref:System.Windows.Forms.ToolStripSystemRenderer> 在所有方向上无缝使用和 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 。 默认情况下，它们在设计时可用于 <xref:System.Windows.Forms.MenuStrip> 控件：

- <xref:System.Windows.Forms.ToolStripMenuItem>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="statusstrip"></a>StatusStrip

<xref:System.Windows.Forms.StatusStrip> 替换 <xref:System.Windows.Forms.StatusBar> 控件。 的特殊功能 <xref:System.Windows.Forms.StatusStrip> 包括自定义表布局、支持窗体的大小调整和移动手柄以及 `Spring` 属性（允许 <xref:System.Windows.Forms.ToolStripStatusLabel> 自动填充可用空间）。

以下各项专用于 <xref:System.Windows.Forms.ToolStripSystemRenderer> 在所有方向上无缝使用和 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 。 默认情况下，它们在设计时可用于 <xref:System.Windows.Forms.StatusStrip> 控件：

- <xref:System.Windows.Forms.ToolStripStatusLabel>

- <xref:System.Windows.Forms.ToolStripDropDownButton>

- <xref:System.Windows.Forms.ToolStripSplitButton>

- <xref:System.Windows.Forms.ToolStripProgressBar>

### <a name="contextmenustrip"></a>ContextMenuStrip

<xref:System.Windows.Forms.ContextMenuStrip> 替换了 <xref:System.Windows.Forms.ContextMenu>。 您可以将 <xref:System.Windows.Forms.ContextMenuStrip> 与任何控件相关联，然后右键单击鼠标右键会自动显示上下文菜单 (或快捷菜单) 。 您可以 <xref:System.Windows.Forms.ContextMenuStrip> 使用方法以编程方式显示 <xref:System.Windows.Forms.ToolStripDropDown.Show%2A> 。 <xref:System.Windows.Forms.ContextMenuStrip> 支持 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 可取消的和 <xref:System.Windows.Forms.ToolStripDropDown.Closing> 事件来处理动态填充和多重单击方案。 <xref:System.Windows.Forms.ContextMenuStrip> 支持图像、菜单项的检查状态、文本、访问键、快捷方式和级联菜单。

以下各项专用于 <xref:System.Windows.Forms.ToolStripSystemRenderer> 在所有方向上无缝使用和 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 。 默认情况下，它们在设计时可用于 <xref:System.Windows.Forms.ContextMenuStrip> 控件：

- <xref:System.Windows.Forms.ToolStripMenuItem>

- <xref:System.Windows.Forms.ToolStripSeparator>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="toolstrip-generic-features"></a>ToolStrip 一般功能

以下主题介绍了和派生的控件的通用功能 <xref:System.Windows.Forms.ToolStrip> 。

#### <a name="painting"></a>绘制

可以通过多种方式在控件中执行自定义绘制 <xref:System.Windows.Forms.ToolStrip> 。 与其他 Windows 窗体控件一样， <xref:System.Windows.Forms.ToolStrip> 和 <xref:System.Windows.Forms.ToolStripItem> 都具有可重写的 `OnPaint` 方法和 `Paint` 事件。 与常规绘制一样，坐标系统是相对于控件的工作区的;也就是说，控件的左上角是0，0。 的 `Paint` 事件和 `OnPaint` 方法的 <xref:System.Windows.Forms.ToolStripItem> 行为类似于其他控件绘制事件。

<xref:System.Windows.Forms.ToolStrip>控件还通过类提供对项和容器的呈现的更精细的访问 <xref:System.Windows.Forms.ToolStripRenderer> ，该类具有可重写的方法，用于绘制背景、项背景、项图像、项箭头、项文本和边框 <xref:System.Windows.Forms.ToolStrip> 。 这些方法的事件自变量会公开几个属性，如矩形、颜色和文本格式，你可以根据需要进行调整。

若要仅调整项绘制方式的几个方面，通常会重写 <xref:System.Windows.Forms.ToolStripRenderer> 。

如果你正在编写一个新项并想要控制绘制的所有方面，则重写 `OnPaint` 方法。 从中 `OnPaint` ，你可以使用中的方法 <xref:System.Windows.Forms.ToolStripRenderer> 。

默认情况下，使用 <xref:System.Windows.Forms.ToolStrip> 设置进行双缓冲。 <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer>

#### <a name="parenting"></a>父级

在控件中，容器所有权和父级的概念 <xref:System.Windows.Forms.ToolStrip> 比其他 Windows 窗体容器控件更复杂。 这对于支持动态方案（如溢出）、跨多个项共享下拉项 <xref:System.Windows.Forms.ToolStrip> 以及支持从控件生成的是必需的 <xref:System.Windows.Forms.ContextMenuStrip> 。

下表描述了与父级相关的成员，并说明了它们的用法。

- <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A> 访问作为下拉项的源的项。 这类似于 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A> ，但它不返回控件，而是返回 <xref:System.Windows.Forms.ToolStripItem> 。

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A> 确定 <xref:System.Windows.Forms.ContextMenuStrip> 当多个控件共享同一时哪个控件是的源 <xref:System.Windows.Forms.ContextMenuStrip> 。

- <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A> 是属性的只读访问器 <xref:System.Windows.Forms.ToolStripItem.Parent%2A> 。 父级不同于所有者，因为父对象表示在其中显示项的返回的当前 <xref:System.Windows.Forms.ToolStrip> （可能在溢出区中）。

- <xref:System.Windows.Forms.ToolStripItem.Owner%2A> 返回 <xref:System.Windows.Forms.ToolStrip> 其项集合包含当前的 <xref:System.Windows.Forms.ToolStripItem> 。 这是在顶级引用或其他属性的最佳方式， <xref:System.Windows.Forms.ToolStrip.ImageList%2A> <xref:System.Windows.Forms.ToolStrip> 无需编写用于处理溢出的特殊代码。

#### <a name="behavior-of-inherited-controls"></a>继承控件的行为

以下控件将在继承中使用时被锁定：

- <xref:System.Windows.Forms.ToolStrip>

- <xref:System.Windows.Forms.MenuStrip>

- <xref:System.Windows.Forms.ContextMenuStrip>

- <xref:System.Windows.Forms.StatusStrip>

- <xref:System.Windows.Forms.ToolStripPanel> ，其中包括 <xref:System.Windows.Forms.ToolStripContainer> 和各个控件中的面板 <xref:System.Windows.Forms.ToolStripPanel> 。

例如，使用上一列表中的一个或多个控件创建新的 Windows 窗体应用程序。 将一个或多个控件的访问修饰符设置为 `public` 或 `protected` ，然后生成项目。 添加从第一个窗体继承的窗体，然后选择继承的控件。 控件显示为锁定状态，其行为与访问修饰符的行为相同 `private` 。

#### <a name="toolstripcontainer-support-of-inheritance"></a>对继承的 ToolStripContainer 支持

<xref:System.Windows.Forms.ToolStripContainer>控件支持限制的继承方案，类似于以下示例：

1. 创建新的 Windows 窗体应用程序。

2. 在窗体上添加一个 <xref:System.Windows.Forms.ToolStripContainer> 控件。

3. 将的访问修饰符设置 <xref:System.Windows.Forms.ToolStripContainer> 为 `public` 或 `protected` 。

4. 将、和控件的任意组合添加 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.MenuStrip> 到的 <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.ToolStripPanel> 区域 <xref:System.Windows.Forms.ToolStripContainer> 。

5. 生成项目。

6. 添加从第一个窗体继承的窗体。

7. 选择 <xref:System.Windows.Forms.ToolStripContainer> 窗体上继承的。

#### <a name="inherited-behavior-of-child-controls"></a>子控件的继承行为

完成前面的步骤后，将发生以下继承行为：

- 在设计器中，控件与继承的图标一起显示。

- <xref:System.Windows.Forms.ToolStripPanel>控件被锁定; 不能选择或重新排列其内容。

- 您可以向中添加控件 <xref:System.Windows.Forms.ToolStripContentPanel> ，移动控件，并使其成为的子控件 <xref:System.Windows.Forms.ToolStripContentPanel> 。

- 生成窗体后，你的更改将保持不变。

  > [!NOTE]
  > 从属于的所有控件中删除访问修饰符 <xref:System.Windows.Forms.ToolStripPanel> <xref:System.Windows.Forms.ToolStripContainer> 。 的访问修饰符 <xref:System.Windows.Forms.ToolStripContainer> 控制整个控件。

#### <a name="partial-trust"></a>部分信任

`ToolStrip`部分信任下的限制旨在防止无意中输入未经授权的人员或服务可能使用的个人信息。 保护措施如下：

- `ToolStripDropDown` 控件需要 <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> 在中显示项 <xref:System.Windows.Forms.ToolStripControlHost> 。 这适用于内部控件 <xref:System.Windows.Forms.ToolStripTextBox> ，例如、和，以及 <xref:System.Windows.Forms.ToolStripComboBox> <xref:System.Windows.Forms.ToolStripProgressBar> 用户创建的控件。 如果未满足此要求，则不会显示这些项。 不引发异常。

- <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A>不允许将属性设置为 `false` ，并且将忽略可取消的 <xref:System.Windows.Forms.ToolStripDropDown.Closing> 事件参数。 这样一来，就不可能输入多个击键而不关闭下拉项。 如果未满足此要求，则不会显示此类项。 不引发异常。

- 如果在的部分信任上下文中发生事件，则不会引发许多击键处理事件 <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> 。

- 未授予访问密钥时，不会对其进行处理 <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> 。

#### <a name="usage"></a>使用情况

以下使用模式与 <xref:System.Windows.Forms.ToolStrip> 布局、键盘交互和最终用户行为有关：

- 联接于 <xref:System.Windows.Forms.ToolStripPanel>

  <xref:System.Windows.Forms.ToolStrip>可以在内 <xref:System.Windows.Forms.ToolStripPanel> 和之间重定位 <xref:System.Windows.Forms.ToolStripPanel> 。 `Dock`忽略属性，如果 <xref:System.Windows.Forms.ToolStrip.Stretch%2A> 属性为 `false` ，则在将 <xref:System.Windows.Forms.ToolStrip> 项添加到 <xref:System.Windows.Forms.ToolStripPanel> 中时，的大小将增长。 通常，不 <xref:System.Windows.Forms.ToolStrip> 参与 tab 键顺序。

- 停靠

  <xref:System.Windows.Forms.ToolStrip>置于固定位置的容器的一侧，其大小会在其停靠到的整个边缘上展开。 通常，不 <xref:System.Windows.Forms.ToolStrip> 参与 tab 键顺序。

- 绝对定位

  与 <xref:System.Windows.Forms.ToolStrip> 其他控件一样，它是由属性放置的，它 <xref:System.Windows.Forms.Control.Location%2A> 具有固定的大小，并且通常参与 tab 键顺序。

#### <a name="keyboard-interaction"></a>键盘交互

##### <a name="access-keys"></a>访问密钥

通过与 ALT 键组合在一起或之后，访问键是使用键盘激活控件的一种方法。 <xref:System.Windows.Forms.ToolStrip> 支持显式和隐式访问密钥。 显式定义使用符号 ( # A0) 字符之前。 隐式定义使用一种算法，该算法根据给定属性中的字符顺序尝试查找匹配项 `Text` 。

##### <a name="shortcut-keys"></a>快捷键

使用的快捷键 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.Keys> (不是特定于顺序) 来定义快捷键的枚举。 你还可以使用 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> 属性来显示仅带有文本的快捷键，例如显示 "Del" 而不是 "Delete"。

##### <a name="navigation"></a>导航

ALT 键激活所 <xref:System.Windows.Forms.MenuStrip> 指向的 <xref:System.Windows.Forms.Form.MainMenuStrip%2A> 。 在这里，CTRL + TAB <xref:System.Windows.Forms.ToolStrip> 在中的控件之间导航 `ToolStripPanel` 。 数字键盘上的 TAB 键和箭头键在中的项之间导航 <xref:System.Windows.Forms.ToolStrip> 。 特殊算法处理溢出区中的导航。 空格键选择 <xref:System.Windows.Forms.ToolStripButton> 、 <xref:System.Windows.Forms.ToolStripDropDownButton> 或 <xref:System.Windows.Forms.ToolStripSplitButton> 。

##### <a name="focus-and-validation"></a>焦点和验证

当通过 ALT 键激活时， <xref:System.Windows.Forms.MenuStrip> 或 <xref:System.Windows.Forms.ToolStrip> 通常不会从当前具有焦点的控件中执行焦点，也不会删除焦点。 如果在或的下拉控件中承载了一个控件 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MenuStrip> ，则当用户按 TAB 键时，控件将获得焦点。 通常， <xref:System.Windows.Forms.Control.GotFocus> <xref:System.Windows.Forms.Control.LostFocus> <xref:System.Windows.Forms.Control.Enter> <xref:System.Windows.Forms.Control.Leave> <xref:System.Windows.Forms.MenuStrip> 当键盘激活时，可能不会引发、、和事件。 在这种情况下， <xref:System.Windows.Forms.MenuStrip.MenuActivate> 请 <xref:System.Windows.Forms.MenuStrip.MenuDeactivate> 改用和事件。

默认情况下， <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> 为 `false` 。 <xref:System.Windows.Forms.ContainerControl.Validate%2A>在窗体上显式调用以执行验证。

#### <a name="layout"></a>Layout

<xref:System.Windows.Forms.ToolStrip>通过选择具有属性的成员之一来控制布局 <xref:System.Windows.Forms.ToolStripLayoutStyle> <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> 。

##### <a name="stack-layouts"></a>堆栈布局

堆栈是在两端并排排列项 <xref:System.Windows.Forms.ToolStrip> 。 下面的列表描述了堆栈布局。

- <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow> 为默认值。 此设置会使 <xref:System.Windows.Forms.ToolStrip> 按照属性自动更改其布局， <xref:System.Windows.Forms.ToolStrip.Orientation%2A> 以便处理拖放和停靠方案。

- <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow> 垂直呈现 <xref:System.Windows.Forms.ToolStrip> 项。

- <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow> 横向呈现 <xref:System.Windows.Forms.ToolStrip> 项。

##### <a name="other-features-of-stack-layouts"></a>堆栈布局的其他功能

<xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 确定 <xref:System.Windows.Forms.ToolStrip> 项要对齐到的末尾。

当项不适合于时 <xref:System.Windows.Forms.ToolStrip> ，会自动显示溢出按钮。 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>属性设置确定某项是否始终出现在溢出区中（根据需要）或从不出现。

在此 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 事件中，你可以检查 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 属性，以确定项是放置在主位置 <xref:System.Windows.Forms.ToolStrip> 、溢出 <xref:System.Windows.Forms.ToolStrip> 还是当前根本不显示。 项未显示的典型原因是项不适合 main <xref:System.Windows.Forms.ToolStrip> ，其 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 属性设置为 <xref:System.Windows.Forms.ToolStripItemOverflow.Never> 。

将 <xref:System.Windows.Forms.ToolStrip> 其放入 <xref:System.Windows.Forms.ToolStripPanel> ，并将其设置为，使成为可移动的 <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> <xref:System.Windows.Forms.ToolStripGripStyle.Visible> 。

##### <a name="other-layout-options"></a>其他布局选项

其他布局选项为 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> 和 <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> 。

##### <a name="flow-layout"></a>流布局

<xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> 布局是、和的默认设置 <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.ToolStripDropDownMenu> <xref:System.Windows.Forms.ToolStripOverflow> 。 它类似于 <xref:System.Windows.Forms.FlowLayoutPanel> 。 布局的功能 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> 如下所示：

- 的所有功能 <xref:System.Windows.Forms.FlowLayoutPanel> 都由 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> 属性公开。 您必须将类强制转换 <xref:System.Windows.Forms.LayoutSettings> 为 <xref:System.Windows.Forms.FlowLayoutSettings> 类。

- 您可以 <xref:System.Windows.Forms.ToolStripItem.Dock%2A> <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> 在代码中使用和属性来对齐行中的项。

- <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 属性被忽略。

- 在此 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 事件中，你可以检查 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 属性，以确定项是放置在主上 <xref:System.Windows.Forms.ToolStrip> 还是不适合。

- 手柄未呈现，因此 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> 无法移动中布局样式中的 <xref:System.Windows.Forms.ToolStripPanel> 。

- <xref:System.Windows.Forms.ToolStrip>溢出按钮不会呈现，将被 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 忽略。

##### <a name="table-layout"></a>表布局

<xref:System.Windows.Forms.ToolStripLayoutStyle.Table> 布局是的默认值 <xref:System.Windows.Forms.StatusStrip> 。 它类似于 <xref:System.Windows.Forms.TableLayoutPanel> 。 布局的功能 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> 如下所示：

- 的所有功能 <xref:System.Windows.Forms.TableLayoutPanel> 都由 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> 属性公开。 您必须将类强制转换 <xref:System.Windows.Forms.LayoutSettings> 为 <xref:System.Windows.Forms.TableLayoutSettings> 类。

- 您可以 <xref:System.Windows.Forms.ToolStripItem.Dock%2A> <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> 在代码中使用和属性来对齐表单元格中的项。

- <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 属性被忽略。

- 在此 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 事件中，你可以检查 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 属性，以确定项是放置在主上 <xref:System.Windows.Forms.ToolStrip> 还是不适合。

- 手柄未呈现，因此 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> 无法移动中布局样式中的 <xref:System.Windows.Forms.ToolStripPanel> 。

- <xref:System.Windows.Forms.ToolStrip>溢出按钮不会呈现，将被 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 忽略。

## <a name="toolstripitem"></a>ToolStripItem

以下主题描述 <xref:System.Windows.Forms.ToolStripItem> 和派生自它的控件。

<xref:System.Windows.Forms.ToolStripItem> 是进入中的所有项的抽象基类 <xref:System.Windows.Forms.ToolStrip> 。 以下对象模型显示了 <xref:System.Windows.Forms.ToolStripItem> 继承层次结构。

![显示 ToolStripItem 对象模型的关系图。](./media/toolstrip-control-architecture/toolstripitem-object-model.gif)

<xref:System.Windows.Forms.ToolStripItem> 类直接从继承 <xref:System.Windows.Forms.ToolStripItem> ，或者它们从或间接继承 <xref:System.Windows.Forms.ToolStripItem> <xref:System.Windows.Forms.ToolStripControlHost> <xref:System.Windows.Forms.ToolStripDropDownItem> 。

<xref:System.Windows.Forms.ToolStripItem> 控件必须包含在、、 <xref:System.Windows.Forms.ToolStrip> 或中， <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ContextMenuStrip> 不能直接添加到窗体中。 各种容器类旨在包含控件的适当子集 <xref:System.Windows.Forms.ToolStripItem> 。

下表列出了常用 <xref:System.Windows.Forms.ToolStripItem> 控件和它们最适合的容器。 尽管任何 <xref:System.Windows.Forms.ToolStrip> 项都可以在任何派生的容器中托管 <xref:System.Windows.Forms.ToolStrip> ，但这些项在以下容器中的设计效果最好：

> [!NOTE]
> <xref:System.Windows.Forms.ToolStripDropDown> 不会出现在设计器工具箱中。

|包含的项|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|
|--------------------|---------------|---------------|----------------------|-----------------|-----------------------|
|<xref:System.Windows.Forms.ToolStripButton>|是|否|否|否|是|
|<xref:System.Windows.Forms.ToolStripComboBox>|是|是|是|否|是|
|<xref:System.Windows.Forms.ToolStripSplitButton>|是|否|否|是|是|
|<xref:System.Windows.Forms.ToolStripLabel>|是|否|否|是|是|
|<xref:System.Windows.Forms.ToolStripSeparator>|是|是|是|否|是|
|<xref:System.Windows.Forms.ToolStripDropDownButton>|是|否|否|是|是|
|<xref:System.Windows.Forms.ToolStripTextBox>|是|是|是|否|是|
|<xref:System.Windows.Forms.ToolStripMenuItem>|否|是|是|否|否|
|<xref:System.Windows.Forms.ToolStripStatusLabel>|否|否|否|是|否|
|<xref:System.Windows.Forms.ToolStripProgressBar>|是|否|否|是|否|
|<xref:System.Windows.Forms.ToolStripControlHost>|是|是|否|是|是|

### <a name="toolstripbutton"></a>ToolStripButton

<xref:System.Windows.Forms.ToolStripButton> 是的按钮项 <xref:System.Windows.Forms.ToolStrip> 。 您可以使用各种边框样式显示它，并且可以使用它来表示和激活操作状态。 你还可以将其定义为默认情况下具有焦点。

### <a name="toolstriplabel"></a>ToolStripLabel

在 <xref:System.Windows.Forms.ToolStripLabel> 控件中提供标签功能 <xref:System.Windows.Forms.ToolStrip> 。 <xref:System.Windows.Forms.ToolStripLabel>类似于 <xref:System.Windows.Forms.ToolStripButton> ，默认情况下不会获得焦点，且不会呈现为按下或突出显示的。

<xref:System.Windows.Forms.ToolStripLabel> 作为托管项，支持访问密钥。

使用 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> 上的、 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 和 <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> 属性 <xref:System.Windows.Forms.ToolStripLabel> 支持中的链接控件 <xref:System.Windows.Forms.ToolStrip> 。

### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel

<xref:System.Windows.Forms.ToolStripStatusLabel> 是专用 <xref:System.Windows.Forms.ToolStripLabel> 于在中使用的的版本 <xref:System.Windows.Forms.StatusStrip> 。 特殊功能包括 <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A> 、 <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A> 和 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> 。

### <a name="toolstripseparator"></a>ToolStripSeparator

根据 <xref:System.Windows.Forms.ToolStripSeparator> 方向，向工具栏或菜单添加垂直或水平线条。 它提供项的分组或区分，如菜单上的项。

您可以 <xref:System.Windows.Forms.ToolStripSeparator> 在设计时通过从下拉列表中选择来添加。 不过，还可以 <xref:System.Windows.Forms.ToolStripSeparator> 通过在设计器模板节点或方法中键入连字符 ( ) 来自动创建 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 。

### <a name="toolstripcontrolhost"></a>ToolStripControlHost

<xref:System.Windows.Forms.ToolStripControlHost> 是、和的抽象基类 <xref:System.Windows.Forms.ToolStripComboBox> <xref:System.Windows.Forms.ToolStripTextBox> <xref:System.Windows.Forms.ToolStripProgressBar> 。 <xref:System.Windows.Forms.ToolStripControlHost> 可以通过两种方式承载其他控件，包括自定义控件：

- <xref:System.Windows.Forms.ToolStripControlHost>使用派生自的类构造 <xref:System.Windows.Forms.Control> 。 若要完全访问所承载的控件和属性，必须将 <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> 属性强制转换回它所表示的实际类。

- 扩展 <xref:System.Windows.Forms.ToolStripControlHost> ，并在继承类的无参数构造函数中，调用基类构造函数，该构造函数传递派生自的类 <xref:System.Windows.Forms.Control> 。 使用此选项可以包装常用控制方法和属性，以便在中轻松访问 <xref:System.Windows.Forms.ToolStrip> 。

### <a name="toolstripcombobox"></a>ToolStripComboBox

<xref:System.Windows.Forms.ToolStripComboBox> 是 <xref:System.Windows.Forms.ComboBox> 针对在中承载的进行了优化 <xref:System.Windows.Forms.ToolStrip> 。 托管控件的属性和事件的子集在 <xref:System.Windows.Forms.ToolStripComboBox> 级别公开，但基础 <xref:System.Windows.Forms.ComboBox> 控件可通过属性完全访问 <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A> 。

### <a name="toolstriptextbox"></a>ToolStripTextBox

<xref:System.Windows.Forms.ToolStripTextBox> 是 <xref:System.Windows.Forms.TextBox> 针对在中承载的进行了优化 <xref:System.Windows.Forms.ToolStrip> 。 托管控件的属性和事件的子集在 <xref:System.Windows.Forms.ToolStripTextBox> 级别公开，但基础 <xref:System.Windows.Forms.TextBox> 控件可通过属性完全访问 <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A> 。

### <a name="toolstripprogressbar"></a>ToolStripProgressBar

<xref:System.Windows.Forms.ToolStripProgressBar> 是 <xref:System.Windows.Forms.ProgressBar> 针对在中承载的进行了优化 <xref:System.Windows.Forms.ToolStrip> 。 托管控件的属性和事件的子集在 <xref:System.Windows.Forms.ToolStripProgressBar> 级别公开，但基础 <xref:System.Windows.Forms.ProgressBar> 控件可通过属性完全访问 <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A> 。

### <a name="toolstripdropdownitem"></a>ToolStripDropDownItem

<xref:System.Windows.Forms.ToolStripDropDownItem> 是、和的抽象基类 <xref:System.Windows.Forms.ToolStripMenuItem> <xref:System.Windows.Forms.ToolStripDropDownButton> <xref:System.Windows.Forms.ToolStripSplitButton> ，它可以直接承载项或在下拉容器中承载附加项。 为此，可将 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> 属性设置为 <xref:System.Windows.Forms.ToolStripDropDown> ，并设置 <xref:System.Windows.Forms.ToolStrip.Items%2A> 的属性 <xref:System.Windows.Forms.ToolStripDropDown> 。 直接通过属性访问这些下拉项 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> 。

### <a name="toolstripmenuitem"></a>ToolStripMenuItem

<xref:System.Windows.Forms.ToolStripMenuItem><xref:System.Windows.Forms.ToolStripDropDownItem>与和配合使用 <xref:System.Windows.Forms.ToolStripDropDownMenu> <xref:System.Windows.Forms.ContextMenuStrip> 来处理菜单的特殊突出显示、布局和列排列。

### <a name="toolstripdropdownbutton"></a>ToolStripDropDownButton

<xref:System.Windows.Forms.ToolStripDropDownButton> 看起来像这样 <xref:System.Windows.Forms.ToolStripButton> ，但当用户单击它时，它会显示一个下拉区域。 通过设置属性，隐藏或显示下拉箭头 <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A> 。 <xref:System.Windows.Forms.ToolStripDropDownButton> 承载 <xref:System.Windows.Forms.ToolStripOverflowButton> 用于显示溢出的项的 <xref:System.Windows.Forms.ToolStrip> 。

### <a name="toolstripsplitbutton"></a>ToolStripSplitButton

<xref:System.Windows.Forms.ToolStripSplitButton> 组合按钮和下拉按钮的功能。

使用 <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A> 属性将所 <xref:System.Windows.Forms.Control.Click> 选下拉项的事件与按钮上显示的项同步。

### <a name="toolstripitem-generic-features"></a>ToolStripItem 一般功能

<xref:System.Windows.Forms.ToolStripItem> 提供以下用于继承控件的通用功能和选项：

- 核心事件

- 图像处理

- 对齐方式

- 文本和图像关系

- 显示样式

#### <a name="core-events"></a>核心事件

<xref:System.Windows.Forms.ToolStripItem> 控件接收自己的 click、鼠标和 paint 事件，还可以执行一些键盘预处理。

#### <a name="image-handling"></a>图像处理

<xref:System.Windows.Forms.ToolStripItem.Image%2A>、、 <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> 、 <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A> <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A> 和 <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> 属性与图像处理的各个方面相关。 在控件中使用图像 <xref:System.Windows.Forms.ToolStrip> ，方法是直接设置这些属性，或者通过设置 "仅运行时–只" <xref:System.Windows.Forms.ToolStrip.ImageList%2A> 属性。

图像缩放是通过和中的属性交互确定的 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripItem> ，如下所示：

- <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A> 最终映像的小数位数，由图像 <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> 设置和容器设置的组合确定 <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> 。

  - 如果 <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> `true` (默认) 并且 <xref:System.Windows.Forms.ToolStripItemImageScaling> 为，则 <xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit> 不会发生图像缩放，并且 <xref:System.Windows.Forms.ToolStrip> 大小是最大项的大小，或者是指定的最小大小。

  - 如果 <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> 为 `false` 且 <xref:System.Windows.Forms.ToolStripItemImageScaling> 为 <xref:System.Windows.Forms.ToolStripItemImageScaling.None> ，则不 <xref:System.Windows.Forms.ToolStrip> 会发生图像和缩放。

#### <a name="alignment"></a>对齐方式

属性的值 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 确定 <xref:System.Windows.Forms.ToolStrip> 项出现的结束位置。 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>仅当的布局样式 <xref:System.Windows.Forms.ToolStrip> 设置为某个堆栈溢出值时，属性才有效。

项按项在 <xref:System.Windows.Forms.ToolStrip> 项集合中出现的顺序放置在上。 若要以编程方式更改项的布局位置，请使用 <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> 方法移动集合中的项。 此方法会移动项，但不会复制该项。

#### <a name="text-and-image-relationship"></a>文本和图像关系

<xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>属性定义图像相对于上的文本的相对位置 <xref:System.Windows.Forms.ToolStripItem> 。 缺少图像、文本或二者的项被视为特殊情况，因此，不 <xref:System.Windows.Forms.ToolStripItem> 会为缺少的元素显示空白点。

#### <a name="display-style"></a>显示样式

<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 允许您设置项的文本和图像属性的值，同时只显示您需要的内容。 这通常用于在不同的上下文中显示相同项时仅更改显示样式。

## <a name="accessory-classes"></a>附件类

提供各种其他功能的类包括：

- <xref:System.Windows.Forms.ToolStripManager> 支持 <xref:System.Windows.Forms.ToolStrip> 与整个应用程序相关的任务，例如合并、设置和呈现器选项。

- <xref:System.Windows.Forms.ToolStripRenderer> 允许您轻松地将特定样式或主题应用于 <xref:System.Windows.Forms.ToolStrip> 。

- <xref:System.Windows.Forms.ToolStripProfessionalRenderer> () ，基于可替换颜色表创建笔和画笔 <xref:System.Windows.Forms.ProfessionalColorTable> 。

- <xref:System.Windows.Forms.ToolStripSystemRenderer> 将系统颜色和平面视觉样式应用于 <xref:System.Windows.Forms.ToolStrip> 应用程序。

- <xref:System.Windows.Forms.ToolStripContainer> 类似于 <xref:System.Windows.Forms.SplitContainer> 。 它使用四个停靠的侧面板 (实例 <xref:System.Windows.Forms.ToolStripPanel>) 和一个中心面板 (实例 <xref:System.Windows.Forms.ToolStripContentPanel>) 以创建典型的排列方式。 不能移除侧面板，但可以隐藏它们。 不能删除或隐藏中央面板。 您可以排列侧面板中的一个或多个 <xref:System.Windows.Forms.ToolStrip> 、 <xref:System.Windows.Forms.MenuStrip> 或控件，还 <xref:System.Windows.Forms.StatusStrip> 可以使用中央面板来查看其他控件。 <xref:System.Windows.Forms.ToolStripContentPanel>还提供了一种方法来获取窗体正文的呈现器支持，以实现一致的外观。 <xref:System.Windows.Forms.ToolStripContainer> 不支持 (MDI) 的多个文档接口。

- <xref:System.Windows.Forms.ToolStripPanel> 为移动和排列控件提供空间 <xref:System.Windows.Forms.ToolStrip> 。 如果选择了，则只能使用一个面板， <xref:System.Windows.Forms.ToolStripPanel> 在 MDI 方案中可以很好地运行。

## <a name="see-also"></a>另请参阅

- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 技术摘要](toolstrip-technology-summary.md)
- [ToolStrip 控件](toolstrip-control-windows-forms.md)
- [MenuStrip 控件](menustrip-control-windows-forms.md)
- [StatusStrip 控件](statusstrip-control.md)
- [ContextMenuStrip 控件](contextmenustrip-control.md)
- [BindingNavigator 控件](bindingnavigator-control-windows-forms.md)
