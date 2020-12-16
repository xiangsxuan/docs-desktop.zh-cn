---
title: 如何管理鼠标指针
description: 了解如何在 .NET 的 Windows 窗体中访问、控制和更改鼠标指针。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.openlocfilehash: b4439c34bf7a7f41a94ce5ec5971520d9c82e469
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941972"
---
# <a name="manage-mouse-pointers-windows-forms-net"></a><span data-ttu-id="a69ff-103">管理鼠标指针（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="a69ff-103">Manage mouse pointers (Windows Forms .NET)</span></span>

<span data-ttu-id="a69ff-104">鼠标指针（有时被称为光标）是一个位图，通过鼠标在屏幕上为用户指定一个输入焦点。</span><span class="sxs-lookup"><span data-stu-id="a69ff-104">The mouse *pointer*, which is sometimes referred to as the cursor, is a bitmap that specifies a focus point on the screen for user input with the mouse.</span></span> <span data-ttu-id="a69ff-105">本主题概述了 Windows 窗体中的鼠标指针，并介绍了一些修改和控制鼠标指针的方法。</span><span class="sxs-lookup"><span data-stu-id="a69ff-105">This topic provides an overview of the mouse pointer in Windows Forms and describes some of the ways to modify and control the mouse pointer.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="accessing-the-mouse-pointer"></a><span data-ttu-id="a69ff-106">访问鼠标指针</span><span class="sxs-lookup"><span data-stu-id="a69ff-106">Accessing the mouse pointer</span></span>

<span data-ttu-id="a69ff-107">鼠标指针由 <xref:System.Windows.Forms.Cursor> 类表示，每个 <xref:System.Windows.Forms.Control> 都具有一个 <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> 属性，该属性指定该控件的指针。</span><span class="sxs-lookup"><span data-stu-id="a69ff-107">The mouse pointer is represented by the <xref:System.Windows.Forms.Cursor> class, and each <xref:System.Windows.Forms.Control> has a <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> property that specifies the pointer for that control.</span></span> <span data-ttu-id="a69ff-108"><xref:System.Windows.Forms.Cursor> 类包含描述指针的属性（如 <xref:System.Windows.Forms.Cursor.Position%2A> 和 <xref:System.Windows.Forms.Cursor.HotSpot%2A> 属性）以及可以修改指针外观的方法（如 <xref:System.Windows.Forms.Cursor.Show%2A>、<xref:System.Windows.Forms.Cursor.Hide%2A> 和 <xref:System.Windows.Forms.Cursor.DrawStretched%2A> 方法）。</span><span class="sxs-lookup"><span data-stu-id="a69ff-108">The <xref:System.Windows.Forms.Cursor> class contains properties that describe the pointer, such as the <xref:System.Windows.Forms.Cursor.Position%2A> and <xref:System.Windows.Forms.Cursor.HotSpot%2A> properties, and methods that can modify the appearance of the pointer, such as the <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>, and <xref:System.Windows.Forms.Cursor.DrawStretched%2A> methods.</span></span>

<span data-ttu-id="a69ff-109">在下面的示例中，会在光标悬停在按钮上时隐藏光标：</span><span class="sxs-lookup"><span data-stu-id="a69ff-109">The following example hides the cursor when the cursor is over a button:</span></span>

:::code language="csharp" source="snippets/how-to-manage-cursor-pointer/csharp/Form1.cs" id="ShowHideCursor":::
:::code language="vb" source="snippets/how-to-manage-cursor-pointer/vb/Form1.vb" id="ShowHideCursor":::

## <a name="controlling-the-mouse-pointer"></a><span data-ttu-id="a69ff-110">控制鼠标指针</span><span class="sxs-lookup"><span data-stu-id="a69ff-110">Controlling the mouse pointer</span></span>

<span data-ttu-id="a69ff-111">有时，你可能想要限制可以使用鼠标指针的区域或更改鼠标的位置。</span><span class="sxs-lookup"><span data-stu-id="a69ff-111">Sometimes you may want to limit the area in which the mouse pointer can be used or change the position the mouse.</span></span> <span data-ttu-id="a69ff-112">可以使用 <xref:System.Windows.Forms.Cursor> 的 <xref:System.Windows.Forms.Cursor.Position%2A> 属性获取或设置鼠标的当前位置。</span><span class="sxs-lookup"><span data-stu-id="a69ff-112">You can get or set the current location of the mouse using the <xref:System.Windows.Forms.Cursor.Position%2A> property of the <xref:System.Windows.Forms.Cursor>.</span></span> <span data-ttu-id="a69ff-113">此外，可以通过设置 <xref:System.Windows.Forms.Cursor.Clip%2A> 属性来限制可以使用鼠标指针的区域。</span><span class="sxs-lookup"><span data-stu-id="a69ff-113">In addition, you can limit the area the mouse pointer can be used be setting the <xref:System.Windows.Forms.Cursor.Clip%2A> property.</span></span> <span data-ttu-id="a69ff-114">默认情况下，剪辑区域是整个屏幕。</span><span class="sxs-lookup"><span data-stu-id="a69ff-114">The clip area, by default, is the entire screen.</span></span>

