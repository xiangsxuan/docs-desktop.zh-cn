---
title: 使用设计器向 ListView 控件添加列
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 627f8627aac861877a05c13def07427199807754
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971514"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="b775f-102">如何：使用设计器向 Windows 窗体 ListView 控件添加列</span><span class="sxs-lookup"><span data-stu-id="b775f-102">How to: Add Columns to the Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="b775f-103"><xref:System.Windows.Forms.ListView>当在 **详细信息** 视图中时，Windows 窗体控件可以显示每个列表项的多个列。</span><span class="sxs-lookup"><span data-stu-id="b775f-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item when in the **Details** view.</span></span> <span data-ttu-id="b775f-104">您可以使用这些列显示有关每个列表项的多种类型的信息。</span><span class="sxs-lookup"><span data-stu-id="b775f-104">You can use the columns to display several types of information about each list item.</span></span> <span data-ttu-id="b775f-105">例如，文件列表可以显示文件的名称、文件类型、大小和文件的上次修改日期。</span><span class="sxs-lookup"><span data-stu-id="b775f-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="b775f-106">有关创建列后对其进行填充的信息，请参阅 [如何：用 Windows 窗体 ListView 控件在列中显示子项](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="b775f-106">For information on populating the columns once they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>

<span data-ttu-id="b775f-107">下面的过程需要一个 **Windows 应用程序** 项目，该项目具有包含控件的窗体 <xref:System.Windows.Forms.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="b775f-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="b775f-108">有关设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="b775f-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-columns-in-the-designer"></a><span data-ttu-id="b775f-109">在设计器中添加列</span><span class="sxs-lookup"><span data-stu-id="b775f-109">To add columns in the designer</span></span>

1. <span data-ttu-id="b775f-110">在 " **属性** " 窗口中，将控件的 <xref:System.Windows.Forms.ListView.View%2A> 属性设置为 <xref:System.Windows.Forms.View.Details> 。</span><span class="sxs-lookup"><span data-stu-id="b775f-110">In the **Properties** window, set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

2. <span data-ttu-id="b775f-111">在 "**属性**" 窗口中，单击 **省略号** 按钮， (![ Visual Studio 属性窗口中的省略号按钮 ( ") "。在 ](./media/visual-studio-ellipsis-button.png) 属性旁) 。 <xref:System.Windows.Forms.ListView.Columns%2A></span><span class="sxs-lookup"><span data-stu-id="b775f-111">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>

     <span data-ttu-id="b775f-112">此时将显示 " **ColumnHeader 集合编辑器** "。</span><span class="sxs-lookup"><span data-stu-id="b775f-112">The **ColumnHeader Collection Editor** appears.</span></span>

3. <span data-ttu-id="b775f-113">使用 " **添加** " 按钮添加新列。</span><span class="sxs-lookup"><span data-stu-id="b775f-113">Use the **Add** button to add new columns.</span></span> <span data-ttu-id="b775f-114">然后，可以选择列标题，并将其文本设置 (列的标题) 、文本对齐方式和宽度。</span><span class="sxs-lookup"><span data-stu-id="b775f-114">You can then select the column header and set its text (the caption of the column), text alignment, and width.</span></span>

## <a name="see-also"></a><span data-ttu-id="b775f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b775f-115">See also</span></span>

- [<span data-ttu-id="b775f-116">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="b775f-116">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="b775f-117">如何：使用 Windows 窗体 ListView 控件添加和移除项</span><span class="sxs-lookup"><span data-stu-id="b775f-117">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="b775f-118">如何：使用 Windows 窗体 ListView 控件在列中显示子项</span><span class="sxs-lookup"><span data-stu-id="b775f-118">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="b775f-119">如何：显示 Windows 窗体 ListView 控件的图标</span><span class="sxs-lookup"><span data-stu-id="b775f-119">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="b775f-120">如何：向 TreeView 或 ListView 控件添加自定义信息（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="b775f-120">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
