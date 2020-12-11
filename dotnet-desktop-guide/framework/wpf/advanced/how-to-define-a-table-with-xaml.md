---
title: 如何：使用 XAML 定义表
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 709e977670b867f6513bf166918d3bcba0a8c62c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972469"
---
# <a name="how-to-define-a-table-with-xaml"></a>如何：使用 XAML 定义表
下面的示例演示如何 <xref:System.Windows.Documents.Table> 使用定义 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。  示例表中有四列 (由 <xref:System.Windows.Documents.TableColumn> 元素) 和多个行 (表示， <xref:System.Windows.Documents.TableRow>) 包含数据的元素以及标题、页眉和页脚信息。  行必须包含在元素中 <xref:System.Windows.Documents.TableRowGroup> 。  表中的每一行都由一个或多个单元格组成， (由 <xref:System.Windows.Documents.TableCell> 元素) 表示。  表单元格中的内容必须包含在元素中 <xref:System.Windows.Documents.Block> ; 在此示例中， <xref:System.Windows.Documents.Paragraph> 使用了元素。  该表还承载了一个超链接 (由 <xref:System.Windows.Documents.Hyperlink> 脚注行中的元素) 表示。  
  
## <a name="example"></a>示例  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 下图显示了此示例中定义的表如何呈现：  
  
 ![使用 XAML 定义的表的屏幕截图。](./media/how-to-define-a-table-with-xaml/planetary-information-xaml-table.png)
