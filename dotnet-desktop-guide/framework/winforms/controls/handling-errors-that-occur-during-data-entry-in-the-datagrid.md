---
title: 演练：处理 DataGridView 控件中的数据输入期间发生的错误
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
ms.openlocfilehash: d65dd038ddc276ec09a1db3af4f14fc87fec56f2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971520"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="24c20-102">演练：处理在 Windows 窗体 DataGridView 控件中输入数据时发生的错误</span><span class="sxs-lookup"><span data-stu-id="24c20-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="24c20-103">处理基础数据存储区中的错误是数据输入应用程序所必需的功能。</span><span class="sxs-lookup"><span data-stu-id="24c20-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="24c20-104"><xref:System.Windows.Forms.DataGridView>通过公开事件，Windows 窗体控件可以轻松地实现这 <xref:System.Windows.Forms.DataGridView.DataError> 一点，在数据存储区检测到违反约束或违反业务规则时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="24c20-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>

<span data-ttu-id="24c20-105">在本演练中，您将从 `Customers` Northwind 示例数据库的表中检索行，并将它们显示在 <xref:System.Windows.Forms.DataGridView> 控件中。</span><span class="sxs-lookup"><span data-stu-id="24c20-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="24c20-106">当 `CustomerID` 在新行或已编辑的现有行中检测到重复值时，将 <xref:System.Windows.Forms.DataGridView.DataError> 发生该事件，将通过显示描述该异常的来处理该事件 <xref:System.Windows.Forms.MessageBox> 。</span><span class="sxs-lookup"><span data-stu-id="24c20-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>

