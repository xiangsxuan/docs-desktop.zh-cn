---
title: 使用控件的概述
description: 了解如何在 .NET 的 Windows 窗体中使用控件。 控件是为用户提供功能的可重用的组件。 提供了许多现成的控件。 还可以创建新的控件。
ms.date: 10/26/2020
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, controls
- controls [Windows Forms]
- custom controls [Windows Forms]
ms.openlocfilehash: 7476ce47a1767a2ab13c25a7408f5861014e7de8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941991"
---
# <a name="overview-of-using-controls-windows-forms-net"></a><span data-ttu-id="6e6c1-106">使用控件的概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="6e6c1-106">Overview of using controls (Windows Forms .NET)</span></span>

<span data-ttu-id="6e6c1-107">Windows 窗体控件是可重用的组件，可以封装用户界面功能并用于基于 Windows 的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-107">Windows Forms controls are reusable components that encapsulate user interface functionality and are used in client-side, Windows-based applications.</span></span> <span data-ttu-id="6e6c1-108">Windows 窗体不仅可以提供许多易用的控件，而且还可以提供用于开发你自己的控件的基础结构。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-108">Not only does Windows Forms provide many ready-to-use controls, it also provides the infrastructure for developing your own controls.</span></span> <span data-ttu-id="6e6c1-109">你可以组合现有的控件、扩展现有的控件或创作你自己的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-109">You can combine existing controls, extend existing controls, or author your own custom controls.</span></span> <span data-ttu-id="6e6c1-110">有关详细信息，请参阅[自定义控件的类型](custom.md)。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-110">For more information, see [Types of custom controls](custom.md).</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="adding-controls"></a><span data-ttu-id="6e6c1-111">添加控件</span><span class="sxs-lookup"><span data-stu-id="6e6c1-111">Adding controls</span></span>

<span data-ttu-id="6e6c1-112">控件是通过 Visual Studio 设计器添加的。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-112">Controls are added through the Visual Studio Designer.</span></span> <span data-ttu-id="6e6c1-113">利用设计器，可以放置、对齐和移动控件并调整其大小。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-113">With the Designer, you can place, size, align, and move controls.</span></span> <span data-ttu-id="6e6c1-114">也可通过代码添加控件。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-114">Alternatively, controls can be added through code.</span></span> <span data-ttu-id="6e6c1-115">有关详细信息，请参阅[添加控件（Windows 窗体）](how-to-add-to-a-form.md)。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-115">For more information, see [Add a control (Windows Forms)](how-to-add-to-a-form.md).</span></span>

## <a name="layout-options"></a><span data-ttu-id="6e6c1-116">布局选项</span><span class="sxs-lookup"><span data-stu-id="6e6c1-116">Layout options</span></span>

<span data-ttu-id="6e6c1-117">控件在父级上的位置由父级表面左上角的 <xref:System.Windows.Forms.Control.Location> 属性的值确定。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-117">The position a control appears on a parent is determined by the value of the <xref:System.Windows.Forms.Control.Location> property relative to the top-left of the parent surface.</span></span> <span data-ttu-id="6e6c1-118">父级中左上角的位置坐标为 `(x0,y0)`。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-118">The top-left position coordinate in the parent is `(x0,y0)`.</span></span> <span data-ttu-id="6e6c1-119">控件的大小由 <xref:System.Windows.Forms.Control.Size> 属性确定，表示控件的宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-119">The size of the control is determined by the <xref:System.Windows.Forms.Control.Size> property and represents the width and height of the control.</span></span>

<span data-ttu-id="6e6c1-120">除了手动定位和调整大小，还提供各种容器控件来帮助自动放置控件。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-120">Besides manual positioning and sizing, various container controls are provided that help with automatic placement of controls.</span></span>

<span data-ttu-id="6e6c1-121">有关详细信息，请参阅[控件的位置和布局](layout.md)。</span><span class="sxs-lookup"><span data-stu-id="6e6c1-121">For more information, see [Position and layout of controls](layout.md).</span></span>
<!-- TODO

## Control events

-->

## <a name="see-also"></a><span data-ttu-id="6e6c1-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e6c1-122">See also</span></span>

- [<span data-ttu-id="6e6c1-123">控件的位置和布局</span><span class="sxs-lookup"><span data-stu-id="6e6c1-123">Position and layout of controls</span></span>](layout.md)
- [<span data-ttu-id="6e6c1-124">Label 控件概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="6e6c1-124">Label control overview (Windows Forms .NET)</span></span>](labels.md)
- [<span data-ttu-id="6e6c1-125">添加控件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="6e6c1-125">Add a control (Windows Forms .NET)</span></span>](how-to-add-to-a-form.md)
