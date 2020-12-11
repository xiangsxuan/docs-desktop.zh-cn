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
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>演练：处理在 Windows 窗体 DataGridView 控件中输入数据时发生的错误

处理基础数据存储区中的错误是数据输入应用程序所必需的功能。 <xref:System.Windows.Forms.DataGridView>通过公开事件，Windows 窗体控件可以轻松地实现这 <xref:System.Windows.Forms.DataGridView.DataError> 一点，在数据存储区检测到违反约束或违反业务规则时，将引发此事件。

在本演练中，您将从 `Customers` Northwind 示例数据库的表中检索行，并将它们显示在 <xref:System.Windows.Forms.DataGridView> 控件中。 当 `CustomerID` 在新行或已编辑的现有行中检测到重复值时，将 <xref:System.Windows.Forms.DataGridView.DataError> 发生该事件，将通过显示描述该异常的来处理该事件 <xref:System.Windows.Forms.MessageBox> 。

若要将本主题中的代码复制为单个列表，请参阅 [如何：处理 Windows 窗体 DataGridView 控件中的数据输入期间发生的错误](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)。

## <a name="prerequisites"></a>先决条件

若要完成本演练，你将需要：

- 访问包含 Northwind SQL Server 示例数据库的服务器。

## <a name="creating-the-form"></a>创建窗体

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>处理 DataGridView 控件中的数据输入错误

1. 创建一个派生自的类， <xref:System.Windows.Forms.Form> 并包含一个 <xref:System.Windows.Forms.DataGridView> 控件和一个 <xref:System.Windows.Forms.BindingSource> 组件。

    下面的代码示例提供了基本的初始化并包含 `Main` 方法。

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. 在窗体的类定义中实现一个方法，用于处理连接到数据库的详细信息。

    此代码示例使用一个 `GetData` 方法，该方法返回填充的 <xref:System.Data.DataTable> 对象。 请确保将 `connectionString` 变量设置为适合数据库的值。

    > [!IMPORTANT]
    > 将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。 有关详细信息，请参阅 [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)。

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. 实现窗体事件的处理程序 <xref:System.Windows.Forms.Form.Load> ，该处理程序初始化 <xref:System.Windows.Forms.DataGridView> 和 <xref:System.Windows.Forms.BindingSource> 并设置数据绑定。

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. 在 <xref:System.Windows.Forms.DataGridView.DataError> 上处理事件 <xref:System.Windows.Forms.DataGridView> 。

    如果错误的上下文是提交操作，请在中显示错误 <xref:System.Windows.Forms.MessageBox> 。

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a>测试应用程序

你现在可以对窗体进行测试，以确保它按预期方式运行。

#### <a name="to-test-the-form"></a>测试窗体

- 按 F5 运行该应用程序。

  您将看到一个 <xref:System.Windows.Forms.DataGridView> 用 Customers 表中的数据填充的控件。 如果为输入重复值 `CustomerID` 并提交编辑，则单元值将自动还原，并且你将看到一个 <xref:System.Windows.Forms.MessageBox> 显示数据输入错误的。

## <a name="next-steps"></a>后续步骤

此应用程序可让你对控件的功能有一个基本的了解 <xref:System.Windows.Forms.DataGridView> 。 可以通过多种方式自定义控件的外观和行为 <xref:System.Windows.Forms.DataGridView> ：

- 更改边框和标题样式。 有关详细信息，请参阅 [如何：更改 Windows 窗体 DataGridView 控件中的边框和网格线样式](change-the-border-and-gridline-styles-in-the-datagrid.md)。

- 启用或限制控件的用户输入 <xref:System.Windows.Forms.DataGridView> 。 有关详细信息，请参阅 [如何：防止在 Windows 窗体 Datagridview 控件中添加和删除行](prevent-row-addition-and-deletion-datagridview.md)，以及 [如何：使列在 Windows 窗体 DataGridView 控件中 Read-Only](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)。

- 验证控件的用户输入 <xref:System.Windows.Forms.DataGridView> 。 有关详细信息，请参阅 [演练：验证 Windows 窗体 DataGridView 控件中的数据](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)。

- 使用虚拟模式处理非常大的数据集。 有关详细信息，请参阅 [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)。

- 自定义单元格的外观。 有关详细信息，请参阅 [如何：自定义 Windows 窗体 Datagridview 控件中单元格的外观](customize-the-appearance-of-cells-in-the-datagrid.md) 和 [如何：为 Windows 窗体 Datagridview 控件设置默认单元格样式](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Windows 窗体 DataGridView 控件中的数据输入](data-entry-in-the-windows-forms-datagridview-control.md)
- [如何：处理在 Windows 窗体 DataGridView 控件中输入数据时发生的错误](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [演练：在 Windows 窗体 DataGridView 控件中验证数据](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)
