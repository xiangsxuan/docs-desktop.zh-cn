---
title: 删除或隐藏 DataGrid 控件中的列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: c730be934e9b978bdaf09bc7e668b4318077fba5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971213"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列
> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 您可以 <xref:System.Windows.Forms.DataGrid> 通过使用 <xref:System.Windows.Forms.GridColumnStylesCollection> <xref:System.Windows.Forms.DataGridColumnStyle> (为类) 成员的属性和方法，以编程方式删除或隐藏 Windows 窗体控件中的列 <xref:System.Windows.Forms.DataGridTableStyle> 。  
  
 已删除或隐藏的列仍然存在于网格绑定到的数据源中，并且仍可通过编程方式进行访问。 它们只在 datagrid 中不可见。  
  
> [!NOTE]
> 如果您的应用程序不访问某些数据列，并且您不希望它们显示在数据网格中，则可能不需要先将它们包含在数据源中。  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>以编程方式从 DataGrid 中删除列  
  
1. 在窗体的声明区域中，声明类的新实例 <xref:System.Windows.Forms.DataGridTableStyle> 。  
  
2. 将 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> 属性设置为您要应用样式的数据源中的表。 下面的示例使用 <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> 属性，该属性假定已经设置。  
  
3. 将新 <xref:System.Windows.Forms.DataGridTableStyle> 对象添加到 datagrid 的表样式集合。  
  
4. 调用的 <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> 集合的方法 <xref:System.Windows.Forms.DataGrid> <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> ，指定要删除的列的列索引。  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a>以编程方式隐藏 DataGrid 中的列  
  
1. 在窗体的声明区域中，声明类的新实例 <xref:System.Windows.Forms.DataGridTableStyle> 。  
  
2. 将 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 的属性设置 <xref:System.Windows.Forms.DataGridTableStyle> 为您要应用样式的数据源中的表。 下面的代码示例使用 <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> 属性，该属性假定已设置。  
  
3. 将新 <xref:System.Windows.Forms.DataGridTableStyle> 对象添加到 datagrid 的表样式集合。  
  
4. 通过将列的属性设置 `Width` 为0来隐藏该列，同时指定要隐藏的列的列索引。  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a>另请参阅

- [如何：更改 Windows 窗体 DataGrid 控件中在运行时显示的数据](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [如何：向 Windows 窗体 DataGrid 控件添加表和列](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
