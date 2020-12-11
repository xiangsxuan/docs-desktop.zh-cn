---
title: 在 ListView 控件中对项进行分组
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
ms.openlocfilehash: a1754d10de2bbb5895ae861cd17f4af1f18810e2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971836"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>如何：对 Windows 窗体 ListView 控件中的项进行分组
通过控件的分组功能 <xref:System.Windows.Forms.ListView> ，您可以在组中显示相关的项集。 这些组按包含组标题的水平组标头在屏幕上进行分隔。 你可以使用 <xref:System.Windows.Forms.ListView> 组，通过按字母顺序、日期或任何其他逻辑分组对项进行分组来更轻松地导航大型列表。 下图显示了某些分组项。  
  
 ![奇数甚至是 ListView 组的屏幕截图。](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  

 若要启用分组，必须先在设计器中或以编程方式创建一个或多个组。 定义组后，可以将 <xref:System.Windows.Forms.ListView> 项分配给组。 还可以通过编程方式将项从一个组移到另一个组。  
  
### <a name="to-add-groups"></a>添加组  
  
1. 使用 <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> 集合的 <xref:System.Windows.Forms.ListView.Groups%2A> 方法。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>删除组  
  
1. 使用 <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 集合的或 <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 方法 <xref:System.Windows.Forms.ListView.Groups%2A> 。  
  
     <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A>方法移除单个组; <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 方法从列表中移除所有组。  
  
    > [!NOTE]
    > 删除组不会删除该组中的项目。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>向组分配项或在组之间移动项  
  
1. 设置 <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> 各项的属性。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView 控件](listview-control-windows-forms.md)
- [ListView 控件概述](listview-control-overview-windows-forms.md)
- [如何：使用 Windows 窗体 ListView 控件添加和移除项](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
