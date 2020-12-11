---
title: 使用设计器在 DataGridView 控件中启用列重新排序
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 14dc1081a8608c6e6add67f641c4b55825d2fc81
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971537"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="7903e-102">如何：使用设计器在 Windows 窗体 DataGridView 控件中启用列重新排序</span><span class="sxs-lookup"><span data-stu-id="7903e-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="7903e-103">查看 Windows 窗体控件中显示的数据时 <xref:System.Windows.Forms.DataGridView> ，用户有时需要比较特定列中的值。</span><span class="sxs-lookup"><span data-stu-id="7903e-103">When viewing data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, users sometimes want to compare the values in specific columns.</span></span> <span data-ttu-id="7903e-104">如果在控件中广泛地分隔列，则这会很不方便，尤其是在用户必须水平来回滚动以便查看他们感兴趣的所有列时。</span><span class="sxs-lookup"><span data-stu-id="7903e-104">This can be inconvenient if the columns are widely separated in the control, especially if users must scroll back and forth horizontally in order to see all the columns they are interested in.</span></span> <span data-ttu-id="7903e-105">您可以通过使您的用户能够对列进行重新排序，使比较列值的任务变得更容易。</span><span class="sxs-lookup"><span data-stu-id="7903e-105">You can make the task of comparing column values easier by enabling your users to reorder the columns.</span></span> <span data-ttu-id="7903e-106">启用列重新排序后，用户可以通过用鼠标拖动列标题来将列移动到新位置。</span><span class="sxs-lookup"><span data-stu-id="7903e-106">When you enable column reordering, users can move a column to a new position by dragging the column header with the mouse.</span></span>

 <span data-ttu-id="7903e-107">下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="7903e-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="7903e-108">有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="7903e-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-enable-column-reordering"></a><span data-ttu-id="7903e-109">启用列重新排序</span><span class="sxs-lookup"><span data-stu-id="7903e-109">To enable column reordering</span></span>

- <span data-ttu-id="7903e-110">单击 ![ 控件右上角 (小型黑色箭头) 的设计器操作标志符号 ](./media/designer-actions-glyph.gif) <xref:System.Windows.Forms.DataGridView> ，然后选择 " **启用列重新排序**"。</span><span class="sxs-lookup"><span data-stu-id="7903e-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Enable Column Reordering**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7903e-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7903e-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7903e-112">如何：使用设计器冻结 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="7903e-112">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="7903e-113">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="7903e-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="7903e-114">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="7903e-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
