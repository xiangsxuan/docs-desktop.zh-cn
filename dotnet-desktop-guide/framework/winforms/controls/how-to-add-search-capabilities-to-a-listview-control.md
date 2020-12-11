---
title: 如何：向 ListView 控件添加搜索功能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
ms.openlocfilehash: d5d4dae55fc9f0613ab6535b2fe57e262d0ef141
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971782"
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a>如何：向 ListView 控件添加搜索功能
在使用控件中的大型项列表时，经常 <xref:System.Windows.Forms.ListView> 需要为用户提供搜索功能。 <xref:System.Windows.Forms.ListView>控件通过两种不同的方式提供此功能：文本匹配和位置搜索。  
  
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A>方法允许您在 <xref:System.Windows.Forms.ListView> 给定搜索字符串和可选起始和结束索引的 in 列表或详细信息视图中执行文本搜索。 与此相反，在 <xref:System.Windows.Forms.ListView.FindNearestItem%2A> <xref:System.Windows.Forms.ListView> 给定一组 x 坐标和 y 坐标以及搜索方向的情况下，该方法允许您在中的图标或磁贴视图中查找项。  
  
### <a name="to-find-an-item-using-text"></a>使用文本查找项  
  
1. 创建一个 <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.ListView.View%2A> 将属性设置为 <xref:System.Windows.Forms.View.Details> 或的 <xref:System.Windows.Forms.View.List> ，然后填充 <xref:System.Windows.Forms.ListView> with 项。  
  
2. 调用 <xref:System.Windows.Forms.ListView.FindItemWithText%2A> 方法，传递要查找的项的文本。  
  
3. 下面的代码示例演示如何创建一个基本的 <xref:System.Windows.Forms.ListView> ，使用项填充该项，并使用用户提供的文本输入查找列表中的项。  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a>使用 x 和 y 坐标查找项  
  
1. 创建一个 <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.View> 将属性设置为 <xref:System.Windows.Forms.View.SmallIcon> 或的 <xref:System.Windows.Forms.View.LargeIcon> ，然后填充 <xref:System.Windows.Forms.ListView> with 项。  
  
2. 调用 <xref:System.Windows.Forms.ListView.FindNearestItem%2A> 方法，传递所需的 x 坐标和 y 坐标以及想要搜索的方向。  
  
3. 下面的代码示例演示如何创建一个基本的图标 <xref:System.Windows.Forms.ListView> ，将其填充到项，并捕获 <xref:System.Windows.Forms.Control.MouseDown> 事件以查找向上方向最近的项。  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.FindItemWithText%2A>
- <xref:System.Windows.Forms.ListView.FindNearestItem%2A>
- [ListView 控件](listview-control-windows-forms.md)
- [ListView 控件概述](listview-control-overview-windows-forms.md)
- [如何：使用 Windows 窗体 ListView 控件添加和移除项](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
