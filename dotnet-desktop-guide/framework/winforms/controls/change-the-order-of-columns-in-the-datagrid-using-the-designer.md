---
title: 使用设计器更改 DataGridView 控件中列的顺序
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: 7540203fb1c0465caeb045275734d1a7c6f25ee8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970713"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="8a766-102">如何：使用设计器更改 Windows 窗体 DataGridView 控件中列的顺序</span><span class="sxs-lookup"><span data-stu-id="8a766-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="8a766-103">将 Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件绑定到数据源时，自动生成的列的显示顺序由数据源决定。</span><span class="sxs-lookup"><span data-stu-id="8a766-103">When you bind a Windows Forms <xref:System.Windows.Forms.DataGridView> control to a data source, the display order of the automatically generated columns is dictated by the data source.</span></span> <span data-ttu-id="8a766-104">如果此顺序不是你喜欢的顺序，则可以使用设计器更改列的顺序。</span><span class="sxs-lookup"><span data-stu-id="8a766-104">If this order is not what you prefer, you can change the order of the columns using the designer.</span></span> <span data-ttu-id="8a766-105">你可能还需要向控件添加未绑定的列并更改其显示顺序。</span><span class="sxs-lookup"><span data-stu-id="8a766-105">You may also want to add unbound columns to the control and change their display order.</span></span> <span data-ttu-id="8a766-106">有关如何以编程方式更改列顺序的信息，请参阅 [如何：更改 Windows 窗体 DataGridView 控件中列的顺序](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="8a766-106">For information about how to change the column order programmatically, see [How to: Change the Order of Columns in the Windows Forms DataGridView Control](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="8a766-107">下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="8a766-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="8a766-108">有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="8a766-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-change-the-column-order-using-the-designer"></a><span data-ttu-id="8a766-109">使用设计器更改列顺序</span><span class="sxs-lookup"><span data-stu-id="8a766-109">To change the column order using the designer</span></span>

1. <span data-ttu-id="8a766-110">单击 ![ 控件右上角 (小型黑色箭头) 的设计器操作标志符号 ](./media/designer-actions-glyph.gif) <xref:System.Windows.Forms.DataGridView> ，然后选择 " **编辑列**"。</span><span class="sxs-lookup"><span data-stu-id="8a766-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="8a766-111">从 " **选定的列** " 列表中选择一列。</span><span class="sxs-lookup"><span data-stu-id="8a766-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="8a766-112">单击 " **所选列** " 列表右侧的向上或向下箭头，直到所选列处于所需的位置。</span><span class="sxs-lookup"><span data-stu-id="8a766-112">Click the up or down arrow to the right of the **Selected Columns** list until the selected column is in the position you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a766-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a766-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="8a766-114">如何：使用设计器添加和移除 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="8a766-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="8a766-115">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="8a766-115">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="8a766-116">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="8a766-116">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
