---
title: 对 ComboBox、ListBox 或 CheckedListBox 控件的内容进行排序
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: dee969d777edf76434622fe632f7e934987a1dc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970903"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>如何：对 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件的内容排序
Windows 窗体控件在数据绑定时不进行排序。 若要显示已排序的数据，请使用支持排序的数据源，然后使数据源对其进行排序。 支持排序的数据源包括数据视图、数据视图管理器和排序数组。  
  
 如果控件不是数据绑定的，则可以对其进行排序。  
  
### <a name="to-sort-the-list"></a>对列表进行排序  
  
1. 将 `Sorted` 属性设置为 `true`。  
  
     此设置会按排序顺序重新定位所有现有列表项。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [Windows 窗体数据绑定](../windows-forms-data-binding.md)
- [如何：在 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件中添加或移除项](add-and-remove-items-from-a-wf-combobox.md)
- [何时使用 Windows 窗体 ComboBox 而非 ListBox](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [用于列出选项的 Windows 窗体控件](windows-forms-controls-used-to-list-options.md)
