---
title: 如何：测试 UserControl 的运行时行为
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c619900ea0b7f1b50976fec8d26dd3145dc07693
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972647"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="ef14e-102">如何：测试 UserControl 的运行时行为</span><span class="sxs-lookup"><span data-stu-id="ef14e-102">How to: Test the run-time behavior of a UserControl</span></span>

<span data-ttu-id="ef14e-103">开发时 <xref:System.Windows.Forms.UserControl> ，需要测试其运行时行为。</span><span class="sxs-lookup"><span data-stu-id="ef14e-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="ef14e-104">您可以创建一个单独的基于 Windows 的应用程序项目，并将您的控件置于测试窗体上，但此过程是不方便的。</span><span class="sxs-lookup"><span data-stu-id="ef14e-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="ef14e-105">更快、更简单的方法是使用 Visual Studio 提供的 **UserControl 测试容器** 。</span><span class="sxs-lookup"><span data-stu-id="ef14e-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="ef14e-106">此测试容器直接从 Windows 控件库项目启动。</span><span class="sxs-lookup"><span data-stu-id="ef14e-106">This test container starts directly from your Windows control library project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef14e-107">对于用于加载的测试容器 <xref:System.Windows.Forms.UserControl> ，控件必须至少有一个公共构造函数。</span><span class="sxs-lookup"><span data-stu-id="ef14e-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>
> [!NOTE]
> <span data-ttu-id="ef14e-108">不能使用 **UserControl 测试容器** 测试 Visual C++ 控件。</span><span class="sxs-lookup"><span data-stu-id="ef14e-108">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="ef14e-109">测试 UserControl 的运行时行为</span><span class="sxs-lookup"><span data-stu-id="ef14e-109">Test the run-time behavior of a UserControl</span></span>

1. <span data-ttu-id="ef14e-110">在 Visual Studio 中，创建一个 Windows 控件库项目，并将其命名为 **TestContainerExample**。</span><span class="sxs-lookup"><span data-stu-id="ef14e-110">In Visual Studio, create a Windows control library project, and name it **TestContainerExample**.</span></span>

2. <span data-ttu-id="ef14e-111">在 **Windows 窗体设计器** 中，将 <xref:System.Windows.Forms.Label> 控件从 " **工具箱** " 拖动到控件的设计图面上。</span><span class="sxs-lookup"><span data-stu-id="ef14e-111">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="ef14e-112">按 <kbd>F5</kbd> 生成项目，并运行 " **UserControl 测试容器**"。</span><span class="sxs-lookup"><span data-stu-id="ef14e-112">Press <kbd>F5</kbd> to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="ef14e-113">测试容器显示 <xref:System.Windows.Forms.UserControl> 在 **预览** 窗格中。</span><span class="sxs-lookup"><span data-stu-id="ef14e-113">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="ef14e-114">选择 <xref:System.Windows.Forms.Control.BackColor%2A> 显示在 "预览" <xref:System.Windows.Forms.PropertyGrid> 窗格右侧的控件中的属性。</span><span class="sxs-lookup"><span data-stu-id="ef14e-114">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="ef14e-115">将其值更改为 **ControlDark**。</span><span class="sxs-lookup"><span data-stu-id="ef14e-115">Change its value to **ControlDark**.</span></span> <span data-ttu-id="ef14e-116">观察控件更改为较暗的颜色。</span><span class="sxs-lookup"><span data-stu-id="ef14e-116">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="ef14e-117">尝试更改其他属性值并观察控件上的效果。</span><span class="sxs-lookup"><span data-stu-id="ef14e-117">Try changing other property values and observe the effect on your control.</span></span>

5. <span data-ttu-id="ef14e-118">单击 "**预览**" 窗格下的 "**停靠填充用户控件**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="ef14e-118">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="ef14e-119">请注意，控件调整大小以填充窗格。</span><span class="sxs-lookup"><span data-stu-id="ef14e-119">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="ef14e-120">调整测试容器的大小，并观察控件是否随窗格一起调整大小。</span><span class="sxs-lookup"><span data-stu-id="ef14e-120">Resize the test container and observe that the control is resized with the pane.</span></span>

6. <span data-ttu-id="ef14e-121">关闭测试容器。</span><span class="sxs-lookup"><span data-stu-id="ef14e-121">Close the test container.</span></span>

