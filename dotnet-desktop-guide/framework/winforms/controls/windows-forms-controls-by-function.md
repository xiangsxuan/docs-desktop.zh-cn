---
title: 按函数控制
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- controls [Windows Forms], by function
- Windows Forms, controls by function
- Windows Forms controls, list of
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
ms.openlocfilehash: edd11f865a033148c780edee53e4a677c28377b1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972475"
---
# <a name="windows-forms-controls-by-function"></a>根据功能列出的 Windows 窗体控件
Windows 窗体提供了执行多个函数的控件和组件。 下表根据常规函数列出了 Windows 窗体控件和组件。 此外，如果存在多个提供同一功能的控件，则会列出推荐的控件，其中包含有关它所取代的控件的说明。 在一个单独的后续表中，将列出被取代的控件及其建议的替换项。  
  
> [!NOTE]
> 下表不列出可在 Windows 窗体中使用的每个控件或组件;有关更全面的列表，请参阅 [Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)  
  
## <a name="recommended-controls-and-components-by-function"></a>推荐的控件和组件（按功能）  
  
|函数|控制|描述|  
|--------------|-------------|-----------------|  
|数据显示|<xref:System.Windows.Forms.DataGridView> 控件|<xref:System.Windows.Forms.DataGridView>控件提供了一个可自定义的表来显示数据。 <xref:System.Windows.Forms.DataGridView>类启用单元格、行、列和边框的自定义。 **注意：** <xref:System.Windows.Forms.DataGridView> 控件提供了许多控件中缺少的基本功能和高级功能 <xref:System.Windows.Forms.DataGrid> 。 有关详细信息，请参阅 [Windows 窗体 DataGridView 和 DataGrid 控件之间的差异](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)|  
|数据绑定和导航|<xref:System.Windows.Forms.BindingSource> 组件|通过提供货币管理、更改通知和其他服务，简化窗体上的控件与数据的绑定。|  
||<xref:System.Windows.Forms.BindingNavigator> 控件|提供用于在窗体上导航和操作数据的工具栏类型接口。|  
|文本编辑|<xref:System.Windows.Forms.TextBox> 控件|显示在设计时输入的文本，用户可以在运行时编辑该文本或以编程方式进行更改。|  
||<xref:System.Windows.Forms.RichTextBox> 控件|允许文本以纯文本格式或 rtf 格式 (格式显示) 。|  
||<xref:System.Windows.Forms.MaskedTextBox> 控件|限制用户输入的格式|  
|信息显示 (只读) |<xref:System.Windows.Forms.Label> 控件|显示用户无法直接编辑的文本。|  
||<xref:System.Windows.Forms.LinkLabel> 控件|将文本显示为 Web 样式的链接，并在用户单击特殊文本时触发事件。 通常，文本是指向另一个窗口或网站的链接。|  
||<xref:System.Windows.Forms.StatusStrip> 控件|使用带有框架的区域（通常位于父窗体的底部）显示有关应用程序的当前状态的信息。|  
||<xref:System.Windows.Forms.ProgressBar> 控件|向用户显示操作的当前进度。|  
|网页显示|<xref:System.Windows.Forms.WebBrowser> 控件|使用户能够在你的窗体中导航网页。|  
|从列表中选择|<xref:System.Windows.Forms.CheckedListBox> 控件|显示项的可滚动列表，每个项都带有一个复选框。|  
||<xref:System.Windows.Forms.ComboBox> 控件|显示项的下拉列表。|  
||<xref:System.Windows.Forms.DomainUpDown> 控件|显示用户可使用向上和向下按钮滚动的文本项的列表。|  
||<xref:System.Windows.Forms.ListBox> 控件|显示 (图标) 文本和图形项的列表。|  
||<xref:System.Windows.Forms.ListView> 控件|以四种不同视图之一显示项。 视图包含纯文本、带有小图标的文本、带有大图标的文本和详细信息视图。|  
||<xref:System.Windows.Forms.NumericUpDown> 控件|显示用户可使用向上和向下按钮滚动的数字列表。|  
||<xref:System.Windows.Forms.TreeView> 控件|显示节点对象的分层集合，这些对象可以包含具有可选复选框或图标的文本。|  
|图形显示|<xref:System.Windows.Forms.PictureBox> 控件|在框架中显示图形文件（如位图和图标）。|  
|图形存储|<xref:System.Windows.Forms.ImageList> 控件|用作映像的存储库。 <xref:System.Windows.Forms.ImageList> 控件及其包含的图像可在应用程序之间重复使用。|  
|值设置|<xref:System.Windows.Forms.CheckBox> 控件|显示一个复选框和一个文本标签。 通常用于设置选项。|  
||<xref:System.Windows.Forms.CheckedListBox> 控件|显示项的可滚动列表，每个项都带有一个复选框。|  
||<xref:System.Windows.Forms.RadioButton> 控件|显示可以打开或关闭的按钮。|  
||<xref:System.Windows.Forms.TrackBar> 控件|允许用户通过在刻度上移动 "thumb" 来设置刻度值。|  
|日期设置|<xref:System.Windows.Forms.DateTimePicker> 控件|显示一个图形日历，以允许用户选择日期或时间。|  
||<xref:System.Windows.Forms.MonthCalendar> 控件|显示一个图形日历，以允许用户选择日期范围。|  
|对话框|<xref:System.Windows.Forms.ColorDialog> 控件|显示 "颜色选取器" 对话框，该对话框允许用户设置 interface 元素的颜色。|  
||<xref:System.Windows.Forms.FontDialog> 控件|显示一个对话框，允许用户设置字体及其特性。|  
||<xref:System.Windows.Forms.OpenFileDialog> 控件|显示一个对话框，使用户可以导航到文件并选择该文件。|  
||<xref:System.Windows.Forms.PrintDialog> 控件|显示一个对话框，允许用户选择打印机并设置其属性。|  
||<xref:System.Windows.Forms.PrintPreviewDialog> 控件|显示一个对话框，该对话框显示控件 <xref:System.Drawing.Printing.PrintDocument> 组件在打印时的显示方式。|  
||<xref:System.Windows.Forms.FolderBrowserDialog> 控件|显示一个对话框，该对话框允许用户浏览、创建和最终选择文件夹|  
||<xref:System.Windows.Forms.SaveFileDialog> 控件|显示一个对话框，允许用户保存文件。|  
|Menu 控件|<xref:System.Windows.Forms.MenuStrip> 控件|创建自定义菜单。 **注意：** <xref:System.Windows.Forms.MenuStrip> 旨在替换 <xref:System.Windows.Forms.MainMenu> 控件。|  
||<xref:System.Windows.Forms.ContextMenuStrip> 控件|创建自定义上下文菜单。 **注意：** <xref:System.Windows.Forms.ContextMenuStrip> 旨在替换 <xref:System.Windows.Forms.ContextMenu> 控件。|  
|命令|<xref:System.Windows.Forms.Button> 控件|启动、停止或中断进程。|  
||<xref:System.Windows.Forms.LinkLabel> 控件|将文本显示为 Web 样式的链接，并在用户单击特殊文本时触发事件。 通常，文本是指向另一个窗口或网站的链接。|  
||<xref:System.Windows.Forms.NotifyIcon> 控件|在任务栏的状态通知区域中显示一个图标，该图标表示在后台运行的应用程序。|  
||<xref:System.Windows.Forms.ToolStrip> 控件|创建可具有 Microsoft Windows XP、Microsoft Office、Microsoft Internet Explorer 或自定义外观的工具栏，无论有无主题，还支持溢出和运行时项重新排序。 **注意：** <xref:System.Windows.Forms.ToolStrip> 控件设计为替换 <xref:System.Windows.Forms.ToolBar> 控件。|  
|用户帮助|<xref:System.Windows.Forms.HelpProvider> 组件|为控件提供弹出帮助或联机帮助。|  
||<xref:System.Windows.Forms.ToolTip> 组件|提供一个弹出窗口，该窗口在用户将指针悬停在控件上时显示控件用途的简短说明。|  
|分组其他控件|<xref:System.Windows.Forms.Panel> 控件|对未标记的可滚动帧上的一组控件进行分组。|  
||<xref:System.Windows.Forms.GroupBox> 控件|对一组控件进行分组， (如) 标记的非滚动框架上的单选按钮。|  
||<xref:System.Windows.Forms.TabControl> 控件|提供用于有效地组织和访问分组对象的选项卡式页面。|  
||<xref:System.Windows.Forms.SplitContainer> 控件|提供由可移动栏分隔的两个面板。 **注意：** <xref:System.Windows.Forms.SplitContainer> 控件设计为替换 <xref:System.Windows.Forms.Splitter> 控件。|  
||<xref:System.Windows.Forms.TableLayoutPanel> 控件|表示一个面板，它可以在一个由行和列组成的网格中对其内容进行动态布局。|  
||<xref:System.Windows.Forms.FlowLayoutPanel> 控件|表示以水平或垂直方式动态布置其内容的面板。|  
|音频|<xref:System.Media.SoundPlayer> 控件|播放 .wav 格式的声音文件。 可以异步加载或播放声音。|  
  
## <a name="superseded-controls-and-components-by-function"></a>被取代的控件和组件按功能  
  
|函数|取代控件|推荐的替换控件|  
|--------------|------------------------|-----------------------------|  
|数据显示|<xref:System.Windows.Forms.DataGrid>|<xref:System.Windows.Forms.DataGridView>|  
| (只读控件的信息显示) |<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Menu 控件|<xref:System.Windows.Forms.ContextMenu>|<xref:System.Windows.Forms.ContextMenuStrip>|  
||<xref:System.Windows.Forms.MainMenu>|<xref:System.Windows.Forms.MenuStrip>|  
|命令|<xref:System.Windows.Forms.ToolBar>|<xref:System.Windows.Forms.ToolStrip>|  
||<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|窗体布局|<xref:System.Windows.Forms.Splitter>|<xref:System.Windows.Forms.SplitContainer>|  
  
## <a name="see-also"></a>另请参阅

- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
- [使用 .NET Framework 开发自定义 Windows 窗体控件](developing-custom-windows-forms-controls.md)
