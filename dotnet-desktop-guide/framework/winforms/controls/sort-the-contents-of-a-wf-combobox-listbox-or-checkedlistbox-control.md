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
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="cd9f9-102">如何：对 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件的内容排序</span><span class="sxs-lookup"><span data-stu-id="cd9f9-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="cd9f9-103">Windows 窗体控件在数据绑定时不进行排序。</span><span class="sxs-lookup"><span data-stu-id="cd9f9-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="cd9f9-104">若要显示已排序的数据，请使用支持排序的数据源，然后使数据源对其进行排序。</span><span class="sxs-lookup"><span data-stu-id="cd9f9-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="cd9f9-105">支持排序的数据源包括数据视图、数据视图管理器和排序数组。</span><span class="sxs-lookup"><span data-stu-id="cd9f9-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="cd9f9-106">如果控件不是数据绑定的，则可以对其进行排序。</span><span class="sxs-lookup"><span data-stu-id="cd9f9-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="cd9f9-107">对列表进行排序</span><span class="sxs-lookup"><span data-stu-id="cd9f9-107">To sort the list</span></span>  
  
1. <span data-ttu-id="cd9f9-108">将 `Sorted` 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="cd9f9-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="cd9f9-109">此设置会按排序顺序重新定位所有现有列表项。</span><span class="sxs-lookup"><span data-stu-id="cd9f9-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd9f9-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd9f9-110">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="cd9f9-111">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="cd9f9-111">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="cd9f9-112">如何：在 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件中添加或移除项</span><span class="sxs-lookup"><span data-stu-id="cd9f9-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="cd9f9-113">何时使用 Windows 窗体 ComboBox 而非 ListBox</span><span class="sxs-lookup"><span data-stu-id="cd9f9-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="cd9f9-114">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="cd9f9-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
