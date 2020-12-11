---
title: 演练：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
ms.openlocfilehash: d71534bed0af142ff71ba9a0c01207b2c72a6d6a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972866"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="c25b0-102">演练：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体</span><span class="sxs-lookup"><span data-stu-id="c25b0-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>

<span data-ttu-id="c25b0-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间支持多文档界面 (MDI) 应用程序，而 <xref:System.Windows.Forms.MenuStrip> 控件支持菜单合并。</span><span class="sxs-lookup"><span data-stu-id="c25b0-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="c25b0-104">MDI 窗体还可支持 <xref:System.Windows.Forms.ToolStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="c25b0-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="c25b0-105">本演练演示如何使用 <xref:System.Windows.Forms.ToolStripPanel> 带有 MDI 窗体的控件。</span><span class="sxs-lookup"><span data-stu-id="c25b0-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="c25b0-106">此窗体还支持菜单与子菜单合并。</span><span class="sxs-lookup"><span data-stu-id="c25b0-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="c25b0-107">此演练演示了下列任务：</span><span class="sxs-lookup"><span data-stu-id="c25b0-107">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="c25b0-108">创建 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="c25b0-108">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="c25b0-109">创建窗体的主菜单。</span><span class="sxs-lookup"><span data-stu-id="c25b0-109">Creating the main menu for your form.</span></span> <span data-ttu-id="c25b0-110">菜单的实际名称将有所不同。</span><span class="sxs-lookup"><span data-stu-id="c25b0-110">The actual name of the menu will vary.</span></span>

- <span data-ttu-id="c25b0-111">将 <xref:System.Windows.Forms.ToolStripPanel> 控件添加到 " **工具箱**"。</span><span class="sxs-lookup"><span data-stu-id="c25b0-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>

- <span data-ttu-id="c25b0-112">创建子窗体。</span><span class="sxs-lookup"><span data-stu-id="c25b0-112">Creating a child form.</span></span>

- <span data-ttu-id="c25b0-113"><xref:System.Windows.Forms.ToolStripPanel>按 z 顺序排列控件。</span><span class="sxs-lookup"><span data-stu-id="c25b0-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>

<span data-ttu-id="c25b0-114">完成后，将拥有一个支持菜单合并和可移动控件的 MDI 窗体 <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="c25b0-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="c25b0-115">若要将本主题中的代码复制为单个列表，请参阅 [如何：创建具有菜单合并和 ToolStrip 控件的 MDI 窗体](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="c25b0-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c25b0-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="c25b0-116">Prerequisites</span></span>

<span data-ttu-id="c25b0-117">需要 Visual Studio 才能完成此演练。</span><span class="sxs-lookup"><span data-stu-id="c25b0-117">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="c25b0-118">创建项目</span><span class="sxs-lookup"><span data-stu-id="c25b0-118">Create the project</span></span>