<span data-ttu-id="a69ff-115">在下面的示例中，会在单击两个按钮时将鼠标指针放置在这两个按钮之间：</span><span class="sxs-lookup"><span data-stu-id="a69ff-115">The following example positions the mouse pointer between two buttons when they are clicked:</span></span>

:::code language="csharp" source="snippets/how-to-manage-cursor-pointer/csharp/Form1.cs" id="MoveCursor":::
:::code language="vb" source="snippets/how-to-manage-cursor-pointer/vb/Form1.vb" id="MoveCursor":::

## <a name="changing-the-mouse-pointer"></a><span data-ttu-id="a69ff-116">更改鼠标指针</span><span class="sxs-lookup"><span data-stu-id="a69ff-116">Changing the mouse pointer</span></span>

<span data-ttu-id="a69ff-117">更改鼠标指针是向用户提供反馈的重要方式。</span><span class="sxs-lookup"><span data-stu-id="a69ff-117">Changing the mouse pointer is an important way of providing feedback to the user.</span></span> <span data-ttu-id="a69ff-118">例如，可以在 <xref:System.Windows.Forms.Control.MouseEnter> 和 <xref:System.Windows.Forms.Control.MouseLeave> 事件的处理程序中修改鼠标指针，以告知用户正在进行计算并限制控件中的用户交互。</span><span class="sxs-lookup"><span data-stu-id="a69ff-118">For example, the mouse pointer can be modified in the handlers of the <xref:System.Windows.Forms.Control.MouseEnter> and <xref:System.Windows.Forms.Control.MouseLeave> events to tell the user that computations are occurring and to limit user interaction in the control.</span></span> <span data-ttu-id="a69ff-119">有时，鼠标指针会因系统事件而发生变化，例如当应用程序涉及拖放操作时。</span><span class="sxs-lookup"><span data-stu-id="a69ff-119">Sometimes, the mouse pointer will change because of system events, such as when your application is involved in a drag-and-drop operation.</span></span>

<span data-ttu-id="a69ff-120">更改鼠标指针的主要方式是将控件的 <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> 或 <xref:System.Windows.Forms.Control.DefaultCursor%2A> 属性设置为新的 <xref:System.Windows.Forms.Cursor>。</span><span class="sxs-lookup"><span data-stu-id="a69ff-120">The primary way to change the mouse pointer is by setting the <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.Control.DefaultCursor%2A> property of a control to a new <xref:System.Windows.Forms.Cursor>.</span></span> <span data-ttu-id="a69ff-121">有关更改鼠标指针的示例，请参阅 <xref:System.Windows.Forms.Cursor> 类中的代码示例。</span><span class="sxs-lookup"><span data-stu-id="a69ff-121">For examples of changing the mouse pointer, see the code example in the <xref:System.Windows.Forms.Cursor> class.</span></span> <span data-ttu-id="a69ff-122">此外，<xref:System.Windows.Forms.Cursors> 类公开了许多不同类型的指针（如手形指针）的一组 <xref:System.Windows.Forms.Cursor> 对象。</span><span class="sxs-lookup"><span data-stu-id="a69ff-122">In addition, the <xref:System.Windows.Forms.Cursors> class exposes a set of <xref:System.Windows.Forms.Cursor> objects for many different types of pointers, such as a pointer that resembles a hand.</span></span>

<span data-ttu-id="a69ff-123">下面的示例将按钮的鼠标指针的光标更改为手形形状：</span><span class="sxs-lookup"><span data-stu-id="a69ff-123">The following example changes the cursor of the mouse pointer for a button to a hand:</span></span>

:::code language="csharp" source="snippets/how-to-manage-cursor-pointer/csharp/Form1.cs" id="SetControlCursor":::
:::code language="vb" source="snippets/how-to-manage-cursor-pointer/vb/Form1.vb" id="SetControlCursor":::

<span data-ttu-id="a69ff-124">若要在鼠标指针位于控件上方时显示等待指针（沙漏状），请使用 <xref:System.Windows.Forms.Control> 类的 <xref:System.Windows.Forms.Control.UseWaitCursor%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="a69ff-124">To display the wait pointer, which resembles an hourglass, whenever the mouse pointer is on the control, use the <xref:System.Windows.Forms.Control.UseWaitCursor%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="a69ff-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a69ff-125">See also</span></span>

- [<span data-ttu-id="a69ff-126">使用鼠标的概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="a69ff-126">Overview of using the mouse (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="a69ff-127">使用鼠标事件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="a69ff-127">Using mouse events (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="a69ff-128">如何区分单击和双击（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="a69ff-128">How to distinguish between clicks and double-clicks (Windows Forms .NET)</span></span>](how-to-distinguish-between-clicks-and-double-clicks.md)
- [<span data-ttu-id="a69ff-129">如何模拟鼠标事件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="a69ff-129">How to simulate mouse events (Windows Forms .NET)</span></span>](how-to-simulate-events.md)
- <xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>
