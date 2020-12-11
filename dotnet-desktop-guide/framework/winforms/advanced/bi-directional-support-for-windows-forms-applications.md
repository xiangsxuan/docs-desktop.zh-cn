---
title: Bi-Directional 支持
ms.date: 09/30/2017
helpviewer_keywords:
- globalization [Windows Forms], bi-directional support in Windows
- Windows Forms, international
- localization [Windows Forms], bi-directional support in Windows
- bi-directional language support [Windows Forms], Windows applications
- Windows Forms, bi-directional support
ms.openlocfilehash: 7d1fcacece1f84c95419b3f3f8b67e3b789e0c19
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970690"
---
# <a name="bi-directional-support-for-windows-forms-applications"></a>Windows 窗体应用程序的双向支持

你可以使用 Visual Studio 来创建基于 Windows 的应用程序，这些应用程序支持以双向 (从右到左的语言（如阿拉伯语和希伯来语）) 语言。 这包括标准窗体、对话框、MDI 窗体以及可在这些窗体中使用的所有控件 — 即，<xref:System.Windows.Forms.Control> 命名空间中的所有对象。

## <a name="culture-support"></a>区域性支持

 区域性和 UI 区域性设置确定应用程序如何使用日期、时间、货币和其他信息。 区域性和 UI 区域性对双向语言的支持与对其他所有语言的支持相同。 有关详细信息，请参阅 [适用于全局 Windows 窗体和 web 窗体的区域性特定类](/visualstudio/ide/globalizing-and-localizing-applications)。

## <a name="righttoleft-and-righttoleftlayout-properties"></a>RightToLeft 和 RightToLeftLayout 属性

 可派生设备的 <xref:System.Windows.Forms.Control> 基类包含可设置用于更改窗体及其控件阅读顺序的 <xref:System.Windows.Forms.Control.RightToLeft%2A> 属性。 如果设置窗体的 <xref:System.Windows.Forms.Control.RightToLeft%2A> 属性，则默认情况下窗体上的控件将继承此设置。 但是，也可在大多数控件上单独设置 <xref:System.Windows.Forms.Control.RightToLeft%2A> 属性。 另请参阅[如何：为全球化在 Windows 窗体中按从右到左的顺序显示文本](/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))。

 <xref:System.Windows.Forms.Control.RightToLeft%2A> 属性对不同控件的影响可能各有不同。 在某些控件中此属性只设置阅读顺序，如 <xref:System.Windows.Forms.Button>、<xref:System.Windows.Forms.TreeView> 和 <xref:System.Windows.Forms.ToolTip> 控件。 在其他控件中，<xref:System.Windows.Forms.Control.RightToLeft%2A> 属性同时更改阅读顺序和布局。 这包括 <xref:System.Windows.Forms.RadioButton>、<xref:System.Windows.Forms.ComboBox> 和 <xref:System.Windows.Forms.CheckBox> 控件。 其他控件要求将 <xref:System.Windows.Forms.Form.RightToLeftLayout%2A> 属性用于从右到左镜像其布局。 下表提供了有关 <xref:System.Windows.Forms.Control.RightToLeft%2A> 和 <xref:System.Windows.Forms.Form.RightToLeftLayout%2A> 属性如何影响单个 Windows 窗体控件的详细信息。

