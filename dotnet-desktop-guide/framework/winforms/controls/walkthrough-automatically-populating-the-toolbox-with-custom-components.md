---
title: 演练：使用自定义组件自动填充工具箱
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 3ceebbf07c0241996479a6f7f72ab19f4cd9aa05
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972588"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="4ee0c-102">演练：使用自定义组件自动填充工具箱</span><span class="sxs-lookup"><span data-stu-id="4ee0c-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>

<span data-ttu-id="4ee0c-103">如果组件由当前打开的解决方案中的项目定义，则它们将自动显示在 " **工具箱**" 中，无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="4ee0c-104">你还可以通过使用 "[选择工具箱项" 对话框 (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))来使用自定义组件手动填充 **工具箱**，但 **工具箱** 会考虑解决方案生成输出中具有以下所有特性的项：</span><span class="sxs-lookup"><span data-stu-id="4ee0c-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>

- <span data-ttu-id="4ee0c-105">实现 <xref:System.ComponentModel.IComponent> ;</span><span class="sxs-lookup"><span data-stu-id="4ee0c-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>

- <span data-ttu-id="4ee0c-106">未 <xref:System.ComponentModel.ToolboxItemAttribute> 将设置为 `false` ;</span><span class="sxs-lookup"><span data-stu-id="4ee0c-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>

- <span data-ttu-id="4ee0c-107">未 <xref:System.ComponentModel.DesignTimeVisibleAttribute> 将设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>

> [!NOTE]
> <span data-ttu-id="4ee0c-108">**工具箱** 不跟踪引用链，因此它不会显示您的解决方案中不是由项目生成的项。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-108">The **Toolbox** does not follow reference chains, so it won't display items that are not built by a project in your solution.</span></span>

<span data-ttu-id="4ee0c-109">此演练演示生成组件后，自定义组件自动出现在 **工具箱** 中的方式。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="4ee0c-110">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="4ee0c-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="4ee0c-111">创建 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-111">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="4ee0c-112">创建自定义组件。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-112">Creating a custom component.</span></span>

- <span data-ttu-id="4ee0c-113">创建自定义组件的实例。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-113">Creating an instance of a custom component.</span></span>

- <span data-ttu-id="4ee0c-114">卸载和重新加载自定义组件。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-114">Unloading and reloading a custom component.</span></span>

<span data-ttu-id="4ee0c-115">完成后，你将看到 " **工具箱** " 中填充了已创建的组件。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="4ee0c-116">创建项目</span><span class="sxs-lookup"><span data-stu-id="4ee0c-116">Create the project</span></span>

