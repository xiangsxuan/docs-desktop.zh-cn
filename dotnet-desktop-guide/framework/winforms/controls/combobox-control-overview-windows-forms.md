---
title: ComboBox 控件概述
ms.date: 03/30/2017
f1_keywords:
- ComboBox
helpviewer_keywords:
- drop-down lists [Windows Forms], Windows Forms
- ComboBox control [Windows Forms], about ComboBox control
- drop-down lists [Windows Forms], ComboBox control
- combo boxes [Windows Forms], about combo boxes
ms.assetid: a58b393f-a614-45d1-8961-857a024b5acd
ms.openlocfilehash: 9fb270d7787902872a32a87c140316f756bd48aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970195"
---
# <a name="combobox-control-overview-windows-forms"></a>ComboBox 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.ComboBox> 控件用于在下拉组合框中显示数据。 默认情况下， <xref:System.Windows.Forms.ComboBox> 控件显示在两个部分中：最上面的部分是允许用户键入列表项的文本框。 第二部分是显示项列表的列表框，用户可以从中选择一个项。 有关组合框的其他样式的详细信息，请参阅 [When To Use a Windows 窗体 ComboBox 而不是 ListBox](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)。  
  
 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A>属性返回对应于选定列表项的整数值。 您可以通过在代码中更改值来以编程方式更改选定项 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> ; 列表中的相应项将出现在组合框的文本框部分。 如果未选择任何项，则 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> 值为-1。 如果选择了列表中的第一项，则 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> 值为0。 <xref:System.Windows.Forms.ComboBox.SelectedItem%2A>属性类似于 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> ，但返回项本身，通常是一个字符串值。 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A>属性反映列表中的项数，并且属性的值 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Count%2A> 始终比最大可能的值大一， <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> 因为 <xref:System.Windows.Forms.ComboBox.SelectedIndex%2A> 它是从零开始的。  
  
 若要在控件中添加或删除项 <xref:System.Windows.Forms.ComboBox> ，请 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A> 使用 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Insert%2A> 、 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Clear%2A> 或 <xref:System.Windows.Forms.ComboBox.ObjectCollection.Remove%2A> 方法。 或者，您可以通过使用 <xref:System.Windows.Forms.ComboBox.Items%2A> 设计器中的属性向列表中添加项。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ComboBox>
- [ListBox 控件概述](listbox-control-overview-windows-forms.md)
- [何时使用 Windows 窗体 ComboBox 而非 ListBox](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [如何：在 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件中添加或移除项](add-and-remove-items-from-a-wf-combobox.md)
- [如何：对 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件的内容排序](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [如何：在 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件中访问特定项](access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)
- [如何：将 Windows 窗体 ComboBox 控件或 ListBox 控件绑定到数据](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [用于列出选项的 Windows 窗体控件](windows-forms-controls-used-to-list-options.md)
- [如何：为 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件创建查找表](create-a-lookup-table-for-a-wf-combobox-listbox.md)
