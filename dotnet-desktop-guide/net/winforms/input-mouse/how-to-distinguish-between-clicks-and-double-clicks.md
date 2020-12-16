---
title: 如何区分单击和双击
description: 介绍用于区分 .NET 的 Windows 窗体的控件或窗体执行单击或双击的不同方式。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse [Windows Forms], click
- mouse [Windows Forms], double-click
- mouse clicks [Windows Forms], single versus double
ms.openlocfilehash: 7b58896a85ffd16ae2637b94d58845ed7a721c4d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941910"
---
# <a name="how-to-distinguish-between-clicks-and-double-clicks-windows-forms-net"></a><span data-ttu-id="b41ad-103">如何区分单击和双击（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="b41ad-103">How to distinguish between clicks and double-clicks (Windows Forms .NET)</span></span>

<span data-ttu-id="b41ad-104">通常情况下，一次单击会启动一个用户界面操作，而一次双击则会扩展该操作 。</span><span class="sxs-lookup"><span data-stu-id="b41ad-104">Typically, a single *click* initiates a user interface action and a *double-click* extends the action.</span></span> <span data-ttu-id="b41ad-105">例如，一次单击通常可选择一个项，而双击则可编辑所选的项。</span><span class="sxs-lookup"><span data-stu-id="b41ad-105">For example, one click usually selects an item, and a double-click edits the selected item.</span></span> <span data-ttu-id="b41ad-106">但是，Windows 窗体 Click 事件无法轻松应用于单击和双击执行多个不兼容操作的方案，因为绑定到 <xref:System.Windows.Forms.Control.Click> 或 <xref:System.Windows.Forms.Control.MouseClick> 事件的操作会在操作绑定到 <xref:System.Windows.Forms.Control.DoubleClick> 或 <xref:System.Windows.Forms.Control.MouseDoubleClick> 事件之前执行。</span><span class="sxs-lookup"><span data-stu-id="b41ad-106">However, the Windows Forms click events do not easily accommodate a scenario where a click and a double-click perform incompatible actions, because an action tied to the <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> event is performed before the action tied to the <xref:System.Windows.Forms.Control.DoubleClick> or <xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span> <span data-ttu-id="b41ad-107">本主题演示此问题的两种解决方案。</span><span class="sxs-lookup"><span data-stu-id="b41ad-107">This topic demonstrates two solutions to this problem.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="b41ad-108">一种解决方案是处理双击事件，并回滚单击事件处理过程中的操作。</span><span class="sxs-lookup"><span data-stu-id="b41ad-108">One solution is to handle the double-click event and roll back the actions in the handling of the click event.</span></span> <span data-ttu-id="b41ad-109">在极少数情况下，可能需要通过处理 <xref:System.Windows.Forms.Control.MouseDown> 事件并使用 <xref:System.Windows.Forms.SystemInformation> 类的 <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> 和 <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> 属性来模拟单击和双击行为。</span><span class="sxs-lookup"><span data-stu-id="b41ad-109">In rare situations you may need to simulate click and double-click behavior by handling the <xref:System.Windows.Forms.Control.MouseDown> event and by using the <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> and <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> properties of the <xref:System.Windows.Forms.SystemInformation> class.</span></span> <span data-ttu-id="b41ad-110">度量点击之间的时间，如果在达到 <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> 值之前发生第二次单击，并且单击发生在由 <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> 定义的矩形范围内，请执行双击操作；否则，请执行单击操作。</span><span class="sxs-lookup"><span data-stu-id="b41ad-110">You measure the time between clicks and if a second click occurs before the value of <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> is reached and the click is within a rectangle defined by <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>, perform the double-click action; otherwise, perform the click action.</span></span>

## <a name="to-roll-back-a-click-action"></a><span data-ttu-id="b41ad-111">回滚单击操作</span><span class="sxs-lookup"><span data-stu-id="b41ad-111">To roll back a click action</span></span>

