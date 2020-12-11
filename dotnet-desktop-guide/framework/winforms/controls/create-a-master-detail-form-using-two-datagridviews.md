---
title: 使用两个 DataGridView 控件创建 Master-Detail 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], creating
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
ms.openlocfilehash: d490af6517e7e45bb2dd48ab7d41c468a7eba2aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970169"
---
# <a name="how-to-create-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>如何：使用两个 Windows 窗体 DataGridView 控件创建一个主/详细信息窗体

以下代码示例使用绑定到两个 <xref:System.Windows.Forms.BindingSource> 组件的两个 <xref:System.Windows.Forms.DataGridView> 控件创建主窗体/详细窗体。 数据源是一个 <xref:System.Data.DataSet>，其中包含来自 Northwind SQL Server 示例数据库的 `Customers` 和 `Orders` 表以及通过 `CustomerID` 列关联这两张表的 <xref:System.Data.DataRelation>。  
  
 一个 <xref:System.Windows.Forms.BindingSource> 被绑定到数据集中的父 `Customers` 表。 此数据在主 <xref:System.Windows.Forms.DataGridView> 控件中显示。 其他 <xref:System.Windows.Forms.BindingSource> 被绑定到第一个数据连接器。 第二个 <xref:System.Windows.Forms.BindingSource> 的 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 属性被设置为 <xref:System.Data.DataRelation> 名称。 这将导致相关联的详细 <xref:System.Windows.Forms.DataGridView> 控件显示子 `Orders` 表中与主 <xref:System.Windows.Forms.DataGridView> 控件中当前行相对应的行。  
  
 有关此代码示例的完整说明，请参阅 [演练：使用两个 Windows 窗体 DataGridView 控件创建主窗体/详细信息窗体](creating-a-master-detail-form-using-two-datagridviews.md)。  
  
## <a name="example"></a>示例  

 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## <a name="compiling-the-code"></a>编译代码  

 此示例需要：  
  
 引用 System、System.Data、System.Windows.Forms 和 System.XML 程序集。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  

 将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。 有关详细信息，请参阅 [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [演练：使用两个 Windows 窗体 DataGridView 控件创建主窗体/详细信息窗体](creating-a-master-detail-form-using-two-datagridviews.md)
- [在 Windows 窗体 DataGridView 控件中显示数据](displaying-data-in-the-windows-forms-datagridview-control.md)
- [保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)
