---
title: 在控件上使用设计器操作执行常见任务
ms.date: 02/13/2019
helpviewer_keywords:
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 342741b9ce032b1b8ec50a6c689d9109d12f5b3b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971767"
---
# <a name="walkthrough-perform-common-tasks-using-designer-actions"></a><span data-ttu-id="c4326-102">演练：使用设计操作执行常规任务</span><span class="sxs-lookup"><span data-stu-id="c4326-102">Walkthrough: Perform common tasks using designer actions</span></span>

<span data-ttu-id="c4326-103">当你为 Windows 窗体应用程序构造窗体和控件时，将重复执行许多任务。</span><span class="sxs-lookup"><span data-stu-id="c4326-103">As you construct forms and controls for your Windows Forms application, there are many tasks you'll perform repeatedly.</span></span> <span data-ttu-id="c4326-104">以下列表显示了你将会遇到的一些常见任务：</span><span class="sxs-lookup"><span data-stu-id="c4326-104">The following list shows some of the commonly performed tasks you'll come across:</span></span>

- <span data-ttu-id="c4326-105">添加或删除上的选项卡 <xref:System.Windows.Forms.TabControl> 。</span><span class="sxs-lookup"><span data-stu-id="c4326-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>
- <span data-ttu-id="c4326-106">将控件停靠到其父控件。</span><span class="sxs-lookup"><span data-stu-id="c4326-106">Docking a control to its parent.</span></span>
- <span data-ttu-id="c4326-107">更改控件的方向 <xref:System.Windows.Forms.SplitContainer> 。</span><span class="sxs-lookup"><span data-stu-id="c4326-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="c4326-108">为了加快开发速度，许多控件都提供设计器操作，这些操作是上下文相关的菜单，可用于在设计时在单个手势中执行类似的任务。</span><span class="sxs-lookup"><span data-stu-id="c4326-108">To speed development, many controls offer designer actions, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="c4326-109">这些任务称为 *设计器操作谓词*。</span><span class="sxs-lookup"><span data-stu-id="c4326-109">These tasks are called *designer actions verbs*.</span></span>

<span data-ttu-id="c4326-110">设计器操作在设计器中保持附加到控件实例的生存期，并且始终可用。</span><span class="sxs-lookup"><span data-stu-id="c4326-110">Designer actions remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="c4326-111">创建项目</span><span class="sxs-lookup"><span data-stu-id="c4326-111">Create the project</span></span>

<span data-ttu-id="c4326-112">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="c4326-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="c4326-113">在 Visual Studio 中，创建一个名为 **DesignerActionsExample** 的基于 Windows 的应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="c4326-113">In Visual Studio, create a Windows-based application project called **DesignerActionsExample**.</span></span>

2. <span data-ttu-id="c4326-114">在 **Windows 窗体设计器** 中选择窗体。</span><span class="sxs-lookup"><span data-stu-id="c4326-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-designer-actions"></a><span data-ttu-id="c4326-115">使用设计器操作</span><span class="sxs-lookup"><span data-stu-id="c4326-115">Use designer actions</span></span>

<span data-ttu-id="c4326-116">设计器操作在提供这些操作的控件上始终可用。</span><span class="sxs-lookup"><span data-stu-id="c4326-116">Designer actions are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="c4326-117">将 <xref:System.Windows.Forms.TabControl> 从 " **工具箱** " 拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="c4326-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="c4326-118">请注意，设计器操作标志符号 (![ 上出现的小黑色箭头 ](./media/designer-actions-glyph.gif)) <xref:System.Windows.Forms.TabControl> 。</span><span class="sxs-lookup"><span data-stu-id="c4326-118">Note the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="c4326-119">单击设计器操作标志符号。</span><span class="sxs-lookup"><span data-stu-id="c4326-119">Click the designer actions glyph.</span></span> <span data-ttu-id="c4326-120">在标志符号旁边显示的快捷菜单中，选择 " **添加" 选项卡** 项。</span><span class="sxs-lookup"><span data-stu-id="c4326-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="c4326-121">请注意，新的选项卡页已添加到中 <xref:System.Windows.Forms.TabControl> 。</span><span class="sxs-lookup"><span data-stu-id="c4326-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="c4326-122">从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="c4326-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="c4326-123">单击设计器操作标志符号。</span><span class="sxs-lookup"><span data-stu-id="c4326-123">Click the designer actions glyph.</span></span> <span data-ttu-id="c4326-124">在出现标志符号旁边的快捷菜单中，选择 " **添加列** " 项。</span><span class="sxs-lookup"><span data-stu-id="c4326-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="c4326-125">请注意，新列已添加到 <xref:System.Windows.Forms.TableLayoutPanel> 控件中。</span><span class="sxs-lookup"><span data-stu-id="c4326-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="c4326-126">从 <xref:System.Windows.Forms.SplitContainer> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="c4326-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="c4326-127">单击设计器操作标志符号。</span><span class="sxs-lookup"><span data-stu-id="c4326-127">Click the designer actions glyph.</span></span> <span data-ttu-id="c4326-128">在标志符号旁边显示的快捷菜单中，选择 " **水平拆分器方向** " 项。</span><span class="sxs-lookup"><span data-stu-id="c4326-128">In the shortcut menu that appears next to the glyph, select the **Horizontal Splitter Orientation** item.</span></span> <span data-ttu-id="c4326-129">观察 <xref:System.Windows.Forms.SplitContainer> 控件的拆分条现在是水平方向的。</span><span class="sxs-lookup"><span data-stu-id="c4326-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4326-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4326-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
