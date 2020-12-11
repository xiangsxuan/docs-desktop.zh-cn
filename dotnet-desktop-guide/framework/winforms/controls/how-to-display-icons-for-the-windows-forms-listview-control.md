---
title: 显示 ListView 控件的图标
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 5fc54c448dae95cab50cdafa8403769fb421dffa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971196"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a>如何：显示 Windows 窗体 ListView 控件的图标
Windows 窗体 <xref:System.Windows.Forms.ListView> 控件可以显示三个图像列表中的图标。 "列表"、"详细信息" 和 "SmallIcon" 视图显示在属性中指定的图像列表中的图像 <xref:System.Windows.Forms.ListView.SmallImageList%2A> 。 LargeIcon 视图显示了在属性中指定的图像列表中的图像 <xref:System.Windows.Forms.ListView.LargeImageList%2A> 。 列表视图还可以显示一组附加的图标，在属性中的 " <xref:System.Windows.Forms.ListView.StateImageList%2A> 大" 或 "小" 图标旁显示。 有关图像列表的详细信息，请参阅 [Imagelist 组件](imagelist-component-windows-forms.md) 和 [如何：通过 Windows 窗体 ImageList 组件添加或删除图像](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)。  
  
### <a name="to-display-images-in-a-list-view"></a>在列表视图中显示图像  
  
1. 将相应的属性（ <xref:System.Windows.Forms.ListView.SmallImageList%2A> 、 <xref:System.Windows.Forms.ListView.LargeImageList%2A> 或 <xref:System.Windows.Forms.ListView.StateImageList%2A> ）设置为要使用的现有 <xref:System.Windows.Forms.ImageList> 组件。  
  
     这些属性可以在设计器中设置属性窗口或代码中。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> 为每个具有关联图标的列表项设置或属性。  
  
     可以在代码中或在 **ListViewItem 集合编辑器** 中设置这些属性。 若要打开 " **ListViewItem 集合编辑器**"，请单击省略号按钮 (![ Visual Studio 属性窗口中的省略号按钮 ( ") "。在 ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.ListView.Items%2A> " **属性** " 窗口中的属性旁) 。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a>另请参阅

- [ListView 控件概述](listview-control-overview-windows-forms.md)
- [如何：使用 Windows 窗体 ListView 控件添加和移除项](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [如何：向 Windows 窗体 ListView 控件中添加列](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [如何：向 TreeView 或 ListView 控件添加自定义信息（Windows 窗体）](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [ImageList 组件](imagelist-component-windows-forms.md)
