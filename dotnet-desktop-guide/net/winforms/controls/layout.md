---
title: 控件布局选项
description: 了解控件上的各种设置，这些设置会影响适用于 .NET 的 Windows 窗体中的布局和位置。 了解影响布局的各种控件容器。
ms.date: 10/26/2020
ms.topic: overview
helpviewer_keywords:
- forms [Windows Forms], aligning controls
- Windows Forms, aligning controls
- controls [Windows Forms], positioning
- controls [Windows Forms], aligning
- TabControl control [Windows Forms], about TabControl control
- SplitContainer control [Windows Forms], about SplitContainer control
- Panel control [Windows Forms], about Panel control
- GroupBox control [Windows Forms], about GroupBox control
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
- sizing [Windows Forms], automatic
- layout [Windows Forms], AutoSize
- automatic sizing
- AutoSizeMode property
ms.openlocfilehash: 542decdf2555dcc01ff544a370f59ac73269ab6c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941927"
---
# <a name="position-and-layout-of-controls-windows-forms-net"></a>控件的位置和布局（Windows 窗体 .NET）

Windows 窗体中的控件位置不仅由控件确定，还由控件的父级确定。 本文介绍了控件上的各种设置，以及影响布局的各种父级容器。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="fixed-position-and-size"></a>固定位置和大小

控件在父级上的位置由父级表面左上角的 <xref:System.Windows.Forms.Control.Location> 属性的值确定。 父级中左上角的位置坐标为 `(x0,y0)`。 控件的大小由 <xref:System.Windows.Forms.Control.Size> 属性确定，表示控件的宽度和高度。

:::image type="content" source="media/layout/location+container.png" alt-text="相对于容器的控件位置":::

将控件添加到强制执行自动放置的父级时，控件的位置和大小将发生变化。 在这种情况下，可能无法手动调整控件的位置和大小，具体取决于父级的类型。

<xref:System.Windows.Forms.Control.MaximumSize%2A> 和 <xref:System.Windows.Forms.Control.MinimumSize%2A> 属性有助于设置控件可利用的最小和最大空间。

## <a name="automatic-placement-and-size"></a>自动放置和大小

控件可以自动放置在其父级中。 某些父级容器会强制放置，而另一些容器会遵循指导放置的控件设置。 控件上有两个属性可帮助在父级中实现自动放置和自动调整大小，它们是 <xref:System.Windows.Forms.Control.Dock%2A> 和 <xref:System.Windows.Forms.Control.Anchor>。

拖动顺序可影响自动放置。 控件的拖动顺序由父级 <xref:System.Windows.Forms.Control.Controls> 集合中控件的索引确定。 此索引称为 :::no-loc text="Z-order":::。 每个控件都按其在集合中的相反顺序进行拖动。 这意味着，该集合是先入后出、后入先出的集合。

<xref:System.Windows.Forms.Control.MinimumSize%2A> 和 <xref:System.Windows.Forms.Control.MaximumSize%2A> 属性有助于设置控件可利用的最小和最大空间。

### <a name="dock"></a>程序坞

`Dock` 属性可设置控件的哪个边与父级的对应边对齐，以及如何在父级中调整控件的大小。

:::image type="content" source="media/layout/dock-modes.png" alt-text="Windows 窗体，其按钮具有停靠设置。":::

停靠控件时，容器将确定控件应占据的空间，然后调整其大小并放置。 基于停靠样式，仍采用控件的宽度和高度。 例如，如果将控件停靠在顶部，则采用控件的 <xref:System.Windows.Forms.Control.Height>，但自动调整 <xref:System.Windows.Forms.Control.Width>。 如果将控件停靠在左侧，则采用控件的 <xref:System.Windows.Forms.Control.Width>，但自动调整 <xref:System.Windows.Forms.Control.Height>。

无法手动设置控件的 <xref:System.Windows.Forms.Control.Location>，因为停靠控件将自动控制其位置。

