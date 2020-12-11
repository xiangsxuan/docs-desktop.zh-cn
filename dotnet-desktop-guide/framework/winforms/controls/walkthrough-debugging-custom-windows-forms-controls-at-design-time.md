---
title: 在设计时调试自定义控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d9e292a1219c24571bcb35db2fe357b0197c8812
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972506"
---
# <a name="walkthrough-debug-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="ba524-102">演练：在设计时调试自定义 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="ba524-102">Walkthrough: Debug Custom Windows Forms Controls at Design Time</span></span>

<span data-ttu-id="ba524-103">当您创建自定义控件时，您通常会发现有必要调试其设计时行为。</span><span class="sxs-lookup"><span data-stu-id="ba524-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="ba524-104">如果要为自定义控件创作自定义设计器，则这一点尤其如此。</span><span class="sxs-lookup"><span data-stu-id="ba524-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="ba524-105">有关详细信息，请参阅 [演练：创建利用 Visual Studio Design-Time 功能的 Windows 窗体控件](creating-a-wf-control-design-time-features.md)。</span><span class="sxs-lookup"><span data-stu-id="ba524-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

<span data-ttu-id="ba524-106">您可以使用 Visual Studio 调试自定义控件，就像调试任何其他 .NET Framework 类一样。</span><span class="sxs-lookup"><span data-stu-id="ba524-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="ba524-107">不同之处在于，您将调试运行您的自定义控件的代码的单独的 Visual Studio 实例。</span><span class="sxs-lookup"><span data-stu-id="ba524-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="ba524-108">创建项目</span><span class="sxs-lookup"><span data-stu-id="ba524-108">Create the project</span></span>

<span data-ttu-id="ba524-109">第一步是创建应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="ba524-109">The first step is to create the application project.</span></span> <span data-ttu-id="ba524-110">将使用此项目生成承载自定义控件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ba524-110">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="ba524-111">在 Visual Studio 中，创建一个 Windows 应用程序项目，并将其命名为 **DebuggingExample**。</span><span class="sxs-lookup"><span data-stu-id="ba524-111">In Visual Studio, create a Windows Application project, and name it **DebuggingExample**.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="ba524-112">创建控件库项目</span><span class="sxs-lookup"><span data-stu-id="ba524-112">Create the control library project</span></span>

1. <span data-ttu-id="ba524-113">将 **Windows 控件库** 项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="ba524-113">Add a **Windows Control Library** project to the solution.</span></span>

2. <span data-ttu-id="ba524-114">向 DebugControlLibrary 项目添加一个新的 **UserControl** 项。</span><span class="sxs-lookup"><span data-stu-id="ba524-114">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="ba524-115">将其命名为 **DebugControl**。</span><span class="sxs-lookup"><span data-stu-id="ba524-115">Name it **DebugControl**.</span></span>

3. <span data-ttu-id="ba524-116">在 **解决方案资源管理器** 中，通过删除基名称为 UserControl1 的代码文件删除项目的默认控件。</span><span class="sxs-lookup"><span data-stu-id="ba524-116">In **Solution Explorer**, delete the project's default control by deleting the code file with a base name of UserControl1.</span></span>

4. <span data-ttu-id="ba524-117">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="ba524-117">Build the solution.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="ba524-118">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="ba524-118">Checkpoint</span></span>

<span data-ttu-id="ba524-119">此时，您将能够在 **工具箱** 中看到您的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="ba524-119">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="ba524-120">若要检查进度，请找到名为 **DebugControlLibrary** 的新选项卡，并单击以将其选中。</span><span class="sxs-lookup"><span data-stu-id="ba524-120">To check your progress, find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="ba524-121">当它打开时，你将看到控件作为 **DebugControl** 列出，其旁边显示了默认图标。</span><span class="sxs-lookup"><span data-stu-id="ba524-121">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>

## <a name="add-a-property-to-your-custom-control"></a><span data-ttu-id="ba524-122">向自定义控件添加属性</span><span class="sxs-lookup"><span data-stu-id="ba524-122">Add a property to your custom control</span></span>

<span data-ttu-id="ba524-123">为了演示自定义控件的代码在设计时运行，您将添加一个属性并在实现属性的代码中设置断点。</span><span class="sxs-lookup"><span data-stu-id="ba524-123">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>

1. <span data-ttu-id="ba524-124">在 **代码编辑器** 中打开 **DebugControl** 。</span><span class="sxs-lookup"><span data-stu-id="ba524-124">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="ba524-125">在类定义中添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="ba524-125">Add the following code to the class definition:</span></span>

    ```vb
    Private demoStringValue As String = Nothing
    <BrowsableAttribute(true)>
    Public Property DemoString() As String

        Get
            Return Me.demoStringValue
        End Get

        Set(ByVal value As String)
            Me.demoStringValue = value
        End Set

    End Property
    ```

    ```csharp
    private string demoStringValue = null;
    [Browsable(true)]
    public string DemoString
    {
        get
        {
            return this.demoStringValue;
        }
        set
        {
            demoStringValue = value;
        }
    }
    ```

