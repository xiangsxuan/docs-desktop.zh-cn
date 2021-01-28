---
title: 使用对齐线排列控件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
ms.openlocfilehash: b916fd83ed35e16864366ba899c9dc9ab4e0624d
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957222"
---
# <a name="walkthrough-arrange-controls-on-windows-forms-using-snaplines"></a>演练：使用对齐线排列 Windows 窗体上的控件

在窗体上精确地放置控件对于许多应用程序而言是高优先级。 Windows 窗体设计器提供了许多布局工具来实现此目的。 最重要的一项是 <xref:System.Windows.Forms.Design.Behavior.SnapLine> 功能。

对齐线可精确显示控件与其他控件的对齐位置。 它们还显示了建议的距离，如 [Windows 用户界面准则](/windows/win32/uxguide/guidelines)所指定。

利用对齐线，你可以轻松地对齐控件，以获得清晰、专业的外观和行为 (外观) 。

## <a name="create-the-project"></a>创建项目

1. 在 Visual Studio 中，创建一个名为 "SnaplineExample" 的基于 Windows 的应用程序项目。

2. 在“窗体设计器”中选择窗体。

## <a name="space-and-align-controls"></a>间距和对齐控件

"对齐线" 为您显示窗体上控件的对齐方式。 当您将选定控件或控件移动到与另一个控件或控件集对齐的位置时，它们将显示。 在将其移到其他控件之后，你的选择将 "对齐" 到建议的位置。

### <a name="to-arrange-controls-using-snaplines"></a>使用对齐线排列控件

1. 从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。

2. 将 <xref:System.Windows.Forms.Button> 控件移动到窗体的右下角。 请注意，当 <xref:System.Windows.Forms.Button> 控件接近窗体的下边框和右边框时显示的对齐线。 这些对齐线显示控件边框与窗体边框之间的建议距离。

3. <xref:System.Windows.Forms.Button>围绕窗体的边框移动控件，并注意对齐线出现的位置。 完成后，将控件移动到 <xref:System.Windows.Forms.Button> 窗体中心附近。

4. 将另一个 <xref:System.Windows.Forms.Button> 控件从 **工具箱** 拖到窗体上。

5. 移动第二个 <xref:System.Windows.Forms.Button> 控件，直到它接近第一个控件。 请注意，在这两个按钮的文本基线上出现的对齐线，并注意您正在移动的控件将对齐到与其他控件完全相同的位置。

6. 移动第二个 <xref:System.Windows.Forms.Button> 控件，直到它直接位于第一个控件的上方。 请注意在这两个按钮的左右边缘上出现的对齐线，并注意您正在移动的控件将对齐到与其他控件完全对齐的位置。

7. 选择其中一个 <xref:System.Windows.Forms.Button> 控件，并将其移动到另一个控件，直到它们接近。 请注意它们之间出现的对齐线。 此距离是控件边框之间建议的距离。 另请注意，正在移动的控件将对齐到此位置。

8. 将两个 <xref:System.Windows.Forms.Panel> 控件从 **工具箱** 拖到窗体上。

9. 移动其中一个 <xref:System.Windows.Forms.Panel> 控件，直到它接近于第一个控件。 请注意沿两个控件的上边缘和下边缘显示的对齐线，并注意您正在移动的控件对齐到与其他控件完全相同的位置。

## <a name="align-to-form-and-container-margins"></a>对齐窗体和容器边距

对齐线有助于以一致的方式将控件与窗体和容器边距对齐。

1. 选择其中一个 <xref:System.Windows.Forms.Button> 控件，并将其移动到窗体的右边框，直到出现对齐线。 对齐线与右边框的距离是控件的 <xref:System.Windows.Forms.Control.Margin%2A> 属性和窗体的 <xref:System.Windows.Forms.Control.Padding%2A> 属性值之和。

   > [!NOTE]
   > 如果窗体的 <xref:System.Windows.Forms.Control.Padding%2A> 属性设置为0，0，0，0，则 Windows 窗体设计器为窗体提供一个阴影 <xref:System.Windows.Forms.Control.Padding%2A> 值9、9、9、9。 若要重写此行为，请指定0、0、0、0以外的值。

2. <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Margin%2A> 通过 <xref:System.Windows.Forms.Control.Margin%2A> 在 "**属性**" 窗口中展开条目并将属性设置为0，可更改控件的属性的值 <xref:System.Windows.Forms.Padding.All%2A> 。 有关详细信息，请参阅 [演练：通过填充、边距和 AutoSize 属性排放 Windows 窗体控件](windows-forms-controls-padding-autosize.md)。

3. 将 <xref:System.Windows.Forms.Button> 控件移动到窗体的右边框附近，直到出现对齐线。 此距离现在由窗体的属性的值提供 <xref:System.Windows.Forms.Control.Padding%2A> 。

4. 从 <xref:System.Windows.Forms.GroupBox> “工具箱” **将** 控件拖到你的窗体上。