|控件/组件|RightToLeft 属性的效果|RightToLeftLayout 属性的效果|是否需要镜像？|
|------------------------|------------------------------------|------------------------------------------|-------------------------|
|<xref:System.Windows.Forms.Button>|设置 RTL 阅读顺序。 反转 <xref:System.Windows.Forms.ButtonBase.TextAlign%2A>、<xref:System.Windows.Forms.ButtonBase.ImageAlign%2A> 和 <xref:System.Windows.Forms.ButtonBase.TextImageRelation%2A>|无影响|否|
|<xref:System.Windows.Forms.CheckBox>|复选框显示在文本右侧|无影响|否|
|<xref:System.Windows.Forms.CheckedListBox>|所有复选框均显示在文本右侧|无影响|否|
|<xref:System.Windows.Forms.ColorDialog>|无影响；取决于操作系统的语言|无影响|否|
|<xref:System.Windows.Forms.ComboBox>|组合框控件中的项呈右对齐|无影响|否|
|<xref:System.Windows.Forms.ContextMenu>|使用 RTL 阅读顺序呈右对齐显示|无影响|否|
|<xref:System.Windows.Forms.DataGrid>|使用 RTL 阅读顺序呈右对齐显示|无影响|否|
|<xref:System.Windows.Forms.DataGridView>|同时影响 RTL 阅读顺序和控件布局|无影响|否|
|<xref:System.Windows.Forms.DateTimePicker>|无影响；取决于操作系统的语言|镜像控件|是|
|<xref:System.Windows.Forms.DomainUpDown>|左对齐向上和向下按钮|无影响|否|
|<xref:System.Windows.Forms.ErrorProvider>|不支持|无影响|否|
|<xref:System.Windows.Forms.FontDialog>|取决于操作系统的语言|无影响|否|
|<xref:System.Windows.Forms.Form>|设置 RTL 阅读顺序，并反转滚动条|镜像窗体|是|
|<xref:System.Windows.Forms.GroupBox>|右对齐显示标题。 子控件可能继承此属性。|在控件内使用 <xref:System.Windows.Forms.TableLayoutPanel> 以获取从右到左的镜像支持|否|
|<xref:System.Windows.Forms.HScrollBar>|从滚动框（缩略图）右对齐开始|无影响|否|
|<xref:System.Windows.Forms.ImageList>|不是必需|无影响|否|
|<xref:System.Windows.Forms.Label>|右对齐显示。 反转 <xref:System.Windows.Forms.Label.TextAlign%2A> 和 <xref:System.Windows.Forms.Label.ImageAlign%2A>|无影响|否|
|<xref:System.Windows.Forms.LinkLabel>|右对齐显示。 反转 <xref:System.Windows.Forms.Label.TextAlign%2A> 和 <xref:System.Windows.Forms.Label.ImageAlign%2A>|无影响|否|
|<xref:System.Windows.Forms.ListBox>|项呈右对齐|无影响|否|
|<xref:System.Windows.Forms.ListView>|将阅读顺序设置为 RTL；元素保持左对齐|镜像控件|是|
|<xref:System.Windows.Forms.MainMenu>|在运行时（非设计时）按 RTL 阅读顺序呈右对齐显示|无影响|否|
|<xref:System.Windows.Forms.MaskedTextBox>|从右到左显示文本。|无影响|否|
|<xref:System.Windows.Forms.MonthCalendar>|无影响；取决于操作系统的语言|镜像控件|是|
|<xref:System.Windows.Forms.NotifyIcon>|不支持|不支持|否|
|<xref:System.Windows.Forms.NumericUpDown>|向上和向下按钮呈左对齐|无影响|否|
|<xref:System.Windows.Forms.OpenFileDialog>|在从右到左的操作系统上，将包含窗体的 <xref:System.Windows.Forms.Control.RightToLeft> 属性设置为使 <xref:System.Windows.Forms.RightToLeft.Yes?displayProperty=nameWithType> 对话框本地化 |无影响|否|
|<xref:System.Windows.Forms.PageSetupDialog>|无影响；取决于操作系统的语言|无影响|否|
|<xref:System.Windows.Forms.Panel>|子控件可能继承此属性|在控件内使用 <xref:System.Windows.Forms.TableLayoutPanel> 以获取从右到左的支持|是|
|<xref:System.Windows.Forms.PictureBox>|不支持|无影响|否|
|<xref:System.Windows.Forms.PrintDialog>|无影响；取决于操作系统的语言|无影响|否|
|<xref:System.Drawing.Printing.PrintDocument>|垂直滚动条呈左对齐，水平滚动条从左侧开始|无影响|否|
|<xref:System.Windows.Forms.PrintPreviewDialog>|不支持|不支持|否|
|<xref:System.Windows.Forms.ProgressBar>|不受此属性影响|镜像控件|是|
|<xref:System.Windows.Forms.RadioButton>|单选按钮显示在文本右侧|无影响|否|
|<xref:System.Windows.Forms.RichTextBox>|包含文本的控件元素按 RTL 阅读顺序从右到左显示|无影响|否|
|<xref:System.Windows.Forms.SaveFileDialog>|无影响；取决于操作系统的语言|无影响|否|
|<xref:System.Windows.Forms.SplitContainer>|反转显示面板布局；垂直滚动条显示在左侧；水平滚动条从右侧开始|使用 <xref:System.Windows.Forms.TableLayoutPanel> 镜像子控件的顺序|否|
|<xref:System.Windows.Forms.Splitter>|不支持|无影响|否|
|<xref:System.Windows.Forms.StatusBar>|不支持；请改用 <xref:System.Windows.Forms.StatusStrip>|无效果；请改用 <xref:System.Windows.Forms.StatusStrip>|否|
|<xref:System.Windows.Forms.TabControl>|不受此属性影响|镜像控件|是|
|<xref:System.Windows.Forms.TextBox>|按 RTL 阅读顺序从右到左显示文本|无影响|否|
|<xref:System.Windows.Forms.Timer>|不是必需|不是必需|否|
|<xref:System.Windows.Forms.ToolBar>|不受此属性影响；请改用 <xref:System.Windows.Forms.ToolStrip>|无效果；请改用 <xref:System.Windows.Forms.ToolStrip>|是|
|<xref:System.Windows.Forms.ToolTip>|设置 RTL 阅读顺序|无影响|否|
|<xref:System.Windows.Forms.TrackBar>|滚动或跟踪从右侧开始；<xref:System.Windows.Forms.TrackBar.Orientation%2A> 呈垂直时，计时周期数从右侧出现|无影响|否|
|<xref:System.Windows.Forms.TreeView>|仅设置 RTL 阅读顺序|镜像控件|是|
|<xref:System.Windows.Forms.UserControl>|垂直滚动条显示在左侧；水平滚动条右侧带有缩略图|不能直接支持；请使用 <xref:System.Windows.Forms.TableLayoutPanel>|否|
|<xref:System.Windows.Forms.VScrollBar>|可滚动控件显示在左侧（而不是右侧）|无影响|否|

