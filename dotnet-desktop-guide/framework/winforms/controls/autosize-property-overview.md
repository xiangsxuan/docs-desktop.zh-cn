---
title: AutoSize 属性概述
ms.date: 03/30/2017
helpviewer_keywords:
- sizing [Windows Forms], automatic
- layout [Windows Forms], AutoSize
- automatic sizing
- AutoSizeMode property
ms.assetid: 62fd82a2-9565-4f65-925b-9d1e66dc4e7d
ms.openlocfilehash: eb87616c2ddcf9a4ab62245d365763ee57ffb964
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970732"
---
# <a name="autosize-property-overview"></a>AutoSize 属性概述
<xref:System.Windows.Forms.Control.AutoSize%2A>属性允许控件更改其大小（如有必要），以获得属性指定的值 <xref:System.Windows.Forms.Control.PreferredSize%2A> 。 可以通过设置属性来调整特定控件的大小调整行为 `AutoSizeMode` 。

## <a name="autosize-behavior"></a>自动调整大小行为
 只有某些控件支持 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性。 此外，某些支持属性的控件 <xref:System.Windows.Forms.Control.AutoSize%2A> 还支持 `AutoSizeMode` 属性。

 <xref:System.Windows.Forms.Control.AutoSize%2A>属性会生成一些不同的行为，具体取决于特定控件类型和属性的值 `AutoSizeMode` （如果该属性存在）。 下表介绍始终为 true 的行为，并提供每个行为的简要说明：

|始终为 true 行为|描述|
|--------------------------|-----------------|
|自动调整大小是一项运行时功能。|这意味着它永远不会增大或缩小控件，而不会进一步生效。|
|如果控件更改大小，则其属性的值 <xref:System.Windows.Forms.Control.Location%2A> 始终保持不变。|当控件的内容导致其增长时，控件向右和向下发展。 控件不会增长到左侧。|
|<xref:System.Windows.Forms.Control.Dock%2A> <xref:System.Windows.Forms.Control.Anchor%2A> 当为时，将接受和属性 <xref:System.Windows.Forms.Control.AutoSize%2A> `true` 。|控件的属性的值 <xref:System.Windows.Forms.Control.Location%2A> 会调整为正确的值。<br /><br /> **注意**<xref:System.Windows.Forms.Label>控件是此规则的例外情况。 将停靠控件的属性的值设置 <xref:System.Windows.Forms.Label> 为时 <xref:System.Windows.Forms.Control.AutoSize%2A> `true` ，该 <xref:System.Windows.Forms.Label> 控件将不拉伸。|
|无论控件的 <xref:System.Windows.Forms.Control.MaximumSize%2A> <xref:System.Windows.Forms.Control.MinimumSize%2A> 属性的值是什么，控件的和属性始终都有效 <xref:System.Windows.Forms.Control.AutoSize%2A> 。|<xref:System.Windows.Forms.Control.MaximumSize%2A>和 <xref:System.Windows.Forms.Control.MinimumSize%2A> 属性不受属性的影响 <xref:System.Windows.Forms.Control.AutoSize%2A> 。|
|默认情况下没有设置最小大小。|这意味着，如果控件设置为在下收缩 <xref:System.Windows.Forms.Control.AutoSize%2A> 并且它没有内容，则其属性的值 <xref:System.Windows.Forms.Control.Size%2A> 为0，0。 在这种情况下，您的控件将缩小到某个点，并且不会一目了然。|
|如果控件未实现 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 方法，则该 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 方法返回赋给属性的最后一个值 <xref:System.Windows.Forms.Control.Size%2A> 。|这意味着设置 <xref:System.Windows.Forms.Control.AutoSize%2A> 为 `true` 将不起作用。|
|单元格中的控件 <xref:System.Windows.Forms.TableLayoutPanel> 总是缩小以适应单元格，直到达到其大小 <xref:System.Windows.Forms.Control.MinimumSize%2A> 。|此大小被强制为最大大小。 当单元格为行或列的一部分时，就不会出现这种情况 <xref:System.Windows.Forms.SizeType.AutoSize> 。|

## <a name="autosizemode-property"></a>AutoSizeMode 属性
 `AutoSizeMode`属性可更精细地控制默认 <xref:System.Windows.Forms.Control.AutoSize%2A> 行为。 `AutoSizeMode`属性指定控件如何调整其内容的大小。 例如，内容可以是控件的文本 <xref:System.Windows.Forms.Button> 或容器的子控件。

 下表显示了 <xref:System.Windows.Forms.AutoSizeMode> 设置以及每个设置 elicits 的行为的说明。

