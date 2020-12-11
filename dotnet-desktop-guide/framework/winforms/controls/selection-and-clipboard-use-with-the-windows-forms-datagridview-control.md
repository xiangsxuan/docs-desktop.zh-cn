---
title: 选择和剪贴板用于 DataGridView 控件
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
ms.openlocfilehash: 6993f77e8ce532d8df1bdc7e6b6abc1cc3268e49
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970287"
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="01dbe-102">Windows 窗体 DataGridView 控件的选项和剪贴板使用</span><span class="sxs-lookup"><span data-stu-id="01dbe-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="01dbe-103">`DataGridView`控件提供多种选项，用于配置用户可以选择单元格、行和列的方式。</span><span class="sxs-lookup"><span data-stu-id="01dbe-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="01dbe-104">例如，你可以启用单个或多个选择、在用户单击单元格时选择整行或列，或者仅在用户单击其标题时选择整行或列，这样就可以选择单元格。</span><span class="sxs-lookup"><span data-stu-id="01dbe-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="01dbe-105">如果要为选择提供自己的用户界面，则可以禁用普通选择并以编程方式处理所有选择。</span><span class="sxs-lookup"><span data-stu-id="01dbe-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="01dbe-106">此外，还可以让用户将所选值复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="01dbe-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01dbe-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="01dbe-107">In This Section</span></span>  
 [<span data-ttu-id="01dbe-108">Windows 窗体 DataGridView 控件中的选择模式</span><span class="sxs-lookup"><span data-stu-id="01dbe-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="01dbe-109">描述控件中用户和编程选择的选项。</span><span class="sxs-lookup"><span data-stu-id="01dbe-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="01dbe-110">如何：设置 Windows 窗体 DataGridView 控件的选择模式</span><span class="sxs-lookup"><span data-stu-id="01dbe-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="01dbe-111">介绍如何在用户单击某个单元格时，将控件配置为单行选择。</span><span class="sxs-lookup"><span data-stu-id="01dbe-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="01dbe-112">如何：获取 Windows 窗体 DataGridView 控件中选定的单元格、行和列</span><span class="sxs-lookup"><span data-stu-id="01dbe-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="01dbe-113">介绍如何使用选定的单元格、行和列集合。</span><span class="sxs-lookup"><span data-stu-id="01dbe-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="01dbe-114">如何：使用户能够将多个单元格从 Windows 窗体 DataGridView 控件复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="01dbe-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="01dbe-115">描述如何在控件中启用剪贴板支持。</span><span class="sxs-lookup"><span data-stu-id="01dbe-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="01dbe-116">参考</span><span class="sxs-lookup"><span data-stu-id="01dbe-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="01dbe-117">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="01dbe-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="01dbe-118">提供属性的参考文档 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 。</span><span class="sxs-lookup"><span data-stu-id="01dbe-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="01dbe-119">提供属性的参考文档 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> 。</span><span class="sxs-lookup"><span data-stu-id="01dbe-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="01dbe-120">提供类的参考文档 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> 。</span><span class="sxs-lookup"><span data-stu-id="01dbe-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="01dbe-121">提供类的参考文档 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> 。</span><span class="sxs-lookup"><span data-stu-id="01dbe-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="01dbe-122">提供类的参考文档 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> 。</span><span class="sxs-lookup"><span data-stu-id="01dbe-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01dbe-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01dbe-123">See also</span></span>

- [<span data-ttu-id="01dbe-124">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="01dbe-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="01dbe-125">Windows 窗体 DataGridView 控件中的默认键盘和鼠标处理</span><span class="sxs-lookup"><span data-stu-id="01dbe-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
