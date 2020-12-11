---
title: DataGrid 控件中的调整大小选项
description: 了解如何设置 Windows Presentation Foundation DataGrid 控件中的单个行和列，使其大小调整到其内容或特定值。
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid control [WPF], sizing
- size [WPF], DataGrid
- automatically size DataGrid [WPF]
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
ms.openlocfilehash: 0f10e385cbf18a26989614363ca6cd9f92bc83ec
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972890"
---
# <a name="sizing-options-in-the-datagrid-control"></a><span data-ttu-id="2ae00-103">DataGrid 控件中的调整大小选项</span><span class="sxs-lookup"><span data-stu-id="2ae00-103">Sizing Options in the DataGrid Control</span></span>
<span data-ttu-id="2ae00-104">可以使用各种选项来控制 <xref:System.Windows.Controls.DataGrid> 大小本身。</span><span class="sxs-lookup"><span data-stu-id="2ae00-104">Various options are available to control how the <xref:System.Windows.Controls.DataGrid> sizes itself.</span></span> <span data-ttu-id="2ae00-105"><xref:System.Windows.Controls.DataGrid>和中的单个行和列 <xref:System.Windows.Controls.DataGrid> 可设置为自动到其内容的大小，也可以设置为特定值。</span><span class="sxs-lookup"><span data-stu-id="2ae00-105">The <xref:System.Windows.Controls.DataGrid>, and individual rows and columns in the <xref:System.Windows.Controls.DataGrid>, can be set to size automatically to their contents or can be set to specific values.</span></span> <span data-ttu-id="2ae00-106">默认情况下， <xref:System.Windows.Controls.DataGrid> 将会放大和缩小以适应其内容大小。</span><span class="sxs-lookup"><span data-stu-id="2ae00-106">By default, the <xref:System.Windows.Controls.DataGrid> will grow and shrink to fit the size of its contents.</span></span>  
  
## <a name="sizing-the-datagrid"></a><span data-ttu-id="2ae00-107">调整 DataGrid 大小</span><span class="sxs-lookup"><span data-stu-id="2ae00-107">Sizing the DataGrid</span></span>  
  