|AutoSizeMode 设置|行为|
|--------------------------|--------------|
|GrowAndShrink|控件增大或缩小以包含其内容。<br /><br /> <xref:System.Windows.Forms.Control.MinimumSize%2A>和 <xref:System.Windows.Forms.Control.MaximumSize%2A> 值是有效的，但属性的当前值 <xref:System.Windows.Forms.Control.Size%2A> 被忽略。<br /><br /> 这与具有属性和属性的控件具有相同的行为 <xref:System.Windows.Forms.Control.AutoSize%2A> `AutoSizeMode` 。|
|GrowOnly|控件根据其内容的大小增长得多，但它不会缩小为小于其属性所指定的值 <xref:System.Windows.Forms.Control.Size%2A> 。<br /><br /> 这是 `AutoSizeMode` 的默认值。|

## <a name="controls-that-support-the-autosize-property"></a>支持 AutoSize 属性的控件
 下表列出了支持和属性的控件 <xref:System.Windows.Forms.Control.AutoSize%2A> `AutoSizeMode` 。

|自动调整大小|控件类型|
|----------------------|------------------|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> 支持的属性。<br />-No `AutoSizeMode` 属性。|<xref:System.Windows.Forms.CheckBox><br /><br /> <xref:System.Windows.Forms.DomainUpDown><br /><br /> <xref:System.Windows.Forms.Label><br /><br /> <xref:System.Windows.Forms.LinkLabel><br /><br /> <xref:System.Windows.Forms.MaskedTextBox> (<xref:System.Windows.Forms.TextBox> 基) <br /><br /> <xref:System.Windows.Forms.NumericUpDown><br /><br /> <xref:System.Windows.Forms.RadioButton><br /><br /> <xref:System.Windows.Forms.TextBox><br /><br /> <xref:System.Windows.Forms.TrackBar>|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> 支持的属性。<br />-   `AutoSizeMode` 支持的属性。|<xref:System.Windows.Forms.Button><br /><br /> <xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.FlowLayoutPanel><br /><br /> <xref:System.Windows.Forms.Form><br /><br /> <xref:System.Windows.Forms.GroupBox><br /><br /> <xref:System.Windows.Forms.Panel><br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>|
|-No <xref:System.Windows.Forms.Control.AutoSize%2A> 属性。|<xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.ComboBox><br /><br /> <xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DateTimePicker><br /><br /> <xref:System.Windows.Forms.ListBox><br /><br /> <xref:System.Windows.Forms.ListView><br /><br /> <xref:System.Windows.Forms.MaskedTextBox><br /><br /> <xref:System.Windows.Forms.MonthCalendar><br /><br /> <xref:System.Windows.Forms.ProgressBar><br /><br /> <xref:System.Windows.Forms.PropertyGrid><br /><br /> <xref:System.Windows.Forms.RichTextBox><br /><br /> <xref:System.Windows.Forms.SplitContainer><br /><br /> <xref:System.Windows.Forms.TabControl><br /><br /> <xref:System.Windows.Forms.TabPage><br /><br /> <xref:System.Windows.Forms.TreeView><br /><br /> <xref:System.Windows.Forms.WebBrowser><br /><br /> <xref:System.Windows.Forms.ScrollBar>|

## <a name="autosize-in-the-design-environment"></a>设计环境中的自动调整
 下表根据控件和属性的值，描述了控件在设计时的大小调整行为 <xref:System.Windows.Forms.Control.AutoSize%2A> `AutoSizeMode` 。

 重写 <xref:System.Windows.Forms.Design.ControlDesigner.SelectionRules%2A> 属性以确定给定控件是否处于用户可调整大小的状态。 在下表中，"can" 表示 <xref:System.Windows.Forms.Design.SelectionRules.Moveable> <xref:System.Windows.Forms.Design.SelectionRules.AllSizeable> 和 <xref:System.Windows.Forms.Design.SelectionRules.Moveable> 。

|自动调整大小|设计时调整大小笔势|
|-----------------------|---------------------------------|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-No `AutoSizeMode` 属性。|除了以下控件，用户不能在设计时调整控件的大小：<br /><br /> -   <xref:System.Windows.Forms.TextBox><br />-   <xref:System.Windows.Forms.MaskedTextBox><br />-   <xref:System.Windows.Forms.RichTextBox><br />-   <xref:System.Windows.Forms.TrackBar>|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>|用户无法在设计时调整控件的大小。|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>|用户可以在设计时调整控件的大小。 <xref:System.Windows.Forms.Control.Size%2A>设置属性后，用户只能增加控件的大小。|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `false`或 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性被隐藏。|用户可以在设计时调整控件的大小。|

> [!NOTE]
> 为了最大限度地提高工作效率，Visual Studio 中的 Windows 窗体设计器将隐藏 <xref:System.Windows.Forms.Control.AutoSize%2A> 类的属性 <xref:System.Windows.Forms.Form> 。 在设计时，窗体的行为如同将 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性设置为 `false` ，而不考虑其实际设置。 在运行时，不会执行任何特殊的便利，并按 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性设置的指定应用属性。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.PreferredSize%2A>
- <xref:System.Windows.Forms.Control.GetPreferredSize%2A>
