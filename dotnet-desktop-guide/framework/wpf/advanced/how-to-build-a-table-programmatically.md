---
title: 如何：以编程方式生成表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tables [WPF], creating programmatically
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
ms.openlocfilehash: 586bff2e0aa1a545dc070a8bab2cdc6ed9a104ce
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971918"
---
# <a name="how-to-build-a-table-programmatically"></a>如何：以编程方式生成表
下面的示例演示如何以编程方式创建 <xref:System.Windows.Documents.Table> 和填充内容。 表中的内容分配为 (由 <xref:System.Windows.Documents.TableRow> 对象中包含的对象 <xref:System.Windows.Documents.Table.RowGroups%2A>) 和六个 (由对象表示) 表示的对象来表示 <xref:System.Windows.Documents.TableColumn> 。 各行用于不同的显示目的，其中，标题行用于显示整个表的标题，标头行用于描述表中的数据列，而页脚行则包含摘要信息。  请注意，“标题”行、“标头”行和“页脚”行并非表格所固有的，它们只是具有不同特征的行。 表单元格包含实际内容，这些内容可以包括文本、图像或几乎任何其他 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 元素。  
  
## <a name="example"></a>示例  
 首先， <xref:System.Windows.Documents.FlowDocument> 创建一个来承载的 <xref:System.Windows.Documents.Table> ，并创建一个新的并将其 <xref:System.Windows.Documents.Table> 添加到的内容中 <xref:System.Windows.Documents.FlowDocument> 。  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## <a name="example"></a>示例  
 接下来， <xref:System.Windows.Documents.TableColumn> 将创建六个对象并将其添加到表的 <xref:System.Windows.Documents.Table.Columns%2A> 集合，并应用某些格式设置。  
  
> [!NOTE]
> 请注意，表的 <xref:System.Windows.Documents.Table.Columns%2A> 集合使用从零开始的标准索引。  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## <a name="example"></a>示例  
 接下来，创建一个标题行，并将其添加到表中，同时应用某些格式设置。  标题行包含一个单元格，该单元格跨表中的全部六列。  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## <a name="example"></a>示例  
 接下来，创建一个标头行并将其添加到表中，同时创建标头行中的单元格并填充其内容。  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## <a name="example"></a>示例  
 接下来，创建一个数据行并将其添加到表中，同时创建此行中的单元格并填充其内容。  生成此行的过程与生成标头行的过程类似，只是应用的格式设置略有不同。  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## <a name="example"></a>示例  
 最后，创建、添加脚注行并设置其格式。  与标题行类似，脚注包含的单元格的跨度为表中的全部六列。  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>另请参阅

- [表概述](table-overview.md)