5. <xref:System.Windows.Forms.GroupBox> <xref:System.Windows.Forms.Control.Padding%2A> 通过 <xref:System.Windows.Forms.Control.Padding%2A> 在 "**属性**" 窗口中展开条目并将属性设置为10，来更改控件的属性的值 <xref:System.Windows.Forms.Padding.All%2A> 。

6. 将 <xref:System.Windows.Forms.Button> 控件从 " **工具箱** " 拖放到 <xref:System.Windows.Forms.GroupBox> 控件中。

7. 将 <xref:System.Windows.Forms.Button> 控件移动到控件的右边框附近， <xref:System.Windows.Forms.GroupBox> 直到出现对齐线。 移动 <xref:System.Windows.Forms.Button> 控件内的控件 <xref:System.Windows.Forms.GroupBox> ，并注意对齐线出现的位置。

## <a name="align-to-grouped-controls"></a>对齐到分组控件

您可以使用对齐线对齐控件中的分组控件和控件 <xref:System.Windows.Forms.GroupBox> 。

1. 选择窗体上的两个控件。 移动所选内容，并记下所选内容与其他控件之间出现的对齐线。

2. 从 <xref:System.Windows.Forms.GroupBox> “工具箱” **将** 控件拖到你的窗体上。

3. 将 <xref:System.Windows.Forms.Button> 控件从 " **工具箱** " 拖放到 <xref:System.Windows.Forms.GroupBox> 控件中。

4. 选择其中一个 <xref:System.Windows.Forms.Button> 控件，并在控件上移动它 <xref:System.Windows.Forms.GroupBox> 。 请注意控件边缘上出现的对齐线 <xref:System.Windows.Forms.GroupBox> 。 另请注意控件所包含控件边缘上出现的对齐线 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.GroupBox> 。 容器控件的子级控件也支持对齐线。

## <a name="use-snaplines-to-place-a-control-by-outlining-its-size"></a>通过勾画控件大小来使用对齐线放置控件

1. 在“工具箱” 中，单击 <xref:System.Windows.Forms.Button> 控件图标。 请勿将其拖到窗体上。

2. 将鼠标指针移动到窗体的设计图面上。 请注意，指针会更改为十字形，同时会附上 <xref:System.Windows.Forms.Button> 控件图标。 另请注意为控件建议对齐位置的对齐线 <xref:System.Windows.Forms.Button> 。

3. 单击并按住鼠标按钮。

4. 在窗体上拖动鼠标指针。 请注意，会绘制一个轮廓，指示控件的位置和大小。

5. 拖动指针，直到它与窗体上的另一个控件对齐。 请注意，将显示一条对齐线以指示对齐方式。

6. 释放鼠标按钮。 控件在由轮廓指示的位置和大小创建。

## <a name="use-snaplines-when-dragging-a-control-from-the-toolbox"></a>从工具箱拖动控件时使用对齐线

1. 将 <xref:System.Windows.Forms.Button> 控件从 " **工具箱** " 拖到窗体上，但不释放鼠标按钮。

2. 将鼠标指针移动到窗体的设计图面上。 请注意，指针会更改以指示 <xref:System.Windows.Forms.Button> 将创建新控件的位置。

3. 在窗体上拖动鼠标指针。 请注意显示的对齐线，用于建议控件的对齐位置 <xref:System.Windows.Forms.Button> 。 查找与其他控件对齐的位置。

4. 释放鼠标按钮。 控件将在对齐线指示的位置创建。

## <a name="resize-a-control-using-snaplines"></a>使用对齐线调整控件大小

1. 从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。

2. 通过获取 <xref:System.Windows.Forms.Button> 一个角大小调整控点并拖动来调整控件的大小。 有关详细信息，请参阅 [如何：在 Windows 窗体上调整控件的大小](how-to-resize-controls-on-windows-forms.md)。

3. 拖动调整大小控点，直到其中一个 <xref:System.Windows.Forms.Button> 控件的边框与另一个控件对齐。 请注意，会显示对齐线。 另请注意，大小调整控点与对齐线指示的位置对齐。

4. <xref:System.Windows.Forms.Button>按不同方向调整控件大小，并将大小调整控点与不同控件对齐。 请注意对齐线如何出现在各种方向上以指示对齐方式。

## <a name="align-a-label-to-a-controls-text"></a>将标签与控件的文本对齐

1. 从 <xref:System.Windows.Forms.TextBox> “工具箱” **将** 控件拖到你的窗体上。 将 <xref:System.Windows.Forms.TextBox> 控件放到窗体上时，单击智能标记标志符号，然后选择 " **将文本设置为 textBox1** " 选项。 有关详细信息，请参阅 [演练：使用设计器操作执行常见任务](perform-common-tasks-design-actions.md)。

2. 从 <xref:System.Windows.Forms.Label> “工具箱” **将** 控件拖到你的窗体上。

