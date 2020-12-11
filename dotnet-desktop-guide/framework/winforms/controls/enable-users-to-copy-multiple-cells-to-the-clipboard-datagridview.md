---
title: 使用户能够将多个单元格从 DataGridView 控件复制到剪贴板
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
ms.openlocfilehash: 2bb74a1f0c59b28ab496ce9c89c1c1b5f9d8147b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971538"
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a><span data-ttu-id="047b1-102">如何：使用户能够将多个单元格从 Windows 窗体 DataGridView 控件复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="047b1-102">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="047b1-103">启用单元格复制时，其他应用程序可以通过 <xref:System.Windows.Forms.Clipboard> 轻松访问 <xref:System.Windows.Forms.DataGridView> 控件中的数据。</span><span class="sxs-lookup"><span data-stu-id="047b1-103">When you enable cell copying, you make the data in your <xref:System.Windows.Forms.DataGridView> control easily accessible to other applications through the <xref:System.Windows.Forms.Clipboard>.</span></span> <span data-ttu-id="047b1-104">将选定单元格的值转换为字符串，并作为制表符分隔的文本值添加到剪贴板以粘贴到记事本和 Excel 等应用程序中，或作为 HTML 格式的表格粘贴到 Word 等应用程序中。</span><span class="sxs-lookup"><span data-stu-id="047b1-104">The values of the selected cells are converted to strings and added to the Clipboard as tab-delimited text values for pasting into applications like Notepad and Excel, and as an HTML-formatted table for pasting into applications like Word.</span></span>  
  
 <span data-ttu-id="047b1-105">可以将单元复制格配置为：当用户选择整行或整列时，仅复制单元格的值、在剪贴板数据中包含行和列的标题文本，或仅包含标题文本。</span><span class="sxs-lookup"><span data-stu-id="047b1-105">You can configure cell copying to copy cell values only, to include row and column header text in the Clipboard data, or to include header text only when users select entire rows or columns.</span></span>  
  
 <span data-ttu-id="047b1-106">根据选择模式，用户可以选择多个不相连的单元格组。</span><span class="sxs-lookup"><span data-stu-id="047b1-106">Depending on the selection mode, users can select multiple disconnected groups of cells.</span></span> <span data-ttu-id="047b1-107">用户将单元格复制到剪贴板时，不会复制不带选定单元格的行和列。</span><span class="sxs-lookup"><span data-stu-id="047b1-107">When a user copies cells to the Clipboard, rows and columns with no selected cells are not copied.</span></span> <span data-ttu-id="047b1-108">所有其他行或列成为复制到剪贴板的数据表中的行和列。</span><span class="sxs-lookup"><span data-stu-id="047b1-108">All other rows or columns become rows and columns in the table of data copied to the Clipboard.</span></span> <span data-ttu-id="047b1-109">将这些行或列中未选定的单元格作为空白占位符复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="047b1-109">Unselected cells in these rows or columns are copied as blank placeholders to the Clipboard.</span></span>  
  
### <a name="to-enable-cell-copying"></a><span data-ttu-id="047b1-110">启用单元格复制</span><span class="sxs-lookup"><span data-stu-id="047b1-110">To enable cell copying</span></span>  
  
- <span data-ttu-id="047b1-111">设置 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="047b1-111">Set the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a><span data-ttu-id="047b1-112">示例</span><span class="sxs-lookup"><span data-stu-id="047b1-112">Example</span></span>  
 <span data-ttu-id="047b1-113">下面的完整代码示例演示如何将单元格复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="047b1-113">The following complete code example demonstrates how cells are copied to the Clipboard.</span></span> <span data-ttu-id="047b1-114">此示例包含一个按钮，该按钮使用 <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> 方法将选定的单元格复制到剪贴板，并在文本框中显示剪贴板内容。</span><span class="sxs-lookup"><span data-stu-id="047b1-114">This example includes a button that copies the selected cells to the Clipboard using the <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> method and displays the Clipboard contents in a text box.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="047b1-115">编译代码</span><span class="sxs-lookup"><span data-stu-id="047b1-115">Compiling the Code</span></span>  
 <span data-ttu-id="047b1-116">此代码需要：</span><span class="sxs-lookup"><span data-stu-id="047b1-116">This code requires:</span></span>  
  
- <span data-ttu-id="047b1-117">引用 N:System and N:System.Windows.Forms 程序集。</span><span class="sxs-lookup"><span data-stu-id="047b1-117">References to the N:System and N:System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="047b1-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="047b1-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>
- <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>
- [<span data-ttu-id="047b1-119">Windows 窗体 DataGridView 控件的选项和剪贴板使用</span><span class="sxs-lookup"><span data-stu-id="047b1-119">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
