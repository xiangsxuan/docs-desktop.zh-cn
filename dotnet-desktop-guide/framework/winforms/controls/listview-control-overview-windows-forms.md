---
title: ListView 控件概述
ms.date: 03/30/2017
f1_keywords:
- ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
ms.openlocfilehash: 9308ff6646704d16b32669827a1f26bebf6958d8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972622"
---
# <a name="listview-control-overview-windows-forms"></a>ListView 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.ListView> 控件显示带图标的项列表。 你可以使用列表视图创建类似 Windows 资源管理器右窗格的用户界面。 控件具有四个视图模式： LargeIcon、SmallIcon、List 和 Details。  
  
## <a name="what-you-can-do-with-the-listview-control"></a>ListView 控件可以执行的操作  
  
> [!NOTE]
> 其他视图模式磁贴仅适用于 Windows XP 和 Windows Server 2003 操作系统。 有关详细信息，请参阅 [如何：在 Windows 窗体 ListView 控件中启用磁贴视图](how-to-enable-tile-view-in-a-windows-forms-listview-control.md)。  
  
 LargeIcon 模式显示项文本旁边的大图标;如果控件足够大，则项显示在多个列中。 SmallIcon 模式相同，只不过它显示小图标。 列表模式显示小图标，但始终显示在单个列中。 详细信息模式显示多个列中的项。 有关详细信息，请参阅 [如何：将列添加到 Windows 窗体 ListView 控件](how-to-add-columns-to-the-windows-forms-listview-control.md)。 视图模式由 <xref:System.Windows.Forms.ListView.View%2A> 属性确定。 所有视图模式都可以显示图像列表中的图像。 有关详细信息，请参阅 [如何：显示 Windows 窗体 ListView 控件的图标](how-to-display-icons-for-the-windows-forms-listview-control.md)。  
  
 下表列出了一些 <xref:System.Windows.Forms.ListView> 成员以及它们在中有效的视图。  
  
|ListView 成员|视图|  
|---------------------|----------|  
|<xref:System.Windows.Forms.ListView.Alignment%2A> 属性|<xref:System.Windows.Forms.View.SmallIcon> 或 <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.AutoArrange%2A> 属性|<xref:System.Windows.Forms.View.SmallIcon> 或 <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.AutoResizeColumn%2A> 方法|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.Columns%2A> 属性|<xref:System.Windows.Forms.View.Details> 或 <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.DrawSubItem> 事件|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.FindItemWithText%2A> 方法|<xref:System.Windows.Forms.View.Details>、<xref:System.Windows.Forms.View.List> 或 <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.FindNearestItem%2A> 方法|<xref:System.Windows.Forms.View.SmallIcon> 或 <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.GetItemAt%2A> 方法|<xref:System.Windows.Forms.View.Details> 或 <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.Groups%2A> 属性|除之外的所有视图 <xref:System.Windows.Forms.View.List>|  
|<xref:System.Windows.Forms.ListView.HeaderStyle%2A> 属性|<xref:System.Windows.Forms.View.Details>.|  
|<xref:System.Windows.Forms.ListView.InsertionMark%2A> 属性|<xref:System.Windows.Forms.View.LargeIcon>、<xref:System.Windows.Forms.View.SmallIcon> 或 <xref:System.Windows.Forms.View.Tile>|  
  
 控件的键属性 <xref:System.Windows.Forms.ListView> 为 <xref:System.Windows.Forms.ListView.Items%2A> ，它包含控件所显示的项。 <xref:System.Windows.Forms.ListView.SelectedItems%2A>属性包含控件中当前选定项的集合。 用户可以选择多个项，例如，如果属性设置为，则将多个项一次拖放到另一个控件 <xref:System.Windows.Forms.ListView.MultiSelect%2A> `true` 。 <xref:System.Windows.Forms.ListView>如果将属性设置为，则控件可以显示项旁边的复选框 <xref:System.Windows.Forms.ListView.CheckBoxes%2A> `true` 。  
  
 <xref:System.Windows.Forms.ListView.Activation%2A>属性确定用户激活列表中的项时必须执行的操作类型：选项为 <xref:System.Windows.Forms.ItemActivation.Standard> 、 <xref:System.Windows.Forms.ItemActivation.OneClick> 和 <xref:System.Windows.Forms.ItemActivation.TwoClick> 。 <xref:System.Windows.Forms.ItemActivation.OneClick> 激活只需单击一次即可激活该项。 <xref:System.Windows.Forms.ItemActivation.TwoClick> 激活要求用户双击激活该项;单击一次即可更改项文本的颜色。 <xref:System.Windows.Forms.ItemActivation.Standard> 激活要求用户双击激活项，但该项不会更改外观。  
  
 该 <xref:System.Windows.Forms.ListView> 控件还支持 WINDOWS XP 平台上可用的视觉样式和其他功能，包括分组、平铺视图和插入标记。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ListView>
- [ListView 控件](listview-control-windows-forms.md)
- [如何：使用 Windows 窗体 ListView 控件添加和移除项](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [如何：向 Windows 窗体 ListView 控件中添加列](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [如何：显示 Windows 窗体 ListView 控件的图标](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [如何：使用 Windows 窗体 ListView 控件在列中显示子项](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [如何：选择 Windows 窗体 ListView 控件中的项](how-to-select-an-item-in-the-windows-forms-listview-control.md)
- [如何：对 Windows 窗体 ListView 控件中的项进行分组](how-to-group-items-in-a-windows-forms-listview-control.md)
- [如何：在 Windows 窗体 ListView 控件中显示插入标记](how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)
- [如何：向 ListView 控件添加搜索功能](how-to-add-search-capabilities-to-a-listview-control.md)
- [如何：向 TreeView 或 ListView 控件添加自定义信息（Windows 窗体）](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [如何：使用 Windows 窗体创建多窗格用户界面](how-to-create-a-multipane-user-interface-with-windows-forms.md)
