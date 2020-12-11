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
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="e0dfe-102">如何：使用 Windows 窗体 BindingSource 组件对 ADO.NET 数据进行排序和筛选</span><span class="sxs-lookup"><span data-stu-id="e0dfe-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>

<span data-ttu-id="e0dfe-103">可以 <xref:System.Windows.Forms.BindingSource> 通过和属性公开控件的排序和筛选功能 <xref:System.Windows.Forms.BindingSource.Sort%2A> <xref:System.Windows.Forms.BindingSource.Filter%2A> 。</span><span class="sxs-lookup"><span data-stu-id="e0dfe-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="e0dfe-104">如果基础数据源是，则可以应用简单排序 <xref:System.ComponentModel.IBindingList> ，如果数据源是，则可以应用筛选和高级排序 <xref:System.ComponentModel.IBindingListView> 。</span><span class="sxs-lookup"><span data-stu-id="e0dfe-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="e0dfe-105"><xref:System.Windows.Forms.BindingSource.Sort%2A>属性需要标准 ADO.NET 语法：一个字符串，表示数据源中的数据列的名称，后跟 `ASC` 或 `DESC` 以指示列表应按升序排序还是按降序排序。</span><span class="sxs-lookup"><span data-stu-id="e0dfe-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard ADO.NET syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="e0dfe-106">您可以通过用逗号分隔符分隔每一列来设置高级排序或多列排序。</span><span class="sxs-lookup"><span data-stu-id="e0dfe-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="e0dfe-107"><xref:System.Windows.Forms.BindingSource.Filter%2A>属性采用字符串表达式。</span><span class="sxs-lookup"><span data-stu-id="e0dfe-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0dfe-108">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="e0dfe-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="e0dfe-109">若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。</span><span class="sxs-lookup"><span data-stu-id="e0dfe-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="e0dfe-110">有关详细信息，请参阅 [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)。</span><span class="sxs-lookup"><span data-stu-id="e0dfe-110">For more information, see [Protecting Connection Information](/dotnet/framework/data/adonet/protecting-connection-information).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="e0dfe-111">用 BindingSource 筛选数据</span><span class="sxs-lookup"><span data-stu-id="e0dfe-111">To filter data with the BindingSource</span></span>  
  
- <span data-ttu-id="e0dfe-112">将 <xref:System.Windows.Forms.BindingSource.Filter%2A> 属性设置为所需的 expression。</span><span class="sxs-lookup"><span data-stu-id="e0dfe-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="e0dfe-113">在下面的代码示例中，表达式是列名，后跟要用于该列的值。</span><span class="sxs-lookup"><span data-stu-id="e0dfe-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="e0dfe-114">用 BindingSource 对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="e0dfe-114">To sort data with the BindingSource</span></span>  
  
1. <span data-ttu-id="e0dfe-115">将属性设置为所需的列名，并将其设置为 <xref:System.Windows.Forms.BindingSource.Sort%2A> `ASC` 或 `DESC` 以指示升序或降序。</span><span class="sxs-lookup"><span data-stu-id="e0dfe-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2. <span data-ttu-id="e0dfe-116">用逗号分隔多个列。</span><span class="sxs-lookup"><span data-stu-id="e0dfe-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="e0dfe-117">示例</span><span class="sxs-lookup"><span data-stu-id="e0dfe-117">Example</span></span>  

 <span data-ttu-id="e0dfe-118">下面的代码示例将 Northwind 示例数据库的 Customers 表中的数据加载到 <xref:System.Windows.Forms.DataGridView> 控件中，并对显示的数据进行筛选和排序。</span><span class="sxs-lookup"><span data-stu-id="e0dfe-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e0dfe-119">编译代码</span><span class="sxs-lookup"><span data-stu-id="e0dfe-119">Compiling the Code</span></span>  

 <span data-ttu-id="e0dfe-120">若要运行此示例，请将代码粘贴到包含 <xref:System.Windows.Forms.BindingSource> 名为的 `BindingSource1` 和名为的的窗体中 <xref:System.Windows.Forms.DataGridView> `dataGridView1` 。</span><span class="sxs-lookup"><span data-stu-id="e0dfe-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="e0dfe-121">处理 <xref:System.Windows.Forms.Form.Load> 窗体的事件，并 `InitializeSortedFilteredBindingSource` 在 load 事件处理程序方法中调用。</span><span class="sxs-lookup"><span data-stu-id="e0dfe-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0dfe-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0dfe-122">See also</span></span>

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- <span data-ttu-id="e0dfe-123">[如何：安装示例数据库](/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e0dfe-123">[How to: Install Sample Databases](/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))</span></span>
- [<span data-ttu-id="e0dfe-124">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="e0dfe-124">BindingSource Component</span></span>](bindingsource-component.md)
