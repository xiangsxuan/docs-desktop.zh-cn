---
title: 用 BindingSource 组件对 ADO.NET 数据进行排序和筛选
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: 404e67f1eeed240a171cb1cfef9094a746c3cecb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970282"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>如何：使用 Windows 窗体 BindingSource 组件对 ADO.NET 数据进行排序和筛选

可以 <xref:System.Windows.Forms.BindingSource> 通过和属性公开控件的排序和筛选功能 <xref:System.Windows.Forms.BindingSource.Sort%2A> <xref:System.Windows.Forms.BindingSource.Filter%2A> 。 如果基础数据源是，则可以应用简单排序 <xref:System.ComponentModel.IBindingList> ，如果数据源是，则可以应用筛选和高级排序 <xref:System.ComponentModel.IBindingListView> 。 <xref:System.Windows.Forms.BindingSource.Sort%2A>属性需要标准 ADO.NET 语法：一个字符串，表示数据源中的数据列的名称，后跟 `ASC` 或 `DESC` 以指示列表应按升序排序还是按降序排序。 您可以通过用逗号分隔符分隔每一列来设置高级排序或多列排序。 <xref:System.Windows.Forms.BindingSource.Filter%2A>属性采用字符串表达式。  
  
> [!NOTE]
> 将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。 有关详细信息，请参阅 [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)。  
  
### <a name="to-filter-data-with-the-bindingsource"></a>用 BindingSource 筛选数据  
  
- 将 <xref:System.Windows.Forms.BindingSource.Filter%2A> 属性设置为所需的 expression。  
  
     在下面的代码示例中，表达式是列名，后跟要用于该列的值。  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>用 BindingSource 对数据进行排序  
  
1. 将属性设置为所需的列名，并将其设置为 <xref:System.Windows.Forms.BindingSource.Sort%2A> `ASC` 或 `DESC` 以指示升序或降序。  
  
2. 用逗号分隔多个列。  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>示例  

 下面的代码示例将 Northwind 示例数据库的 Customers 表中的数据加载到 <xref:System.Windows.Forms.DataGridView> 控件中，并对显示的数据进行筛选和排序。  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  

 若要运行此示例，请将代码粘贴到包含 <xref:System.Windows.Forms.BindingSource> 名为的 `BindingSource1` 和名为的的窗体中 <xref:System.Windows.Forms.DataGridView> `dataGridView1` 。 处理 <xref:System.Windows.Forms.Form.Load> 窗体的事件，并 `InitializeSortedFilteredBindingSource` 在 load 事件处理程序方法中调用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [如何：安装示例数据库](/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [BindingSource 组件](bindingsource-component.md)