3. 将 <xref:System.Windows.Forms.Label> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性值更改为 `true`。 请注意，控件的边框会调整以适应显示文本。

4. 将 <xref:System.Windows.Forms.Label> 控件移动到控件的左侧 <xref:System.Windows.Forms.TextBox> ，使其与控件的下边缘对齐 <xref:System.Windows.Forms.TextBox> 。 请注意在两个控件的下边缘显示的对齐线。

5. <xref:System.Windows.Forms.Label>稍微向上移动控件，直到 <xref:System.Windows.Forms.Label> 文本和 <xref:System.Windows.Forms.TextBox> 文本对齐。 请注意显示的样式不同的对齐线，指示两个控件的文本字段对齐的时间。

## <a name="use-snaplines-with-keyboard-navigation"></a>通过键盘导航使用对齐线

1. 从 <xref:System.Windows.Forms.Button> “工具箱” **将** 控件拖到你的窗体上。 将其放在窗体的左上角。

2. 按 **Ctrl** + **向下** 键。 请注意，控件向下移动到第一个可用的水平对齐位置。

3. 按 **Ctrl** + **向下键**，直到控件到达窗体的底部。 请注意，它在窗体中向下移动时所占据的位置。

4. 按 **Ctrl** + **向右箭头**。 请注意，控件在窗体上移动到第一个可用的垂直对齐位置。

5. 按 **Ctrl** + **向右箭头** 直到控件到达窗体的一侧。 请注意，它在窗体中移动时所占据的位置。

6. 使用箭头键的组合在窗体周围移动控件。 请注意控件占据的位置以及伴随控件的对齐线。

7. 按 **Shift** + **箭头键** 可按 <xref:System.Windows.Forms.Button> 一个像素的增量调整控件的大小。

8. 按 **Ctrl** + **Shift** + **箭头键** 可 <xref:System.Windows.Forms.Button> 在对齐线增量中调整控件的大小。

## <a name="selectively-disable-snaplines"></a>有选择地禁用对齐线

1. 从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。

2. 在“工具箱” <xref:System.Windows.Forms.Button>**中，双击** 控件图标。 请注意，新的按钮控件出现在 <xref:System.Windows.Forms.TableLayoutPanel> 控件的第一个单元格中。

3. 再次双击 <xref:System.Windows.Forms.Button> **工具箱** 中的控件图标。 这会在控件中保留一个空单元 <xref:System.Windows.Forms.TableLayoutPanel> 。

4. 将 <xref:System.Windows.Forms.Button> 控件从 " **工具箱** " 拖到控件的空单元中 <xref:System.Windows.Forms.TableLayoutPanel> 。 请注意，不会显示对齐线。

5. 将 <xref:System.Windows.Forms.Button> 控件拖出 <xref:System.Windows.Forms.TableLayoutPanel> 控件，并将其移动到 <xref:System.Windows.Forms.TableLayoutPanel> 控件上。 请注意，对齐线将再次出现。

## <a name="disable-snaplines"></a>禁用对齐线

按 **Alt** 键，同时在窗体中移动控件。

不会出现对齐线，并且控件不会对齐任何可能的对齐位置。

### <a name="to-disable-snaplines-in-the-design-environment"></a>禁用设计环境中的对齐线

1. 从 " **工具** " 菜单中，打开 " **选项** " 对话框。 选择 **Windows 窗体设计器**。

2. 选择 " **常规** " 节点。 在 " **布局模式** " 部分中，将所选内容从 **对齐线** 更改为 " **对齐**"。

3. 选择 **"确定"** 以应用设置。

4. 选择窗体上的控件，并将其移动到其他控件上。 请注意，不会显示对齐线。

## <a name="next-steps"></a>后续步骤

对齐线提供了在窗体上对齐控件的直观方式。 建议了解的其他内容包括：

- 尝试将 <xref:System.Windows.Forms.GroupBox> 控件嵌套在另一个 <xref:System.Windows.Forms.GroupBox> 控件中。 将 <xref:System.Windows.Forms.Button> 控件置于子控件内，并将其放在 <xref:System.Windows.Forms.GroupBox> 父 <xref:System.Windows.Forms.GroupBox> 控件中。 移动 <xref:System.Windows.Forms.Button> 控件以查看对齐线跨容器边界的方式。

- 创建列 <xref:System.Windows.Forms.TextBox> 控件和相应的 <xref:System.Windows.Forms.Label> 控件列。 将控件的属性值设置 <xref:System.Windows.Forms.Label> <xref:System.Windows.Forms.Control.AutoSize%2A> 为 `true` 。 使用对齐线移动 <xref:System.Windows.Forms.Label> 控件，使其显示的文本与控件中的文本对齐 <xref:System.Windows.Forms.TextBox> 。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Design.Behavior.SnapLine>
- [演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [演练：使用 Padding、Margins 和 AutoSize 属性对 Windows 窗体控件进行布局](windows-forms-controls-padding-autosize.md)
