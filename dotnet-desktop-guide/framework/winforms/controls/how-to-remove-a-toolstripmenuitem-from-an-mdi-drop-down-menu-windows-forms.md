---
title: 如何：从 MDI 下拉菜单中删除 ToolStripMenuItem
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], removing from MDI drop-down menus
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], removing
- MDI [Windows Forms], merging menu items
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
ms.openlocfilehash: 3198195cf0991734826508aa65818505bf2038c8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971143"
---
# <a name="how-to-remove-a-toolstripmenuitem-from-an-mdi-drop-down-menu-windows-forms"></a><span data-ttu-id="84ba9-102">如何：从 MDI 下拉菜单移除 ToolStripMenuItem（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="84ba9-102">How to: Remove a ToolStripMenuItem from an MDI Drop-Down Menu (Windows Forms)</span></span>
<span data-ttu-id="84ba9-103">在某些应用程序中，多文档界面 (MDI) 子窗口的类型可以不同于 MDI 父窗口。</span><span class="sxs-lookup"><span data-stu-id="84ba9-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="84ba9-104">例如，MDI 父窗口可能为电子表格，而 MDI 子窗口可能为图表。</span><span class="sxs-lookup"><span data-stu-id="84ba9-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="84ba9-105">在这种情况下，由于激活了不同类型的 MDI 子窗口，你想用 MDI 子菜单上的内容更新 MDI 父菜单的内容。</span><span class="sxs-lookup"><span data-stu-id="84ba9-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="84ba9-106">下面的过程使用 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 、 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 、 <xref:System.Windows.Forms.MergeAction> 和 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 属性从 MDI 父菜单的下拉部分中删除菜单项。</span><span class="sxs-lookup"><span data-stu-id="84ba9-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to remove a menu item from the drop-down part of the MDI parent menu.</span></span> <span data-ttu-id="84ba9-107">关闭 MDI 子窗口会将移除的菜单项还原到 MDI 父菜单。</span><span class="sxs-lookup"><span data-stu-id="84ba9-107">Closing the MDI child window restores the removed menu items to the MDI parent menu.</span></span>  
  
### <a name="to-remove-a-menustrip-from-an-mdi-drop-down-menu"></a><span data-ttu-id="84ba9-108">从 MDI 下拉菜单中删除 MenuStrip</span><span class="sxs-lookup"><span data-stu-id="84ba9-108">To remove a MenuStrip from an MDI drop-down menu</span></span>  
  
1. <span data-ttu-id="84ba9-109">创建一个窗体并将其 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="84ba9-109">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="84ba9-110">将 <xref:System.Windows.Forms.MenuStrip> 添加到 `Form1` 并将 <xref:System.Windows.Forms.MenuStrip> 的 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="84ba9-110">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3. <span data-ttu-id="84ba9-111">将顶级菜单项添加到 `Form1`<xref:System.Windows.Forms.MenuStrip> 并将其 <xref:System.Windows.Forms.Control.Text%2A> 属性设置为 `&File`。</span><span class="sxs-lookup"><span data-stu-id="84ba9-111">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
4. <span data-ttu-id="84ba9-112">将三个子菜单项添加到 `&File` 菜单项，并将其 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 属性设置为 `&Open` 、 `&Import from` 和 `E&xit` 。</span><span class="sxs-lookup"><span data-stu-id="84ba9-112">Add three submenu items to the `&File` menu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Open`, `&Import from`, and `E&xit`.</span></span>  
  
5. <span data-ttu-id="84ba9-113">向子菜单项添加两个子菜单项 `&Import from` ，并将其 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 属性设置为 `&Word` 和 `&Excel` 。</span><span class="sxs-lookup"><span data-stu-id="84ba9-113">Add two submenu items to the `&Import from` submenu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Word` and `&Excel`.</span></span>  
  