控件的 :::no-loc text="Z-order"::: 会影响停靠。 对停靠后的控件进行布局时将占用可用空间。 例如，如果控件先出并停靠在顶部，则它将占用容器的整个宽度。 如果下一个控件停靠在左侧，则它可占用的垂直空间会更少。

:::image type="content" source="media/layout/dock-top-then-left.png" alt-text="Windows 窗体，其按钮停靠在左侧和顶部，且顶部按钮更大。":::

如果将控件的 :::no-loc text="Z-order"::: 颠倒，则停靠在左侧的控件现将具有更多的初始可用空间。 控件使用容器的整个高度。 停靠在顶部的控件的可用水平空间更少。

:::image type="content" source="media/layout/dock-left-then-top.png" alt-text="Windows 窗体，其按钮停靠在左侧和顶部，且左侧按钮更大。":::

随着容器增大和缩小，停靠在容器上的控件将重新定位并调整大小，以保持其位置和大小处于适当状态。

:::image type="content" source="media/layout/dock-resize.gif" alt-text="显示如何对在所有位置上都停靠了按钮的 Windows 窗体调整大小的动画。":::

如果多个控件停靠在容器的同一侧，则根据其 :::no-loc text="Z-order"::: 将其堆叠。

:::image type="content" source="media/layout/dock-left-left.png" alt-text="Windows 窗体，其中两个按钮停靠在左侧。":::

### <a name="anchor"></a>定位点

通过定位控件，可将控件绑定到父级容器的一侧或多侧。 容器尺寸发生变化时，任何子级控件都将保持其与定位侧的距离。

控件可以定位到一侧或多侧，不存在限制。 定位点由 <xref:System.Windows.Forms.Control.Anchor> 属性设置。

:::image type="content" source="media/layout/anchor-resize.gif" alt-text="显示如何对在所有位置上都定位了按钮的 Windows 窗体调整大小的动画。":::

### <a name="automatic-sizing"></a>自动调整大小

必要情况下，可使用 <xref:System.Windows.Forms.Control.AutoSize> 属性更改控件的大小，以适应 <xref:System.Windows.Forms.Control.PreferredSize> 属性指定的大小。 可通过设置 `AutoSizeMode` 属性来调整特定控件的调整大小行为。

仅某些控件支持 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性。 此外，支持 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性的某些控件也支持 `AutoSizeMode` 属性。

| Always true 行为 | 描述 |
|--|--|
| 自动调整大小是一种运行时间功能。 | 这意味着它永远不会增大或缩小控件，因此不会产生进一步的影响。 |
| 即使控件更改大小，它的 <xref:System.Windows.Forms.Control.Location%2A> 属性的值也始终保持不变。 | 控件的内容导致控件增大时，控件将向右和向下扩展。 控件不会向左侧扩展。 |
| <xref:System.Windows.Forms.Control.AutoSize%2A> 为 `true` 时，采用 <xref:System.Windows.Forms.Control.Dock%2A> 和 <xref:System.Windows.Forms.Control.Anchor%2A> 属性。 | 控件的 <xref:System.Windows.Forms.Control.Location%2A> 属性的值将调整为正确值。<br /><br /> <xref:System.Windows.Forms.Label> 控件是此项规则的例外情况。 将停靠的 <xref:System.Windows.Forms.Label> 控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性的值设置为 `true` 时，<xref:System.Windows.Forms.Label> 控件将不会拉伸。 |
| 无论控件的 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性的值如何，始终采用其 <xref:System.Windows.Forms.Control.MaximumSize%2A> 和 <xref:System.Windows.Forms.Control.MinimumSize%2A> 属性。 | <xref:System.Windows.Forms.Control.MaximumSize%2A> 和 <xref:System.Windows.Forms.Control.MinimumSize%2A> 属性不受 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性的影响。 |
| 默认情况下，不设置最小大小。 | 这意味着，如果在 <xref:System.Windows.Forms.Control.AutoSize%2A> 下方将控件设置为缩小，且不包含任何内容，则其 <xref:System.Windows.Forms.Control.Size%2A> 属性的值为 `(0x,0y)`。 在这种情况下，控件将缩小为点，且不明显可见。 |
| 如果控件未实现 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 方法，则 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 方法将返回分配给 <xref:System.Windows.Forms.Control.Size%2A> 属性的最后一个值。 | 这意味着将 <xref:System.Windows.Forms.Control.AutoSize%2A> 设置为 `true` 无效。 |
| <xref:System.Windows.Forms.TableLayoutPanel> 单元格中的控件始终会缩小以适应单元格，直到达到其 <xref:System.Windows.Forms.Control.MinimumSize%2A>。 | 此大小强制作为最大大小。 如果单元格属于 <xref:System.Windows.Forms.SizeType.AutoSize> 行或列，则不会出现这种情况。 |

