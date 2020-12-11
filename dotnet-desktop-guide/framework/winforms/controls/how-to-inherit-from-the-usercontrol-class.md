---
title: 如何：从 UserControl 类继承
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5c278cfadd1bb0c9720718c08791a37f90d964d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972521"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a><span data-ttu-id="ec53f-102">如何：从 UserControl 类继承</span><span class="sxs-lookup"><span data-stu-id="ec53f-102">How to: Inherit from the UserControl Class</span></span>

<span data-ttu-id="ec53f-103">若要通过自定义代码将一个或多个 Windows 窗体控件的功能进行组合，可以创建一个用户控件。</span><span class="sxs-lookup"><span data-stu-id="ec53f-103">To combine the functionality of one or more Windows Forms controls with custom code, you can create a *user control*.</span></span> <span data-ttu-id="ec53f-104">用户控件将快速控件开发、标准 Windows 窗体控件功能以及自定义属性和方法的多功能组合在一起。</span><span class="sxs-lookup"><span data-stu-id="ec53f-104">User controls combine rapid control development, standard Windows Forms control functionality, and the versatility of custom properties and methods.</span></span> <span data-ttu-id="ec53f-105">开始创建用户控件时，系统将为你提供一个可见的设计器，可以将标准 Windows 窗体控件放置在该设计器中。</span><span class="sxs-lookup"><span data-stu-id="ec53f-105">When you begin creating a user control, you are presented with a visible designer, upon which you can place standard Windows Forms controls.</span></span> <span data-ttu-id="ec53f-106">这些控件保留其所有继承的功能以及标准控件的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="ec53f-106">These controls retain all of their inherent functionality, as well as the appearance and behavior (look and feel) of standard controls.</span></span> <span data-ttu-id="ec53f-107">但是，一旦将这些控件内置到用户控件中，便不能再通过代码来使用。</span><span class="sxs-lookup"><span data-stu-id="ec53f-107">Once these controls are built into the user control, however, they are no longer available to you through code.</span></span> <span data-ttu-id="ec53f-108">用户控件执行其自身的绘图工作，同时也处理与控件相关联的所有基本功能。</span><span class="sxs-lookup"><span data-stu-id="ec53f-108">The user control does its own painting and also handles all of the basic functionality associated with controls.</span></span>

## <a name="to-create-a-user-control"></a><span data-ttu-id="ec53f-109">创建用户控件</span><span class="sxs-lookup"><span data-stu-id="ec53f-109">To create a user control</span></span>

1. <span data-ttu-id="ec53f-110">在 Visual Studio 中创建新的 **Windows 控件库** 项目。</span><span class="sxs-lookup"><span data-stu-id="ec53f-110">Create a new **Windows Control Library** project in Visual Studio.</span></span>

   <span data-ttu-id="ec53f-111">新创建的项目中将包含一个空白用户控件。</span><span class="sxs-lookup"><span data-stu-id="ec53f-111">A new project is created with a blank user control.</span></span>

2. <span data-ttu-id="ec53f-112">将控件从“工具箱”的“Windows 窗体”选项卡中拖到设计器上。</span><span class="sxs-lookup"><span data-stu-id="ec53f-112">Drag controls from the **Windows Forms** tab of the **Toolbox** onto your designer.</span></span>

3. <span data-ttu-id="ec53f-113">应对这些控件进行定位并设计成你希望它们显示在最终用户控件中的样子。</span><span class="sxs-lookup"><span data-stu-id="ec53f-113">These controls should be positioned and designed as you want them to appear in the final user control.</span></span> <span data-ttu-id="ec53f-114">如果要允许开发人员访问构成控件，则必须将这些控件声明为公共的，或有选择地公开构成控件的属性。</span><span class="sxs-lookup"><span data-stu-id="ec53f-114">If you want to allow developers to access the constituent controls, you must declare them as public, or selectively expose properties of the constituent control.</span></span> <span data-ttu-id="ec53f-115">有关详细信息，请参阅[如何：公开构成控件的属性](how-to-expose-properties-of-constituent-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="ec53f-115">For details, see [How to: Expose Properties of Constituent Controls](how-to-expose-properties-of-constituent-controls.md).</span></span>

4. <span data-ttu-id="ec53f-116">实现控件将纳入的任何自定义方法或属性。</span><span class="sxs-lookup"><span data-stu-id="ec53f-116">Implement any custom methods or properties that your control will incorporate.</span></span>

5. <span data-ttu-id="ec53f-117">按 **F5** 生成项目并在 " **UserControl 测试容器**" 中运行控件。</span><span class="sxs-lookup"><span data-stu-id="ec53f-117">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="ec53f-118">有关详细信息，请参阅 [如何：测试 UserControl 的 Run-Time 行为](how-to-test-the-run-time-behavior-of-a-usercontrol.md)。</span><span class="sxs-lookup"><span data-stu-id="ec53f-118">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ec53f-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec53f-119">See also</span></span>

- [<span data-ttu-id="ec53f-120">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="ec53f-120">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="ec53f-121">如何：从 Control 类继承</span><span class="sxs-lookup"><span data-stu-id="ec53f-121">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="ec53f-122">如何：从现有 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="ec53f-122">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="ec53f-123">如何：创作 Windows 窗体的控件</span><span class="sxs-lookup"><span data-stu-id="ec53f-123">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="ec53f-124">排查 Visual Basic 中继承的事件处理程序问题</span><span class="sxs-lookup"><span data-stu-id="ec53f-124">Troubleshoot Inherited Event Handlers in Visual Basic</span></span>](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers)
- [<span data-ttu-id="ec53f-125">如何：测试 UserControl 的运行时行为</span><span class="sxs-lookup"><span data-stu-id="ec53f-125">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