1. <span data-ttu-id="c25b0-119">在 Visual Studio 中，创建名为 **system.windows.forms.toolstrip.mdiform** (文件 "   >  **新建**  >  **项目**" "  >  **Visual c #** " 或 " **Visual Basic**  >  **经典桌面**  >  **Windows 窗体应用程序**) " 的 Windows 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="c25b0-119">In Visual Studio, create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="c25b0-120">在 Windows 窗体设计器中，选择窗体。</span><span class="sxs-lookup"><span data-stu-id="c25b0-120">In the Windows Forms Designer, select the form.</span></span>

3. <span data-ttu-id="c25b0-121">在属性窗口中，将的值设置 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="c25b0-121">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>

## <a name="create-the-main-menu"></a><span data-ttu-id="c25b0-122">创建主菜单</span><span class="sxs-lookup"><span data-stu-id="c25b0-122">Create the main menu</span></span>

<span data-ttu-id="c25b0-123">父 MDI 窗体包含主菜单。</span><span class="sxs-lookup"><span data-stu-id="c25b0-123">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="c25b0-124">主菜单中有一个名为 **Window** 的菜单项。</span><span class="sxs-lookup"><span data-stu-id="c25b0-124">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="c25b0-125">通过 " **窗口** " 菜单项，可以创建子窗体。</span><span class="sxs-lookup"><span data-stu-id="c25b0-125">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="c25b0-126">子窗体中的菜单项将合并到主菜单。</span><span class="sxs-lookup"><span data-stu-id="c25b0-126">Menu items from child forms are merged into the main menu.</span></span>

1. <span data-ttu-id="c25b0-127">从 " **工具箱**" 中，将 <xref:System.Windows.Forms.MenuStrip> 控件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="c25b0-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>

2. <span data-ttu-id="c25b0-128">将添加 <xref:System.Windows.Forms.ToolStripMenuItem> 到 <xref:System.Windows.Forms.MenuStrip> 控件并将其命名为 " **窗口**"。</span><span class="sxs-lookup"><span data-stu-id="c25b0-128">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>

3. <span data-ttu-id="c25b0-129">选择 <xref:System.Windows.Forms.MenuStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="c25b0-129">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

4. <span data-ttu-id="c25b0-130">在属性窗口中，将属性的值设置 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 为 `ToolStripMenuItem1` 。</span><span class="sxs-lookup"><span data-stu-id="c25b0-130">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>

5. <span data-ttu-id="c25b0-131">将子项添加到 " **窗口** " 菜单项，然后将子项命名为 " **新**"。</span><span class="sxs-lookup"><span data-stu-id="c25b0-131">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>

6. <span data-ttu-id="c25b0-132">在“属性”窗口中，单击“事件”。</span><span class="sxs-lookup"><span data-stu-id="c25b0-132">In the Properties window, click **Events**.</span></span>

7. <span data-ttu-id="c25b0-133">双击该 <xref:System.Windows.Forms.ToolStripItem.Click> 事件。</span><span class="sxs-lookup"><span data-stu-id="c25b0-133">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

     <span data-ttu-id="c25b0-134">Windows 窗体设计器生成事件的事件处理程序 <xref:System.Windows.Forms.ToolStripItem.Click> 。</span><span class="sxs-lookup"><span data-stu-id="c25b0-134">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

8. <span data-ttu-id="c25b0-135">将以下代码插入到事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="c25b0-135">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="c25b0-136">将 ToolStripPanel 控件添加到工具箱</span><span class="sxs-lookup"><span data-stu-id="c25b0-136">Add the ToolStripPanel control to the Toolbox</span></span>

<span data-ttu-id="c25b0-137">使用 <xref:System.Windows.Forms.MenuStrip> 带有 MDI 窗体的控件时，必须具有 <xref:System.Windows.Forms.ToolStripPanel> 控件。</span><span class="sxs-lookup"><span data-stu-id="c25b0-137">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="c25b0-138">必须将控件添加 <xref:System.Windows.Forms.ToolStripPanel> 到 " **工具箱** "，才能在 WINDOWS 窗体设计器中生成 MDI 窗体。</span><span class="sxs-lookup"><span data-stu-id="c25b0-138">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="c25b0-139">打开 " **工具箱**"，然后单击 " **所有 Windows 窗体** " 选项卡以显示可用的 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="c25b0-139">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>

2. <span data-ttu-id="c25b0-140">右键单击以打开快捷菜单，然后选择 " **选择项**"。</span><span class="sxs-lookup"><span data-stu-id="c25b0-140">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>

3. <span data-ttu-id="c25b0-141">在 " **选择工具箱项** " 对话框中，在 " **名称** " 列中向下滚动，直到找到 **ToolStripPanel**。</span><span class="sxs-lookup"><span data-stu-id="c25b0-141">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>

4. <span data-ttu-id="c25b0-142">选中 " **ToolStripPanel**" 复选框，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c25b0-142">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>

     <span data-ttu-id="c25b0-143"><xref:System.Windows.Forms.ToolStripPanel>控件将出现在 **工具箱** 中。</span><span class="sxs-lookup"><span data-stu-id="c25b0-143">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>

## <a name="create-a-child-form"></a><span data-ttu-id="c25b0-144">创建子窗体</span><span class="sxs-lookup"><span data-stu-id="c25b0-144">Create a child form</span></span>

<span data-ttu-id="c25b0-145">在此过程中，您将定义一个具有自己的控件的单独的子窗体类 <xref:System.Windows.Forms.MenuStrip> 。</span><span class="sxs-lookup"><span data-stu-id="c25b0-145">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="c25b0-146">此窗体的菜单项与父窗体的菜单项合并。</span><span class="sxs-lookup"><span data-stu-id="c25b0-146">The menu items for this form are merged with those of the parent form.</span></span>

1. <span data-ttu-id="c25b0-147">向项目中添加一个名为的新窗体 `ChildForm` 。</span><span class="sxs-lookup"><span data-stu-id="c25b0-147">Add a new form named `ChildForm` to the project.</span></span>

     <span data-ttu-id="c25b0-148">有关详细信息，请参阅 [如何：将 Windows 窗体添加到项目](/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="c25b0-148">For more information, see [How to: Add Windows Forms to a Project](/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>

2. <span data-ttu-id="c25b0-149">从 " **工具箱**" 中，将 <xref:System.Windows.Forms.MenuStrip> 控件拖动到子窗体上。</span><span class="sxs-lookup"><span data-stu-id="c25b0-149">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>

3. <span data-ttu-id="c25b0-150">单击 <xref:System.Windows.Forms.MenuStrip> 控件的设计器操作标志符号 (![ 小型黑色箭头 ](./media/designer-actions-glyph.gif)) ，然后选择 " **编辑项**"。</span><span class="sxs-lookup"><span data-stu-id="c25b0-150">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)), and then select **Edit Items**.</span></span>

4. <span data-ttu-id="c25b0-151">在 " **项集合编辑器** " 对话框中，将一个 <xref:System.Windows.Forms.ToolStripMenuItem> 名为 **ChildMenuItem** 的新添加到子菜单中。</span><span class="sxs-lookup"><span data-stu-id="c25b0-151">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>

     <span data-ttu-id="c25b0-152">有关详细信息，请参阅 [ToolStrip 项集合编辑器](/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="c25b0-152">For more information, see [ToolStrip Items Collection Editor](/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>

## <a name="test-the-form"></a><span data-ttu-id="c25b0-153">测试窗体</span><span class="sxs-lookup"><span data-stu-id="c25b0-153">Test the form</span></span>

1. <span data-ttu-id="c25b0-154">按 **F5** 编译并运行您的窗体。</span><span class="sxs-lookup"><span data-stu-id="c25b0-154">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="c25b0-155">单击 " **窗口** " 菜单项以打开菜单，然后单击 " **新建**"。</span><span class="sxs-lookup"><span data-stu-id="c25b0-155">Click the **Window** menu item to open the menu, and then click **New**.</span></span>

     <span data-ttu-id="c25b0-156">在窗体的 MDI 工作区中创建一个新的子窗体。</span><span class="sxs-lookup"><span data-stu-id="c25b0-156">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="c25b0-157">子窗体的菜单与主菜单合并在一起。</span><span class="sxs-lookup"><span data-stu-id="c25b0-157">The child form's menu is merged with the main menu.</span></span>

3. <span data-ttu-id="c25b0-158">关闭子窗体。</span><span class="sxs-lookup"><span data-stu-id="c25b0-158">Close the child form.</span></span>

     <span data-ttu-id="c25b0-159">子窗体的菜单将从主菜单中删除。</span><span class="sxs-lookup"><span data-stu-id="c25b0-159">The child form's menu is removed from the main menu.</span></span>

4. <span data-ttu-id="c25b0-160">单击 " **新建** " 多次。</span><span class="sxs-lookup"><span data-stu-id="c25b0-160">Click **New** several times.</span></span>

     <span data-ttu-id="c25b0-161">子窗体自动列在 " **窗口** " 菜单项下，因为 <xref:System.Windows.Forms.MenuStrip> 分配了控件的 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="c25b0-161">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>

## <a name="add-toolstrip-support"></a><span data-ttu-id="c25b0-162">添加 ToolStrip 支持</span><span class="sxs-lookup"><span data-stu-id="c25b0-162">Add ToolStrip support</span></span>

<span data-ttu-id="c25b0-163">在此过程中，您将向 <xref:System.Windows.Forms.ToolStrip> MDI 父窗体添加四个控件。</span><span class="sxs-lookup"><span data-stu-id="c25b0-163">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="c25b0-164">每个 <xref:System.Windows.Forms.ToolStrip> 控件都将添加 <xref:System.Windows.Forms.ToolStripPanel> 到控件内，该控件停靠到窗体的边缘。</span><span class="sxs-lookup"><span data-stu-id="c25b0-164">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>

1. <span data-ttu-id="c25b0-165">从 " **工具箱**" 中，将 <xref:System.Windows.Forms.ToolStripPanel> 控件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="c25b0-165">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>

2. <span data-ttu-id="c25b0-166"><xref:System.Windows.Forms.ToolStripPanel>选中控件后，双击 <xref:System.Windows.Forms.ToolStrip> **工具箱** 中的控件。</span><span class="sxs-lookup"><span data-stu-id="c25b0-166">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>

     <span data-ttu-id="c25b0-167"><xref:System.Windows.Forms.ToolStrip>在控件中创建控件 <xref:System.Windows.Forms.ToolStripPanel> 。</span><span class="sxs-lookup"><span data-stu-id="c25b0-167">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

3. <span data-ttu-id="c25b0-168">选择 <xref:System.Windows.Forms.ToolStripPanel> 控件。</span><span class="sxs-lookup"><span data-stu-id="c25b0-168">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

4. <span data-ttu-id="c25b0-169">在属性窗口中，将控件的属性值更改 <xref:System.Windows.Forms.Control.Dock%2A> 为 <xref:System.Windows.Forms.DockStyle.Left> 。</span><span class="sxs-lookup"><span data-stu-id="c25b0-169">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>

     <span data-ttu-id="c25b0-170"><xref:System.Windows.Forms.ToolStripPanel>控件停靠在主菜单下的窗体的左侧。</span><span class="sxs-lookup"><span data-stu-id="c25b0-170">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="c25b0-171">根据控件调整 MDI 客户端区域大小 <xref:System.Windows.Forms.ToolStripPanel> 。</span><span class="sxs-lookup"><span data-stu-id="c25b0-171">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

5. <span data-ttu-id="c25b0-172">重复步骤1到4。</span><span class="sxs-lookup"><span data-stu-id="c25b0-172">Repeat steps 1 through 4.</span></span>

     <span data-ttu-id="c25b0-173">将新 <xref:System.Windows.Forms.ToolStripPanel> 控件停靠到窗体的顶部。</span><span class="sxs-lookup"><span data-stu-id="c25b0-173">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>

     <span data-ttu-id="c25b0-174"><xref:System.Windows.Forms.ToolStripPanel>控件停靠在主菜单下，而位于第一个控件的右侧 <xref:System.Windows.Forms.ToolStripPanel> 。</span><span class="sxs-lookup"><span data-stu-id="c25b0-174">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="c25b0-175">此步骤说明了正确定位控件时 z 顺序的重要性 <xref:System.Windows.Forms.ToolStripPanel> 。</span><span class="sxs-lookup"><span data-stu-id="c25b0-175">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

6. <span data-ttu-id="c25b0-176">对两个以上的控件重复步骤1到 4 <xref:System.Windows.Forms.ToolStripPanel> 。</span><span class="sxs-lookup"><span data-stu-id="c25b0-176">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

     <span data-ttu-id="c25b0-177">将新 <xref:System.Windows.Forms.ToolStripPanel> 控件停靠到窗体的右侧和底部。</span><span class="sxs-lookup"><span data-stu-id="c25b0-177">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>

## <a name="arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="c25b0-178">按 Z 顺序排列 ToolStripPanel 控件</span><span class="sxs-lookup"><span data-stu-id="c25b0-178">Arrange ToolStripPanel controls by Z-order</span></span>

<span data-ttu-id="c25b0-179">停靠 <xref:System.Windows.Forms.ToolStripPanel> 控件在 MDI 窗体上的位置由该控件在 z 顺序中的位置确定。</span><span class="sxs-lookup"><span data-stu-id="c25b0-179">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="c25b0-180">您可以轻松地在 "文档大纲" 窗口中排列控件的 z 顺序。</span><span class="sxs-lookup"><span data-stu-id="c25b0-180">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>

1. <span data-ttu-id="c25b0-181">在 " **视图** " 菜单上，单击 " **其他窗口**"，然后单击 " **文档大纲**"。</span><span class="sxs-lookup"><span data-stu-id="c25b0-181">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>

     <span data-ttu-id="c25b0-182"><xref:System.Windows.Forms.ToolStripPanel>前面的过程中的控件排列是非标准的。</span><span class="sxs-lookup"><span data-stu-id="c25b0-182">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="c25b0-183">这是因为 z 顺序不正确。</span><span class="sxs-lookup"><span data-stu-id="c25b0-183">This is because the z-order is not correct.</span></span> <span data-ttu-id="c25b0-184">使用 "文档大纲" 窗口可以更改控件的 z 顺序。</span><span class="sxs-lookup"><span data-stu-id="c25b0-184">Use the Document Outline window to change the z-order of the controls.</span></span>

2. <span data-ttu-id="c25b0-185">在 "文档大纲" 窗口中，选择 " **ToolStripPanel4**"。</span><span class="sxs-lookup"><span data-stu-id="c25b0-185">In the Document Outline window, select **ToolStripPanel4**.</span></span>

3. <span data-ttu-id="c25b0-186">重复单击向下箭头按钮，直到 **ToolStripPanel4** 位于列表底部。</span><span class="sxs-lookup"><span data-stu-id="c25b0-186">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>

     <span data-ttu-id="c25b0-187">**ToolStripPanel4** 控件停靠在窗体底部的其他控件下。</span><span class="sxs-lookup"><span data-stu-id="c25b0-187">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>

4. <span data-ttu-id="c25b0-188">选择 **ToolStripPanel2**。</span><span class="sxs-lookup"><span data-stu-id="c25b0-188">Select **ToolStripPanel2**.</span></span>

5. <span data-ttu-id="c25b0-189">单击向下箭头按钮一次，将控件置于列表中的第三位。</span><span class="sxs-lookup"><span data-stu-id="c25b0-189">Click the down-arrow button one time to position the control third in the list.</span></span>

     <span data-ttu-id="c25b0-190">**ToolStripPanel2** 控件停靠在窗体的顶部，位于主菜单的下方和其他控件的上方。</span><span class="sxs-lookup"><span data-stu-id="c25b0-190">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>

6. <span data-ttu-id="c25b0-191">在 " **文档大纲** " 窗口中选择各个控件，并将它们移动到 z 顺序中的不同位置。</span><span class="sxs-lookup"><span data-stu-id="c25b0-191">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="c25b0-192">请注意 z 顺序对停靠控件位置的影响。</span><span class="sxs-lookup"><span data-stu-id="c25b0-192">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="c25b0-193">使用 CTRL + Z 或 "**编辑**" 菜单上的 "**撤消**" 可撤消更改。</span><span class="sxs-lookup"><span data-stu-id="c25b0-193">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>

## <a name="checkpoint---test-your-form"></a><span data-ttu-id="c25b0-194">检查点-测试窗体</span><span class="sxs-lookup"><span data-stu-id="c25b0-194">Checkpoint - test your form</span></span>

1. <span data-ttu-id="c25b0-195">按 **F5** 编译并运行您的窗体。</span><span class="sxs-lookup"><span data-stu-id="c25b0-195">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="c25b0-196">单击控件的手柄 <xref:System.Windows.Forms.ToolStrip> ，将控件拖动到窗体上的不同位置。</span><span class="sxs-lookup"><span data-stu-id="c25b0-196">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>

     <span data-ttu-id="c25b0-197">可以将 <xref:System.Windows.Forms.ToolStrip> 一个控件从一个 <xref:System.Windows.Forms.ToolStripPanel> 控件拖动到另一个控件。</span><span class="sxs-lookup"><span data-stu-id="c25b0-197">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c25b0-198">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c25b0-198">Next steps</span></span>

<span data-ttu-id="c25b0-199">在本演练中，您已创建了一个具有 <xref:System.Windows.Forms.ToolStrip> 控件和菜单合并的 MDI 父窗体。</span><span class="sxs-lookup"><span data-stu-id="c25b0-199">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="c25b0-200">可以将 <xref:System.Windows.Forms.ToolStrip> 控件系列用于许多其他用途：</span><span class="sxs-lookup"><span data-stu-id="c25b0-200">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="c25b0-201">为控件创建快捷菜单 <xref:System.Windows.Forms.ContextMenuStrip> 。</span><span class="sxs-lookup"><span data-stu-id="c25b0-201">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="c25b0-202">有关详细信息，请参阅 [ContextMenu 组件概述](contextmenu-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="c25b0-202">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="c25b0-203">创建了一个带有自动填充的标准菜单的窗体。</span><span class="sxs-lookup"><span data-stu-id="c25b0-203">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="c25b0-204">有关详细信息，请参阅 [演练：向窗体提供标准菜单项](walkthrough-providing-standard-menu-items-to-a-form.md)。</span><span class="sxs-lookup"><span data-stu-id="c25b0-204">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="c25b0-205">为 <xref:System.Windows.Forms.ToolStrip> 控件指定专业外观。</span><span class="sxs-lookup"><span data-stu-id="c25b0-205">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="c25b0-206">有关详细信息，请参阅 [如何：为应用程序设置 ToolStrip 呈现](how-to-set-the-toolstrip-renderer-for-an-application.md)器。</span><span class="sxs-lookup"><span data-stu-id="c25b0-206">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c25b0-207">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c25b0-207">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="c25b0-208">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="c25b0-208">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="c25b0-209">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="c25b0-209">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="c25b0-210">如何：将 MenuStrip 插入 MDI 下拉菜单</span><span class="sxs-lookup"><span data-stu-id="c25b0-210">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="c25b0-211">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="c25b0-211">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
