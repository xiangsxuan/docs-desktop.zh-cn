---
title: 通过 DataGrid 控件创建 Master-Detail 列表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
ms.openlocfilehash: e8ab63d52d97a8a6e6f60da741186e3937350e1e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971219"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="b4edc-102">如何：使用 Windows 窗体 DataGrid 控件创建主/详细信息列表</span><span class="sxs-lookup"><span data-stu-id="b4edc-102">How to: Create Master/Detail Lists with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="b4edc-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="b4edc-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="b4edc-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="b4edc-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="b4edc-105">如果您 <xref:System.Data.DataSet> 包含一系列相关的表，则可以使用两个 <xref:System.Windows.Forms.DataGrid> 控件以主/详细信息格式显示数据。</span><span class="sxs-lookup"><span data-stu-id="b4edc-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master/detail format.</span></span> <span data-ttu-id="b4edc-106">将一个 <xref:System.Windows.Forms.DataGrid> 网格指定为主网格，并将第二个指定为详细信息网格。</span><span class="sxs-lookup"><span data-stu-id="b4edc-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="b4edc-107">当你在 "主列表" 中选择条目时，所有相关的子项都显示在 "详细信息" 列表中。</span><span class="sxs-lookup"><span data-stu-id="b4edc-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="b4edc-108">例如，如果您 <xref:System.Data.DataSet> 包含 customers 表和相关订单表，则您可以将 customers 表指定为主网格，将 Orders 表指定为详细信息网格。</span><span class="sxs-lookup"><span data-stu-id="b4edc-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="b4edc-109">从主网格中选择客户时，"订单" 表中与该客户关联的所有订单都将显示在 "详细信息" 网格中。</span><span class="sxs-lookup"><span data-stu-id="b4edc-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a><span data-ttu-id="b4edc-110">以编程方式设置主/从关系</span><span class="sxs-lookup"><span data-stu-id="b4edc-110">To set a master/detail relationship programmatically</span></span>  
  
1. <span data-ttu-id="b4edc-111">创建两个新 <xref:System.Windows.Forms.DataGrid> 控件并设置其属性。</span><span class="sxs-lookup"><span data-stu-id="b4edc-111">Create two new <xref:System.Windows.Forms.DataGrid> controls and set their properties.</span></span>  
  
2. <span data-ttu-id="b4edc-112">向数据集添加表。</span><span class="sxs-lookup"><span data-stu-id="b4edc-112">Add tables to the dataset.</span></span>  
  
3. <span data-ttu-id="b4edc-113">声明类型的变量 <xref:System.Data.DataRelation> ，以表示要创建的关系。</span><span class="sxs-lookup"><span data-stu-id="b4edc-113">Declare a variable of type <xref:System.Data.DataRelation> to represent the relation you want to create.</span></span>  
  
4. <span data-ttu-id="b4edc-114">通过指定关系的名称并指定将绑定两个表的表、列和项来实例化关系。</span><span class="sxs-lookup"><span data-stu-id="b4edc-114">Instantiate the relationship by specifying a name for the relationship and specifying the table, column, and item that will tie the two tables.</span></span>  
  
5. <span data-ttu-id="b4edc-115">将关系添加到 <xref:System.Data.DataSet> 对象的 <xref:System.Data.DataSet.Relations%2A> 集合中。</span><span class="sxs-lookup"><span data-stu-id="b4edc-115">Add the relationship to the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Relations%2A> collection.</span></span>  
  
6. <span data-ttu-id="b4edc-116">使用的 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 方法将 <xref:System.Windows.Forms.DataGrid> 每个网格绑定到 <xref:System.Data.DataSet> 。</span><span class="sxs-lookup"><span data-stu-id="b4edc-116">Use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method of the <xref:System.Windows.Forms.DataGrid> to bind each of the grids to the <xref:System.Data.DataSet>.</span></span>  
  
     <span data-ttu-id="b4edc-117">下面的示例演示如何设置之前生成的 () 中的 Customers 和 Orders 表之间的主/从 <xref:System.Data.DataSet> 关系 `ds` 。</span><span class="sxs-lookup"><span data-stu-id="b4edc-117">The following example shows how to set a master/detail relationship between the Customers and Orders tables in a previously generated <xref:System.Data.DataSet> (`ds`).</span></span>  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b4edc-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4edc-118">See also</span></span>

- [<span data-ttu-id="b4edc-119">DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="b4edc-119">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="b4edc-120">DataGrid 控件概述</span><span class="sxs-lookup"><span data-stu-id="b4edc-120">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="b4edc-121">如何：将 Windows 窗体 DataGrid 控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="b4edc-121">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
