---
title: ListBox 控件概述
ms.date: 03/30/2017
f1_keywords:
- ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
ms.openlocfilehash: 1abf8bea5c786f2ce326631370fa294ada09a92c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972624"
---
# <a name="listbox-control-overview-windows-forms"></a>ListBox 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.ListBox> 控件将显示一个列表，用户可从中选择一个或多个项。 如果项总数超过了可以显示的数目，则会自动向控件添加滚动条 <xref:System.Windows.Forms.ListBox> 。 当 <xref:System.Windows.Forms.ListBox.MultiColumn%2A> 属性设置为时 `true` ，列表框将在多个列中显示项，并显示水平滚动条。 当 <xref:System.Windows.Forms.ListBox.MultiColumn%2A> 属性设置为时 `false` ，列表框将显示单个列中的项，并且将显示一个垂直滚动条。 当 <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A> 设置为时 `true` ，将显示滚动条，而不考虑项的数目。 <xref:System.Windows.Forms.ListBox.SelectionMode%2A>属性确定一次可以选择多少个列表项。  
  
## <a name="ways-to-change-the-listbox-control"></a>更改 ListBox 控件的方式  
 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A>属性返回一个整数值，该整数值对应于列表框中的第一个选定项。 您可以通过在代码中更改值来以编程方式更改选定项 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> ; 列表中的相应项将显示在 Windows 窗体上。 如果未选择任何项，则 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 值为-1。 如果选择列表中的第一项，则 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 值为0。 选择多个项时， <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 值将反映列表中第一个出现的选定项。 <xref:System.Windows.Forms.ListBox.SelectedItem%2A>属性类似于 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> ，但返回项本身，通常是一个字符串值。 <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A>属性反映列表中的项数，并且属性的值 <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> 始终比最大可能的值大一， <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 因为 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 它是从零开始的。  
  
 若要在控件中添加或删除项 <xref:System.Windows.Forms.ListBox> ，请 <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A> 使用 <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A> 、 <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> 或 <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A> 方法。 或者，您可以在设计时使用属性向列表中添加项 <xref:System.Windows.Forms.ListBox.Items%2A> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ListBox>
- [如何：在 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件中添加或移除项](add-and-remove-items-from-a-wf-combobox.md)
- [如何：对 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件的内容排序](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [如何：将 Windows 窗体 ComboBox 控件或 ListBox 控件绑定到数据](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [ComboBox 控件概述](combobox-control-overview-windows-forms.md)
- [CheckedListBox 控件概述](checkedlistbox-control-overview-windows-forms.md)
- [用于列出选项的 Windows 窗体控件](windows-forms-controls-used-to-list-options.md)
- [如何：为 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件创建查找表](create-a-lookup-table-for-a-wf-combobox-listbox.md)