<span data-ttu-id="b41ad-112">请确保你正在使用的控件具有标准双击行为。</span><span class="sxs-lookup"><span data-stu-id="b41ad-112">Ensure that the control you are working with has standard double-click behavior.</span></span> <span data-ttu-id="b41ad-113">如果不具有标准双击行为，请启用具有 <xref:System.Windows.Forms.Control.SetStyle%2A> 方法的控件。</span><span class="sxs-lookup"><span data-stu-id="b41ad-113">If not, enable the control with the <xref:System.Windows.Forms.Control.SetStyle%2A> method.</span></span> <span data-ttu-id="b41ad-114">处理双击事件，并回滚单击操作以及双击操作。</span><span class="sxs-lookup"><span data-stu-id="b41ad-114">Handle the double-click event and roll back the click action as well as the double-click action.</span></span> <span data-ttu-id="b41ad-115">下面的代码示例演示了如何在启用了双击的情况下创建自定义按钮，以及如何回滚双击事件处理代码中的单击操作。</span><span class="sxs-lookup"><span data-stu-id="b41ad-115">The following code example demonstrates a how to create a custom button with double-click enabled, as well as how to roll back the click action in the double-click event handling code.</span></span>

<span data-ttu-id="b41ad-116">此代码示例使用可启用双击的新按钮控件：</span><span class="sxs-lookup"><span data-stu-id="b41ad-116">This code example uses a new button control that enables double-clicks:</span></span>

:::code language="csharp" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/csharp/DoubleClickButton.cs" id="DoubleClickButton":::
:::code language="vb" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/vb/DoubleClickButton.vb" id="DoubleClickButton":::

<span data-ttu-id="b41ad-117">下面的代码演示了窗体如何通过单击或双击新按钮控件来更改边框样式：</span><span class="sxs-lookup"><span data-stu-id="b41ad-117">The following code demonstrates how a form changes the style of border based on a click or double-click of the new button control:</span></span>

:::code language="csharp" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/csharp/Form1.cs" id="RollbackForm":::
:::code language="vb" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/vb/Form1.vb" id="RollbackForm":::

## <a name="to-distinguish-between-clicks"></a><span data-ttu-id="b41ad-118">区分点击</span><span class="sxs-lookup"><span data-stu-id="b41ad-118">To distinguish between clicks</span></span>

<span data-ttu-id="b41ad-119">请使用 <xref:System.Windows.Forms.SystemInformation> 属性和 <xref:System.Windows.Forms.Timer> 组件来处理 <xref:System.Windows.Forms.Control.MouseDown> 事件和确定点击之间的位置和时间跨度。</span><span class="sxs-lookup"><span data-stu-id="b41ad-119">Handle the <xref:System.Windows.Forms.Control.MouseDown> event and determine the location and time span between clicks using the <xref:System.Windows.Forms.SystemInformation> property and a <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="b41ad-120">根据是否发生单击或双击执行相应的操作。</span><span class="sxs-lookup"><span data-stu-id="b41ad-120">Perform the appropriate action depending on whether a click or double-click takes place.</span></span> <span data-ttu-id="b41ad-121">下面的代码示例演示如何实现这一点。</span><span class="sxs-lookup"><span data-stu-id="b41ad-121">The following code example demonstrates how this can be done.</span></span>

:::code language="csharp" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/csharp/Form2.cs":::
:::code language="vb" source="snippets/how-to-distinguish-between-clicks-and-double-clicks/vb/Form2.vb":::

## <a name="see-also"></a><span data-ttu-id="b41ad-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b41ad-122">See also</span></span>

- [<span data-ttu-id="b41ad-123">使用鼠标的概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="b41ad-123">Overview of using the mouse (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="b41ad-124">使用鼠标事件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="b41ad-124">Using mouse events (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="b41ad-125">管理鼠标指针（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="b41ad-125">Manage mouse pointers (Windows Forms .NET)</span></span>](how-to-manage-cursor-pointer.md)
- [<span data-ttu-id="b41ad-126">如何模拟鼠标事件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="b41ad-126">How to simulate mouse events (Windows Forms .NET)</span></span>](how-to-simulate-events.md)
- <xref:System.Windows.Forms.Control.Click?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.MouseDown?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.SetStyle%2A?displayProperty=nameWithType>
