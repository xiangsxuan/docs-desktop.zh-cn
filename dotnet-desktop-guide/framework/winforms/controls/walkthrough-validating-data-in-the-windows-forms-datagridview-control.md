---
title: 演练：在 DataGridView 控件中验证数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating data [Windows Forms], Windows Forms
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
ms.openlocfilehash: 822a09565e81d308179dd0b51993a758738922bb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972491"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>演练：验证 Windows 窗体 DataGridView 控件中的数据

向用户显示数据输入功能时，通常需要验证输入到窗体中的数据。 <xref:System.Windows.Forms.DataGridView>类提供一种在数据提交到数据存储之前执行验证的便捷方法。 可以通过处理事件来验证数据 <xref:System.Windows.Forms.DataGridView.CellValidating> ，该事件由 <xref:System.Windows.Forms.DataGridView> 当前单元格更改时引发。

在本演练中，您将从 `Customers` Northwind 示例数据库的表中检索行，并将它们显示在 <xref:System.Windows.Forms.DataGridView> 控件中。 当用户编辑列中的单元格 `CompanyName` 并尝试离开单元格时， <xref:System.Windows.Forms.DataGridView.CellValidating> 事件处理程序将检查新公司名称字符串以确保它不为空; 如果新值为空字符串， <xref:System.Windows.Forms.DataGridView> 将阻止用户的光标离开该单元格，直到输入非空字符串。

若要将本主题中的代码复制为单个列表，请参阅 [如何：验证 Windows 窗体 DataGridView 控件中的数据](how-to-validate-data-in-the-windows-forms-datagridview-control.md)。

## <a name="prerequisites"></a>先决条件

若要完成本演练，你将需要：

- 访问包含 Northwind SQL Server 示例数据库的服务器。

## <a name="creating-the-form"></a>创建窗体

#### <a name="to-validate-data-entered-in-a-datagridview"></a>验证 DataGridView 中输入的数据

1. 创建一个派生自的类， <xref:System.Windows.Forms.Form> 并包含一个 <xref:System.Windows.Forms.DataGridView> 控件和一个 <xref:System.Windows.Forms.BindingSource> 组件。

    下面的代码示例提供了基本的初始化并包含 `Main` 方法。

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]

2. 在窗体的类定义中实现一个方法，用于处理连接到数据库的详细信息。

    此代码示例使用一个 `GetData` 方法，该方法返回填充的 <xref:System.Data.DataTable> 对象。 请确保将 `connectionString` 变量设置为适合数据库的值。

    > [!IMPORTANT]
    > 将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 使用 Windows 身份验证（也称为集成安全性）是一种更安全的方式来控制对数据库的访问。 有关详细信息，请参阅 [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)。

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]

3. 实现窗体事件的处理程序 <xref:System.Windows.Forms.Form.Load> ，该处理程序初始化 <xref:System.Windows.Forms.DataGridView> 和 <xref:System.Windows.Forms.BindingSource> 并设置数据绑定。

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]

4. 为 <xref:System.Windows.Forms.DataGridView> 控件的和事件实现处理程序 <xref:System.Windows.Forms.DataGridView.CellValidating> <xref:System.Windows.Forms.DataGridView.CellEndEdit> 。

    在 <xref:System.Windows.Forms.DataGridView.CellValidating> 事件处理程序中，您可以确定列中单元格的值是否为 `CompanyName` 空。 如果单元格值验证失败，请将 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 类的属性设置 <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> 为 `true` 。 这将导致 <xref:System.Windows.Forms.DataGridView> 控件阻止光标离开该单元格。 将 <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> 行中的属性设置为解释性字符串。 这会显示一个错误图标，其中包含包含错误文本的工具提示。 在 <xref:System.Windows.Forms.DataGridView.CellEndEdit> 事件处理程序中，将 <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> 行上的属性设置为空字符串。 <xref:System.Windows.Forms.DataGridView.CellEndEdit>仅当单元格退出编辑模式时，才会发生此事件，如果验证失败，则无法执行此操作。

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]

## <a name="testing-the-application"></a>测试应用程序

你现在可以对窗体进行测试，以确保它按预期方式运行。

#### <a name="to-test-the-form"></a>测试窗体

- 编译并运行该应用程序。

  您将看到 <xref:System.Windows.Forms.DataGridView> 使用表中的数据进行 `Customers` 填充。 双击列中的单元时 `CompanyName` ，可以编辑值。 如果删除所有字符并按 TAB 键退出单元格，则 <xref:System.Windows.Forms.DataGridView> 会阻止你退出。 当您在单元格中键入非空字符串时， <xref:System.Windows.Forms.DataGridView> 控件允许您退出单元。

## <a name="next-steps"></a>后续步骤

此应用程序可让你对控件的功能有一个基本的了解 <xref:System.Windows.Forms.DataGridView> 。 可以通过多种方式自定义控件的外观和行为 <xref:System.Windows.Forms.DataGridView> ：

- 更改边框和标题样式。 有关详细信息，请参阅 [如何：更改 Windows 窗体 DataGridView 控件中的边框和网格线样式](change-the-border-and-gridline-styles-in-the-datagrid.md)。

- 启用或限制控件的用户输入 <xref:System.Windows.Forms.DataGridView> 。 有关详细信息，请参阅 [如何：防止在 Windows 窗体 Datagridview 控件中添加和删除行](prevent-row-addition-and-deletion-datagridview.md)，以及 [如何：使列在 Windows 窗体 DataGridView 控件中 Read-Only](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)。

- 检查用户输入中的数据库相关错误。 有关详细信息，请参阅 [演练：处理 Windows 窗体 DataGridView 控件中的数据输入过程中发生的错误](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)。

- 使用虚拟模式处理非常大的数据集。 有关详细信息，请参阅 [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)。

- 自定义单元格的外观。 有关详细信息，请参阅 [如何：自定义 Windows 窗体 Datagridview 控件中单元格的外观](customize-the-appearance-of-cells-in-the-datagrid.md) 和 [如何：在 Windows 窗体 Datagridview 控件中设置字体和颜色样式](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Windows 窗体 DataGridView 控件中的数据输入](data-entry-in-the-windows-forms-datagridview-control.md)
- [如何：验证 Windows 窗体 DataGridView 控件中的数据](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [演练：处理在 Windows 窗体 DataGridView 控件中输入数据时发生的错误](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)
