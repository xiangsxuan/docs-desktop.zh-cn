---
title: 如何：通过 Columns 属性操作表列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating table columns
- properties [WPF], Columns [WPF], manipulating table columns
- tables [WPF], manipulating columns
- Columns property [WPF]
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
ms.openlocfilehash: 18a26c76688ebf668293cb1254404d6d2cf15208
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973661"
---
# <a name="how-to-manipulate-a-tables-columns-through-the-columns-property"></a><span data-ttu-id="0278a-102">如何：通过 Columns 属性操作表列</span><span class="sxs-lookup"><span data-stu-id="0278a-102">How to: Manipulate a Table's Columns through the Columns Property</span></span>
<span data-ttu-id="0278a-103">此示例演示了一些更常见的操作，这些操作可通过属性在表的列上执行 <xref:System.Windows.Documents.Table.Columns%2A> 。</span><span class="sxs-lookup"><span data-stu-id="0278a-103">This example demonstrates some of the more common operations that can be performed on a table's columns through the <xref:System.Windows.Documents.Table.Columns%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0278a-104">示例</span><span class="sxs-lookup"><span data-stu-id="0278a-104">Example</span></span>  
 <span data-ttu-id="0278a-105">下面的示例创建一个新表，然后使用 <xref:System.Windows.Documents.TableColumnCollection.Add%2A> 方法将列添加到表的 <xref:System.Windows.Documents.Table.Columns%2A> 集合中。</span><span class="sxs-lookup"><span data-stu-id="0278a-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableColumnCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a><span data-ttu-id="0278a-106">示例</span><span class="sxs-lookup"><span data-stu-id="0278a-106">Example</span></span>  
 <span data-ttu-id="0278a-107">下面的示例插入一个新的 <xref:System.Windows.Documents.TableColumn> 。</span><span class="sxs-lookup"><span data-stu-id="0278a-107">The following example inserts a new <xref:System.Windows.Documents.TableColumn>.</span></span>  <span data-ttu-id="0278a-108">新列将插入到索引位置0，使其成为表中的新第一列。</span><span class="sxs-lookup"><span data-stu-id="0278a-108">The new column is inserted at index position 0, making it the new first column in the table.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0278a-109">该 <xref:System.Windows.Documents.TableColumnCollection> 集合使用从零开始的标准索引。</span><span class="sxs-lookup"><span data-stu-id="0278a-109">The <xref:System.Windows.Documents.TableColumnCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a><span data-ttu-id="0278a-110">示例</span><span class="sxs-lookup"><span data-stu-id="0278a-110">Example</span></span>  
 <span data-ttu-id="0278a-111">下面的示例对集合中的列访问一些任意属性 <xref:System.Windows.Documents.TableColumnCollection> ，并按索引引用特定的列。</span><span class="sxs-lookup"><span data-stu-id="0278a-111">The following example accesses some arbitrary properties on columns in the <xref:System.Windows.Documents.TableColumnCollection> collection, referring to particular columns by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a><span data-ttu-id="0278a-112">示例</span><span class="sxs-lookup"><span data-stu-id="0278a-112">Example</span></span>  
 <span data-ttu-id="0278a-113">下面的示例获取表当前承载的列数。</span><span class="sxs-lookup"><span data-stu-id="0278a-113">The following example gets the number of columns currently hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a><span data-ttu-id="0278a-114">示例</span><span class="sxs-lookup"><span data-stu-id="0278a-114">Example</span></span>  
 <span data-ttu-id="0278a-115">下面的示例按引用删除特定列。</span><span class="sxs-lookup"><span data-stu-id="0278a-115">The following example removes a particular column by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a><span data-ttu-id="0278a-116">示例</span><span class="sxs-lookup"><span data-stu-id="0278a-116">Example</span></span>  
 <span data-ttu-id="0278a-117">下面的示例按索引删除特定列。</span><span class="sxs-lookup"><span data-stu-id="0278a-117">The following example removes a particular column by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a><span data-ttu-id="0278a-118">示例</span><span class="sxs-lookup"><span data-stu-id="0278a-118">Example</span></span>  
 <span data-ttu-id="0278a-119">下面的示例从表的 columns 集合中删除所有列。</span><span class="sxs-lookup"><span data-stu-id="0278a-119">The following example removes all columns from the table's columns collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="0278a-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0278a-120">See also</span></span>

- [<span data-ttu-id="0278a-121">表概述</span><span class="sxs-lookup"><span data-stu-id="0278a-121">Table Overview</span></span>](table-overview.md)
- [<span data-ttu-id="0278a-122">使用 XAML 定义表</span><span class="sxs-lookup"><span data-stu-id="0278a-122">Define a Table with XAML</span></span>](how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="0278a-123">以编程方式生成表</span><span class="sxs-lookup"><span data-stu-id="0278a-123">Build a Table Programmatically</span></span>](how-to-build-a-table-programmatically.md)
- [<span data-ttu-id="0278a-124">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="0278a-124">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="0278a-125">通过 Blocks 属性操作 FlowDocument</span><span class="sxs-lookup"><span data-stu-id="0278a-125">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="0278a-126">通过 RowGroups 属性操作表的行组</span><span class="sxs-lookup"><span data-stu-id="0278a-126">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
