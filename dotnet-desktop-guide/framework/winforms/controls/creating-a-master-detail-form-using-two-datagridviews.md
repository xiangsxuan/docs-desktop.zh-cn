---
title: 演练：使用两个 DataGridView 控件创建主/详细信息窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
ms.openlocfilehash: d6057eb16e8fc32c269d3013ee99cc1f276ecab6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970161"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a><span data-ttu-id="c8a59-102">演练：使用两个 Windows 窗体 DataGridView 控件创建一个主/详细信息窗体</span><span class="sxs-lookup"><span data-stu-id="c8a59-102">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>

<span data-ttu-id="c8a59-103">使用控件的最常见方案之一 <xref:System.Windows.Forms.DataGridView> 是 *主/详细信息* 窗体，其中显示两个数据库表之间的父/子关系。</span><span class="sxs-lookup"><span data-stu-id="c8a59-103">One of the most common scenarios for using the <xref:System.Windows.Forms.DataGridView> control is the *master/detail* form, in which a parent/child relationship between two database tables is displayed.</span></span> <span data-ttu-id="c8a59-104">如果选择主表中的行，则会将详细信息表更新为相应的子数据。</span><span class="sxs-lookup"><span data-stu-id="c8a59-104">Selecting rows in the master table causes the detail table to update with the corresponding child data.</span></span>

<span data-ttu-id="c8a59-105">使用控件和组件之间的交互可以轻松实现主/详细信息窗体 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.BindingSource> 。</span><span class="sxs-lookup"><span data-stu-id="c8a59-105">Implementing a master/detail form is easy using the interaction between the <xref:System.Windows.Forms.DataGridView> control and the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="c8a59-106">在本演练中，您将使用两个 <xref:System.Windows.Forms.DataGridView> 控件和两个组件生成窗体 <xref:System.Windows.Forms.BindingSource> 。</span><span class="sxs-lookup"><span data-stu-id="c8a59-106">In this walkthrough, you will build the form using two <xref:System.Windows.Forms.DataGridView> controls and two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="c8a59-107">此窗体将在 Northwind SQL Server 示例数据库中显示两个相关的表： `Customers` 和 `Orders` 。</span><span class="sxs-lookup"><span data-stu-id="c8a59-107">The form will show two related tables in the Northwind SQL Server sample database: `Customers` and `Orders`.</span></span> <span data-ttu-id="c8a59-108">完成后，您将获得一个窗体，其中显示了主数据库中的所有客户 <xref:System.Windows.Forms.DataGridView> 以及所选客户在详细信息中的所有订单 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="c8a59-108">When you are finished, you will have a form that shows all the customers in the database in the master <xref:System.Windows.Forms.DataGridView> and all the orders for the selected customer in the detail <xref:System.Windows.Forms.DataGridView>.</span></span>

