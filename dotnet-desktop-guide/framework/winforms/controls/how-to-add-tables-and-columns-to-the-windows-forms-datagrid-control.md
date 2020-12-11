---
title: 向 DataGrid 控件添加表和列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
ms.openlocfilehash: 2db2e38c326cbcd78c58ee4fe00cd9ed20ae0e8a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971908"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a><span data-ttu-id="a45c3-102">如何：向 Windows 窗体 DataGrid 控件添加表和列</span><span class="sxs-lookup"><span data-stu-id="a45c3-102">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="a45c3-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="a45c3-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="a45c3-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="a45c3-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

<span data-ttu-id="a45c3-105">可以 <xref:System.Windows.Forms.DataGrid> 通过创建 **DataGridTableStyle** 对象并将其添加到 **system.windows.forms.gridtablestylescollection>** 对象（可通过 <xref:System.Windows.Forms.DataGrid> 控件的 **system.windows.forms.datagrid.tablestyles** 属性访问）来在表和列的 Windows 窗体控件中显示数据。</span><span class="sxs-lookup"><span data-stu-id="a45c3-105">You can display data in the Windows Forms <xref:System.Windows.Forms.DataGrid> control in tables and columns by creating **DataGridTableStyle** objects and adding them to the **GridTableStylesCollection** object, which is accessed through the <xref:System.Windows.Forms.DataGrid> control's **TableStyles** property.</span></span> <span data-ttu-id="a45c3-106">每个表样式显示在 **DataGridTableStyle** 对象的 **MappingName** 属性中指定的任何数据表的内容。</span><span class="sxs-lookup"><span data-stu-id="a45c3-106">Each table style displays the contents of whatever data table is specified in the **DataGridTableStyle** object's **MappingName** property.</span></span> <span data-ttu-id="a45c3-107">默认情况下，未指定列样式的表样式将显示该数据表中的所有列。</span><span class="sxs-lookup"><span data-stu-id="a45c3-107">By default, a table style with no column styles specified will display all the columns within that data table.</span></span> <span data-ttu-id="a45c3-108">可以通过将 **system.windows.forms.datagridcolumnstyle>** 对象添加到 **system.windows.forms.gridcolumnstylescollection>** 对象（通过每个 **DataGridTableStyle** 对象的 **system.windows.forms.datagridtablestyle.gridcolumnstyles** 属性访问）来限制显示表中的哪些列。</span><span class="sxs-lookup"><span data-stu-id="a45c3-108">You can restrict which columns from the table appear by adding **DataGridColumnStyle** objects to the **GridColumnStylesCollection** object, which is accessed through the **GridColumnStyles** property of each **DataGridTableStyle** object.</span></span>

### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a><span data-ttu-id="a45c3-109">以编程方式向 DataGrid 添加表和列</span><span class="sxs-lookup"><span data-stu-id="a45c3-109">To add a table and column to a DataGrid programmatically</span></span>

