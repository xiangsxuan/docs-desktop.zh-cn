---
title: 演练：向窗体提供标准菜单项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: ee80aad445c00bb4b98b49c80495fa512150bcef
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972499"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="b3acd-102">演练：向窗体提供标准菜单项</span><span class="sxs-lookup"><span data-stu-id="b3acd-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>

<span data-ttu-id="b3acd-103">可使用 <xref:System.Windows.Forms.MenuStrip> 控件向窗体提供标准菜单。</span><span class="sxs-lookup"><span data-stu-id="b3acd-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="b3acd-104">本演练演示如何使用 <xref:System.Windows.Forms.MenuStrip> 控件创建标准菜单。</span><span class="sxs-lookup"><span data-stu-id="b3acd-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="b3acd-105">窗体还在用户选择菜单项时做出响应。</span><span class="sxs-lookup"><span data-stu-id="b3acd-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="b3acd-106">此演练演示了下列任务：</span><span class="sxs-lookup"><span data-stu-id="b3acd-106">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="b3acd-107">创建 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="b3acd-107">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="b3acd-108">创建标准菜单。</span><span class="sxs-lookup"><span data-stu-id="b3acd-108">Creating a standard menu.</span></span>

- <span data-ttu-id="b3acd-109">创建 <xref:System.Windows.Forms.StatusStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="b3acd-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

- <span data-ttu-id="b3acd-110">处理菜单项选择。</span><span class="sxs-lookup"><span data-stu-id="b3acd-110">Handling menu item selection.</span></span>

<span data-ttu-id="b3acd-111">完成后，将获得一个带有标准菜单的窗体，其中显示了控件中的菜单项选择 <xref:System.Windows.Forms.StatusStrip> 。</span><span class="sxs-lookup"><span data-stu-id="b3acd-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

<span data-ttu-id="b3acd-112">若要将本主题中的代码复制为单个列表，请参阅 [如何：向窗体提供标准菜单项](how-to-provide-standard-menu-items-to-a-form.md)。</span><span class="sxs-lookup"><span data-stu-id="b3acd-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b3acd-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="b3acd-113">Prerequisites</span></span>

<span data-ttu-id="b3acd-114">需要 Visual Studio 才能完成此演练。</span><span class="sxs-lookup"><span data-stu-id="b3acd-114">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="b3acd-115">创建项目</span><span class="sxs-lookup"><span data-stu-id="b3acd-115">Create the project</span></span>