<span data-ttu-id="c8a59-109">若要将本主题中的代码复制为单个列表，请参阅 [如何：使用两个 Windows 窗体 DataGridView 控件创建主窗体/详细信息窗体](create-a-master-detail-form-using-two-datagridviews.md)。</span><span class="sxs-lookup"><span data-stu-id="c8a59-109">To copy the code in this topic as a single listing, see [How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls](create-a-master-detail-form-using-two-datagridviews.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c8a59-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="c8a59-110">Prerequisites</span></span>

<span data-ttu-id="c8a59-111">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="c8a59-111">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="c8a59-112">访问包含 Northwind SQL Server 示例数据库的服务器。</span><span class="sxs-lookup"><span data-stu-id="c8a59-112">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="c8a59-113">创建窗体</span><span class="sxs-lookup"><span data-stu-id="c8a59-113">Creating the form</span></span>

#### <a name="to-create-a-masterdetail-form"></a><span data-ttu-id="c8a59-114">创建主窗体/详细信息窗体</span><span class="sxs-lookup"><span data-stu-id="c8a59-114">To create a master/detail form</span></span>

1. <span data-ttu-id="c8a59-115">创建一个从派生的类， <xref:System.Windows.Forms.Form> 其中包含两个 <xref:System.Windows.Forms.DataGridView> 控件和两个 <xref:System.Windows.Forms.BindingSource> 组件。</span><span class="sxs-lookup"><span data-stu-id="c8a59-115">Create a class that derives from <xref:System.Windows.Forms.Form> and contains two <xref:System.Windows.Forms.DataGridView> controls and two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="c8a59-116">下面的代码提供基本的窗体初始化并包含 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="c8a59-116">The following code provides basic form initialization and includes a `Main` method.</span></span> <span data-ttu-id="c8a59-117">如果你使用 Visual Studio 设计器来创建窗体，则可以使用设计器生成的代码而不是此代码，但请务必使用此处的变量声明中显示的名称。</span><span class="sxs-lookup"><span data-stu-id="c8a59-117">If you use the Visual Studio designer to create your form, you can use the designer generated code instead of this code, but be sure to use the names shown in the variable declarations here.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. <span data-ttu-id="c8a59-118">在窗体的类定义中实现一个方法，用于处理连接到数据库的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c8a59-118">Implement a method in your form's class definition for handling the detail of connecting to the database.</span></span> <span data-ttu-id="c8a59-119">此示例使用一个 `GetData` 方法，该方法填充 <xref:System.Data.DataSet> 对象，将 <xref:System.Data.DataRelation> 对象添加到数据集，并绑定这些 <xref:System.Windows.Forms.BindingSource> 组件。</span><span class="sxs-lookup"><span data-stu-id="c8a59-119">This example uses a `GetData` method that populates a <xref:System.Data.DataSet> object, adds a <xref:System.Data.DataRelation> object to the data set, and binds the <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="c8a59-120">请确保将 `connectionString` 变量设置为适合数据库的值。</span><span class="sxs-lookup"><span data-stu-id="c8a59-120">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c8a59-121">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="c8a59-121">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="c8a59-122">若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。</span><span class="sxs-lookup"><span data-stu-id="c8a59-122">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="c8a59-123">有关详细信息，请参阅 [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)。</span><span class="sxs-lookup"><span data-stu-id="c8a59-123">For more information, see [Protecting Connection Information](/dotnet/framework/data/adonet/protecting-connection-information).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. <span data-ttu-id="c8a59-124">实现窗体事件的处理程序 <xref:System.Windows.Forms.Form.Load> ，该处理程序将 <xref:System.Windows.Forms.DataGridView> 控件绑定到 <xref:System.Windows.Forms.BindingSource> 组件并调用 `GetData` 方法。</span><span class="sxs-lookup"><span data-stu-id="c8a59-124">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that binds the <xref:System.Windows.Forms.DataGridView> controls to the <xref:System.Windows.Forms.BindingSource> components and calls the `GetData` method.</span></span> <span data-ttu-id="c8a59-125">下面的示例包含 <xref:System.Windows.Forms.DataGridView> 可调整列大小以适应显示的数据的代码。</span><span class="sxs-lookup"><span data-stu-id="c8a59-125">The following example includes code that resizes <xref:System.Windows.Forms.DataGridView> columns to fit the displayed data.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a><span data-ttu-id="c8a59-126">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="c8a59-126">Testing the Application</span></span>

<span data-ttu-id="c8a59-127">你现在可以对窗体进行测试，以确保它按预期方式运行。</span><span class="sxs-lookup"><span data-stu-id="c8a59-127">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="c8a59-128">测试窗体</span><span class="sxs-lookup"><span data-stu-id="c8a59-128">To test the form</span></span>

- <span data-ttu-id="c8a59-129">编译并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c8a59-129">Compile and run the application.</span></span>

  <span data-ttu-id="c8a59-130">您将看到两个 <xref:System.Windows.Forms.DataGridView> 控件，一个在对方。</span><span class="sxs-lookup"><span data-stu-id="c8a59-130">You will see two <xref:System.Windows.Forms.DataGridView> controls, one above the other.</span></span> <span data-ttu-id="c8a59-131">在顶部是 Northwind 表中的客户 `Customers` ，底部是 `Orders` 对应于所选客户的。</span><span class="sxs-lookup"><span data-stu-id="c8a59-131">On top are the customers from the Northwind `Customers` table, and at the bottom are the `Orders` corresponding to the selected customer.</span></span> <span data-ttu-id="c8a59-132">选择上部的不同行时，会 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView> 相应地更改的内容。</span><span class="sxs-lookup"><span data-stu-id="c8a59-132">As you select different rows in the upper <xref:System.Windows.Forms.DataGridView>, the contents of the lower <xref:System.Windows.Forms.DataGridView> change accordingly.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c8a59-133">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c8a59-133">Next Steps</span></span>

<span data-ttu-id="c8a59-134">此应用程序可让你对控件的功能有一个基本的了解 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="c8a59-134">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="c8a59-135">可以通过多种方式自定义控件的外观和行为 <xref:System.Windows.Forms.DataGridView> ：</span><span class="sxs-lookup"><span data-stu-id="c8a59-135">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="c8a59-136">更改边框和标题样式。</span><span class="sxs-lookup"><span data-stu-id="c8a59-136">Change border and header styles.</span></span> <span data-ttu-id="c8a59-137">有关详细信息，请参阅 [如何：更改 Windows 窗体 DataGridView 控件中的边框和网格线样式](change-the-border-and-gridline-styles-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="c8a59-137">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="c8a59-138">启用或限制控件的用户输入 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="c8a59-138">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c8a59-139">有关详细信息，请参阅 [如何：防止在 Windows 窗体 Datagridview 控件中添加和删除行](prevent-row-addition-and-deletion-datagridview.md)，以及 [如何：使列在 Windows 窗体 DataGridView 控件中 Read-Only](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="c8a59-139">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="c8a59-140">验证控件的用户输入 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="c8a59-140">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c8a59-141">有关详细信息，请参阅 [演练：验证 Windows 窗体 DataGridView 控件中的数据](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="c8a59-141">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="c8a59-142">使用虚拟模式处理非常大的数据集。</span><span class="sxs-lookup"><span data-stu-id="c8a59-142">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="c8a59-143">有关详细信息，请参阅 [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="c8a59-143">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="c8a59-144">自定义单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="c8a59-144">Customize the appearance of cells.</span></span> <span data-ttu-id="c8a59-145">有关详细信息，请参阅 [如何：自定义 Windows 窗体 Datagridview 控件中单元格的外观](customize-the-appearance-of-cells-in-the-datagrid.md) 和 [如何：为 Windows 窗体 Datagridview 控件设置默认单元格样式](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="c8a59-145">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8a59-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8a59-146">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="c8a59-147">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="c8a59-147">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="c8a59-148">如何：使用两个 Windows 窗体 DataGridView 控件创建一个主/详细信息窗体</span><span class="sxs-lookup"><span data-stu-id="c8a59-148">How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](create-a-master-detail-form-using-two-datagridviews.md)
- [<span data-ttu-id="c8a59-149">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="c8a59-149">Protecting Connection Information</span></span>](/dotnet/framework/data/adonet/protecting-connection-information)