6. <span data-ttu-id="84ba9-114">将窗体添加到项目，将 <xref:System.Windows.Forms.MenuStrip> 添加该窗体，并将 `Form2`<xref:System.Windows.Forms.MenuStrip> 的 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="84ba9-114">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7. <span data-ttu-id="84ba9-115">将顶级菜单项添加到 `Form2`<xref:System.Windows.Forms.MenuStrip> 并将其 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 属性设置为 `&File`。</span><span class="sxs-lookup"><span data-stu-id="84ba9-115">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&File`.</span></span>  
  
8. <span data-ttu-id="84ba9-116">将 `&Import from` 子菜单项添加到的 `&File` 菜单 `Form2` ，然后将 `&Word` 子菜单项添加到 `&File` 菜单中。</span><span class="sxs-lookup"><span data-stu-id="84ba9-116">Add an `&Import from` submenu item to the `&File` menu of `Form2`, and add an `&Word` submenu item to the `&File` menu.</span></span>  
  
9. <span data-ttu-id="84ba9-117">设置 <xref:System.Windows.Forms.MergeAction> 菜单项的和属性，如下 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> `Form2` 表所示。</span><span class="sxs-lookup"><span data-stu-id="84ba9-117">Set the <xref:System.Windows.Forms.MergeAction> and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties of the `Form2` menu items as shown in the following table.</span></span>  
  
    |<span data-ttu-id="84ba9-118">Form2 菜单项</span><span class="sxs-lookup"><span data-stu-id="84ba9-118">Form2 menu item</span></span>|<span data-ttu-id="84ba9-119">MergeAction 值</span><span class="sxs-lookup"><span data-stu-id="84ba9-119">MergeAction value</span></span>|<span data-ttu-id="84ba9-120">MergeIndex 值</span><span class="sxs-lookup"><span data-stu-id="84ba9-120">MergeIndex value</span></span>|  
    |---------------------|-----------------------|----------------------|  
    |<span data-ttu-id="84ba9-121">文件</span><span class="sxs-lookup"><span data-stu-id="84ba9-121">File</span></span>|<span data-ttu-id="84ba9-122">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="84ba9-122">MatchOnly</span></span>|<span data-ttu-id="84ba9-123">-1</span><span class="sxs-lookup"><span data-stu-id="84ba9-123">-1</span></span>|  
    |<span data-ttu-id="84ba9-124">导入自</span><span class="sxs-lookup"><span data-stu-id="84ba9-124">Import from</span></span>|<span data-ttu-id="84ba9-125">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="84ba9-125">MatchOnly</span></span>|<span data-ttu-id="84ba9-126">-1</span><span class="sxs-lookup"><span data-stu-id="84ba9-126">-1</span></span>|  
    |<span data-ttu-id="84ba9-127">Word</span><span class="sxs-lookup"><span data-stu-id="84ba9-127">Word</span></span>|<span data-ttu-id="84ba9-128">删除</span><span class="sxs-lookup"><span data-stu-id="84ba9-128">Remove</span></span>|<span data-ttu-id="84ba9-129">-1</span><span class="sxs-lookup"><span data-stu-id="84ba9-129">-1</span></span>|  
  
10. <span data-ttu-id="84ba9-130">在中 `Form1` ，为的事件创建一个事件处理程序 <xref:System.Windows.Forms.Control.Click> `&Open` <xref:System.Windows.Forms.ToolStripMenuItem> 。</span><span class="sxs-lookup"><span data-stu-id="84ba9-130">In `Form1`, create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="84ba9-131">在事件处理程序中，插入类似于以下代码示例的代码，以创建和显示的新实例 `Form2` 作为的 MDI 子级 `Form1` ：</span><span class="sxs-lookup"><span data-stu-id="84ba9-131">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`:</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
12. <span data-ttu-id="84ba9-132">将类似于以下示例代码的代码放在 `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> 中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="84ba9-132">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new _  
    System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="84ba9-133">编译代码</span><span class="sxs-lookup"><span data-stu-id="84ba9-133">Compiling the Code</span></span>  
 <span data-ttu-id="84ba9-134">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="84ba9-134">This example requires:</span></span>  
  
- <span data-ttu-id="84ba9-135">名为 `Form1` 和 `Form2` 的两个 <xref:System.Windows.Forms.Form> 控件。</span><span class="sxs-lookup"><span data-stu-id="84ba9-135">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="84ba9-136">`Form1` 上名为 `menuStrip1` 的 <xref:System.Windows.Forms.MenuStrip> 控件和 `Form2` 上名为 `menuStrip2` 的 <xref:System.Windows.Forms.MenuStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="84ba9-136">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="84ba9-137">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="84ba9-137">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84ba9-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84ba9-138">See also</span></span>

- [<span data-ttu-id="84ba9-139">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="84ba9-139">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="84ba9-140">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="84ba9-140">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="84ba9-141">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="84ba9-141">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