## <a name="container-form"></a>容器：窗体

<xref:System.Windows.Forms.Form> 是 Windows 窗体的主要对象。 Windows 窗体应用程序通常会始终显示窗体。 窗体包含控件，并采用控件的 <xref:System.Windows.Forms.Control.Location> 和 <xref:System.Windows.Forms.Control.Size> 属性来实现手动放置。 窗体还响应 [Dock](#dock) 属性，以实现自动放置。

多数情况下，窗体边缘带有手柄，用户可使用这些手柄调整窗体的大小。 控件的 <xref:System.Windows.Forms.Control.Anchor> 属性允许控件在调整窗体大小时增大和缩小。

## <a name="container-panel"></a>容器：Panel

<xref:System.Windows.Forms.Panel> 控件类似于直接将控件组合在一起的窗体。 它支持窗体所支持的手动和自动放置样式。 有关更多信息，请参见[容器：窗体](#container-form)部分。

面板与父级无缝相融，并切断超出面板边界的控件的任何区域。 如果控件在面板边界之外，且 <xref:System.Windows.Forms.Form.AutoScroll> 设置为 `true`，则会显示滚动条，并且用户可以滚动面板。

与[分组框](#container-group-box)控件不同，面板没有描述文字和边界。

:::image type="content" source="media/layout/panel-groupbox.png" alt-text="Windows 窗体，带有面板和分组框。":::

上图的面板设置了 <xref:System.Windows.Forms.Panel.BorderStyle%2A> 属性，以演示面板的边界。

## <a name="container-group-box"></a>容器：分组框

<xref:System.Windows.Forms.GroupBox> 控件为其他控件提供可识别分组。 通常，可使用分组框按功能细分窗体。 例如，窗体可能显示个人信息，并且与地址有关的字段将组合在一起。 设计时，可轻松移动分组框及其包含的控件。

分组框支持窗体所支持的手动和自动放置样式。 有关更多信息，请参见[容器：窗体](#container-form)部分。 分组框还会切断控件超出面板边界的任何部分。

与[面板](#container-panel)控件不同，分组框无法滚动内容和显示滚动条。

:::image type="content" source="media/layout/panel-groupbox.png" alt-text="Windows 窗体，带有面板和分组框。":::

## <a name="container-flow-layout"></a>容器：流布局

<xref:System.Windows.Forms.FlowLayoutPanel> 控件沿水平或纵排方向排列其内容。 可从一行到下一行，或从一列到下一列来进行控件内容换行。 或者，可以剪切其内容，而非进行换行。  
  
可以通过设置 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> 属性的值来指定排列方向。 <xref:System.Windows.Forms.FlowLayoutPanel> 控件在从右到左 (RTL) 布局中正确地反转其排列方向。 也可通过设置 <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> 属性的值来指定是对 <xref:System.Windows.Forms.FlowLayoutPanel> 控件的内容进行换行还是剪切。  

将 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性设置为 `true` 时，<xref:System.Windows.Forms.FlowLayoutPanel> 控件自动调整根据其内容调整大小。 它还为其子控件提供了 `FlowBreak` 属性。 将 `FlowBreak` 属性的值设置为 `true` 会使 <xref:System.Windows.Forms.FlowLayoutPanel> 控件停止按当前排列方向对控件进行布局，并换行到下一行或下一列。  

:::image type="content" source="media/layout/flow.png" alt-text="Windows 窗体，带有两个流面板控件。":::

上图的两个 `FlowLayoutPanel` 控件设置了 <xref:System.Windows.Forms.Panel.BorderStyle> 属性，以演示控件的边界。

## <a name="container-table-layout"></a>容器：表格布局

<xref:System.Windows.Forms.TableLayoutPanel> 控件将其内容排列在网格中。 由于布局是同时在设计时和运行时执行的，因此它可随应用程序环境的变化而动态地变化。 这使得面板中的控件能够按比例调整大小，以便能够响应更改（例如父控件的大小调整或本地化产生的文本长度更改）。

任何 Windows 窗体控件均可以是 <xref:System.Windows.Forms.TableLayoutPanel> 控制的子控件，包括 <xref:System.Windows.Forms.TableLayoutPanel> 的其他实例。 这使你可以构造适应在运行时发生更改的复杂布局。

在 <xref:System.Windows.Forms.TableLayoutPanel> 控件充满子控件后，还可控制扩展的方向（水平或垂直）。 默认情况下，<xref:System.Windows.Forms.TableLayoutPanel> 控件通过添加行向下扩展。

可以使用 <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> 和 <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> 属性来控制行和列的大小和样式。 可分别设置行或列的属性。

<xref:System.Windows.Forms.TableLayoutPanel> 控件将以下属性添加到其子控件中：`Cell`、`Column`、`Row`、`ColumnSpan` 和 `RowSpan`。

:::image type="content" source="media/layout/table.png" alt-text="Windows 窗体，带有表格布局控件。":::

上图的表格设置了 <xref:System.Windows.Forms.TableLayoutPanel.CellBorderStyle> 属性，以演示每个单元格的边界。

## <a name="container-split-container"></a>容器：拆分容器

Windows 窗体 <xref:System.Windows.Forms.SplitContainer> 控件可视为一个复合控件；它是由可移动条隔开的两个面板。 当鼠标指针位于条上方时，指针将改变形状以表示条可移动。  

<xref:System.Windows.Forms.SplitContainer> 控件可用于创建复杂的用户界面；通常情况下，在一个面板中的选择将决定显示在另一个面板中的对象。 这种安排对于显示和浏览信息有效。 拥有两个面板使你能够在区域、条或“拆分器”中聚合信息，使用户可轻松地调整面板大小。

:::image type="content" source="media/layout/splitcontainer.png" alt-text="Windows 窗体，带有嵌套的拆分容器。":::

上图的拆分容器用于创建左右窗格。 右窗格包含第二个拆分容器，其中 <xref:System.Windows.Forms.SplitContainer.Orientation> 设置为 <xref:System.Windows.Forms.Orientation.Vertical>。 设置 <xref:System.Windows.Forms.SplitContainer.BorderStyle> 属性，以演示每个面板的边界。

## <a name="container-tab-control"></a>容器：Tab 控件

<xref:System.Windows.Forms.TabControl> 显示多个选项卡，就像笔记本中的分隔线或档案柜中一组文件夹的标签。 选项卡可以包含图片和其他控件。 使用选项卡控件可生成多页对话框，该对话框可在 Windows 操作系统中的许多位置显示，例如“控制面板”和“显示属性”。 此外，<xref:System.Windows.Forms.TabControl> 可用于创建属性页面，该页面用于设置一组相关属性。

<xref:System.Windows.Forms.TabControl> 最重要的属性是 <xref:System.Windows.Forms.TabControl.TabPages%2A>，其中包含各个选项卡。 每个选项卡都是 <xref:System.Windows.Forms.TabPage> 对象。

:::image type="content" source="media/layout/tabcontrol.png" alt-text="Windows 窗体，其中选项卡控件带有两个选项卡页。":::
