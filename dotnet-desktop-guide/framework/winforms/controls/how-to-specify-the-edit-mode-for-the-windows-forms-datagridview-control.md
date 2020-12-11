---
title: 指定 DataGridView 控件的编辑模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: c0318202a80f9a43f1b656201732ef032f430b5b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972546"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="7cf25-102">如何：指定 Windows 窗体 DataGridView 控件的编辑模式</span><span class="sxs-lookup"><span data-stu-id="7cf25-102">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="7cf25-103">默认情况下，用户可以 <xref:System.Windows.Forms.DataGridView> 通过键入或按 F2 来编辑当前文本框单元格的内容。</span><span class="sxs-lookup"><span data-stu-id="7cf25-103">By default, users can edit the contents of the current <xref:System.Windows.Forms.DataGridView> text box cell by typing in it or pressing F2.</span></span> <span data-ttu-id="7cf25-104">如果满足以下所有条件，则会将单元格置于编辑模式：</span><span class="sxs-lookup"><span data-stu-id="7cf25-104">This puts the cell in edit mode if all of the following conditions are met:</span></span>  
  
- <span data-ttu-id="7cf25-105">基础数据源支持编辑。</span><span class="sxs-lookup"><span data-stu-id="7cf25-105">The underlying data source supports editing.</span></span>  
  
- <span data-ttu-id="7cf25-106"><xref:System.Windows.Forms.DataGridView>控件已启用。</span><span class="sxs-lookup"><span data-stu-id="7cf25-106">The <xref:System.Windows.Forms.DataGridView> control is enabled.</span></span>  
  
- <span data-ttu-id="7cf25-107"><xref:System.Windows.Forms.DataGridView.EditMode%2A> 属性值不为 <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>。</span><span class="sxs-lookup"><span data-stu-id="7cf25-107">The <xref:System.Windows.Forms.DataGridView.EditMode%2A> property value is not <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span></span>  
  
- <span data-ttu-id="7cf25-108">`ReadOnly`单元格、行、列和控件的属性均设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="7cf25-108">The `ReadOnly` properties of the cell, row, column, and control are all set to `false`.</span></span>  
  
 <span data-ttu-id="7cf25-109">在编辑模式下，用户可以更改单元值并按 ENTER 来提交更改，或按 ESC 将单元恢复到其原始值。</span><span class="sxs-lookup"><span data-stu-id="7cf25-109">In edit mode, the user can change the cell value and press ENTER to commit the change or ESC to revert the cell to its original value.</span></span>  
  
 <span data-ttu-id="7cf25-110">你可以配置 <xref:System.Windows.Forms.DataGridView> 控件，使单元格成为当前单元格后进入编辑模式。</span><span class="sxs-lookup"><span data-stu-id="7cf25-110">You can configure a <xref:System.Windows.Forms.DataGridView> control so that a cell enters edit mode as soon as it becomes the current cell.</span></span> <span data-ttu-id="7cf25-111">在这种情况下，ENTER 和 ESC 键的行为是不变的，但在提交或还原值后，该单元格仍处于编辑模式。</span><span class="sxs-lookup"><span data-stu-id="7cf25-111">The behavior of the ENTER and ESC keys is unchanged in this case, but the cell remains in edit mode after the value is committed or reverted.</span></span> <span data-ttu-id="7cf25-112">你还可以配置控件，以便仅当用户在单元格中输入时，或仅当用户按下 F2 时单元格进入编辑模式。</span><span class="sxs-lookup"><span data-stu-id="7cf25-112">You can also configure the control so that cells enter edit mode only when users type in the cell or only when users press F2.</span></span> <span data-ttu-id="7cf25-113">最后，你可以防止单元格进入编辑模式，除非调用 <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="7cf25-113">Finally, you can prevent cells from entering edit mode except when you call the <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> method.</span></span>  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a><span data-ttu-id="7cf25-114">更改 DataGridView 控件的编辑模式</span><span class="sxs-lookup"><span data-stu-id="7cf25-114">To change the edit mode of a DataGridView control</span></span>  
  
- <span data-ttu-id="7cf25-115">将 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> 属性设置为相应的 <xref:System.Windows.Forms.DataGridViewEditMode> 枚举。</span><span class="sxs-lookup"><span data-stu-id="7cf25-115">Set the <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> property to the appropriate <xref:System.Windows.Forms.DataGridViewEditMode> enumeration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7cf25-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="7cf25-116">Compiling the Code</span></span>  
 <span data-ttu-id="7cf25-117">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="7cf25-117">This example requires:</span></span>  
  
- <span data-ttu-id="7cf25-118">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="7cf25-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="7cf25-119">对 <xref:System> 和 <xref:System.Windows.Forms> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="7cf25-119">References to the <xref:System> and <xref:System.Windows.Forms> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf25-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7cf25-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7cf25-121">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="7cf25-121">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
