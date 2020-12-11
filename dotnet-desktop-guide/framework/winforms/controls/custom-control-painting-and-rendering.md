---
title: 自定义控件的绘制和呈现
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: 14abac5678bfffa3cdb61307fd3cb54681c82a99
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970152"
---
# <a name="custom-control-painting-and-rendering"></a><span data-ttu-id="e4761-102">自定义控件的绘制和呈现</span><span class="sxs-lookup"><span data-stu-id="e4761-102">Custom Control Painting and Rendering</span></span>
<span data-ttu-id="e4761-103">控件的自定义绘制是 .NET Framework 容易实现的众多复杂任务之一。</span><span class="sxs-lookup"><span data-stu-id="e4761-103">Custom painting of controls is one of the many complicated tasks made easy by the .NET Framework.</span></span> <span data-ttu-id="e4761-104">创作自定义控件时，有许多有关控件图形外观的选项。</span><span class="sxs-lookup"><span data-stu-id="e4761-104">When authoring a custom control, you have many options regarding your control's graphical appearance.</span></span> <span data-ttu-id="e4761-105">如果要创作从继承的控件 `Control` ，则必须提供使控件呈现其图形表示形式的代码。</span><span class="sxs-lookup"><span data-stu-id="e4761-105">If you are authoring a control that inherits from the `Control`, you must provide code that allows your control to render its graphical representation.</span></span> <span data-ttu-id="e4761-106">如果要通过从继承 `UserControl` ，或从某个 Windows 窗体控件继承来创建用户控件，则可以重写标准图形表示形式，并提供您自己的图形代码。</span><span class="sxs-lookup"><span data-stu-id="e4761-106">If you are creating a user control by inheriting from the `UserControl`, or are inheriting from one of the Windows Forms controls, you may override the standard graphical representation and provide your own graphics code.</span></span> <span data-ttu-id="e4761-107">如果要为创作控件提供自定义呈现 `UserControl` ，则选项会变得更有限，但仍允许控件和应用程序的各种图形化可能性。</span><span class="sxs-lookup"><span data-stu-id="e4761-107">If you want to provide custom rendering for the constituent controls of a `UserControl` you are authoring, your options become more limited, but still allow a wide range of graphical possibilities for your controls and applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e4761-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="e4761-108">In This Section</span></span>  
 [<span data-ttu-id="e4761-109">呈现 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="e4761-109">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)  
 <span data-ttu-id="e4761-110">演示如何对显示控件的逻辑进行编程。</span><span class="sxs-lookup"><span data-stu-id="e4761-110">Shows how to program the logic that displays a control.</span></span>  
  
 [<span data-ttu-id="e4761-111">用户描述的控件</span><span class="sxs-lookup"><span data-stu-id="e4761-111">User-Drawn Controls</span></span>](user-drawn-controls.md)  
 <span data-ttu-id="e4761-112">概述编写和重写控件的呈现代码所涉及的步骤。</span><span class="sxs-lookup"><span data-stu-id="e4761-112">Gives an overview of the steps involved in writing and overriding rendering code for your control.</span></span>  
  
 [<span data-ttu-id="e4761-113">构成控件</span><span class="sxs-lookup"><span data-stu-id="e4761-113">Constituent Controls</span></span>](constituent-controls.md)  
 <span data-ttu-id="e4761-114">介绍如何实现用户控件和窗体中构成控件的自定义呈现代码。</span><span class="sxs-lookup"><span data-stu-id="e4761-114">Describes how to implement custom rendering code for constituent controls in your user controls and forms.</span></span>  
  
 [<span data-ttu-id="e4761-115">如何：使控件在运行时不可见</span><span class="sxs-lookup"><span data-stu-id="e4761-115">How to: Make Your Control Invisible at Run Time</span></span>](how-to-make-your-control-invisible-at-run-time.md)  
 <span data-ttu-id="e4761-116">演示如何使用 <xref:System.Windows.Forms.Control.Visible%2A> 属性隐藏和显示控件。</span><span class="sxs-lookup"><span data-stu-id="e4761-116">Shows how to use the <xref:System.Windows.Forms.Control.Visible%2A> property to hide and show a control.</span></span>  
  
 [<span data-ttu-id="e4761-117">如何：使控件拥有透明背景</span><span class="sxs-lookup"><span data-stu-id="e4761-117">How to: Give Your Control a Transparent Background</span></span>](how-to-give-your-control-a-transparent-background.md)  
 <span data-ttu-id="e4761-118">演示如何使用 <xref:System.Windows.Forms.Control.SetStyle%2A> 方法创建不透明、透明或部分透明的背景色。</span><span class="sxs-lookup"><span data-stu-id="e4761-118">Shows how to use the <xref:System.Windows.Forms.Control.SetStyle%2A> method to create a background color that is opaque, transparent, or partially transparent.</span></span>  
  
 [<span data-ttu-id="e4761-119">使用视觉样式呈现控件</span><span class="sxs-lookup"><span data-stu-id="e4761-119">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)  
 <span data-ttu-id="e4761-120">演示如何在支持视觉样式的操作系统中使用视觉样式呈现控件。</span><span class="sxs-lookup"><span data-stu-id="e4761-120">Shows how to render controls using visual styles in operating systems that support them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e4761-121">参考</span><span class="sxs-lookup"><span data-stu-id="e4761-121">Reference</span></span>  
 <xref:System.Windows.Forms.Control>  
 <span data-ttu-id="e4761-122">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="e4761-122">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="e4761-123">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="e4761-123">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <span data-ttu-id="e4761-124">描述此方法。</span><span class="sxs-lookup"><span data-stu-id="e4761-124">Describes this method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e4761-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="e4761-125">Related Sections</span></span>  
 [<span data-ttu-id="e4761-126">如何：创建用于绘制的 Graphics 对象</span><span class="sxs-lookup"><span data-stu-id="e4761-126">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)  
 <span data-ttu-id="e4761-127">介绍 Visual Studio 中的 GDI + 图形功能，并提供指向详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="e4761-127">Introduces GDI+ graphics functionality from a Visual Studio perspective and gives links to more information.</span></span>  
  
 [<span data-ttu-id="e4761-128">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="e4761-128">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)  
 <span data-ttu-id="e4761-129">介绍可以创作的自定义控件类型。</span><span class="sxs-lookup"><span data-stu-id="e4761-129">Describes the kinds of custom controls you can author.</span></span>