2. <span data-ttu-id="ba524-126">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="ba524-126">Build the solution.</span></span>

## <a name="add-your-custom-control-to-the-host-form"></a><span data-ttu-id="ba524-127">向宿主窗体添加自定义控件</span><span class="sxs-lookup"><span data-stu-id="ba524-127">Add your custom control to the host form</span></span>

<span data-ttu-id="ba524-128">若要调试自定义控件的设计时行为，你需要将自定义控件类的实例放置在主机窗体上。</span><span class="sxs-lookup"><span data-stu-id="ba524-128">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>

1. <span data-ttu-id="ba524-129">在 "DebuggingExample" 项目中，在 **Windows 窗体设计器** 中打开 "Form1"。</span><span class="sxs-lookup"><span data-stu-id="ba524-129">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>

2. <span data-ttu-id="ba524-130">在 " **工具箱**" 中，打开 " **DebugControlLibrary 组件** " 选项卡，并将 " **DebugControl** " 实例拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="ba524-130">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>

3. <span data-ttu-id="ba524-131">`DemoString`在 "**属性**" 窗口中查找自定义属性。</span><span class="sxs-lookup"><span data-stu-id="ba524-131">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="ba524-132">请注意，您可以像更改任何其他属性一样更改其值。</span><span class="sxs-lookup"><span data-stu-id="ba524-132">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="ba524-133">另请注意，在 `DemoString` 选择属性后，属性的说明字符串会出现在 " **属性** " 窗口的底部。</span><span class="sxs-lookup"><span data-stu-id="ba524-133">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="ba524-134">设置项目以进行设计时调试</span><span class="sxs-lookup"><span data-stu-id="ba524-134">Set up the project for design-time debugging</span></span>

<span data-ttu-id="ba524-135">若要调试自定义控件的设计时行为，您将调试运行您的自定义控件的代码的单独的 Visual Studio 实例。</span><span class="sxs-lookup"><span data-stu-id="ba524-135">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