1. <span data-ttu-id="a45c3-110">若要在表中显示数据，必须先将 <xref:System.Windows.Forms.DataGrid> 控件绑定到数据集。</span><span class="sxs-lookup"><span data-stu-id="a45c3-110">In order to display data in the table, you must first bind the <xref:System.Windows.Forms.DataGrid> control to a dataset.</span></span> <span data-ttu-id="a45c3-111">有关详细信息，请参阅 [如何：将 Windows 窗体 DataGrid 控件绑定到数据源](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)。</span><span class="sxs-lookup"><span data-stu-id="a45c3-111">For more information, see [How to: Bind the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>

    > [!CAUTION]
    > <span data-ttu-id="a45c3-112">以编程方式指定列样式时，应始终创建 **system.windows.forms.datagridcolumnstyle>** 对象并将其添加到 **system.windows.forms.gridcolumnstylescollection>** 对象，然后再将 **DataGridTableStyle** 对象添加到 **system.windows.forms.gridtablestylescollection>** 对象。</span><span class="sxs-lookup"><span data-stu-id="a45c3-112">When programmatically specifying column styles, always create **DataGridColumnStyle** objects and add them to the **GridColumnStylesCollection** object before adding **DataGridTableStyle** objects to the **GridTableStylesCollection** object.</span></span> <span data-ttu-id="a45c3-113">将空的 **DataGridTableStyle** 对象添加到集合时，会自动为你生成 **system.windows.forms.datagridcolumnstyle>** 对象。</span><span class="sxs-lookup"><span data-stu-id="a45c3-113">When you add an empty **DataGridTableStyle** object to the collection, **DataGridColumnStyle** objects are automatically generated for you.</span></span> <span data-ttu-id="a45c3-114">因此，如果尝试将具有重复 **MappingName** 值的新 **system.windows.forms.datagridcolumnstyle>** 对象添加到 **system.windows.forms.gridcolumnstylescollection>** 对象，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="a45c3-114">Consequently, an exception will be thrown if you try to add new **DataGridColumnStyle** objects with duplicate **MappingName** values to the **GridColumnStylesCollection** object.</span></span>

2. <span data-ttu-id="a45c3-115">声明新的表样式并设置其映射名称。</span><span class="sxs-lookup"><span data-stu-id="a45c3-115">Declare a new table style and set its mapping name.</span></span>

    ```vb
    Dim ts1 As New DataGridTableStyle()
    ts1.MappingName = "Customers"
    ```

    ```csharp
    DataGridTableStyle ts1 = new DataGridTableStyle();
    ts1.MappingName = "Customers";
    ```

    ```cpp
    DataGridTableStyle* ts1 = new DataGridTableStyle();
    ts1->MappingName = S"Customers";
    ```

3. <span data-ttu-id="a45c3-116">声明新的列样式，并设置其映射名称和其他属性。</span><span class="sxs-lookup"><span data-stu-id="a45c3-116">Declare a new column style and set its mapping name and other properties.</span></span>

    ```vb
    Dim myDataCol As New DataGridBoolColumn()
    myDataCol.HeaderText = "My New Column"
    myDataCol.MappingName = "Current"
    ```

    ```csharp
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();
    myDataCol.HeaderText = "My New Column";
    myDataCol.MappingName = "Current";
    ```

    ```cpp
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();
    myDataCol->HeaderText = "My New Column";
    myDataCol->MappingName = "Current";
    ```

4. <span data-ttu-id="a45c3-117">调用 **system.windows.forms.gridcolumnstylescollection>** 对象的 **add** 方法，将该列添加到表样式中</span><span class="sxs-lookup"><span data-stu-id="a45c3-117">Call the **Add** method of the **GridColumnStylesCollection** object to add the column to the table style</span></span>

    ```vb
    ts1.GridColumnStyles.Add(myDataCol)
    ```

    ```csharp
    ts1.GridColumnStyles.Add(myDataCol);
    ```

    ```cpp
    ts1->GridColumnStyles->Add(myDataCol);
    ```

5. <span data-ttu-id="a45c3-118">调用 **system.windows.forms.gridtablestylescollection>** 对象的 **add** 方法，将表样式添加到数据网格。</span><span class="sxs-lookup"><span data-stu-id="a45c3-118">Call the **Add** method of the **GridTableStylesCollection** object to add the table style to the data grid.</span></span>

    ```vb
    DataGrid1.TableStyles.Add(ts1)
    ```

    ```csharp
    dataGrid1.TableStyles.Add(ts1);
    ```

    ```cpp
    dataGrid1->TableStyles->Add(ts1);
    ```

## <a name="see-also"></a><span data-ttu-id="a45c3-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a45c3-119">See also</span></span>

- [<span data-ttu-id="a45c3-120">DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="a45c3-120">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="a45c3-121">如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列</span><span class="sxs-lookup"><span data-stu-id="a45c3-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
