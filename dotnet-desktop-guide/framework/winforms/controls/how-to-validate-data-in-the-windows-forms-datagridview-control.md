---
title: 在 DataGridView 控件中验证数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
ms.assetid: d10aef35-701e-4a3c-a684-2a2ed1aeaca6
ms.openlocfilehash: 120a228910a4e6f45d45eaf0001c6cba33fdb733
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971116"
---
# <a name="how-to-validate-data-in-the-windows-forms-datagridview-control"></a>如何：验证 Windows 窗体 DataGridView 控件中的数据

下面的代码示例演示如何验证由用户输入到 <xref:System.Windows.Forms.DataGridView> 控件中的数据。 在此示例中，使用 Northwind 示例数据的 `Customers` 表中的行填充 <xref:System.Windows.Forms.DataGridView>。 用户编辑 `CompanyName` 列中的单元格时，通过检查单元格不为空而测试其值的有效性。 如果 <xref:System.Windows.Forms.DataGridView.CellValidating> 事件的事件处理程序发现该值为空字符串，<xref:System.Windows.Forms.DataGridView> 会阻止用户退出单元格，直到输入了一个非空字符串。  
  
 有关此代码示例的完整说明，请参阅[演练：验证 Windows 窗体 DataGridView 控件中的数据](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="example"></a>示例  

 [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#00)]  
  
## <a name="compiling-the-code"></a>编译代码  

 此示例需要：  
  
- 引用 System、System.Data、System.Windows.Forms 和 System.XML 程序集。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  

 将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。 有关详细信息，请参阅 [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [演练：在 Windows 窗体 DataGridView 控件中验证数据](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的数据输入](data-entry-in-the-windows-forms-datagridview-control.md)
- [演练：处理在 Windows 窗体 DataGridView 控件中输入数据时发生的错误](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)