## <a name="encoding"></a>编码

 Windows 窗体支持 Unicode，因此在创建双向应用程序时可包括任何字符集。 但是，并非所有 Windows 窗体控件在所有平台上均支持 Unicode。

## <a name="gdi"></a>GDI+

 您可以使用 GDI + 按从右到左的阅读顺序绘制文本。 用于绘制文本的 <xref:System.Drawing.Graphics.DrawString%2A> 方法支持 `StringFormat` 参数，可将此参数设置为 <xref:System.Drawing.StringFormatFlags> 枚举的 <xref:System.Drawing.StringFormatFlags.DirectionRightToLeft> 成员以反转文本的起点。

## <a name="common-dialog-boxes"></a>通用对话框

 “打开文件”对话框等系统工具由 Windows 控制。 它们都从操作系统继承语言元素。 如果使用的 Windows 版本具有正确的语言设置，则这些对话框将以双向语言正常工作。

 同样，消息框通过操作系统，并支持双向文本。 消息框按钮上的标题基于当前语言设置。 默认情况下，消息框不会使用从右到左的阅读顺序，但可指定参数以更改消息框显示时的阅读顺序。

## <a name="righttoleft-scrollbars-and-scrollablecontrol"></a>RightToLeft、滚动条和 ScrollableControl

 目前 Windows 窗受到如下限制：当 <xref:System.Windows.Forms.Control.RightToLeft%2A> 启用且 <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A>设置为 <xref:System.Windows.Forms.RightToLeft.Yes> 时，系统将阻止所有派生自 <xref:System.Windows.Forms.ScrollableControl> 的类正常运行。 例如，假设在窗体上放置了一个控件（如 <xref:System.Windows.Forms.Panel>）或派生自 <xref:System.Windows.Forms.Panel> 的一个容器类（如 <xref:System.Windows.Forms.FlowLayoutPanel> 或 <xref:System.Windows.Forms.TableLayoutPanel>）。 如果将容器上的 <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> 设置为 <xref:System.Windows.Forms.RightToLeft.Yes>，然后将容器内一个或多个控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性设置为 <xref:System.Windows.Forms.AnchorStyles.Right>，则不会出现任何滚动条。 派生自 <xref:System.Windows.Forms.ScrollableControl> 的类的运行方式与将 <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> 设置为 <xref:System.Windows.Forms.RightToLeft.No> 时相同。

 目前，唯一的解决方法是将 <xref:System.Windows.Forms.ScrollableControl> 嵌套到其他 <xref:System.Windows.Forms.ScrollableControl> 内。 例如，如果需要在此情况下运行 <xref:System.Windows.Forms.TableLayoutPanel>，可以将它置于 <xref:System.Windows.Forms.Panel> 控件中并将 <xref:System.Windows.Forms.Panel> 上的 <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> 设置为 <xref:System.Windows.Forms.RightToLeft.Yes>。

## <a name="mirroring"></a>镜像

 镜像是指反转 UI 元素布局，使其从右到左排列。 例如，在镜像的 Windows 窗体中，“最小化”、“最大化”和“关闭”按钮均显示在标题栏的最左侧，而不是最右侧。

 将窗体或控件的 <xref:System.Windows.Forms.Control.RightToLeft%2A> 属性设置为 `true` 可反转窗体上元素的阅读顺序，但此设置不会将布局反转为从右到左显示 — 也就是说，它不会导致镜像。 例如，设置此属性不会将窗体标题栏中的“最小化”、“最大化”和“关闭”按钮移动到窗体左侧。 同样，某些控件（如 <xref:System.Windows.Forms.TreeView> 控件）需要镜像来更改显示方式，以便适合于阿拉伯语或希伯来语。 可通过设置 <xref:System.Windows.Forms.Form.RightToLeftLayout%2A> 属性镜像这些控件。

 可创建以下控件的镜像版本：

- <xref:System.Windows.Forms.ColumnHeader.ListView%2A>

- <xref:System.Windows.Forms.Panel>

- <xref:System.Windows.Forms.StatusBar>

- <xref:System.Windows.Forms.TabControl>

- <xref:System.Windows.Forms.TabPage>

- <xref:System.Windows.Forms.ToolBar>

- <xref:System.Windows.Forms.TreeView>

 已封装某些控件。 因此，它们无法派生出新控件。 这些包括 <xref:System.Windows.Forms.ImageList> 和 <xref:System.Windows.Forms.ProgressBar> 控件。

## <a name="see-also"></a>另请参阅

- [ASP.NET Web 应用程序的双向支持](/previous-versions/aspnet/6eedwbtt(v=vs.100))