1. <span data-ttu-id="4ee0c-117">在 visual Studio 中，创建一个名为 " `ToolboxExample` (**文件**" "  >  **新建**  >  **项目**" "  >  **Visual c #** " 或 **Visual Basic**  >  **经典桌面**  >  **Windows 窗体应用程序**) 的基于 Windows 的应用程序项目</span><span class="sxs-lookup"><span data-stu-id="4ee0c-117">In Visual Studio, create a Windows-based application project called `ToolboxExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="4ee0c-118">向项目中添加新组件。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-118">Add a new component to the project.</span></span> <span data-ttu-id="4ee0c-119">将其命名为 `DemoComponent`。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-119">Call it `DemoComponent`.</span></span>

     <span data-ttu-id="4ee0c-120">有关详细信息，请参阅 [如何：添加新项目项](/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-120">For more information, see [How to: Add New Project Items](/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span>

3. <span data-ttu-id="4ee0c-121">生成项目。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-121">Build the project.</span></span>

4. <span data-ttu-id="4ee0c-122">从 " **工具** " 菜单中，单击 " **选项** " 项。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-122">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="4ee0c-123">单击 " **Windows 窗体设计器**" 项下的 "**常规**"，并确保 " **AutoToolboxPopulate** " 选项设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-123">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>

## <a name="create-an-instance-of-a-custom-component"></a><span data-ttu-id="4ee0c-124">创建自定义组件的实例</span><span class="sxs-lookup"><span data-stu-id="4ee0c-124">Create an instance of a custom component</span></span>

<span data-ttu-id="4ee0c-125">下一步是在窗体上创建自定义组件的实例。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-125">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="4ee0c-126">因为 **工具箱** 会自动为新组件提供帐户，所以这与创建任何其他组件或控件一样简单。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-126">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>

1. <span data-ttu-id="4ee0c-127">在 **窗体设计器** 中打开项目的窗体。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-127">Open the project's form in the **Forms Designer**.</span></span>

2. <span data-ttu-id="4ee0c-128">在 " **工具箱**" 中，单击名为 " **ToolboxExample 组件**" 的新选项卡。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-128">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>

     <span data-ttu-id="4ee0c-129">单击该选项卡后，你将看到 **DemoComponent**。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-129">Once you click the tab, you will see **DemoComponent**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ee0c-130">出于性能原因，" **工具箱** " 的 "自动填充" 区域中的组件不显示自定义位图，并且 <xref:System.Drawing.ToolboxBitmapAttribute> 不受支持。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-130">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="4ee0c-131">若要在 **工具箱** 中显示自定义组件的图标，请使用 " **选择工具箱项** " 对话框加载组件。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-131">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>

3. <span data-ttu-id="4ee0c-132">将组件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-132">Drag your component onto your form.</span></span>

     <span data-ttu-id="4ee0c-133">将创建组件的实例，并将其添加到 **组件栏**。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-133">An instance of the component is created and added to the **Component Tray**.</span></span>

## <a name="unload-and-reload-a-custom-component"></a><span data-ttu-id="4ee0c-134">卸载和重新加载自定义组件</span><span class="sxs-lookup"><span data-stu-id="4ee0c-134">Unload and reload a custom component</span></span>

<span data-ttu-id="4ee0c-135">**工具箱** 会考虑每个加载的项目中的组件，并且在卸载项目时，它将删除对项目的组件的引用。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-135">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>

1. <span data-ttu-id="4ee0c-136">从解决方案中卸载项目。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-136">Unload the project from the solution.</span></span>

     <span data-ttu-id="4ee0c-137">有关卸载项目的详细信息，请参阅 [如何：卸载和重新加载项目](/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-137">For more information about unloading projects, see [How to: Unload and Reload Projects](/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span></span> <span data-ttu-id="4ee0c-138">如果系统提示您保存，请选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-138">If you are prompted to save, choose **Yes**.</span></span>

2. <span data-ttu-id="4ee0c-139">向解决方案中添加一个新的 **Windows 应用程序** 项目。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-139">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="4ee0c-140">在 **设计器** 中打开窗体。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-140">Open the form in the **Designer**.</span></span>

     <span data-ttu-id="4ee0c-141">以前项目中的 " **ToolboxExample 组件** " 选项卡现在已消失。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-141">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>

3. <span data-ttu-id="4ee0c-142">重新加载 `ToolboxExample` 项目。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-142">Reload the `ToolboxExample` project.</span></span>

     <span data-ttu-id="4ee0c-143">" **ToolboxExample 组件** " 选项卡现在再次出现。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-143">The **ToolboxExample Components** tab now reappears.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4ee0c-144">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4ee0c-144">Next steps</span></span>

<span data-ttu-id="4ee0c-145">此演练演示 **工具箱** 会考虑项目的组件，但 **工具箱** 也会考虑控件。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-145">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="4ee0c-146">通过在你的解决方案中添加和移除控件项目，试验你自己的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="4ee0c-146">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ee0c-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ee0c-147">See also</span></span>

- <span data-ttu-id="4ee0c-148">[“选项”对话框 -&gt;“Windows 窗体设计器”-&gt;“常规”](/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4ee0c-148">[General, Windows Forms Designer, Options Dialog Box](/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- <span data-ttu-id="4ee0c-149">[如何：操作工具箱选项卡](/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4ee0c-149">[How to: Manipulate Toolbox Tabs](/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span></span>
- <span data-ttu-id="4ee0c-150">[“选择工具箱项”对话框 (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4ee0c-150">[Choose Toolbox Items Dialog Box (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- [<span data-ttu-id="4ee0c-151">将控件放在 Windows 窗体上</span><span class="sxs-lookup"><span data-stu-id="4ee0c-151">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
