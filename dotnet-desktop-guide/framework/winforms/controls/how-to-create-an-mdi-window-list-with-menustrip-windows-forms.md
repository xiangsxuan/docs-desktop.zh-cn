---
title: 如何：使用 MenuStrip 创建 MDI 窗口列表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: f013c3df2ab5783a22fe2c34402dc53a328cafa2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971222"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a><span data-ttu-id="933ef-102">如何：使用 MenuStrip 创建 MDI 窗口列表（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="933ef-102">How to: Create an MDI Window List with MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="933ef-103">使用多文档界面 (MDI) 创建可同时打开多个文档的应用程序，并将内容从一个文档复制并粘贴到另一个文档中。</span><span class="sxs-lookup"><span data-stu-id="933ef-103">Use the multiple-document interface (MDI) to create applications that can open several documents at the same time and copy and paste content from one document to the other.</span></span>  
  
 <span data-ttu-id="933ef-104">此过程说明如何在父窗口菜单上创建所有活动子窗体的列表。</span><span class="sxs-lookup"><span data-stu-id="933ef-104">This procedure shows you how to create a list of all the active child forms on the parent's Window menu.</span></span>  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a><span data-ttu-id="933ef-105">在 MenuStrip 上创建 MDI 窗口列表</span><span class="sxs-lookup"><span data-stu-id="933ef-105">To create an MDI Window list on a MenuStrip</span></span>  
  
1. <span data-ttu-id="933ef-106">创建一个窗体并将其 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="933ef-106">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="933ef-107">在窗体上添加一个 <xref:System.Windows.Forms.MenuStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="933ef-107">Add a <xref:System.Windows.Forms.MenuStrip> to the form.</span></span>  
  
3. <span data-ttu-id="933ef-108">向添加两个顶级菜单项 <xref:System.Windows.Forms.MenuStrip> ，并将其 <xref:System.Windows.Forms.Control.Text%2A> 属性设置为 `&File` 和 `&Window` 。</span><span class="sxs-lookup"><span data-stu-id="933ef-108">Add two top-level menu items to the <xref:System.Windows.Forms.MenuStrip> and set their <xref:System.Windows.Forms.Control.Text%2A> properties to `&File` and `&Window`.</span></span>  
  
4. <span data-ttu-id="933ef-109">将子菜单项添加到 `&File` 菜单项，并将其 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 属性设置为 `&Open`。</span><span class="sxs-lookup"><span data-stu-id="933ef-109">Add a submenu item to the `&File` menu item and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&Open`.</span></span>  
  
5. <span data-ttu-id="933ef-110">将 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 的属性设置 <xref:System.Windows.Forms.MenuStrip> 为 `&Window` <xref:System.Windows.Forms.ToolStripMenuItem> 。</span><span class="sxs-lookup"><span data-stu-id="933ef-110">Set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property of the <xref:System.Windows.Forms.MenuStrip> to the `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
6. <span data-ttu-id="933ef-111">向项目中添加一个窗体，并向其添加所需的控件，如另一个 <xref:System.Windows.Forms.MenuStrip> 。</span><span class="sxs-lookup"><span data-stu-id="933ef-111">Add a form to the project and add the control you want to it, such as another <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
7. <span data-ttu-id="933ef-112">为 `&New`<xref:System.Windows.Forms.ToolStripMenuItem> 的 <xref:System.Windows.Forms.Control.Click> 事件创建一个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="933ef-112">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
8. <span data-ttu-id="933ef-113">在事件处理程序中，插入类似于下面的代码，以便创建和显示的新实例 `Form2` 作为的 MDI 子级 `Form1` 。</span><span class="sxs-lookup"><span data-stu-id="933ef-113">Within the event handler, insert code similar to the following to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. <span data-ttu-id="933ef-114">将类似于以下代码的代码放入， `&New` <xref:System.Windows.Forms.ToolStripMenuItem> 以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="933ef-114">Place code like the following in the `&New`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="933ef-115">编译代码</span><span class="sxs-lookup"><span data-stu-id="933ef-115">Compiling the Code</span></span>  
 <span data-ttu-id="933ef-116">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="933ef-116">This example requires:</span></span>  
  
- <span data-ttu-id="933ef-117">名为 `Form1` 和 `Form2` 的两个 <xref:System.Windows.Forms.Form> 控件。</span><span class="sxs-lookup"><span data-stu-id="933ef-117">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="933ef-118">`Form1` 上名为 `menuStrip1` 的 <xref:System.Windows.Forms.MenuStrip> 控件和 `Form2` 上名为 `menuStrip2` 的 <xref:System.Windows.Forms.MenuStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="933ef-118">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="933ef-119">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="933ef-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="933ef-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="933ef-120">See also</span></span>

- [<span data-ttu-id="933ef-121">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="933ef-121">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="933ef-122">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="933ef-122">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="933ef-123">MenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="933ef-123">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
