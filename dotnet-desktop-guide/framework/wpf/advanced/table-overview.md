---
title: 表概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], Table
- documents [WPF], tables
- tables [WPF]
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
ms.openlocfilehash: 3923e39fce021d815a1b2218c95a70f5c4ef4853
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971053"
---
# <a name="table-overview"></a><span data-ttu-id="980b5-102">表概述</span><span class="sxs-lookup"><span data-stu-id="980b5-102">Table Overview</span></span>
<span data-ttu-id="980b5-103"><xref:System.Windows.Documents.Table> 是一个块级别元素，它支持流文档内容的基于网格的表示形式。</span><span class="sxs-lookup"><span data-stu-id="980b5-103"><xref:System.Windows.Documents.Table> is a block level element that supports grid-based presentation of Flow document content.</span></span> <span data-ttu-id="980b5-104">此元素极具灵活性，因此很有用，但也因此显得更加复杂，从而不容易理解和正确使用。</span><span class="sxs-lookup"><span data-stu-id="980b5-104">The flexibility of this element makes it very useful, but also makes it more complicated to understand and use correctly.</span></span>  
  
 <span data-ttu-id="980b5-105">本主题包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="980b5-105">This topic contains the following sections.</span></span>  
  
- [<span data-ttu-id="980b5-106">表基础</span><span class="sxs-lookup"><span data-stu-id="980b5-106">Table Basics</span></span>](#table_basics)  
  
- [<span data-ttu-id="980b5-107">表与网格有什么区别？</span><span class="sxs-lookup"><span data-stu-id="980b5-107">How is Table Different then Grid?</span></span>](#table_vs_Grid)  
  
- [<span data-ttu-id="980b5-108">基本表结构</span><span class="sxs-lookup"><span data-stu-id="980b5-108">Basic Table Structure</span></span>](#basic_table_structure)  
  
- [<span data-ttu-id="980b5-109">表包容</span><span class="sxs-lookup"><span data-stu-id="980b5-109">Table Containment</span></span>](#table_containment)  
  
- [<span data-ttu-id="980b5-110">行分组</span><span class="sxs-lookup"><span data-stu-id="980b5-110">Row Groupings</span></span>](#row_groupings)  
  
- [<span data-ttu-id="980b5-111">背景呈现优先级</span><span class="sxs-lookup"><span data-stu-id="980b5-111">Background Rendering Precedence</span></span>](#rendering_precedence)  
  
- [<span data-ttu-id="980b5-112">跨行或列 </span><span class="sxs-lookup"><span data-stu-id="980b5-112">Spanning Rows or Columns</span></span>](#spanning_rows_or_columns)  
  
- [<span data-ttu-id="980b5-113">使用代码生成表</span><span class="sxs-lookup"><span data-stu-id="980b5-113">Building a Table With Code</span></span>](#building_a_table_with_code)  
  
- <span data-ttu-id="980b5-114">[相关主题]</span><span class="sxs-lookup"><span data-stu-id="980b5-114">[Related Topics]</span></span>
  
<a name="table_basics"></a>
## <a name="table-basics"></a><span data-ttu-id="980b5-115">表基础</span><span class="sxs-lookup"><span data-stu-id="980b5-115">Table Basics</span></span>  
  
<a name="table_vs_Grid"></a>
### <a name="how-is-table-different-then-grid"></a><span data-ttu-id="980b5-116">表与网格有什么区别？</span><span class="sxs-lookup"><span data-stu-id="980b5-116">How is Table Different then Grid?</span></span>  
 <span data-ttu-id="980b5-117"><xref:System.Windows.Documents.Table> 和 <xref:System.Windows.Controls.Grid> 共享一些通用功能，但每个功能最适合于不同的方案。</span><span class="sxs-lookup"><span data-stu-id="980b5-117"><xref:System.Windows.Documents.Table> and <xref:System.Windows.Controls.Grid> share some common functionality, but each is best suited for different scenarios.</span></span> <span data-ttu-id="980b5-118"><xref:System.Windows.Documents.Table>旨在在流内容中使用 (请参阅[流文档概述](flow-document-overview.md)，了解有关流内容的详细信息) 。</span><span class="sxs-lookup"><span data-stu-id="980b5-118">A <xref:System.Windows.Documents.Table> is designed for use within flow content (see [Flow Document Overview](flow-document-overview.md) for more information on flow content).</span></span> <span data-ttu-id="980b5-119">网格最适合在表单中（主要在流内容以外的任意位置）使用。</span><span class="sxs-lookup"><span data-stu-id="980b5-119">Grids are best used inside of forms (basically anywhere outside of flow content).</span></span> <span data-ttu-id="980b5-120">在中 <xref:System.Windows.Documents.FlowDocument> ， <xref:System.Windows.Documents.Table> 支持流内容行为，如分页、列重排和内容选择，而不支持 <xref:System.Windows.Controls.Grid> 。</span><span class="sxs-lookup"><span data-stu-id="980b5-120">Within a <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> supports flow content behaviors like pagination, column reflow, and content selection while a <xref:System.Windows.Controls.Grid> does not.</span></span> <span data-ttu-id="980b5-121"><xref:System.Windows.Controls.Grid>另一方面，最好是在之外使用， <xref:System.Windows.Documents.FlowDocument> 因为这样做的原因很多 <xref:System.Windows.Controls.Grid> ，包括基于行和列索引添加元素 <xref:System.Windows.Documents.Table> 。</span><span class="sxs-lookup"><span data-stu-id="980b5-121">A <xref:System.Windows.Controls.Grid> on the other hand is best used outside of a <xref:System.Windows.Documents.FlowDocument> for many reasons including <xref:System.Windows.Controls.Grid> adds elements based on a row and column index, <xref:System.Windows.Documents.Table> does not.</span></span> <span data-ttu-id="980b5-122"><xref:System.Windows.Controls.Grid>元素允许将子内容分层，允许多个元素存在于单个 "单元" 中。</span><span class="sxs-lookup"><span data-stu-id="980b5-122">The <xref:System.Windows.Controls.Grid> element allows layering of child content, allowing more than one element to exist within a single "cell."</span></span> <span data-ttu-id="980b5-123"><xref:System.Windows.Documents.Table> 不支持分层。</span><span class="sxs-lookup"><span data-stu-id="980b5-123"><xref:System.Windows.Documents.Table> does not support layering.</span></span> <span data-ttu-id="980b5-124">的子元素 <xref:System.Windows.Controls.Grid> 可相对于其 "单元格" 边界区域进行绝对定位。</span><span class="sxs-lookup"><span data-stu-id="980b5-124">Child elements of a <xref:System.Windows.Controls.Grid> can be absolutely positioned relative to the area of their "cell" boundaries.</span></span> <span data-ttu-id="980b5-125"><xref:System.Windows.Documents.Table> 不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="980b5-125"><xref:System.Windows.Documents.Table> does not support this feature.</span></span> <span data-ttu-id="980b5-126">最后， <xref:System.Windows.Controls.Grid> 需要较少的资源， <xref:System.Windows.Documents.Table> 因此，请考虑使用 <xref:System.Windows.Controls.Grid> 来提高性能。</span><span class="sxs-lookup"><span data-stu-id="980b5-126">Finally, a <xref:System.Windows.Controls.Grid> requires less resources then a <xref:System.Windows.Documents.Table> so consider using a <xref:System.Windows.Controls.Grid> to improve performance.</span></span>  
  
<a name="basic_table_structure"></a>
### <a name="basic-table-structure"></a><span data-ttu-id="980b5-127">基本表结构</span><span class="sxs-lookup"><span data-stu-id="980b5-127">Basic Table Structure</span></span>  
 <span data-ttu-id="980b5-128"><xref:System.Windows.Documents.Table> 提供了一种基于网格的表示形式，该表示形式由 <xref:System.Windows.Documents.TableColumn>) 和 () 元素所表示的行 (表示 <xref:System.Windows.Documents.TableRow> 。</span><span class="sxs-lookup"><span data-stu-id="980b5-128"><xref:System.Windows.Documents.Table> provides a grid-based presentation consisting of columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and rows (represented by <xref:System.Windows.Documents.TableRow> elements).</span></span> <span data-ttu-id="980b5-129"><xref:System.Windows.Documents.TableColumn> 元素不承载内容;它们只定义列和列的特征。</span><span class="sxs-lookup"><span data-stu-id="980b5-129"><xref:System.Windows.Documents.TableColumn> elements do not host content; they simply define columns and characteristics of columns.</span></span> <span data-ttu-id="980b5-130"><xref:System.Windows.Documents.TableRow> 元素必须承载在元素中 <xref:System.Windows.Documents.TableRowGroup> ，该元素定义表中的一组行。</span><span class="sxs-lookup"><span data-stu-id="980b5-130"><xref:System.Windows.Documents.TableRow> elements must be hosted in a <xref:System.Windows.Documents.TableRowGroup> element, which defines a grouping of rows for the table.</span></span> <span data-ttu-id="980b5-131"><xref:System.Windows.Documents.TableCell> 元素（其中包含要由表提供的实际内容）必须托管在 <xref:System.Windows.Documents.TableRow> 元素中。</span><span class="sxs-lookup"><span data-stu-id="980b5-131"><xref:System.Windows.Documents.TableCell> elements, which contain the actual content to be presented by the table, must be hosted in a <xref:System.Windows.Documents.TableRow> element.</span></span> <span data-ttu-id="980b5-132"><xref:System.Windows.Documents.TableCell> 可能只包含从派生的元素 <xref:System.Windows.Documents.Block> 。</span><span class="sxs-lookup"><span data-stu-id="980b5-132"><xref:System.Windows.Documents.TableCell> may only contain elements that derive from <xref:System.Windows.Documents.Block>.</span></span>  <span data-ttu-id="980b5-133">Include 的有效子元素 <xref:System.Windows.Documents.TableCell> 。</span><span class="sxs-lookup"><span data-stu-id="980b5-133">Valid child elements for a <xref:System.Windows.Documents.TableCell> include.</span></span>  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> <span data-ttu-id="980b5-134"><xref:System.Windows.Documents.TableCell> 元素不能直接承载文本内容。</span><span class="sxs-lookup"><span data-stu-id="980b5-134"><xref:System.Windows.Documents.TableCell> elements may not directly host text content.</span></span> <span data-ttu-id="980b5-135">有关流内容元素（如）的包含规则的详细信息 <xref:System.Windows.Documents.TableCell> ，请参阅 [流文档概述](flow-document-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="980b5-135">For more information about the containment rules for flow content elements like <xref:System.Windows.Documents.TableCell>, see [Flow Document Overview](flow-document-overview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="980b5-136"><xref:System.Windows.Documents.Table> 与元素类似， <xref:System.Windows.Controls.Grid> 但具有更多的功能，因此需要更大的资源开销。</span><span class="sxs-lookup"><span data-stu-id="980b5-136"><xref:System.Windows.Documents.Table> is similar to the <xref:System.Windows.Controls.Grid> element but has more capabilities and, therefore, requires greater resource overhead.</span></span>  
  
 <span data-ttu-id="980b5-137">下面的示例使用 XAML 定义了一个简单的 2 x 3 表。</span><span class="sxs-lookup"><span data-stu-id="980b5-137">The following example defines a simple 2 x 3 table with XAML.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 <span data-ttu-id="980b5-138">下图显示了此示例的呈现效果。</span><span class="sxs-lookup"><span data-stu-id="980b5-138">The following figure shows how this example renders.</span></span>  
  
 ![显示基本表呈现方式的屏幕截图。](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>
### <a name="table-containment"></a><span data-ttu-id="980b5-140">表包容</span><span class="sxs-lookup"><span data-stu-id="980b5-140">Table Containment</span></span>  
 <span data-ttu-id="980b5-141"><xref:System.Windows.Documents.Table> 从元素派生 <xref:System.Windows.Documents.Block> ，并遵循 level 元素的通用规则 <xref:System.Windows.Documents.Block> 。</span><span class="sxs-lookup"><span data-stu-id="980b5-141"><xref:System.Windows.Documents.Table> derives from the <xref:System.Windows.Documents.Block> element, and adheres to the common rules for <xref:System.Windows.Documents.Block> level elements.</span></span>  <span data-ttu-id="980b5-142"><xref:System.Windows.Documents.Table>元素可以包含在以下任何元素中：</span><span class="sxs-lookup"><span data-stu-id="980b5-142">A <xref:System.Windows.Documents.Table> element may be contained by any of the following elements:</span></span>  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>
### <a name="row-groupings"></a><span data-ttu-id="980b5-143">行分组</span><span class="sxs-lookup"><span data-stu-id="980b5-143">Row Groupings</span></span>  
 <span data-ttu-id="980b5-144"><xref:System.Windows.Documents.TableRowGroup>元素提供了一种方法，用于对表中的行进行任意分组; 表中的每一行都必须属于行分组。</span><span class="sxs-lookup"><span data-stu-id="980b5-144">The <xref:System.Windows.Documents.TableRowGroup> element provides a way to arbitrarily group rows within a table; every row in a table must belong to a row grouping.</span></span>  <span data-ttu-id="980b5-145">行分组中的行通常具有相同的用途，并可作为一个组来设置样式。</span><span class="sxs-lookup"><span data-stu-id="980b5-145">Rows within a row group often share a common intent, and may be styled as a group.</span></span>  <span data-ttu-id="980b5-146">行分组的一个常见使用方式是用于将特定用途的行（如标题行、标头和页脚行）与表中所含的主内容分隔开来。</span><span class="sxs-lookup"><span data-stu-id="980b5-146">A common use for row groupings is to separate special-purpose rows, such as a title, header, and footer rows, from the primary content contained by the table.</span></span>  
  
 <span data-ttu-id="980b5-147">下面的示例使用 XAML 来定义具有样式的标头行和表尾行的表。</span><span class="sxs-lookup"><span data-stu-id="980b5-147">The following example uses XAML to define a table with styled header and footer rows.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 <span data-ttu-id="980b5-148">下图显示了此示例的呈现效果。</span><span class="sxs-lookup"><span data-stu-id="980b5-148">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="980b5-149">![屏幕快照：表行组](./media/table-rowgroups.png "Table_RowGroups")</span><span class="sxs-lookup"><span data-stu-id="980b5-149">![Screenshot: Table row groups](./media/table-rowgroups.png "Table_RowGroups")</span></span>  
  
<a name="rendering_precedence"></a>
### <a name="background-rendering-precedence"></a><span data-ttu-id="980b5-150">背景呈现优先级</span><span class="sxs-lookup"><span data-stu-id="980b5-150">Background Rendering Precedence</span></span>  
 <span data-ttu-id="980b5-151">表元素以下列顺序呈现（按 Z 顺序从最低到最高排列）。</span><span class="sxs-lookup"><span data-stu-id="980b5-151">Table elements render in the following order (z-order from lowest to highest).</span></span> <span data-ttu-id="980b5-152">此顺序不能更改。</span><span class="sxs-lookup"><span data-stu-id="980b5-152">This order cannot be changed.</span></span> <span data-ttu-id="980b5-153">例如，对于这些元素，没有可用于替换此已有顺序的“Z 顺序”属性。</span><span class="sxs-lookup"><span data-stu-id="980b5-153">For example, there is no "Z-order" property for these elements that you can use to override this established order.</span></span>  
  
1. <xref:System.Windows.Documents.Table>  
  
2. <xref:System.Windows.Documents.TableColumn>  
  
3. <xref:System.Windows.Documents.TableRowGroup>  
  
4. <xref:System.Windows.Documents.TableRow>  
  
5. <xref:System.Windows.Documents.TableCell>  
  
 <span data-ttu-id="980b5-154">请参考以下示例，该示例对表内每个元素的背景色进行定义。</span><span class="sxs-lookup"><span data-stu-id="980b5-154">Consider the following example, which defines background colors for each of these elements within a table.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 <span data-ttu-id="980b5-155">下图显示了此示例的呈现方式（仅显示背景色）。</span><span class="sxs-lookup"><span data-stu-id="980b5-155">The following figure shows how this example renders (showing background colors only).</span></span>  
  
 <span data-ttu-id="980b5-156">![屏幕快照：表 z&#45;顺序](./media/table-zorder.png "Table_ZOrder")</span><span class="sxs-lookup"><span data-stu-id="980b5-156">![Screenshot: Table z&#45;order](./media/table-zorder.png "Table_ZOrder")</span></span>  
  
<a name="spanning_rows_or_columns"></a>
### <a name="spanning-rows-or-columns"></a><span data-ttu-id="980b5-157">跨行或列</span><span class="sxs-lookup"><span data-stu-id="980b5-157">Spanning Rows or Columns</span></span>  
 <span data-ttu-id="980b5-158">可以通过分别使用或特性将表单元配置为跨多个行或列 <xref:System.Windows.Documents.TableCell.RowSpan%2A> <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> 。</span><span class="sxs-lookup"><span data-stu-id="980b5-158">Table cells may be configured to span multiple rows or columns by using the <xref:System.Windows.Documents.TableCell.RowSpan%2A> or <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> attributes, respectively.</span></span>  
  
 <span data-ttu-id="980b5-159">请参考以下示例，该示例中有一个跨三列的单元格。</span><span class="sxs-lookup"><span data-stu-id="980b5-159">Consider the following example, in which a cell spans three columns.</span></span>  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 <span data-ttu-id="980b5-160">下图显示了此示例的呈现效果。</span><span class="sxs-lookup"><span data-stu-id="980b5-160">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="980b5-161">![屏幕快照：跨全部三列的单元格](./media/table-columnspan.png "Table_ColumnSpan")</span><span class="sxs-lookup"><span data-stu-id="980b5-161">![Screenshot: Cell spanning all three columns](./media/table-columnspan.png "Table_ColumnSpan")</span></span>  
  
<a name="building_a_table_with_code"></a>
## <a name="building-a-table-with-code"></a><span data-ttu-id="980b5-162">使用代码生成表</span><span class="sxs-lookup"><span data-stu-id="980b5-162">Building a Table With Code</span></span>  
 <span data-ttu-id="980b5-163">下面的示例演示如何以编程方式创建 <xref:System.Windows.Documents.Table> 和填充内容。</span><span class="sxs-lookup"><span data-stu-id="980b5-163">The following examples show how to programmatically create a <xref:System.Windows.Documents.Table> and populate it with content.</span></span> <span data-ttu-id="980b5-164">表中的内容分配为 (由 <xref:System.Windows.Documents.TableRow> 对象中包含的对象 <xref:System.Windows.Documents.Table.RowGroups%2A>) 和六个 (由对象表示) 表示的对象来表示 <xref:System.Windows.Documents.TableColumn> 。</span><span class="sxs-lookup"><span data-stu-id="980b5-164">The contents of the table are apportioned into five rows (represented by <xref:System.Windows.Documents.TableRow> objects contained in a <xref:System.Windows.Documents.Table.RowGroups%2A> object) and six columns (represented by <xref:System.Windows.Documents.TableColumn> objects).</span></span> <span data-ttu-id="980b5-165">各行用于不同的显示目的，其中，标题行用于显示整个表的标题，标头行用于描述表中的数据列，而页脚行则包含摘要信息。</span><span class="sxs-lookup"><span data-stu-id="980b5-165">The rows are used for different presentation purposes, including a title row intended to title the entire table, a header row to describe the columns of data in the table, and a footer row with summary information.</span></span>  <span data-ttu-id="980b5-166">请注意，“标题”行、“标头”行和“页脚”行并非表格所固有的，它们只是具有不同特征的行。</span><span class="sxs-lookup"><span data-stu-id="980b5-166">Note that the notion of "title", "header", and "footer" rows are not inherent to the table; these are simply rows with different characteristics.</span></span> <span data-ttu-id="980b5-167">表单元格包含实际内容，这些内容可以包括文本、图像或几乎任何其他 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 元素。</span><span class="sxs-lookup"><span data-stu-id="980b5-167">Table cells contain the actual content, which can be comprised of text, images, or nearly any other [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] element.</span></span>  
  
 <span data-ttu-id="980b5-168">首先， <xref:System.Windows.Documents.FlowDocument> 创建一个来承载的 <xref:System.Windows.Documents.Table> ，并创建一个新的并将其 <xref:System.Windows.Documents.Table> 添加到的内容中 <xref:System.Windows.Documents.FlowDocument> 。</span><span class="sxs-lookup"><span data-stu-id="980b5-168">First, a <xref:System.Windows.Documents.FlowDocument> is created to host the <xref:System.Windows.Documents.Table>, and a new <xref:System.Windows.Documents.Table> is created and added to the contents of the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 <span data-ttu-id="980b5-169">接下来， <xref:System.Windows.Documents.TableColumn> 将创建六个对象并将其添加到表的 <xref:System.Windows.Documents.Table.Columns%2A> 集合，并应用某些格式设置。</span><span class="sxs-lookup"><span data-stu-id="980b5-169">Next, six <xref:System.Windows.Documents.TableColumn> objects are created and added to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection, with some formatting applied.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="980b5-170">请注意，表的 <xref:System.Windows.Documents.Table.Columns%2A> 集合使用从零开始的标准索引。</span><span class="sxs-lookup"><span data-stu-id="980b5-170">Note that the table's <xref:System.Windows.Documents.Table.Columns%2A> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 <span data-ttu-id="980b5-171">接下来，创建一个标题行，并将其添加到表中，同时应用某些格式设置。</span><span class="sxs-lookup"><span data-stu-id="980b5-171">Next, a title row is created and added to the table with some formatting applied.</span></span>  <span data-ttu-id="980b5-172">标题行包含一个单元格，该单元格跨表中的全部六列。</span><span class="sxs-lookup"><span data-stu-id="980b5-172">The title row happens to contain a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 <span data-ttu-id="980b5-173">接下来，创建一个标头行并将其添加到表中，同时创建标头行中的单元格并填充其内容。</span><span class="sxs-lookup"><span data-stu-id="980b5-173">Next, a header row is created and added to the table, and the cells in the header row are created and populated with content.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 <span data-ttu-id="980b5-174">接下来，创建一个数据行并将其添加到表中，同时创建此行中的单元格并填充其内容。</span><span class="sxs-lookup"><span data-stu-id="980b5-174">Next, a row for data is created and added to the table, and the cells in this row are created and populated with content.</span></span>  <span data-ttu-id="980b5-175">生成此行的过程与生成标头行的过程类似，只是应用的格式设置略有不同。</span><span class="sxs-lookup"><span data-stu-id="980b5-175">Building this row is similar to building the header row, with slightly different formatting applied.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 <span data-ttu-id="980b5-176">最后，创建、添加脚注行并设置其格式。</span><span class="sxs-lookup"><span data-stu-id="980b5-176">Finally, a footer row is created, added, and formatted.</span></span>  <span data-ttu-id="980b5-177">与标题行类似，脚注包含的单元格的跨度为表中的全部六列。</span><span class="sxs-lookup"><span data-stu-id="980b5-177">Like the title row, the footer contains a single cell that spans all six columns in the table.</span></span>  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a><span data-ttu-id="980b5-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="980b5-178">See also</span></span>

- [<span data-ttu-id="980b5-179">流文档概述</span><span class="sxs-lookup"><span data-stu-id="980b5-179">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="980b5-180">使用 XAML 定义表</span><span class="sxs-lookup"><span data-stu-id="980b5-180">Define a Table with XAML</span></span>](how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="980b5-181">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="980b5-181">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="980b5-182">使用流内容元素</span><span class="sxs-lookup"><span data-stu-id="980b5-182">Use Flow Content Elements</span></span>](how-to-use-flow-content-elements.md)
