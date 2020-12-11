---
title: 如何：向 ToolStripMenuItem 添加增强功能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- commands [Windows Forms], grouping on menus
- check marks [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], displaying access keys
- menus [Windows Forms], grouping commands
- menu items [Windows Forms], displaying shortcut keys
- ToolStripMenuItems
- separators [Windows Forms], displaying on menus
- menu items [Windows Forms], showing separators
- menu items [Windows Forms], adding check marks
- ToolStripMenuItems [Windows Forms], adding check marks
- menu items [Windows Forms], adding images
- ToolStripSeparators [Windows Forms], displaying on MenuStrips
- menu items [Windows Forms], displaying access keys
- ToolStripMenuItems [Windows Forms], displaying shortcut keys
- ToolStripMenuItems [Windows Forms], adding images
- keyboard shortcuts [Windows Forms], displaying on menus
- images [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], showing separator bars
ms.assetid: aa5f19bb-b545-4378-bfa6-36ba592f0d7c
ms.openlocfilehash: 61a79b9bbe101d7bf694240bdffdecee5187adf2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971910"
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="1b2d2-102">如何：向 ToolStripMenuItem 添加增强功能</span><span class="sxs-lookup"><span data-stu-id="1b2d2-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="1b2d2-103">可以 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> 通过以下方式增强和控制的可用性：</span><span class="sxs-lookup"><span data-stu-id="1b2d2-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
- <span data-ttu-id="1b2d2-104">添加复选标记以指定是否打开或关闭某个功能，例如标尺是否沿字处理应用程序的边距显示，或指示正在显示的文件列表中的哪个文件（如在 **窗口** 菜单上）。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
- <span data-ttu-id="1b2d2-105">添加直观表示菜单命令的图像。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-105">Add images that visually represent menu commands.</span></span>  
  
- <span data-ttu-id="1b2d2-106">显示快捷键以提供用于执行命令的鼠标替代项。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="1b2d2-107">例如，按 CTRL + C 将执行 **复制** 命令。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
- <span data-ttu-id="1b2d2-108">显示 "访问键"，为菜单导航提供鼠标替代方法。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="1b2d2-109">例如，按 ALT + F 会选择 " **文件** " 菜单。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
- <span data-ttu-id="1b2d2-110">显示用于对相关命令进行分组并使菜单更具可读性的分隔条。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="1b2d2-111">在菜单命令中显示复选标记</span><span class="sxs-lookup"><span data-stu-id="1b2d2-111">To display a check mark on a menu command</span></span>  
  
- <span data-ttu-id="1b2d2-112">将其 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="1b2d2-113">这还会将 <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="1b2d2-114">仅当你希望菜单命令显示为 "默认选中" 时才使用此过程，无论是否选择了此选项。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="1b2d2-115">显示每次单击更改状态的复选标记</span><span class="sxs-lookup"><span data-stu-id="1b2d2-115">To display a check mark that changes state with each click</span></span>  
  
- <span data-ttu-id="1b2d2-116">将菜单命令的 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="1b2d2-117">向菜单命令添加图像</span><span class="sxs-lookup"><span data-stu-id="1b2d2-117">To add an image to a menu command</span></span>  
  
- <span data-ttu-id="1b2d2-118">将菜单命令的 <xref:System.Windows.Forms.ToolStripItem.Image%2A> 属性设置为图像的名称。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="1b2d2-119">如果 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 此菜单命令的属性设置为 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> 或 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> ，则无法显示该图像。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b2d2-120">如果选择此选项，图像边距也会显示复选标记。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="1b2d2-121">此外，您还可以将 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 图像的属性设置为 `true` ，并且在运行时，图像将以阴影线边框显示。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="1b2d2-122">显示菜单命令的快捷键</span><span class="sxs-lookup"><span data-stu-id="1b2d2-122">To display a shortcut key for a menu command</span></span>  
  
- <span data-ttu-id="1b2d2-123">将菜单命令的 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> 属性设置为所需的键盘组合，如 " **打开** " 菜单命令的 CTRL + O，并将 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="1b2d2-124">显示菜单命令的自定义快捷键</span><span class="sxs-lookup"><span data-stu-id="1b2d2-124">To display custom shortcut keys for a menu command</span></span>  
  
- <span data-ttu-id="1b2d2-125">将菜单命令的 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> 属性设置为所需的键盘组合，如 CTRL + SHIFT + o 而非 SHIFT + CTRL + o，并将 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="1b2d2-126">显示菜单命令的访问键</span><span class="sxs-lookup"><span data-stu-id="1b2d2-126">To display an access key for a menu command</span></span>  
  
- <span data-ttu-id="1b2d2-127">设置 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 菜单命令的属性时，请在要加下划线的字母前输入与号 ( # A0) 。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="1b2d2-128">例如，键入 `&Open` 作为 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 菜单项的属性将生成一个显示为 " <u>O</u>笔" 的菜单命令。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as <u>O</u>pen.</span></span>
  
     <span data-ttu-id="1b2d2-129">若要导航到此菜单命令，请按 ALT，将焦点置于 <xref:System.Windows.Forms.MenuStrip> ，并按菜单名称的访问键。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="1b2d2-130">当菜单打开并显示带有访问键的项时，只需按 "访问键" 即可选择菜单命令。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b2d2-131">避免定义重复访问键，如在同一菜单系统中定义两次 ALT + F。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="1b2d2-132">无法保证重复访问键的选择顺序。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="1b2d2-133">在菜单命令之间显示分隔条</span><span class="sxs-lookup"><span data-stu-id="1b2d2-133">To display a separator bar between menu commands</span></span>  
  
- <span data-ttu-id="1b2d2-134">定义 <xref:System.Windows.Forms.MenuStrip> 及其所包含的项后，请使用 <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> 或 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 方法，按所需顺序向中添加菜单命令和 <xref:System.Windows.Forms.ToolStripSeparator> 控件 <xref:System.Windows.Forms.MenuStrip> 。</span><span class="sxs-lookup"><span data-stu-id="1b2d2-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
    ```vb  
    ' This code adds a top-level File menu to the MenuStrip.  
    Me.menuStrip1.Items.Add(New ToolStripMenuItem() _  
    {Me.fileToolStripMenuItem})  
  
    ' This code adds the New and Open menu commands, a separator bar,
    ' and the Save and Exit menu commands to the top-level File menu,
    ' in that order.  
    Me.fileToolStripMenuItem.DropDownItems.AddRange(New _  
    ToolStripMenuItem() {Me.newToolStripMenuItem, _  
    Me.openToolStripMenuItem, Me.toolStripSeparator1, _  
    Me.saveToolStripMenuItem, Me.exitToolStripMenuItem})  
    ```  
  
    ```csharp  
    // This code adds a top-level File menu to the MenuStrip.  
    this.menuStrip1.Items.Add(new ToolStripItem[]_  
    {this.fileToolStripMenuItem});  
  
    // This code adds the New and Open menu commands, a separator bar,
    // and the Save and Exit menu commands to the top-level File menu,
    // in that order.  
    this.fileToolStripMenuItem.DropDownItems.AddRange(new _  
    ToolStripItem[] {  
    this.newToolStripMenuItem,  
    this.openToolStripMenuItem,  
    this.toolStripSeparator1,  
    this.saveToolStripMenuItem,  
    this.exitToolStripMenuItem});  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1b2d2-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b2d2-135">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="1b2d2-136">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="1b2d2-136">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
