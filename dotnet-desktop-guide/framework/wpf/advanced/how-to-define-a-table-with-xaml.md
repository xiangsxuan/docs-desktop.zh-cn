---
title: 如何：使用 XAML 定义表
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 709e977670b867f6513bf166918d3bcba0a8c62c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972469"
---
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="25b58-102">如何：使用 XAML 定义表</span><span class="sxs-lookup"><span data-stu-id="25b58-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="25b58-103">下面的示例演示如何 <xref:System.Windows.Documents.Table> 使用定义 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="25b58-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="25b58-104">示例表中有四列 (由 <xref:System.Windows.Documents.TableColumn> 元素) 和多个行 (表示， <xref:System.Windows.Documents.TableRow>) 包含数据的元素以及标题、页眉和页脚信息。</span><span class="sxs-lookup"><span data-stu-id="25b58-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="25b58-105">行必须包含在元素中 <xref:System.Windows.Documents.TableRowGroup> 。</span><span class="sxs-lookup"><span data-stu-id="25b58-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="25b58-106">表中的每一行都由一个或多个单元格组成， (由 <xref:System.Windows.Documents.TableCell> 元素) 表示。</span><span class="sxs-lookup"><span data-stu-id="25b58-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="25b58-107">表单元格中的内容必须包含在元素中 <xref:System.Windows.Documents.Block> ; 在此示例中， <xref:System.Windows.Documents.Paragraph> 使用了元素。</span><span class="sxs-lookup"><span data-stu-id="25b58-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="25b58-108">该表还承载了一个超链接 (由 <xref:System.Windows.Documents.Hyperlink> 脚注行中的元素) 表示。</span><span class="sxs-lookup"><span data-stu-id="25b58-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25b58-109">示例</span><span class="sxs-lookup"><span data-stu-id="25b58-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="25b58-110">下图显示了此示例中定义的表如何呈现：</span><span class="sxs-lookup"><span data-stu-id="25b58-110">The following figure shows how the table defined in this example renders:</span></span>  
  
 ![使用 XAML 定义的表的屏幕截图。](./media/how-to-define-a-table-with-xaml/planetary-information-xaml-table.png)