1. <span data-ttu-id="b3acd-116">在 Visual Studio 中，创建名为 **StandardMenuForm** (文件 "   >  **新建**  >  **项目**" "  >  **Visual c #** " 或 " **Visual Basic**  >  **经典桌面**  >  **Windows 窗体应用程序**) " 的 Windows 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="b3acd-116">In Visual Studio, create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="b3acd-117">在 Windows 窗体设计器中，选择窗体。</span><span class="sxs-lookup"><span data-stu-id="b3acd-117">In the Windows Forms Designer, select the form.</span></span>

## <a name="create-a-standard-menu"></a><span data-ttu-id="b3acd-118">创建标准菜单</span><span class="sxs-lookup"><span data-stu-id="b3acd-118">Create a standard menu</span></span>

<span data-ttu-id="b3acd-119">Windows 窗体设计器可以 <xref:System.Windows.Forms.MenuStrip> 使用标准菜单项自动填充控件。</span><span class="sxs-lookup"><span data-stu-id="b3acd-119">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>

1. <span data-ttu-id="b3acd-120">从 " **工具箱**" 中，将 <xref:System.Windows.Forms.MenuStrip> 控件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="b3acd-120">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>

2. <span data-ttu-id="b3acd-121">单击 <xref:System.Windows.Forms.MenuStrip> 控件的设计器操作标志符号 (![ 小号黑色箭头 ](./media/designer-actions-glyph.gif)) 并选择 " **插入标准项**"。</span><span class="sxs-lookup"><span data-stu-id="b3acd-121">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Insert Standard Items**.</span></span>

     <span data-ttu-id="b3acd-122"><xref:System.Windows.Forms.MenuStrip>控件将用标准菜单项进行填充。</span><span class="sxs-lookup"><span data-stu-id="b3acd-122">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>

3. <span data-ttu-id="b3acd-123">单击 " **文件** " 菜单项可查看其默认菜单项和相应的图标。</span><span class="sxs-lookup"><span data-stu-id="b3acd-123">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>

## <a name="create-a-statusstrip-control"></a><span data-ttu-id="b3acd-124">创建 StatusStrip 控件</span><span class="sxs-lookup"><span data-stu-id="b3acd-124">Create a StatusStrip control</span></span>

<span data-ttu-id="b3acd-125">使用 <xref:System.Windows.Forms.StatusStrip> 控件显示 Windows 窗体应用程序的状态。</span><span class="sxs-lookup"><span data-stu-id="b3acd-125">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="b3acd-126">在当前的示例中，用户选择的菜单项显示在控件中 <xref:System.Windows.Forms.StatusStrip> 。</span><span class="sxs-lookup"><span data-stu-id="b3acd-126">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

1. <span data-ttu-id="b3acd-127">从 " **工具箱**" 中，将 <xref:System.Windows.Forms.StatusStrip> 控件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="b3acd-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>

     <span data-ttu-id="b3acd-128"><xref:System.Windows.Forms.StatusStrip>控件会自动停靠到窗体的底部。</span><span class="sxs-lookup"><span data-stu-id="b3acd-128">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>

2. <span data-ttu-id="b3acd-129">单击 <xref:System.Windows.Forms.StatusStrip> 控件的下拉按钮，然后选择 " **statuslabel 设置** "，将 <xref:System.Windows.Forms.ToolStripStatusLabel> 控件添加到 <xref:System.Windows.Forms.StatusStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="b3acd-129">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>

## <a name="handle-item-selection"></a><span data-ttu-id="b3acd-130">处理项选择</span><span class="sxs-lookup"><span data-stu-id="b3acd-130">Handle item selection</span></span>

<span data-ttu-id="b3acd-131">处理 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 事件，以便在用户选择菜单项时做出响应。</span><span class="sxs-lookup"><span data-stu-id="b3acd-131">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>

1. <span data-ttu-id="b3acd-132">单击在创建标准菜单部分中创建的 " **文件** " 菜单项。</span><span class="sxs-lookup"><span data-stu-id="b3acd-132">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>

2. <span data-ttu-id="b3acd-133">在“属性”窗口中，单击“事件”。</span><span class="sxs-lookup"><span data-stu-id="b3acd-133">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="b3acd-134">双击该 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 事件。</span><span class="sxs-lookup"><span data-stu-id="b3acd-134">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

     <span data-ttu-id="b3acd-135">Windows 窗体设计器生成事件的事件处理程序 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 。</span><span class="sxs-lookup"><span data-stu-id="b3acd-135">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

4. <span data-ttu-id="b3acd-136">将以下代码插入到事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="b3acd-136">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. <span data-ttu-id="b3acd-137">将 `UpdateStatus` 实用工具方法定义插入窗体中。</span><span class="sxs-lookup"><span data-stu-id="b3acd-137">Insert the `UpdateStatus` utility method definition into the form.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a><span data-ttu-id="b3acd-138">检查点-测试窗体</span><span class="sxs-lookup"><span data-stu-id="b3acd-138">Checkpoint -test your form</span></span>

1. <span data-ttu-id="b3acd-139">按 **F5** 编译并运行您的窗体。</span><span class="sxs-lookup"><span data-stu-id="b3acd-139">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="b3acd-140">单击 " **文件** " 菜单项，打开菜单。</span><span class="sxs-lookup"><span data-stu-id="b3acd-140">Click the **File** menu item to open the menu.</span></span>

3. <span data-ttu-id="b3acd-141">在 " **文件** " 菜单上，单击其中一个项目以将其选中。</span><span class="sxs-lookup"><span data-stu-id="b3acd-141">On the **File** menu, click one of the items to select it.</span></span>

     <span data-ttu-id="b3acd-142"><xref:System.Windows.Forms.StatusStrip>控件显示选定的项。</span><span class="sxs-lookup"><span data-stu-id="b3acd-142">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b3acd-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b3acd-143">Next steps</span></span>

<span data-ttu-id="b3acd-144">在本演练中，您已创建了一个带有标准菜单的窗体。</span><span class="sxs-lookup"><span data-stu-id="b3acd-144">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="b3acd-145">可以将 <xref:System.Windows.Forms.ToolStrip> 控件系列用于许多其他用途：</span><span class="sxs-lookup"><span data-stu-id="b3acd-145">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="b3acd-146">为控件创建快捷菜单 <xref:System.Windows.Forms.ContextMenuStrip> 。</span><span class="sxs-lookup"><span data-stu-id="b3acd-146">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="b3acd-147">有关详细信息，请参阅 [ContextMenu 组件概述](contextmenu-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="b3acd-147">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="b3acd-148">使用停靠控件 (MDI) 窗体创建多文档界面 <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="b3acd-148">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="b3acd-149">有关详细信息，请参阅 [演练：创建具有菜单合并和 ToolStrip 控件的 MDI 窗体](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="b3acd-149">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

- <span data-ttu-id="b3acd-150">为 <xref:System.Windows.Forms.ToolStrip> 控件指定专业外观。</span><span class="sxs-lookup"><span data-stu-id="b3acd-150">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="b3acd-151">有关详细信息，请参阅 [如何：为应用程序设置 ToolStrip 呈现](how-to-set-the-toolstrip-renderer-for-an-application.md)器。</span><span class="sxs-lookup"><span data-stu-id="b3acd-151">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b3acd-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3acd-152">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="b3acd-153">MenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="b3acd-153">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