1. <span data-ttu-id="ba524-136">右键单击 "**解决方案资源管理器** 中的 **DebugControlLibrary** 项目，然后选择"**属性**"。</span><span class="sxs-lookup"><span data-stu-id="ba524-136">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="ba524-137">在 **DebugControlLibrary** 属性表中，选择 " **调试** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="ba524-137">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>

     <span data-ttu-id="ba524-138">在 " **启动操作** " 部分中，选择 " **启动外部程序**"。</span><span class="sxs-lookup"><span data-stu-id="ba524-138">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="ba524-139">你将调试一个单独的 Visual Studio 实例，因此单击 " ![ visual) studio 的属性窗口中的省略号按钮 ( ... ) " ("， ](./media/visual-studio-ellipsis-button.png) 以浏览 VISUAL studio IDE。</span><span class="sxs-lookup"><span data-stu-id="ba524-139">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="ba524-140">可执行文件的名称是 **devenv.exe** 的，如果你已安装到默认位置，则其路径为 *% ProgramFiles (x86) % \ Microsoft Visual Studio\2019 \\ \<edition> \Common7\IDE*。</span><span class="sxs-lookup"><span data-stu-id="ba524-140">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\\\<edition>\Common7\IDE*.</span></span>

3. <span data-ttu-id="ba524-141">选择“确定”关闭对话框  。</span><span class="sxs-lookup"><span data-stu-id="ba524-141">Select **OK** to close the dialog box.</span></span>

4. <span data-ttu-id="ba524-142">右键单击 " **DebugControlLibrary** " 项目，然后选择 " **设为启动项目** " 来启用此调试配置。</span><span class="sxs-lookup"><span data-stu-id="ba524-142">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="debug-your-custom-control-at-design-time"></a><span data-ttu-id="ba524-143">在设计时调试自定义控件</span><span class="sxs-lookup"><span data-stu-id="ba524-143">Debug your custom control at design time</span></span>

<span data-ttu-id="ba524-144">现在，你已准备好调试自定义控件，因为它在设计模式下运行。</span><span class="sxs-lookup"><span data-stu-id="ba524-144">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="ba524-145">当你启动调试会话时，将创建一个新的 Visual Studio 实例，你将使用它来加载 "DebuggingExample" 解决方案。</span><span class="sxs-lookup"><span data-stu-id="ba524-145">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="ba524-146">在 **窗体设计器** 中打开 Form1 时，将创建自定义控件的一个实例，并将开始运行。</span><span class="sxs-lookup"><span data-stu-id="ba524-146">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>

1. <span data-ttu-id="ba524-147">在 **代码编辑器** 中打开 **DebugControl** 源文件，并在属性的访问器上放置一个断点 `Set` `DemoString` 。</span><span class="sxs-lookup"><span data-stu-id="ba524-147">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>

2. <span data-ttu-id="ba524-148">按 **F5** 启动调试会话。</span><span class="sxs-lookup"><span data-stu-id="ba524-148">Press **F5** to start the debugging session.</span></span> <span data-ttu-id="ba524-149">创建 Visual Studio 的新实例。</span><span class="sxs-lookup"><span data-stu-id="ba524-149">A new instance of Visual Studio is created.</span></span> <span data-ttu-id="ba524-150">可以通过两种方式区分实例：</span><span class="sxs-lookup"><span data-stu-id="ba524-150">You can distinguish between the instances in two ways:</span></span>

    - <span data-ttu-id="ba524-151">调试实例的标题栏中有一个 **运行** 的词</span><span class="sxs-lookup"><span data-stu-id="ba524-151">The debugging instance has the word **Running** in its title bar</span></span>

    - <span data-ttu-id="ba524-152">调试实例禁用了其 **调试** 工具栏上的 "**启动**" 按钮</span><span class="sxs-lookup"><span data-stu-id="ba524-152">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>

   <span data-ttu-id="ba524-153">在调试实例中设置断点。</span><span class="sxs-lookup"><span data-stu-id="ba524-153">Your breakpoint is set in the debugging instance.</span></span>

3. <span data-ttu-id="ba524-154">在 Visual Studio 的新实例中，打开 "DebuggingExample" 解决方案。</span><span class="sxs-lookup"><span data-stu-id="ba524-154">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="ba524-155">通过从 "**文件**" 菜单中选择 "**最近使用的项目**"，可以轻松地找到解决方案。</span><span class="sxs-lookup"><span data-stu-id="ba524-155">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="ba524-156">"DebuggingExample" 解决方案文件将作为最近使用过的文件列出。</span><span class="sxs-lookup"><span data-stu-id="ba524-156">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="ba524-157">在 **窗体设计器** 中打开 "Form1"，然后选择 " **DebugControl** " 控件。</span><span class="sxs-lookup"><span data-stu-id="ba524-157">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>

5. <span data-ttu-id="ba524-158">更改 `DemoString` 属性的值。</span><span class="sxs-lookup"><span data-stu-id="ba524-158">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="ba524-159">提交更改时，Visual Studio 的调试实例将获取焦点，并在断点处停止执行。</span><span class="sxs-lookup"><span data-stu-id="ba524-159">When you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="ba524-160">您可以单步执行属性访问器，就像对待任何其他代码一样。</span><span class="sxs-lookup"><span data-stu-id="ba524-160">You can single-step through the property accessor just as your would any other code.</span></span>

6. <span data-ttu-id="ba524-161">若要停止调试，请退出 Visual Studio 的托管实例，或在调试实例中选择 " **停止调试** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="ba524-161">To stop debugging, exit the hosted instance of Visual Studio or select the **Stop Debugging** button in the debugging instance.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ba524-162">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ba524-162">Next steps</span></span>

<span data-ttu-id="ba524-163">现在你可以在设计时调试自定义控件，因此可以通过许多方式来扩展控件与 Visual Studio IDE 的交互。</span><span class="sxs-lookup"><span data-stu-id="ba524-163">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>

- <span data-ttu-id="ba524-164">您可以使用 <xref:System.ComponentModel.Component.DesignMode%2A> 类的属性 <xref:System.ComponentModel.Component> 来编写仅在设计时执行的代码。</span><span class="sxs-lookup"><span data-stu-id="ba524-164">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="ba524-165">有关详细信息，请参阅 <xref:System.ComponentModel.Component.DesignMode%2A>。</span><span class="sxs-lookup"><span data-stu-id="ba524-165">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>

- <span data-ttu-id="ba524-166">可以将多个属性应用于控件的属性，以操作自定义控件与设计器的交互。</span><span class="sxs-lookup"><span data-stu-id="ba524-166">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="ba524-167">可在命名空间中找到这些属性 <xref:System.ComponentModel?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="ba524-167">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>

- <span data-ttu-id="ba524-168">可以编写自定义控件的自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="ba524-168">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="ba524-169">这使你可以使用由 Visual Studio 公开的可扩展设计器基础结构来完全控制设计体验。</span><span class="sxs-lookup"><span data-stu-id="ba524-169">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="ba524-170">有关详细信息，请参阅 [演练：创建利用 Visual Studio Design-Time 功能的 Windows 窗体控件](creating-a-wf-control-design-time-features.md)。</span><span class="sxs-lookup"><span data-stu-id="ba524-170">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ba524-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba524-171">See also</span></span>

- [<span data-ttu-id="ba524-172">演练：创建利用 Visual Studio Design-Time 功能的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="ba524-172">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)
