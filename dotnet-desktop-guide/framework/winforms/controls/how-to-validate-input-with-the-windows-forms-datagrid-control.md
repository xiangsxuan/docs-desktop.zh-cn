---
title: 通过 DataGrid 控件验证输入
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid control [Windows Forms], examples
- user input [Windows Forms], validating
- examples [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], validating input
- validation [Windows Forms], user input
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
ms.openlocfilehash: 3958089007401d2e977c9c96f07c9196e6216596
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972645"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="b11c9-102">如何：用 Windows 窗体 DataGrid 控件验证输入</span><span class="sxs-lookup"><span data-stu-id="b11c9-102">How to: Validate Input with the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="b11c9-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="b11c9-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="b11c9-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="b11c9-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

<span data-ttu-id="b11c9-105">Windows 窗体控件可使用两种类型的输入验证 <xref:System.Windows.Forms.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="b11c9-105">There are two types of input validation available for the Windows Forms <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="b11c9-106">如果用户尝试输入的值不是单元格的不可接受的数据类型（例如，将字符串转换为整数），则新的无效值将替换为旧值。</span><span class="sxs-lookup"><span data-stu-id="b11c9-106">If the user attempts to enter a value that is of an unacceptable data type for the cell, for example a string into an integer, the new invalid value is replaced with the old value.</span></span> <span data-ttu-id="b11c9-107">这种输入验证是自动完成的，不能进行自定义。</span><span class="sxs-lookup"><span data-stu-id="b11c9-107">This kind of input validation is done automatically and cannot be customized.</span></span>

<span data-ttu-id="b11c9-108">其他类型的输入验证可用于拒绝任何不可接受的数据，例如，字段中的值必须大于或等于1，或者字符串不正确。</span><span class="sxs-lookup"><span data-stu-id="b11c9-108">The other type of input validation can be used to reject any unacceptable data, for example a 0 value in a field that must be greater than or equal to 1, or an inappropriate string.</span></span> <span data-ttu-id="b11c9-109">通过为或事件编写事件处理程序，可以在数据集中完成此操作 <xref:System.Data.DataTable.ColumnChanging> <xref:System.Data.DataTable.RowChanging> 。</span><span class="sxs-lookup"><span data-stu-id="b11c9-109">This is done in the dataset by writing an event handler for the <xref:System.Data.DataTable.ColumnChanging> or <xref:System.Data.DataTable.RowChanging> event.</span></span> <span data-ttu-id="b11c9-110">下面的示例使用 <xref:System.Data.DataTable.ColumnChanging> 事件，因为特定的 "Product" 列不允许使用不可接受的值。</span><span class="sxs-lookup"><span data-stu-id="b11c9-110">The example below uses the <xref:System.Data.DataTable.ColumnChanging> event because the unacceptable value is disallowed for the "Product" column in particular.</span></span> <span data-ttu-id="b11c9-111">您可以使用 <xref:System.Data.DataTable.RowChanging> 事件来检查 "结束日期" 列的值是否晚于同一行中的 "开始日期" 列。</span><span class="sxs-lookup"><span data-stu-id="b11c9-111">You might use the <xref:System.Data.DataTable.RowChanging> event for checking that the value of an "End Date" column is later than the "Start Date" column in the same row.</span></span>

## <a name="to-validate-user-input"></a><span data-ttu-id="b11c9-112">验证用户输入</span><span class="sxs-lookup"><span data-stu-id="b11c9-112">To validate user input</span></span>

1. <span data-ttu-id="b11c9-113">编写代码来处理 <xref:System.Data.DataTable.ColumnChanging> 相应表的事件。</span><span class="sxs-lookup"><span data-stu-id="b11c9-113">Write code to handle the <xref:System.Data.DataTable.ColumnChanging> event for the appropriate table.</span></span> <span data-ttu-id="b11c9-114">如果检测到不正确的输入，请调用 <xref:System.Data.DataRow.SetColumnError%2A> 对象的方法 <xref:System.Data.DataRow> 。</span><span class="sxs-lookup"><span data-stu-id="b11c9-114">When inappropriate input is detected, call the <xref:System.Data.DataRow.SetColumnError%2A> method of the <xref:System.Data.DataRow> object.</span></span>

    ```vb
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _
    ByVal e As System.Data.DataColumnChangeEventArgs)
       ' Only check for errors in the Product column
       If (e.Column.ColumnName.Equals("Product")) Then
          ' Do not allow "Automobile" as a product.
          If CType(e.ProposedValue, String) = "Automobile" Then
             Dim badValue As Object = e.ProposedValue
             e.ProposedValue = "Bad Data"
             e.Row.RowError = "The Product column contains an error"
             e.Row.SetColumnError(e.Column, "Product cannot be " & _
             CType(badValue, String))
          End If
       End If
    End Sub
    ```

    ```csharp
    //Handle column changing events on the Customers table
    private void Customers_ColumnChanging(object sender, System.Data.DataColumnChangeEventArgs e) {

       //Only check for errors in the Product column
       if (e.Column.ColumnName.Equals("Product")) {

          //Do not allow "Automobile" as a product
          if (e.ProposedValue.Equals("Automobile")) {
             object badValue = e.ProposedValue;
             e.ProposedValue = "Bad Data";
             e.Row.RowError = "The Product column contains an error";
             e.Row.SetColumnError(e.Column, "Product cannot be " + badValue);
          }
       }
    }
    ```

2. <span data-ttu-id="b11c9-115">将事件处理程序连接到事件。</span><span class="sxs-lookup"><span data-stu-id="b11c9-115">Connect the event handler to the event.</span></span>

    <span data-ttu-id="b11c9-116">将以下代码放在窗体的 <xref:System.Windows.Forms.Form.Load> 事件或其构造函数中。</span><span class="sxs-lookup"><span data-stu-id="b11c9-116">Place the following code within either the form's <xref:System.Windows.Forms.Form.Load> event or its constructor.</span></span>

    ```vb
    ' Assumes the grid is bound to a dataset called customersDataSet1
    ' with a table called Customers.
    ' Put this code in the form's Load event or its constructor.
    AddHandler customersDataSet1.Tables("Customers").ColumnChanging, AddressOf Customers_ColumnChanging
    ```

    ```csharp
    // Assumes the grid is bound to a dataset called customersDataSet1
    // with a table called Customers.
    // Put this code in the form's Load event or its constructor.
    customersDataSet1.Tables["Customers"].ColumnChanging += new DataColumnChangeEventHandler(this.Customers_ColumnChanging);
    ```

## <a name="see-also"></a><span data-ttu-id="b11c9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b11c9-117">See also</span></span>

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [<span data-ttu-id="b11c9-118">DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="b11c9-118">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