### <a name="cautions-when-using-automatic-sizing"></a><span data-ttu-id="2ae00-108">使用自动调整大小时的注意事项</span><span class="sxs-lookup"><span data-stu-id="2ae00-108">Cautions When Using Automatic Sizing</span></span>  
 <span data-ttu-id="2ae00-109">默认情况下，的 <xref:System.Windows.FrameworkElement.Height%2A> 和 <xref:System.Windows.FrameworkElement.Width%2A> 属性 <xref:System.Windows.Controls.DataGrid> 设置为 <xref:System.Double.NaN?displayProperty=nameWithType> `Auto` XAML) 中 ( ""，并且 <xref:System.Windows.Controls.DataGrid> 会调整为其内容的大小。</span><span class="sxs-lookup"><span data-stu-id="2ae00-109">By default, the <xref:System.Windows.FrameworkElement.Height%2A> and <xref:System.Windows.FrameworkElement.Width%2A> properties of the <xref:System.Windows.Controls.DataGrid> are set to <xref:System.Double.NaN?displayProperty=nameWithType> ("`Auto`" in XAML), and the <xref:System.Windows.Controls.DataGrid> will adjust to the size of its contents.</span></span>  
  
 <span data-ttu-id="2ae00-110">当放置在不限制其子级大小的容器中时（例如 <xref:System.Windows.Controls.Canvas> 或 <xref:System.Windows.Controls.StackPanel> ）， <xref:System.Windows.Controls.DataGrid> 将延伸到超出容器的可见边界，且不会显示滚动条。</span><span class="sxs-lookup"><span data-stu-id="2ae00-110">When placed inside a container that does not restrict the size of its children, such as a <xref:System.Windows.Controls.Canvas> or <xref:System.Windows.Controls.StackPanel>, the <xref:System.Windows.Controls.DataGrid> will stretch beyond the visible bounds of the container and scrollbars will not be shown.</span></span> <span data-ttu-id="2ae00-111">此条件有可用性和性能方面的影响。</span><span class="sxs-lookup"><span data-stu-id="2ae00-111">This condition has both usability and performance implications.</span></span>  
  
 <span data-ttu-id="2ae00-112">绑定到数据集时，如果 <xref:System.Windows.FrameworkElement.Height%2A> 的 <xref:System.Windows.Controls.DataGrid> 不受限制，它将继续为绑定数据集中的每个数据项添加一行。</span><span class="sxs-lookup"><span data-stu-id="2ae00-112">When bound to a data set, if the <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Controls.DataGrid> is not restricted, it will continue to add a row for each data item in the bound data set.</span></span> <span data-ttu-id="2ae00-113">这可能会导致 <xref:System.Windows.Controls.DataGrid> 添加行时，在应用程序的可见边界之外增长。</span><span class="sxs-lookup"><span data-stu-id="2ae00-113">This can cause the <xref:System.Windows.Controls.DataGrid> to grow outside the visible bounds of your application as rows are added.</span></span> <span data-ttu-id="2ae00-114"><xref:System.Windows.Controls.DataGrid>在这种情况下，将不会显示滚动条，因为它 <xref:System.Windows.FrameworkElement.Height%2A> 将继续增长以容纳新行。</span><span class="sxs-lookup"><span data-stu-id="2ae00-114">The <xref:System.Windows.Controls.DataGrid> will not show scrollbars in this case because its <xref:System.Windows.FrameworkElement.Height%2A> will continue to grow to accommodate the new rows.</span></span>  
  
 <span data-ttu-id="2ae00-115">为中的每行创建一个对象 <xref:System.Windows.Controls.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-115">An object is created for each row in the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="2ae00-116">如果你使用的是一个大型数据集，并且你允许 <xref:System.Windows.Controls.DataGrid> 自动调整其大小，则创建大量对象可能会影响你的应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="2ae00-116">If you are working with a large data set and you allow the <xref:System.Windows.Controls.DataGrid> to automatically size itself, the creation of a large number of objects may affect the performance of your application.</span></span>  
  
 <span data-ttu-id="2ae00-117">若要在使用大型数据集时避免这些问题，建议您专门设置的，或将 <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Controls.DataGrid> 其放在将限制其的容器中 <xref:System.Windows.FrameworkElement.Height%2A> ，例如 <xref:System.Windows.Controls.Grid> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-117">To avoid these issues when you work with large data sets, it is recommended that you specifically set the <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Controls.DataGrid> or place it in a container that will restrict its <xref:System.Windows.FrameworkElement.Height%2A>, such as a <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="2ae00-118">当受到 <xref:System.Windows.FrameworkElement.Height%2A> 限制时， <xref:System.Windows.Controls.DataGrid> 将仅创建将在其指定范围内容纳的行， <xref:System.Windows.FrameworkElement.Height%2A> 并根据需要回收这些行以显示新数据。</span><span class="sxs-lookup"><span data-stu-id="2ae00-118">When the <xref:System.Windows.FrameworkElement.Height%2A> is restricted, the <xref:System.Windows.Controls.DataGrid> will only create the rows that will fit within its specified <xref:System.Windows.FrameworkElement.Height%2A>, and will recycle those rows as needed to display new data.</span></span>  
  
### <a name="setting-the-datagrid-size"></a><span data-ttu-id="2ae00-119">设置 DataGrid 大小</span><span class="sxs-lookup"><span data-stu-id="2ae00-119">Setting the DataGrid Size</span></span>  
 <span data-ttu-id="2ae00-120"><xref:System.Windows.Controls.DataGrid>可以设置为指定边界内的自动大小，也可以 <xref:System.Windows.Controls.DataGrid> 设置为特定大小。</span><span class="sxs-lookup"><span data-stu-id="2ae00-120">The <xref:System.Windows.Controls.DataGrid> can be set to automatically size within specified boundaries, or the <xref:System.Windows.Controls.DataGrid> can be set to a specific size.</span></span> <span data-ttu-id="2ae00-121">下表显示可以设置以控制大小的属性 <xref:System.Windows.Controls.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-121">The following table shows the properties that can be set to control the <xref:System.Windows.Controls.DataGrid> size.</span></span>  
  
|<span data-ttu-id="2ae00-122">属性</span><span class="sxs-lookup"><span data-stu-id="2ae00-122">Property</span></span>|<span data-ttu-id="2ae00-123">描述</span><span class="sxs-lookup"><span data-stu-id="2ae00-123">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|<span data-ttu-id="2ae00-124">设置的特定高度 <xref:System.Windows.Controls.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-124">Sets a specific height for the <xref:System.Windows.Controls.DataGrid>.</span></span>|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|<span data-ttu-id="2ae00-125">设置的高度上限 <xref:System.Windows.Controls.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-125">Sets the upper bound for the height of the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="2ae00-126"><xref:System.Windows.Controls.DataGrid>将垂直增长，直到达到此高度。</span><span class="sxs-lookup"><span data-stu-id="2ae00-126">The <xref:System.Windows.Controls.DataGrid> will grow vertically until it reaches this height.</span></span>|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|<span data-ttu-id="2ae00-127">设置的高度的下限 <xref:System.Windows.Controls.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-127">Sets the lower bound for the height of the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="2ae00-128"><xref:System.Windows.Controls.DataGrid>将垂直收缩，直到达到此高度。</span><span class="sxs-lookup"><span data-stu-id="2ae00-128">The <xref:System.Windows.Controls.DataGrid> will shrink vertically until it reaches this height.</span></span>|  
|<xref:System.Windows.FrameworkElement.Width%2A>|<span data-ttu-id="2ae00-129">设置的特定宽度 <xref:System.Windows.Controls.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-129">Sets a specific width for the <xref:System.Windows.Controls.DataGrid>.</span></span>|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|<span data-ttu-id="2ae00-130">设置的宽度的上限 <xref:System.Windows.Controls.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-130">Sets the upper bound for the width of the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="2ae00-131"><xref:System.Windows.Controls.DataGrid>将水平增长，直到达到此宽度。</span><span class="sxs-lookup"><span data-stu-id="2ae00-131">The <xref:System.Windows.Controls.DataGrid> will grow horizontally until it reaches this width.</span></span>|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|<span data-ttu-id="2ae00-132">设置的宽度的下限 <xref:System.Windows.Controls.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-132">Sets the lower bound for the width of the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="2ae00-133"><xref:System.Windows.Controls.DataGrid>将水平收缩，直到达到此宽度。</span><span class="sxs-lookup"><span data-stu-id="2ae00-133">The <xref:System.Windows.Controls.DataGrid> will shrink horizontally until it reaches this width.</span></span>|  
  
## <a name="sizing-rows-and-row-headers"></a><span data-ttu-id="2ae00-134">调整行和行标题的大小</span><span class="sxs-lookup"><span data-stu-id="2ae00-134">Sizing Rows and Row Headers</span></span>  
  
### <a name="datagrid-rows"></a><span data-ttu-id="2ae00-135">DataGrid 行</span><span class="sxs-lookup"><span data-stu-id="2ae00-135">DataGrid Rows</span></span>  
 <span data-ttu-id="2ae00-136">默认情况下， <xref:System.Windows.Controls.DataGrid> 行的 <xref:System.Windows.FrameworkElement.Height%2A> 属性设置为 <xref:System.Double.NaN?displayProperty=nameWithType> `Auto` XAML) 中 ( ""，行高将扩展为其内容的大小。</span><span class="sxs-lookup"><span data-stu-id="2ae00-136">By default, a <xref:System.Windows.Controls.DataGrid> row's <xref:System.Windows.FrameworkElement.Height%2A> property is set to <xref:System.Double.NaN?displayProperty=nameWithType> ("`Auto`" in XAML), and the row height will expand to the size of its contents.</span></span> <span data-ttu-id="2ae00-137"><xref:System.Windows.Controls.DataGrid>可以通过设置属性来指定中所有行的高度 <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-137">The height of all rows in the <xref:System.Windows.Controls.DataGrid> can be specified by setting the <xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2ae00-138">用户可以通过拖动行标题分隔线来更改行高。</span><span class="sxs-lookup"><span data-stu-id="2ae00-138">Users can change the row height by dragging the row header dividers.</span></span>  
  
### <a name="datagrid-row-headers"></a><span data-ttu-id="2ae00-139">DataGrid 行标题</span><span class="sxs-lookup"><span data-stu-id="2ae00-139">DataGrid Row Headers</span></span>  
 <span data-ttu-id="2ae00-140">若要显示行标题， <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> 属性必须设置为 <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> 或 <xref:System.Windows.Controls.DataGridHeadersVisibility.All?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-140">To display row headers, the <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> property must be set to <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> or <xref:System.Windows.Controls.DataGridHeadersVisibility.All?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2ae00-141">默认情况下，将显示行标题，并自动调整其大小以适应其内容。</span><span class="sxs-lookup"><span data-stu-id="2ae00-141">By default, row headers are displayed and they automatically size to fit their content.</span></span> <span data-ttu-id="2ae00-142">可以通过设置属性，将行标题指定为特定的宽度 <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-142">The row headers can be given a specific width by setting the <xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="sizing-columns-and-column-headers"></a><span data-ttu-id="2ae00-143">调整列和列标题的大小</span><span class="sxs-lookup"><span data-stu-id="2ae00-143">Sizing Columns and Column Headers</span></span>  
  
### <a name="datagrid-columns"></a><span data-ttu-id="2ae00-144">DataGrid 列</span><span class="sxs-lookup"><span data-stu-id="2ae00-144">DataGrid Columns</span></span>  
 <span data-ttu-id="2ae00-145"><xref:System.Windows.Controls.DataGrid>使用和结构的值 <xref:System.Windows.Controls.DataGridLength> <xref:System.Windows.Controls.DataGridLengthUnitType> 来指定绝对或自动调整大小模式。</span><span class="sxs-lookup"><span data-stu-id="2ae00-145">The <xref:System.Windows.Controls.DataGrid> uses values of the <xref:System.Windows.Controls.DataGridLength> and the <xref:System.Windows.Controls.DataGridLengthUnitType> structure to specify absolute or automatic sizing modes.</span></span>  
  
 <span data-ttu-id="2ae00-146">下表显示了结构提供的值 <xref:System.Windows.Controls.DataGridLengthUnitType> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-146">The following table shows the values provided by the <xref:System.Windows.Controls.DataGridLengthUnitType> structure.</span></span>  
  
|<span data-ttu-id="2ae00-147">名称</span><span class="sxs-lookup"><span data-stu-id="2ae00-147">Name</span></span>|<span data-ttu-id="2ae00-148">描述</span><span class="sxs-lookup"><span data-stu-id="2ae00-148">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Auto>|<span data-ttu-id="2ae00-149">默认的自动调整大小模式根据 <xref:System.Windows.Controls.DataGrid> 单元格和列标题的内容调整列的大小。</span><span class="sxs-lookup"><span data-stu-id="2ae00-149">The default automatic sizing mode sizes <xref:System.Windows.Controls.DataGrid> columns based on the contents of both cells and column headers.</span></span>|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToCells>|<span data-ttu-id="2ae00-150">基于单元格的自动调整大小模式根据 <xref:System.Windows.Controls.DataGrid> 列中单元格的内容（不包括列标题）来调整列的大小。</span><span class="sxs-lookup"><span data-stu-id="2ae00-150">The cell-based automatic sizing mode sizes <xref:System.Windows.Controls.DataGrid> columns based on the contents of cells in the column, not including column headers.</span></span>|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToHeader>|<span data-ttu-id="2ae00-151">基于标头的自动调整大小模式 <xref:System.Windows.Controls.DataGrid> 仅基于列标题的内容调整列的大小。</span><span class="sxs-lookup"><span data-stu-id="2ae00-151">The header-based automatic sizing mode sizes <xref:System.Windows.Controls.DataGrid> columns based on the contents of column headers only.</span></span>|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Pixel>|<span data-ttu-id="2ae00-152">基于像素的大小调整模式 <xref:System.Windows.Controls.DataGrid> 基于提供的数值调整列的大小。</span><span class="sxs-lookup"><span data-stu-id="2ae00-152">The pixel-based sizing mode sizes <xref:System.Windows.Controls.DataGrid> columns based on the numeric value provided.</span></span>|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Star>|<span data-ttu-id="2ae00-153">星形调整大小模式用于按加权比例分布可用空间。</span><span class="sxs-lookup"><span data-stu-id="2ae00-153">The star sizing mode is used to distribute available space by weighted proportions.</span></span><br /><br /> <span data-ttu-id="2ae00-154">在 XAML 中，星号值表示为 n \*，其中 n 表示数值。</span><span class="sxs-lookup"><span data-stu-id="2ae00-154">In XAML, star values are expressed as n\* where n represents a numeric value.</span></span> <span data-ttu-id="2ae00-155">1与 \* 等效 \* 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-155">1\* is equivalent to \*.</span></span> <span data-ttu-id="2ae00-156">例如，如果中的两个列的 <xref:System.Windows.Controls.DataGrid> 宽度为 \* 和 2 \* ，则第一列将接收一个部分可用空间，第二列将接收可用空间的两个部分。</span><span class="sxs-lookup"><span data-stu-id="2ae00-156">For example, if two columns in a <xref:System.Windows.Controls.DataGrid> had widths of \* and 2\*, the first column would receive one portion of the available space and the second column would receive two portions of the available space.</span></span>|  
  
 <span data-ttu-id="2ae00-157"><xref:System.Windows.Controls.DataGridLengthConverter>类可用于在数值或字符串值与值之间转换数据 <xref:System.Windows.Controls.DataGridLength> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-157">The <xref:System.Windows.Controls.DataGridLengthConverter> class can be used to convert data between numeric or string values and <xref:System.Windows.Controls.DataGridLength> values.</span></span>  
  
 <span data-ttu-id="2ae00-158">默认情况下， <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType> 属性设置为 <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A> ， <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType> 属性设置为 <xref:System.Windows.Controls.DataGridLength.Auto%2A> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-158">By default, the <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType> property is set to <xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A>, and the <xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType> property is set to <xref:System.Windows.Controls.DataGridLength.Auto%2A>.</span></span> <span data-ttu-id="2ae00-159">当调整大小模式设置为 <xref:System.Windows.Controls.DataGridLength.Auto%2A> 或时 <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A> ，列会增长到其最宽可见内容的宽度。</span><span class="sxs-lookup"><span data-stu-id="2ae00-159">When the sizing mode is set to <xref:System.Windows.Controls.DataGridLength.Auto%2A> or <xref:System.Windows.Controls.DataGridLength.SizeToCells%2A>, columns will grow to the width of their widest visible content.</span></span> <span data-ttu-id="2ae00-160">滚动时，如果大于当前列大小的内容滚动到视图中，则这些大小调整模式将导致列展开。</span><span class="sxs-lookup"><span data-stu-id="2ae00-160">When scrolling, these sizing modes will cause columns to expand if content that is larger than the current column size is scrolled into view.</span></span> <span data-ttu-id="2ae00-161">在内容滚动出视图后，列将不会收缩。</span><span class="sxs-lookup"><span data-stu-id="2ae00-161">The column will not shrink after the content is scrolled out of view.</span></span>  
  
 <span data-ttu-id="2ae00-162">还可以将中的列 <xref:System.Windows.Controls.DataGrid> 设置为仅在指定边界内自动调整大小，或者可以将列设置为特定大小。</span><span class="sxs-lookup"><span data-stu-id="2ae00-162">Columns in the <xref:System.Windows.Controls.DataGrid> can also be set to automatically size only within specified boundaries, or columns can be set to a specific size.</span></span> <span data-ttu-id="2ae00-163">下表显示了可设置为控制列大小的属性。</span><span class="sxs-lookup"><span data-stu-id="2ae00-163">The following table shows the properties that can be set to control column sizes.</span></span>  
  
|<span data-ttu-id="2ae00-164">属性</span><span class="sxs-lookup"><span data-stu-id="2ae00-164">Property</span></span>|<span data-ttu-id="2ae00-165">描述</span><span class="sxs-lookup"><span data-stu-id="2ae00-165">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>|<span data-ttu-id="2ae00-166">设置中所有列的上限 <xref:System.Windows.Controls.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-166">Sets the upper bound for all columns in the <xref:System.Windows.Controls.DataGrid>.</span></span>|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=nameWithType>|<span data-ttu-id="2ae00-167">设置单个列的上限。</span><span class="sxs-lookup"><span data-stu-id="2ae00-167">Sets the upper bound for an individual column.</span></span> <span data-ttu-id="2ae00-168">重写 <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="2ae00-168">Overrides <xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>|<span data-ttu-id="2ae00-169">设置中所有列的下限 <xref:System.Windows.Controls.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-169">Sets the lower bound for all columns in the <xref:System.Windows.Controls.DataGrid>.</span></span>|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=nameWithType>|<span data-ttu-id="2ae00-170">设置单个列的下限。</span><span class="sxs-lookup"><span data-stu-id="2ae00-170">Sets the lower bound for an individual column.</span></span> <span data-ttu-id="2ae00-171">重写 <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="2ae00-171">Overrides <xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>|<span data-ttu-id="2ae00-172">设置中所有列的特定宽度 <xref:System.Windows.Controls.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-172">Sets a specific width for all columns in the <xref:System.Windows.Controls.DataGrid>.</span></span>|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType>|<span data-ttu-id="2ae00-173">设置单个列的特定宽度。</span><span class="sxs-lookup"><span data-stu-id="2ae00-173">Sets a specific width for an individual column.</span></span> <span data-ttu-id="2ae00-174">重写 <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="2ae00-174">Overrides <xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>.</span></span>|  
  
### <a name="datagrid-column-headers"></a><span data-ttu-id="2ae00-175">DataGrid 列标题</span><span class="sxs-lookup"><span data-stu-id="2ae00-175">DataGrid Column Headers</span></span>  
 <span data-ttu-id="2ae00-176">默认情况下， <xref:System.Windows.Controls.DataGrid> 将显示列标题。</span><span class="sxs-lookup"><span data-stu-id="2ae00-176">By default, <xref:System.Windows.Controls.DataGrid> column headers are displayed.</span></span> <span data-ttu-id="2ae00-177">若要隐藏列标题，则 <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> 必须将属性设置为 <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> 或 <xref:System.Windows.Controls.DataGridHeadersVisibility.None?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-177">To hide column headers, the <xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A> property must be set to <xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType> or <xref:System.Windows.Controls.DataGridHeadersVisibility.None?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2ae00-178">默认情况下，当显示列标题时，它们会自动调整大小以适应其内容。</span><span class="sxs-lookup"><span data-stu-id="2ae00-178">By default, when column headers are displayed, they automatically size to fit their content.</span></span> <span data-ttu-id="2ae00-179">可以通过设置属性来为列标题提供特定的高度 <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-179">The column headers can be given a specific height by setting the <xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=nameWithType> property.</span></span>  
  
### <a name="resizing-with-the-mouse"></a><span data-ttu-id="2ae00-180">用鼠标调整大小</span><span class="sxs-lookup"><span data-stu-id="2ae00-180">Resizing with the Mouse</span></span>  
 <span data-ttu-id="2ae00-181">用户可以 <xref:System.Windows.Controls.DataGrid> 通过拖动行标题或列标题分隔线来调整行和列的大小。</span><span class="sxs-lookup"><span data-stu-id="2ae00-181">Users can resize <xref:System.Windows.Controls.DataGrid> rows and columns by dragging the row or column header dividers.</span></span> <span data-ttu-id="2ae00-182"><xref:System.Windows.Controls.DataGrid>还支持通过双击行标题或列标题分隔符来自动调整行和列的大小。</span><span class="sxs-lookup"><span data-stu-id="2ae00-182">The <xref:System.Windows.Controls.DataGrid> also supports automatic resizing of rows and columns by double-clicking the row or column header divider.</span></span> <span data-ttu-id="2ae00-183">若要防止用户调整特定列的大小，请将 <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> 单个列的属性设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-183">To prevent a user from resizing particular columns, set the <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> property to `false` for the individual columns.</span></span> <span data-ttu-id="2ae00-184">若要防止用户调整所有列的大小，请将 <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> 属性设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-184">To prevent users from resizing all columns, set the <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> property to `false`.</span></span> <span data-ttu-id="2ae00-185">若要防止用户调整所有行的大小，请将 <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=nameWithType> 属性设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="2ae00-185">To prevent users from resizing all rows, set the <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae00-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ae00-186">See also</span></span>

- <xref:System.Windows.Controls.DataGrid>
- <xref:System.Windows.Controls.DataGridColumn>
- <xref:System.Windows.Controls.DataGridLength>
- <xref:System.Windows.Controls.DataGridLengthConverter>