7. <span data-ttu-id="ef14e-122">向 **TestContainerExample** 项目添加另一个用户控件。</span><span class="sxs-lookup"><span data-stu-id="ef14e-122">Add another user control to the **TestContainerExample** project.</span></span>

8. <span data-ttu-id="ef14e-123">在 **Windows 窗体设计器** 中，将 <xref:System.Windows.Forms.Button> 控件从 " **工具箱** " 拖动到控件的设计图面上。</span><span class="sxs-lookup"><span data-stu-id="ef14e-123">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>

9. <span data-ttu-id="ef14e-124">按 <kbd>F5</kbd> 生成项目并运行测试容器。</span><span class="sxs-lookup"><span data-stu-id="ef14e-124">Press <kbd>F5</kbd> to build the project and run the test container.</span></span>

10. <span data-ttu-id="ef14e-125">单击 " **选择用户控件**" <xref:System.Windows.Forms.ComboBox> 以在两个用户控件之间切换。</span><span class="sxs-lookup"><span data-stu-id="ef14e-125">Click the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>

## <a name="test-user-controls-from-another-project"></a><span data-ttu-id="ef14e-126">测试其他项目中的用户控件</span><span class="sxs-lookup"><span data-stu-id="ef14e-126">Test user controls from another project</span></span>

<span data-ttu-id="ef14e-127">可以在当前项目的测试容器中测试其他项目中的用户控件。</span><span class="sxs-lookup"><span data-stu-id="ef14e-127">You can test user controls from other projects in your current project's test container.</span></span>

1. <span data-ttu-id="ef14e-128">在 Visual Studio 中，创建一个 Windows 控件库项目，并将其命名为 **TestContainerExample2**。</span><span class="sxs-lookup"><span data-stu-id="ef14e-128">In Visual Studio, create a Windows control library project, and name it **TestContainerExample2**.</span></span>

2. <span data-ttu-id="ef14e-129">在 **Windows 窗体设计器** 中，将 <xref:System.Windows.Forms.RadioButton> 控件从 " **工具箱** " 拖动到控件的设计图面上。</span><span class="sxs-lookup"><span data-stu-id="ef14e-129">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="ef14e-130">按 <kbd>F5</kbd> 生成项目并运行测试容器。</span><span class="sxs-lookup"><span data-stu-id="ef14e-130">Press <kbd>F5</kbd> to build the project and run the test container.</span></span> <span data-ttu-id="ef14e-131">测试容器显示 <xref:System.Windows.Forms.UserControl> 在 **预览** 窗格中。</span><span class="sxs-lookup"><span data-stu-id="ef14e-131">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="ef14e-132">单击“**加载**”按钮。</span><span class="sxs-lookup"><span data-stu-id="ef14e-132">Click the **Load** button.</span></span>

5. <span data-ttu-id="ef14e-133">在 " **打开** " 对话框中，导航到在前面的过程中生成的 *TestContainerExample.dll*。</span><span class="sxs-lookup"><span data-stu-id="ef14e-133">In the **Open** dialog box, navigate to *TestContainerExample.dll*, which you built in the previous procedure.</span></span> <span data-ttu-id="ef14e-134">选择 " *TestContainerExample.dll* "，然后单击 " **打开** " 按钮以加载用户控件。</span><span class="sxs-lookup"><span data-stu-id="ef14e-134">Select *TestContainerExample.dll* and click the **Open** button to load the user controls.</span></span>

6. <span data-ttu-id="ef14e-135">使用 " **选择用户" 控件** <xref:System.Windows.Forms.ComboBox> 可以从 **TestContainerExample** 项目中的两个用户控件之间切换。</span><span class="sxs-lookup"><span data-stu-id="ef14e-135">Use the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef14e-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef14e-136">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="ef14e-137">如何：创作复合控件</span><span class="sxs-lookup"><span data-stu-id="ef14e-137">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="ef14e-138">演练：创作复合控件</span><span class="sxs-lookup"><span data-stu-id="ef14e-138">Walkthrough: Authoring a Composite Control</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- <span data-ttu-id="ef14e-139">[用户控件设计器](/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ef14e-139">[User Control Designer](/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
