---
title: 使用自动布局概述
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: 471deeb6cc19ff8d31caa7c1ea122b3f50754bec
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664062"
---
# <a name="use-automatic-layout-overview"></a>使用自动布局概述

本主题介绍了有关如何编写 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 具有可本地化的用户界面)  (ui 的应用程序的指南。 过去，UI 的本地化是一个耗时的过程。 UI 调整的每种语言都需要像素的像素调整。 如今，使用正确的设计和右编码标准，可以构造 Ui，使本地化人员可以更少地调整大小和重新定位。 编写可以更方便地调整大小和重新定位的应用程序的方法称为自动布局，可以使用 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序设计实现此目的。

<a name="advantages_of_autolayout"></a>

## <a name="advantages-of-using-automatic-layout"></a>使用自动布局的优点

由于 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 呈现系统功能强大且灵活，因此它提供了在应用程序中布局元素的功能，可以根据不同语言的要求进行调整。 下面列出自动布局的部分优点。

- UI 以任何语言正确显示。

- 减少了文本转换完后重新调整控件位置和大小的需要。

- 减少了重新调整窗口大小的需要。

- UI 布局在任何语言中都正确呈现。

- 本地化过程可缩减为与进行字符串转换差不多。

<a name="autolayout_controls"></a>

## <a name="automatic-layout-and-controls"></a>自动布局和控件

利用自动布局，应用程序可以自动调整控件大小。 例如，控件可按字符串长度相应改变。 利用此功能，本地化人员可转换字符串，而无需再调整控件大小以适应转换后的文本。 下面的示例创建一个带有英文内容的按钮。

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]

在此示例中，只需更改文本即可生成一个西班牙文按钮。 例如，

[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]

下图显示了代码示例的输出：

![具有不同语言的文本的同一按钮](./media/use-automatic-layout-overview/auto-resizable-button.png)

<a name="autolayout_coding"></a>

## <a name="automatic-layout-and-coding-standards"></a>自动布局和编码标准

使用自动布局方法需要一组编码和设计标准和规则，以生成可完全本地化的 UI。 下列准则可帮助完成自动布局编码。

**不要使用绝对位置**

- 不要使用 <xref:System.Windows.Controls.Canvas> ，因为它以绝对方式定位元素。

- 使用 <xref:System.Windows.Controls.DockPanel> 、 <xref:System.Windows.Controls.StackPanel> 和 <xref:System.Windows.Controls.Grid> 定位控件。

有关各种面板的讨论，请参阅 [面板概述](../controls/panels-overview.md)。

**不要为窗口设置固定大小**

- 使用 <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>。 例如：

  [!code-xaml[LocalizationGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

**添加 <xref:System.Windows.FrameworkElement.FlowDirection%2A>**

- 将添加 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 到应用程序的根元素。

  WPF 提供了一种简便的方法来支持水平、双向和垂直布局。 在表示框架中， <xref:System.Windows.FrameworkElement.FlowDirection%2A> 属性可用于定义布局。 流方向模式包括：

  - <xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) —拉丁语、东亚等的水平布局。

  - <xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb) -针对阿拉伯语、希伯来语等的双向。

**使用复合字体而不是物理字体**

- 对于复合字体， <xref:System.Windows.Controls.Control.FontFamily%2A> 无需本地化属性。

- 开发人员可以使用以下字体之一，也可以创建自己的字体。

  - Global User Interface
  - Global San Serif
  - Global Serif

**添加 xml： lang**

- `xml:lang`在 UI 的根元素中添加特性，如 `xml:lang="en-US"` 用于英语应用程序的。

- 由于复合字体使用 `xml:lang` 来确定要使用的字体，因此请将此属性设置为支持多语言方案。

<a name="autolay_grids"></a>

## <a name="automatic-layout-and-grids"></a>自动布局和网格

<xref:System.Windows.Controls.Grid>元素对于自动布局非常有用，因为它允许开发人员定位元素。 <xref:System.Windows.Controls.Grid>控件可以使用列和行排列在其子元素之间分布可用空间。 UI 元素可以跨多个单元格，并且可以在网格中包含网格。 网格非常有用，因为它们使你能够创建和定位复杂的 UI。 下面的示例演示使用网格来定位某些按钮和文本。 请注意，单元格的高度和宽度设置为 <xref:System.Windows.GridUnitType.Auto> ; 因此，包含带图像按钮的单元格会调整以适应图像。

[!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]

下图显示了以上代码生成的网格。

![网格示例](./media/glob-grid.png "glob_grid") 格

<a name="autolay_grids_issharedsizescope"></a>

## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a>使用 IsSharedSizeScope 属性的自动布局和网格

<xref:System.Windows.Controls.Grid>元素在可本地化的应用程序中非常有用，可以创建调整以适应内容的控件。 不过，有时可能希望控件无论包含什么内容都可以保持特定大小。 例如，对于“确定”、“取消”和“浏览”按钮，可能不希望按钮根据内容调整大小。 在这种情况下， <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> 附加属性可用于在多个网格元素之间共享相同的大小。 下面的示例演示如何在多个元素之间共享列和行大小调整数据 <xref:System.Windows.Controls.Grid> 。

[!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]

> [!NOTE]
> 有关完整的代码示例，请参阅 [在网格之间共享大小调整属性](../controls/how-to-share-sizing-properties-between-grids.md)。

## <a name="see-also"></a>请参阅

- [WPF 的全球化](globalization-for-wpf.md)
- [使用自动布局创建按钮](how-to-use-automatic-layout-to-create-a-button.md)
- [使用网格进行自动布局](how-to-use-a-grid-for-automatic-layout.md)
