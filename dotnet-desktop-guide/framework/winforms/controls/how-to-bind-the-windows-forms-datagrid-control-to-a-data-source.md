---
title: 将 DataGrid 控件绑定到数据源
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
ms.openlocfilehash: 42514c6a0ab9cf912a32b13675a069976632ece5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972062"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a><span data-ttu-id="64ba8-102">如何：将 Windows 窗体 DataGrid 控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="64ba8-102">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>
> [!NOTE]
> <span data-ttu-id="64ba8-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="64ba8-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="64ba8-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="64ba8-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="64ba8-105">Windows 窗体 <xref:System.Windows.Forms.DataGrid> 控件专门用于显示数据源中的信息。</span><span class="sxs-lookup"><span data-stu-id="64ba8-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="64ba8-106">可以通过调用方法在运行时绑定控件 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 。</span><span class="sxs-lookup"><span data-stu-id="64ba8-106">You bind the control at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="64ba8-107">尽管可以显示来自多种数据源的数据，但最常见的数据源是数据集和数据视图。</span><span class="sxs-lookup"><span data-stu-id="64ba8-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a><span data-ttu-id="64ba8-108">以编程方式对 DataGrid 控件进行数据绑定</span><span class="sxs-lookup"><span data-stu-id="64ba8-108">To data-bind the DataGrid control programmatically</span></span>  
  
1. <span data-ttu-id="64ba8-109">编写代码以填充数据集。</span><span class="sxs-lookup"><span data-stu-id="64ba8-109">Write code to fill the dataset.</span></span>  
  
     <span data-ttu-id="64ba8-110">如果数据源是基于数据集表的数据集或数据视图，请将代码添加到窗体中以填充数据集。</span><span class="sxs-lookup"><span data-stu-id="64ba8-110">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="64ba8-111">你使用的确切代码取决于数据集获取数据的位置。</span><span class="sxs-lookup"><span data-stu-id="64ba8-111">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="64ba8-112">如果直接从数据库填充数据集，则通常调用 `Fill` 数据适配器的方法，如下面的示例所示，该示例将填充名为的数据集 `DsCategories1` ：</span><span class="sxs-lookup"><span data-stu-id="64ba8-112">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     <span data-ttu-id="64ba8-113">如果数据集是从 XML Web service 中填充的，则通常在代码中创建服务的实例，然后调用其方法之一来返回数据集。</span><span class="sxs-lookup"><span data-stu-id="64ba8-113">If the dataset is being filled from an XML Web service, you typically create an instance of the service in your code and then call one of its methods to return a dataset.</span></span> <span data-ttu-id="64ba8-114">然后，将数据集从 XML Web service 合并到本地数据集。</span><span class="sxs-lookup"><span data-stu-id="64ba8-114">You then merge the dataset from the XML Web service into your local dataset.</span></span> <span data-ttu-id="64ba8-115">下面的示例演示如何创建名为的 XML Web service 的实例 `CategoriesService` ，调用其 `GetCategories` 方法，并将生成的数据集合并到名为的本地数据集 `DsCategories1` ：</span><span class="sxs-lookup"><span data-stu-id="64ba8-115">The following example shows how you can create an instance of an XML Web service called `CategoriesService`, call its `GetCategories` method, and merge the resulting dataset into a local dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2. <span data-ttu-id="64ba8-116">调用 <xref:System.Windows.Forms.DataGrid> 控件的 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 方法，将数据源和数据成员传递给它。</span><span class="sxs-lookup"><span data-stu-id="64ba8-116">Call the <xref:System.Windows.Forms.DataGrid> control's <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method, passing it the data source and a data member.</span></span> <span data-ttu-id="64ba8-117">如果不需要显式传递数据成员，请传递一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="64ba8-117">If you do not need to explicitly pass a data member, pass an empty string.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="64ba8-118">如果是第一次绑定网格，则可以设置控件的 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 和 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="64ba8-118">If you are binding the grid for the first time, you can set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties.</span></span> <span data-ttu-id="64ba8-119">但是，一旦设置了这些属性，就不能对其进行重置。</span><span class="sxs-lookup"><span data-stu-id="64ba8-119">However, you cannot reset these properties once they have been set.</span></span> <span data-ttu-id="64ba8-120">因此，建议你始终使用 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="64ba8-120">Therefore, it is recommended that you always use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span>  
  
     <span data-ttu-id="64ba8-121">下面的示例演示如何以编程方式绑定到数据集中名为的 Customers 表 `DsCustomers1` ：</span><span class="sxs-lookup"><span data-stu-id="64ba8-121">The following example shows how you can programmatically bind to the Customers table in a dataset called `DsCustomers1`:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     <span data-ttu-id="64ba8-122">如果 Customers 表是数据集中的唯一表，则可以按如下方式绑定网格：</span><span class="sxs-lookup"><span data-stu-id="64ba8-122">If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. <span data-ttu-id="64ba8-123"> (可选) 将相应的表样式和列样式添加到网格。</span><span class="sxs-lookup"><span data-stu-id="64ba8-123">(Optional) Add the appropriate table styles and column styles to the grid.</span></span> <span data-ttu-id="64ba8-124">如果没有表样式，您将看到该表，但其格式设置和所有列都可见。</span><span class="sxs-lookup"><span data-stu-id="64ba8-124">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ba8-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64ba8-125">See also</span></span>

- [<span data-ttu-id="64ba8-126">DataGrid 控件概述</span><span class="sxs-lookup"><span data-stu-id="64ba8-126">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="64ba8-127">如何：向 Windows 窗体 DataGrid 控件添加表和列</span><span class="sxs-lookup"><span data-stu-id="64ba8-127">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="64ba8-128">DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="64ba8-128">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="64ba8-129">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="64ba8-129">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