<span data-ttu-id="24c20-107">若要将本主题中的代码复制为单个列表，请参阅 [如何：处理 Windows 窗体 DataGridView 控件中的数据输入期间发生的错误](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="24c20-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="24c20-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="24c20-108">Prerequisites</span></span>

<span data-ttu-id="24c20-109">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="24c20-109">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="24c20-110">访问包含 Northwind SQL Server 示例数据库的服务器。</span><span class="sxs-lookup"><span data-stu-id="24c20-110">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="24c20-111">创建窗体</span><span class="sxs-lookup"><span data-stu-id="24c20-111">Creating the Form</span></span>

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="24c20-112">处理 DataGridView 控件中的数据输入错误</span><span class="sxs-lookup"><span data-stu-id="24c20-112">To handle data-entry errors in the DataGridView control</span></span>

1. <span data-ttu-id="24c20-113">创建一个派生自的类， <xref:System.Windows.Forms.Form> 并包含一个 <xref:System.Windows.Forms.DataGridView> 控件和一个 <xref:System.Windows.Forms.BindingSource> 组件。</span><span class="sxs-lookup"><span data-stu-id="24c20-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>

    <span data-ttu-id="24c20-114">下面的代码示例提供了基本的初始化并包含 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="24c20-114">The following code example provides basic initialization and includes a `Main` method.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. <span data-ttu-id="24c20-115">在窗体的类定义中实现一个方法，用于处理连接到数据库的详细信息。</span><span class="sxs-lookup"><span data-stu-id="24c20-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>

    <span data-ttu-id="24c20-116">此代码示例使用一个 `GetData` 方法，该方法返回填充的 <xref:System.Data.DataTable> 对象。</span><span class="sxs-lookup"><span data-stu-id="24c20-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="24c20-117">请确保将 `connectionString` 变量设置为适合数据库的值。</span><span class="sxs-lookup"><span data-stu-id="24c20-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="24c20-118">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="24c20-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="24c20-119">若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。</span><span class="sxs-lookup"><span data-stu-id="24c20-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="24c20-120">有关详细信息，请参阅 [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)。</span><span class="sxs-lookup"><span data-stu-id="24c20-120">For more information, see [Protecting Connection Information](/dotnet/framework/data/adonet/protecting-connection-information).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. <span data-ttu-id="24c20-121">实现窗体事件的处理程序 <xref:System.Windows.Forms.Form.Load> ，该处理程序初始化 <xref:System.Windows.Forms.DataGridView> 和 <xref:System.Windows.Forms.BindingSource> 并设置数据绑定。</span><span class="sxs-lookup"><span data-stu-id="24c20-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. <span data-ttu-id="24c20-122">在 <xref:System.Windows.Forms.DataGridView.DataError> 上处理事件 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="24c20-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>

    <span data-ttu-id="24c20-123">如果错误的上下文是提交操作，请在中显示错误 <xref:System.Windows.Forms.MessageBox> 。</span><span class="sxs-lookup"><span data-stu-id="24c20-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a><span data-ttu-id="24c20-124">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="24c20-124">Testing the Application</span></span>

<span data-ttu-id="24c20-125">你现在可以对窗体进行测试，以确保它按预期方式运行。</span><span class="sxs-lookup"><span data-stu-id="24c20-125">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="24c20-126">测试窗体</span><span class="sxs-lookup"><span data-stu-id="24c20-126">To test the form</span></span>

- <span data-ttu-id="24c20-127">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="24c20-127">Press F5 to run the application.</span></span>

  <span data-ttu-id="24c20-128">您将看到一个 <xref:System.Windows.Forms.DataGridView> 用 Customers 表中的数据填充的控件。</span><span class="sxs-lookup"><span data-stu-id="24c20-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="24c20-129">如果为输入重复值 `CustomerID` 并提交编辑，则单元值将自动还原，并且你将看到一个 <xref:System.Windows.Forms.MessageBox> 显示数据输入错误的。</span><span class="sxs-lookup"><span data-stu-id="24c20-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="24c20-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="24c20-130">Next Steps</span></span>

<span data-ttu-id="24c20-131">此应用程序可让你对控件的功能有一个基本的了解 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="24c20-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="24c20-132">可以通过多种方式自定义控件的外观和行为 <xref:System.Windows.Forms.DataGridView> ：</span><span class="sxs-lookup"><span data-stu-id="24c20-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="24c20-133">更改边框和标题样式。</span><span class="sxs-lookup"><span data-stu-id="24c20-133">Change border and header styles.</span></span> <span data-ttu-id="24c20-134">有关详细信息，请参阅 [如何：更改 Windows 窗体 DataGridView 控件中的边框和网格线样式](change-the-border-and-gridline-styles-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="24c20-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="24c20-135">启用或限制控件的用户输入 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="24c20-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="24c20-136">有关详细信息，请参阅 [如何：防止在 Windows 窗体 Datagridview 控件中添加和删除行](prevent-row-addition-and-deletion-datagridview.md)，以及 [如何：使列在 Windows 窗体 DataGridView 控件中 Read-Only](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="24c20-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="24c20-137">验证控件的用户输入 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="24c20-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="24c20-138">有关详细信息，请参阅 [演练：验证 Windows 窗体 DataGridView 控件中的数据](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="24c20-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="24c20-139">使用虚拟模式处理非常大的数据集。</span><span class="sxs-lookup"><span data-stu-id="24c20-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="24c20-140">有关详细信息，请参阅 [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="24c20-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="24c20-141">自定义单元格的外观。</span><span class="sxs-lookup"><span data-stu-id="24c20-141">Customize the appearance of cells.</span></span> <span data-ttu-id="24c20-142">有关详细信息，请参阅 [如何：自定义 Windows 窗体 Datagridview 控件中单元格的外观](customize-the-appearance-of-cells-in-the-datagrid.md) 和 [如何：为 Windows 窗体 Datagridview 控件设置默认单元格样式](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="24c20-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="24c20-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24c20-143">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="24c20-144">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="24c20-144">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="24c20-145">如何：处理在 Windows 窗体 DataGridView 控件中输入数据时发生的错误</span><span class="sxs-lookup"><span data-stu-id="24c20-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="24c20-146">演练：在 Windows 窗体 DataGridView 控件中验证数据</span><span class="sxs-lookup"><span data-stu-id="24c20-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="24c20-147">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="24c20-147">Protecting Connection Information</span></span>](/dotnet/framework/data/adonet/protecting-connection-information)
