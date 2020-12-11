---
title: 在运行时更改 DataGrid 控件中显示的数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
ms.openlocfilehash: 41f22b3149c1d411dcfbdeec4b83c6c0c52c10df
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970712"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>如何：更改 Windows 窗体 DataGrid 控件中在运行时显示的数据

> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 <xref:System.Windows.Forms.DataGrid>使用设计时功能创建 Windows 窗体后，你可能还希望 <xref:System.Data.DataSet> 在运行时动态更改网格对象的元素。 这可以包括更改表的单个值或更改绑定到控件的数据源 <xref:System.Windows.Forms.DataGrid> 。 对单个值的更改是通过 <xref:System.Data.DataSet> 对象（而不是控件）完成的 <xref:System.Windows.Forms.DataGrid> 。  
  
### <a name="to-change-data-programmatically"></a>以编程方式更改数据  
  
1. 从该对象指定所需的表 <xref:System.Data.DataSet> 以及表中所需的行和字段，并将该单元格设置为等于新的值。  
  
    > [!NOTE]
    > 若要指定表的第一个表 <xref:System.Data.DataSet> 或表的第一行，请使用0。  
  
     下面的示例演示如何通过单击更改数据集中第一个表的第一行的第二个条目 `Button1` 。 <xref:System.Data.DataSet> `ds` 之前已创建 () 和表 (`0` 和 `1`) 。  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
    ```  
  
    ```cpp  
    private:
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
      (Visual c # 中，Visual C++) 将以下代码放在窗体构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     在运行时，可以使用 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 方法将 <xref:System.Windows.Forms.DataGrid> 控件绑定到不同的数据源。 例如，您可能有多个 ADO.NET 数据控件，每个控件都连接到不同的数据库。  
  
### <a name="to-change-the-datasource-programmatically"></a>以编程方式更改数据源  
  
1. 将 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 方法设置为要绑定到的数据源和表的名称。  
  
     下面的示例演示如何使用 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 方法将 ADO.NET 数据控件的数据源更改为连接到 Pubs 数据库中的 Authors 表 (adoPubsAuthors) 。  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## <a name="see-also"></a>另请参阅

- [ADO.NET 数据集](/dotnet/framework/data/adonet/ado-net-datasets)
- [如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [如何：向 Windows 窗体 DataGrid 控件添加表和列](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [如何：将 Windows 窗体 DataGrid 控件绑定到数据源](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
