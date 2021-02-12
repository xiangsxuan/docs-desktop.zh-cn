---
title: 使用 Visual Studio 创建新应用教程
description: 遵循本教程，了解如何使用 Visual Studio 2019 创建适用于 .NET 的新 WPF 应用。
ms.date: 01/18/2021
ms.topic: tutorial
dev_langs:
- csharp
- vb
ms.openlocfilehash: b2769d4901b211cf5bc7cffbe4c1bf65d26a0758
ms.sourcegitcommit: 455923e44f1e8df30a233807a54ded94ddc1cf62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "99510047"
---
# <a name="tutorial-create-a-new-wpf-app-wpf-net"></a><span data-ttu-id="83258-103">教程：创建新的 WPF 应用 (WPF .NET)</span><span class="sxs-lookup"><span data-stu-id="83258-103">Tutorial: Create a new WPF app (WPF .NET)</span></span>

<span data-ttu-id="83258-104">本简短教程将介绍如何使用 Visual Studio 创建新的 Windows Presentation Foundation (WPF) 应用。</span><span class="sxs-lookup"><span data-stu-id="83258-104">In this short tutorial, you'll learn how to create a new Windows Presentation Foundation (WPF) app with Visual Studio.</span></span> <span data-ttu-id="83258-105">生成初始应用后，你将了解如何添加控件以及如何处理事件。</span><span class="sxs-lookup"><span data-stu-id="83258-105">Once the initial app has been generated, you'll learn how to add controls and how to handle events.</span></span> <span data-ttu-id="83258-106">学完本教程后，你将拥有一个可将名称添加到列表框的简单应用。</span><span class="sxs-lookup"><span data-stu-id="83258-106">By the end of this tutorial, you'll have a simple app that adds names to a list box.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="83258-107">在本教程中，你将了解如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="83258-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="83258-108">创建新的 WPF 应用</span><span class="sxs-lookup"><span data-stu-id="83258-108">Create a new WPF app</span></span>
> - <span data-ttu-id="83258-109">将控件添加到窗体</span><span class="sxs-lookup"><span data-stu-id="83258-109">Add controls to a form</span></span>
> - <span data-ttu-id="83258-110">处理控制事件以提供应用功能</span><span class="sxs-lookup"><span data-stu-id="83258-110">Handle control events to provide app functionality</span></span>
> - <span data-ttu-id="83258-111">运行应用</span><span class="sxs-lookup"><span data-stu-id="83258-111">Run the app</span></span>

<span data-ttu-id="83258-112">下面是按照本教程生成的应用的预览：</span><span class="sxs-lookup"><span data-stu-id="83258-112">Here's a preview of the app you'll build while following this tutorial:</span></span>

:::image type="content" source="media/create-app-visual-studio/app-finished.png" alt-text="已完成的 WPF 示例应用教程":::

## <a name="prerequisites"></a><span data-ttu-id="83258-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="83258-114">Prerequisites</span></span>

- [<span data-ttu-id="83258-115">Visual Studio 2019 版本 16.8.4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="83258-115">Visual Studio 2019 version 16.8.4 or later versions</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+wpf)
  - <span data-ttu-id="83258-116">选择 [Visual Studio Desktop 工作负载](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)</span><span class="sxs-lookup"><span data-stu-id="83258-116">Select the [Visual Studio Desktop workload](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)</span></span>
  - <span data-ttu-id="83258-117">选择 [.NET 5 单个组件](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)</span><span class="sxs-lookup"><span data-stu-id="83258-117">Select the [.NET 5 individual component](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)</span></span>

## <a name="create-a-wpf-app"></a><span data-ttu-id="83258-118">创建 WPF 应用</span><span class="sxs-lookup"><span data-stu-id="83258-118">Create a WPF app</span></span>

<span data-ttu-id="83258-119">创建新应用的第一步是打开 Visual Studio 并通过模板生成应用。</span><span class="sxs-lookup"><span data-stu-id="83258-119">The first step to creating a new app is opening Visual Studio and generating the app from a template.</span></span>

01. <span data-ttu-id="83258-120">打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="83258-120">Open Visual Studio.</span></span>
01. <span data-ttu-id="83258-121">选择“创建新项目”。</span><span class="sxs-lookup"><span data-stu-id="83258-121">Select **Create a new project**.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-create-new-project.png" alt-text="在 Visual Studio 2019 中创建适用于 .NET 的新 WPF 项目":::

01. <span data-ttu-id="83258-123">在“搜索模板”框中，键入“wpf”，然后按 <kbd>Enter</kbd> 。</span><span class="sxs-lookup"><span data-stu-id="83258-123">In the **Search for templates** box, type **wpf**, and then press <kbd>Enter</kbd>.</span></span>
01. <span data-ttu-id="83258-124">在“代码语言”下拉列表中，选择“C#”或“Visual Basic”  。</span><span class="sxs-lookup"><span data-stu-id="83258-124">In the **code language** dropdown, choose **C#** or **Visual Basic**.</span></span>
01. <span data-ttu-id="83258-125">在模板列表中，选择“WPF 应用程序”，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="83258-125">In the templates list, select **WPF Application** and then select **Next**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="83258-126">请勿选择“WPF 应用程序(.NET Framework)”模板。</span><span class="sxs-lookup"><span data-stu-id="83258-126">Don't select the **WPF Application (.NET _Framework_)** template.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-template-search-16.8.png" alt-text="在 Visual Studio 2019 中搜索适用于 .NET 的 WPF 模板":::

01. <span data-ttu-id="83258-128">在“配置新项目”窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="83258-128">In the **Configure your new project** window, do the following:</span></span>

    01. <span data-ttu-id="83258-129">在“项目名称”框中，输入“Names”。</span><span class="sxs-lookup"><span data-stu-id="83258-129">In the **Project name** box, enter **Names**.</span></span>
    01. <span data-ttu-id="83258-130">选中“将解决方案和项目放在同一目录中”复选框。</span><span class="sxs-lookup"><span data-stu-id="83258-130">Select the **Place solution and project in the same directory** check box.</span></span>
    01. <span data-ttu-id="83258-131">（可选）选择其他位置以保存代码。</span><span class="sxs-lookup"><span data-stu-id="83258-131">Optionally, choose a different **Location** to save your code.</span></span>
    01. <span data-ttu-id="83258-132">选择“创建”按钮。</span><span class="sxs-lookup"><span data-stu-id="83258-132">Select the **Create** button.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project-16.8.png" alt-text="在 Visual Studio 2019 中配置适用于 .NET 的新 WPF 项目":::

<!-- THIS IS FOR 16.9 when it's released. Also, change the last child step of the previous step to **Next**

01. In the **Additional information** window, select **.NET 5.0 (Current)** for **Target Framework** and make sure that the **Run on .NET Framework** check box is cleared. Select the **Create** button.

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project-next.png" alt-text="Select target framework for new WPF project in Visual Studio 2019 for .NET":::
-->

<span data-ttu-id="83258-134">生成应用后，Visual Studio 应会打开默认窗口 MainWindow 的 XAML 设计器窗格。</span><span class="sxs-lookup"><span data-stu-id="83258-134">Once the app is generated, Visual Studio should open the XAML designer pane for the default window, _MainWindow_.</span></span> <span data-ttu-id="83258-135">如果看不到设计器，请在“解决方案资源管理器”窗格中双击 MainWindow.xaml 文件以打开设计器。</span><span class="sxs-lookup"><span data-stu-id="83258-135">If the designer isn't visible, double-click on the _MainWindow.xaml_ file in the **Solution Explorer** pane to open the designer.</span></span>

### <a name="important-parts-of-visual-studio"></a><span data-ttu-id="83258-136">Visual Studio 的重要部分</span><span class="sxs-lookup"><span data-stu-id="83258-136">Important parts of Visual Studio</span></span>

<span data-ttu-id="83258-137">Visual Studio 中对 WPF 的支持包含五个在创建应用时你将与之交互的重要组件：</span><span class="sxs-lookup"><span data-stu-id="83258-137">Support for WPF in Visual Studio has five important components that you'll interact with as you create an app:</span></span>

:::image type="content" source="media/create-app-visual-studio/vs-main-window.png" alt-text="创建适用于 .NET 的 WPF 项目时应了解的 Visual Studio 重要组件":::

01. <span data-ttu-id="83258-139">解决方案资源管理器</span><span class="sxs-lookup"><span data-stu-id="83258-139">Solution Explorer</span></span>

    <span data-ttu-id="83258-140">所有项目文件、代码、窗口、资源都将显示在此窗格中。</span><span class="sxs-lookup"><span data-stu-id="83258-140">All of your project files, code, windows, resources, will appear in this pane.</span></span>

02. <span data-ttu-id="83258-141">属性</span><span class="sxs-lookup"><span data-stu-id="83258-141">Properties</span></span>

    <span data-ttu-id="83258-142">此窗格显示可以基于所选项进行配置的属性设置。</span><span class="sxs-lookup"><span data-stu-id="83258-142">This pane shows property settings you can configure based on the item selected.</span></span> <span data-ttu-id="83258-143">例如，如果从“解决方案资源管理器”中选择一个项，你会看到与该文件相关的属性设置。</span><span class="sxs-lookup"><span data-stu-id="83258-143">For example, if you select an item from **Solution Explorer**, you'll see property settings related to the file.</span></span> <span data-ttu-id="83258-144">如果在“设计器”中选择一个对象，你会看到该项目的设置。</span><span class="sxs-lookup"><span data-stu-id="83258-144">If you select an object in the **Designer**, you'll see settings for that item.</span></span>

03. <span data-ttu-id="83258-145">工具箱</span><span class="sxs-lookup"><span data-stu-id="83258-145">Toolbox</span></span>

    <span data-ttu-id="83258-146">工具箱包含可添加到窗体的所有控件。</span><span class="sxs-lookup"><span data-stu-id="83258-146">The toolbox contains all of the controls you can add to a form.</span></span> <span data-ttu-id="83258-147">若要将控件添加到当前窗体，请双击控件或拖放控件。</span><span class="sxs-lookup"><span data-stu-id="83258-147">To add a control to the current form, double-click a control or drag-and-drop the control.</span></span>

04. <span data-ttu-id="83258-148">XAML 设计器</span><span class="sxs-lookup"><span data-stu-id="83258-148">XAML designer</span></span>

    <span data-ttu-id="83258-149">这是 XAML 文档的设计器。</span><span class="sxs-lookup"><span data-stu-id="83258-149">This is the designer for a XAML document.</span></span> <span data-ttu-id="83258-150">它是交互式的，可以从“工具箱”拖放对象。</span><span class="sxs-lookup"><span data-stu-id="83258-150">It's interactive and you can drag-and-drop objects from the **Toolbox**.</span></span> <span data-ttu-id="83258-151">通过在设计器中选择和移动项，可以直观地为应用构建用户界面 (UI)。</span><span class="sxs-lookup"><span data-stu-id="83258-151">By selecting and moving items in the designer, you can visually compose the user interface (UI) for your app.</span></span>

    <span data-ttu-id="83258-152">当设计器和编辑器都可见时，对设计器的更改会反映在编辑器中，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="83258-152">When both the designer and editor are visible, changes to one is reflected in the other.</span></span> <span data-ttu-id="83258-153">在设计器中选择项目时，“属性”窗格会显示有关该对象的属性和特性。</span><span class="sxs-lookup"><span data-stu-id="83258-153">When you select items in the designer, the **Properties** pane displays the properties and attributes about that object.</span></span>

05. <span data-ttu-id="83258-154">XAML 代码编辑器</span><span class="sxs-lookup"><span data-stu-id="83258-154">XAML code editor</span></span>

    <span data-ttu-id="83258-155">这是 XAML 文档的 XAML 代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="83258-155">This is the XAML code editor for a XAML document.</span></span> <span data-ttu-id="83258-156">XAML 代码编辑器是一种无需设计器即可手动创建 UI 的方法。</span><span class="sxs-lookup"><span data-stu-id="83258-156">The XAML code editor is a way to craft your UI by hand without a designer.</span></span> <span data-ttu-id="83258-157">将控件添加到设计器中时，设计器可以推断控件上的属性值。</span><span class="sxs-lookup"><span data-stu-id="83258-157">The designer may infer the values of properties on a control when the control is added in the designer.</span></span> <span data-ttu-id="83258-158">XAML 代码编辑器则为你提供更多控制权。</span><span class="sxs-lookup"><span data-stu-id="83258-158">The XAML code editor gives you a lot more control.</span></span>

    <span data-ttu-id="83258-159">当设计器和编辑器都可见时，对设计器的更改会反映在编辑器中，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="83258-159">When both the designer and editor are visible, changes to one is reflected in the other.</span></span> <span data-ttu-id="83258-160">在代码编辑器中导航文本插入点时，“属性”窗格会显示有关该对象的属性和特性。</span><span class="sxs-lookup"><span data-stu-id="83258-160">As you navigate the text caret in the code editor, the **Properties** pane displays the properties and attributes about that object.</span></span>

## <a name="target-net-50"></a><span data-ttu-id="83258-161">面向 .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="83258-161">Target .NET 5.0</span></span>

<span data-ttu-id="83258-162">创建项目后，将目标框架更改为 .NET 5.0。</span><span class="sxs-lookup"><span data-stu-id="83258-162">After you create your project, change the target framework to .NET 5.0.</span></span> <span data-ttu-id="83258-163">在“解决方案资源管理器”中双击“Names”项目文件。</span><span class="sxs-lookup"><span data-stu-id="83258-163">Double-click on the _Names_ project file in the **Solution Explorer**.</span></span> <span data-ttu-id="83258-164">这将打开项目文件进行编辑。</span><span class="sxs-lookup"><span data-stu-id="83258-164">This opens up the project file for editing.</span></span> <span data-ttu-id="83258-165">将 `<TargetFramework>` 元素设置为 `net5.0-windows`：</span><span class="sxs-lookup"><span data-stu-id="83258-165">Set the `<TargetFramework>` element to `net5.0-windows`:</span></span>

```xml
<TargetFramework>net5.0-windows</TargetFramework>
```

<span data-ttu-id="83258-166">保存项目文件，然后关闭编辑器选项卡。</span><span class="sxs-lookup"><span data-stu-id="83258-166">Save the project file and then close the editor tab.</span></span>

## <a name="examine-the-xaml"></a><span data-ttu-id="83258-167">检查 XAML</span><span class="sxs-lookup"><span data-stu-id="83258-167">Examine the XAML</span></span>

<span data-ttu-id="83258-168">创建项目后，将显示 XAML 代码编辑器，并以最少的 XAML 代码显示窗口。</span><span class="sxs-lookup"><span data-stu-id="83258-168">After your project is created, the XAML code editor is visible with a minimal amount of XAML code to display the window.</span></span> <span data-ttu-id="83258-169">如果编辑器未打开，请在“解决方案资源管理器”中双击“MainWindow.xaml”项目。</span><span class="sxs-lookup"><span data-stu-id="83258-169">If the editor isn't open, double-click the _MainWindow.xaml_ item in the **Solution Explorer**.</span></span> <span data-ttu-id="83258-170">你应该会看到类似于以下内容的 XAML：</span><span class="sxs-lookup"><span data-stu-id="83258-170">You should see XAML similar to the following:</span></span>

```xaml
<Window x:Class="Names.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Names"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>

    </Grid>
</Window>
```

<span data-ttu-id="83258-171">让我们分解此 XAML 代码，以便更好地了解它。</span><span class="sxs-lookup"><span data-stu-id="83258-171">Let's break down this XAML code to understand it better.</span></span> <span data-ttu-id="83258-172">XAML 就是可由 WPF 使用的编译器进行处理的 XML。</span><span class="sxs-lookup"><span data-stu-id="83258-172">XAML is simply XML that can be processed by the compilers that WPF uses.</span></span> <span data-ttu-id="83258-173">它描述 WPF UI 并与 .NET 代码进行交互。</span><span class="sxs-lookup"><span data-stu-id="83258-173">It describes the WPF UI and interacts with .NET code.</span></span> <span data-ttu-id="83258-174">若要了解 XAML，至少应熟悉 XML 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="83258-174">To understand XAML, you should, at a minimum, be familiar with the basics of XML.</span></span>

<span data-ttu-id="83258-175">文档根 `<Window>` 表示 XAML 文件描述的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="83258-175">The document root `<Window>` represents the type of object being described by the XAML file.</span></span> <span data-ttu-id="83258-176">它声明八个特性，这些特性通常分为三类：</span><span class="sxs-lookup"><span data-stu-id="83258-176">There are eight attributes declared, and they generally belong to three categories:</span></span>

- <span data-ttu-id="83258-177">命名空间</span><span class="sxs-lookup"><span data-stu-id="83258-177">Namespaces</span></span>

  <span data-ttu-id="83258-178">XML 命名空间为 XML 提供结构，确定允许或不允许在文件中声明的内容。</span><span class="sxs-lookup"><span data-stu-id="83258-178">An XML namespace provides structure to the XML, determining what is or isn't allowed to be declared in the file.</span></span>

  <span data-ttu-id="83258-179">主要 `xmlns` 特性将导入整个文件的 XML 命名空间，在本例中，将映射到 WPF 声明的类型。</span><span class="sxs-lookup"><span data-stu-id="83258-179">The main `xmlns` attribute imports the XML namespace for the entire file, and in this case, maps to the types declared by WPF.</span></span> <span data-ttu-id="83258-180">其他 XML 命名空间声明一个前缀，并导入 XAML 文件的其他类型和对象。</span><span class="sxs-lookup"><span data-stu-id="83258-180">The other XML namespaces declare a prefix and import other types and objects for the XAML file.</span></span> <span data-ttu-id="83258-181">例如，`xmlns:local` 命名空间声明 `local` 前缀，并映射到项目声明的对象，即，在 `Names` 代码命名空间中声明的对象。</span><span class="sxs-lookup"><span data-stu-id="83258-181">For example, the `xmlns:local` namespace declares the `local` prefix and maps to the objects declared by your project, the ones declared in the `Names` code namespace.</span></span>

- <span data-ttu-id="83258-182">`x:Class` 特性</span><span class="sxs-lookup"><span data-stu-id="83258-182">`x:Class` attribute</span></span>

  <span data-ttu-id="83258-183">此特性将 `<Window>` 映射到代码定义的类型：MainWindow.xaml.cs 或 MainWindow.xaml.vb 文件，即 `Names.MainWindow` 类。</span><span class="sxs-lookup"><span data-stu-id="83258-183">This attribute maps the `<Window>` to the type defined by your code: the _MainWindow.xaml.cs_ or _MainWindow.xaml.vb_ file, which is the `Names.MainWindow` class.</span></span>

- <span data-ttu-id="83258-184">`Title` 特性</span><span class="sxs-lookup"><span data-stu-id="83258-184">`Title` attribute</span></span>

  <span data-ttu-id="83258-185">在 XAML 对象上声明的任何常规特性都会设置该对象的属性。</span><span class="sxs-lookup"><span data-stu-id="83258-185">Any normal attribute declared on the XAML object sets a property of that object.</span></span> <span data-ttu-id="83258-186">在本例中，`Title` 特性将设置 `Window.Title` 属性。</span><span class="sxs-lookup"><span data-stu-id="83258-186">In this case the `Title` attribute sets the `Window.Title` property.</span></span>

## <a name="change-the-window"></a><span data-ttu-id="83258-187">更改窗口</span><span class="sxs-lookup"><span data-stu-id="83258-187">Change the window</span></span>

<span data-ttu-id="83258-188">首先，让我们运行项目并查看默认输出。</span><span class="sxs-lookup"><span data-stu-id="83258-188">First, let's run the project and see the default output.</span></span> <span data-ttu-id="83258-189">你会看到一个没有任何控件且标题为 MainWindow 的弹出窗口：</span><span class="sxs-lookup"><span data-stu-id="83258-189">You'll see that a window that pops up, without any controls, and a title of **MainWindow**:</span></span>

:::image type="content" source="media/create-app-visual-studio/app-default.png" alt-text="空白的 WPF 应用":::

<span data-ttu-id="83258-191">对于我们的示例应用，此窗口太大，并且标题栏不是描述性的。</span><span class="sxs-lookup"><span data-stu-id="83258-191">For our example app, this window is too large, and the title bar isn't descriptive.</span></span> <span data-ttu-id="83258-192">通过将 XAML 中的相应特性更改为以下值，来更改窗口的标题和大小：</span><span class="sxs-lookup"><span data-stu-id="83258-192">Change the title and size of the window by changing the appropriate attributes in the XAML to the following values:</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/Start.xaml" highlight="8":::

## <a name="prepare-the-layout"></a><span data-ttu-id="83258-193">准备布局</span><span class="sxs-lookup"><span data-stu-id="83258-193">Prepare the layout</span></span>

<span data-ttu-id="83258-194">WPF 提供一个功能强大的布局系统，其中包含许多不同的布局控件。</span><span class="sxs-lookup"><span data-stu-id="83258-194">WPF provides a powerful layout system with many different layout controls.</span></span> <span data-ttu-id="83258-195">布局控件可帮助放置子控件和调整其大小，甚至可以自动执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="83258-195">Layout controls help place and size child controls, and can even do so automatically.</span></span> <span data-ttu-id="83258-196">此 XAML 中提供给你的默认布局控件是 `<Grid>` 控件。</span><span class="sxs-lookup"><span data-stu-id="83258-196">The default layout control provided to you in this XAML is the `<Grid>` control.</span></span>

<span data-ttu-id="83258-197">通过使用 `Grid` 控件，可以像定义表一样定义行和列，并将控件置于特定行和列组合的边界内。</span><span class="sxs-lookup"><span data-stu-id="83258-197">The `Grid` control lets you define rows and columns, much like a table, and place controls within the bounds of a specific row and column combination.</span></span> <span data-ttu-id="83258-198">你可以将任意数量的子控件或其他布局控件添加到 `Grid` 中。</span><span class="sxs-lookup"><span data-stu-id="83258-198">You can have any number of child controls or other layout controls added to the `Grid`.</span></span> <span data-ttu-id="83258-199">例如，你可以在特定的行和列组合中放置另一个 `Grid` 控件，然后新的 `Grid` 可以定义更多的行和列，并拥有自己的子级。</span><span class="sxs-lookup"><span data-stu-id="83258-199">For example, you can place another `Grid` control in a specific row and column combination, and that new `Grid` can then define more rows and columns and have its own children.</span></span>

<span data-ttu-id="83258-200">`<Grid>` 控件定义控件所在的行和列。</span><span class="sxs-lookup"><span data-stu-id="83258-200">The `<Grid>` control defines rows and columns in which your controls will be.</span></span> <span data-ttu-id="83258-201">网格始终只声明单行和单列，这意味着默认情况下，网格就是一个单元格。</span><span class="sxs-lookup"><span data-stu-id="83258-201">A grid always has a single row and column declared, meaning, the grid by default is a single cell.</span></span> <span data-ttu-id="83258-202">这并不能让你真正灵活地放置控件。</span><span class="sxs-lookup"><span data-stu-id="83258-202">That doesn't really give you much flexibility in placing controls.</span></span>

<span data-ttu-id="83258-203">在添加新的行和列之前，请向 `<Grid>` 元素添加一个新特性：`Margin="10"`。</span><span class="sxs-lookup"><span data-stu-id="83258-203">Before we add the new rows and columns, add a new attribute to the `<Grid>` element: `Margin="10"`.</span></span> <span data-ttu-id="83258-204">这样就可以从窗口中插入网格，使它看起来更漂亮一些。</span><span class="sxs-lookup"><span data-stu-id="83258-204">This insets the grid from the window and makes it look a little nicer.</span></span>

<span data-ttu-id="83258-205">接下来，定义两行两列，将网格划分为四个单元格：</span><span class="sxs-lookup"><span data-stu-id="83258-205">Next, define two rows and two columns, dividing the grid into four cells:</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep2.xaml" highlight="9-21":::

<span data-ttu-id="83258-206">在 XAML 代码编辑器或 XAML 设计器中选择网格，你将看到 XAML 设计器显示每一行和每一列：</span><span class="sxs-lookup"><span data-stu-id="83258-206">Select the grid in either the XAML code editor or XAML designer, you'll see that the XAML designer shows each row and column:</span></span>

:::image type="content" source="media/create-app-visual-studio/vs-designer-grid-rows-columns.png" alt-text="在网格上设置了边距的 WPF 应用":::

## <a name="add-the-first-control"></a><span data-ttu-id="83258-208">添加第一个控件</span><span class="sxs-lookup"><span data-stu-id="83258-208">Add the first control</span></span>

<span data-ttu-id="83258-209">现在已经创建了网格，接下来可以开始向其添加控件。</span><span class="sxs-lookup"><span data-stu-id="83258-209">Now that the grid has been created, we can start adding controls to it.</span></span> <span data-ttu-id="83258-210">首先，从标签控件开始。</span><span class="sxs-lookup"><span data-stu-id="83258-210">First, start with the label control.</span></span> <span data-ttu-id="83258-211">在 `<Grid>` 元素内的行定义和列定义后面创建一个新的 `<Label>` 元素，并为其指定字符串值 `Names`：</span><span class="sxs-lookup"><span data-stu-id="83258-211">Create a new `<Label>` element inside the `<Grid>` element, after the row and column definitions, and give it a string value of `Names`:</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep3.xaml" range="9-23" highlight="13":::

<span data-ttu-id="83258-212">`<Label>Names</Label>` 定义内容 `Names`。</span><span class="sxs-lookup"><span data-stu-id="83258-212">The `<Label>Names</Label>` defines the content `Names`.</span></span> <span data-ttu-id="83258-213">有些控件知道如何处理内容，有些则不知道。</span><span class="sxs-lookup"><span data-stu-id="83258-213">Some controls understand how to handle content, others don't.</span></span> <span data-ttu-id="83258-214">控件的内容映射到 `Content` 属性。</span><span class="sxs-lookup"><span data-stu-id="83258-214">The content of a control maps to the `Content` property.</span></span> <span data-ttu-id="83258-215">通过 XAML 特性语法设置内容时，将使用以下格式：`<Label Content="Names" />`。</span><span class="sxs-lookup"><span data-stu-id="83258-215">Setting the content through XAML attribute syntax, you would use this format: `<Label Content="Names" />`.</span></span> <span data-ttu-id="83258-216">这两种方法可以实现相同的目的，即，将标签内容设置为显示文本 `Names`。</span><span class="sxs-lookup"><span data-stu-id="83258-216">Both ways accomplish the same thing, setting the content of the label to display the text `Names`.</span></span>

<span data-ttu-id="83258-217">不过，我们有一个问题，由于标签是自动分配给网格的第一行和第一列的，因此它占据了半个窗口。</span><span class="sxs-lookup"><span data-stu-id="83258-217">We have a problem though, the label takes up half the window as it was automatically assigned to the first row and column of the grid.</span></span> <span data-ttu-id="83258-218">对于第一行，我们不需要那么多空间，因为我们只需要在这一行放置标签。</span><span class="sxs-lookup"><span data-stu-id="83258-218">For our first row, we don't need that much space because we're only going to use that row for the label.</span></span> <span data-ttu-id="83258-219">将第一个 `<RowDefinition>` 的 `Height` 特性从 `*` 更改为 `Auto`。</span><span class="sxs-lookup"><span data-stu-id="83258-219">Change the `Height` attribute of the first `<RowDefinition>` from `*` to `Auto`.</span></span> <span data-ttu-id="83258-220">`Auto` 值会自动将网格行的大小调整为其内容（在本例中为标签控件）的大小。</span><span class="sxs-lookup"><span data-stu-id="83258-220">The `Auto` value automatically sizes the grid row to the size of its contents, in this case, the label control.</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep4.xaml" range="11-14" highlight="2":::

<span data-ttu-id="83258-221">请注意，设计器现在显示标签占据的可用高度较少。</span><span class="sxs-lookup"><span data-stu-id="83258-221">Notice that the designer now shows the label occupying a small amount of the available height.</span></span> <span data-ttu-id="83258-222">现在，下一行有更多空间可用。</span><span class="sxs-lookup"><span data-stu-id="83258-222">There's now more room for the next row to occupy.</span></span> <span data-ttu-id="83258-223">大多数控件会定义应该占用的最适合自己的某种高度和宽度值。</span><span class="sxs-lookup"><span data-stu-id="83258-223">Most controls define some sort of height and width value that they should occupy that looks best for them.</span></span> <span data-ttu-id="83258-224">对于标签控件，其高度值可确保你可以读取它。</span><span class="sxs-lookup"><span data-stu-id="83258-224">In the case of the label control, it has a height value that ensures that you can read it.</span></span>

:::image type="content" source="media/create-app-visual-studio/vs-designer-grid-rows-columns-label.png" alt-text="在网格上设置了边距并且第一行有标签控件的 WPF 应用":::

### <a name="control-placement"></a><span data-ttu-id="83258-226">控件放置</span><span class="sxs-lookup"><span data-stu-id="83258-226">Control placement</span></span>

<span data-ttu-id="83258-227">让我们谈谈控件的放置。</span><span class="sxs-lookup"><span data-stu-id="83258-227">Let's talk about control placement.</span></span> <span data-ttu-id="83258-228">上一部分中创建的标签已自动放置在网格的第 0 行和第 0 列。</span><span class="sxs-lookup"><span data-stu-id="83258-228">The label created in the section above was automatically placed in row 0 and column 0 of the grid.</span></span> <span data-ttu-id="83258-229">行和列的编号从 0 开始，每新增一行或一列，编号就递增 1。</span><span class="sxs-lookup"><span data-stu-id="83258-229">The numbering for rows and columns starts at 0 and increments by 1 for each new row or column.</span></span> <span data-ttu-id="83258-230">控件无法识别网格，并且不会定义任何属性来控制其在网格中的位置。</span><span class="sxs-lookup"><span data-stu-id="83258-230">The control doesn't know anything about the grid, and the control doesn't define any properties to control its placement within the grid.</span></span> <span data-ttu-id="83258-231">控件甚至可能放置在其他布局控件中，后者有自己的一组规则来定义如何放置控件。</span><span class="sxs-lookup"><span data-stu-id="83258-231">The control could have even been placed within some other layout control which has its own set of rules defining how to place controls.</span></span>

<span data-ttu-id="83258-232">当控件无法识别网格时，如何告诉控件使用其他行或列？</span><span class="sxs-lookup"><span data-stu-id="83258-232">How do you tell a control to use a different row or column when the control has no knowledge of the grid?</span></span> <span data-ttu-id="83258-233">附加属性！</span><span class="sxs-lookup"><span data-stu-id="83258-233">Attached properties!</span></span> <span data-ttu-id="83258-234">网格采用 WPF 提供的强大属性系统。</span><span class="sxs-lookup"><span data-stu-id="83258-234">The grid takes advantage of the powerful property system provided by WPF.</span></span> <span data-ttu-id="83258-235">网格定义了子控件可以声明和使用的新属性。</span><span class="sxs-lookup"><span data-stu-id="83258-235">The grid defines new properties that the child controls can declare and use.</span></span> <span data-ttu-id="83258-236">控件本身其实并不存在这些属性，它们是在将控件添加到网格时由网格附加的。</span><span class="sxs-lookup"><span data-stu-id="83258-236">The properties don't actually exist on the control itself, they're attached by the grid when the control is added to the grid.</span></span>

<span data-ttu-id="83258-237">网格定义两个属性来确定子控件的行和列位置：`Grid.Row` 和 `Grid.Column`。</span><span class="sxs-lookup"><span data-stu-id="83258-237">The grid defines two properties to determine the row and column placement of a child control: `Grid.Row` and `Grid.Column`.</span></span> <span data-ttu-id="83258-238">如果控件中省略了这些属性，则意味着它们的默认值为 0，因此，控件将放置在网格的第 `0` 行和第 `0` 列。</span><span class="sxs-lookup"><span data-stu-id="83258-238">If these properties are omitted from the control, it's implied that they have the default values of 0, so, the control is placed in row `0` and column `0` of the grid.</span></span> <span data-ttu-id="83258-239">尝试通过将 `Grid.Column` 属性设置为 `1` 来更改 `<Label>` 控件的位置：</span><span class="sxs-lookup"><span data-stu-id="83258-239">Try changing the placement of the `<Label>` control by setting the `Grid.Column` attribute to `1`:</span></span>

```xaml
<Label Grid.Column="1">Names</Label>
```

<span data-ttu-id="83258-240">注意标签现在如何移动到第二列。</span><span class="sxs-lookup"><span data-stu-id="83258-240">Notice how your label now moved to the second column.</span></span> <span data-ttu-id="83258-241">你可以使用 `Grid.Row` 和 `Grid.Column` 附加属性来放置我们接下来要创建的控件。</span><span class="sxs-lookup"><span data-stu-id="83258-241">You can use the `Grid.Row` and `Grid.Column` attached properties to place the next controls we'll create.</span></span> <span data-ttu-id="83258-242">不过现在，请将标签还原到第 0 行。</span><span class="sxs-lookup"><span data-stu-id="83258-242">For now though, restore the label to row 0.</span></span>

## <a name="create-the-name-list-box"></a><span data-ttu-id="83258-243">创建名称列表框</span><span class="sxs-lookup"><span data-stu-id="83258-243">Create the name list box</span></span>

<span data-ttu-id="83258-244">现在已经正确调整了网格的大小并创建了标签，接下来，在标签下方的行中添加一个列表框控件。</span><span class="sxs-lookup"><span data-stu-id="83258-244">Now that the grid is correctly sized and the label created, add a list box control on the row below the label.</span></span> <span data-ttu-id="83258-245">列表框将位于第 `1` 行和第 `0` 列。</span><span class="sxs-lookup"><span data-stu-id="83258-245">The list box will be in row `1` and column `0`.</span></span> <span data-ttu-id="83258-246">我们还将此控件命名为 `lstNames`。</span><span class="sxs-lookup"><span data-stu-id="83258-246">We'll also give this control the name of `lstNames`.</span></span> <span data-ttu-id="83258-247">为控件命名后，即可在代码隐藏中对其进行引用。</span><span class="sxs-lookup"><span data-stu-id="83258-247">Once a control is named, it can be referenced in the code behind.</span></span> <span data-ttu-id="83258-248">该名称通过 `x:Name` 特性分配给控件。</span><span class="sxs-lookup"><span data-stu-id="83258-248">The name is assigned to the control with the `x:Name` attribute.</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls1.xaml" range="9-24" highlight="14":::

## <a name="add-the-remaining-controls"></a><span data-ttu-id="83258-249">添加其余控件</span><span class="sxs-lookup"><span data-stu-id="83258-249">Add the remaining controls</span></span>

<span data-ttu-id="83258-250">我们将添加的最后两个控件是一个文本框和一个按钮，用户将使用它们来输入要添加到列表框中的名称。</span><span class="sxs-lookup"><span data-stu-id="83258-250">The last two controls we'll add are a text box and a button, which the user will use to enter a name to add to the list box.</span></span> <span data-ttu-id="83258-251">但是，我们没有尝试为网格创建更多行和列，而是将这些控件放入 `<StackPanel>` 布局控件中。</span><span class="sxs-lookup"><span data-stu-id="83258-251">However, instead of trying to create more rows and columns for the grid, we'll put these controls into the `<StackPanel>` layout control.</span></span>

<span data-ttu-id="83258-252">堆叠面板与网格的不同之处在于控件的放置方式。</span><span class="sxs-lookup"><span data-stu-id="83258-252">The stack panel differs from the grid in how the controls are placed.</span></span> <span data-ttu-id="83258-253">你告诉网格你希望使用 `Grid.Row` 和 `Grid.Column` 附加属性将控件放置在哪个位置，堆叠面板则自动按以下方式运行：先放置第一个控件，然后将下一个控件置于其后，一直到所有控件都放置完毕。</span><span class="sxs-lookup"><span data-stu-id="83258-253">While you tell the grid where you want the controls to be with the `Grid.Row` and `Grid.Column` attached properties, the stack panel works automatically by placing the first control, then placing the next control after it, continuing until all controls have been placed.</span></span> <span data-ttu-id="83258-254">它将每个控件“堆叠”在另一个控件之下。</span><span class="sxs-lookup"><span data-stu-id="83258-254">It "stacks" each control below the other.</span></span>

<span data-ttu-id="83258-255">在列表框后创建 `<StackPanel>` 控件，并将其放在网格的第 `1` 行、第 `1` 列。</span><span class="sxs-lookup"><span data-stu-id="83258-255">Create the `<StackPanel>` control after the list box and put it in grid row `1` column `1`.</span></span> <span data-ttu-id="83258-256">另外添加一个名为 `Margin` 且值为 `5,0,0,0` 的特性：</span><span class="sxs-lookup"><span data-stu-id="83258-256">Add another attribute named `Margin` with a value of `5,0,0,0`:</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls2.xaml" id="StackPanel1":::

<span data-ttu-id="83258-257">之前在网格上使用了 `Margin` 特性，但我们只输入了一个值 (`10`)。</span><span class="sxs-lookup"><span data-stu-id="83258-257">The `Margin` attribute was previously used on the grid, but we only put in a single value, `10`.</span></span> <span data-ttu-id="83258-258">现在，我们在堆叠面板上使用了值 `5,0,0,0`。</span><span class="sxs-lookup"><span data-stu-id="83258-258">Now we've used a value of `5,0,0,0` on the stack panel.</span></span> <span data-ttu-id="83258-259">边距是 `Thickness` 类型，可以解释这两个值。</span><span class="sxs-lookup"><span data-stu-id="83258-259">The margin is a `Thickness` type and can interpret both values.</span></span> <span data-ttu-id="83258-260">粗细定义矩形框每条边（分别为左、顶、右、底）周围的空间。</span><span class="sxs-lookup"><span data-stu-id="83258-260">A thickness defines the space around each side of a rectangular frame, **left**, **top**, **right**, **bottom**, respectively.</span></span> <span data-ttu-id="83258-261">如果边距的值是单一值，则四条边均使用该值。</span><span class="sxs-lookup"><span data-stu-id="83258-261">If the value for the margin is a single value, it uses that value for all four sides.</span></span>

<span data-ttu-id="83258-262">接下来，在 `<StackPanel>` 中创建 `<TextBox>` 和 `<Button>` 控件。</span><span class="sxs-lookup"><span data-stu-id="83258-262">Next, create a `<TextBox>` and `<Button>` control in the `<StackPanel>`.</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls2.xaml" id="StackPanel2":::

<span data-ttu-id="83258-263">窗口的布局已完成。</span><span class="sxs-lookup"><span data-stu-id="83258-263">The layout for the window is complete.</span></span> <span data-ttu-id="83258-264">但是，我们的应用不包含任何逻辑，无法真正发挥作用。</span><span class="sxs-lookup"><span data-stu-id="83258-264">However, our app doesn't have any logic in it to actually be functional.</span></span> <span data-ttu-id="83258-265">接下来，我们需要将控件事件挂钩到代码，让应用能够实际派上用场。</span><span class="sxs-lookup"><span data-stu-id="83258-265">Next, we need to hook up the control events to code and get the app to actually do something.</span></span>

## <a name="add-code-for-the-click-event"></a><span data-ttu-id="83258-266">为 Click 事件添加代码</span><span class="sxs-lookup"><span data-stu-id="83258-266">Add code for the Click event</span></span>

<span data-ttu-id="83258-267">我们创建的 `<Button>` 具有一个 `Click` 事件，该事件在用户按下按钮时引发。</span><span class="sxs-lookup"><span data-stu-id="83258-267">The `<Button>` we created has a `Click` event that is raised when the user presses the button.</span></span> <span data-ttu-id="83258-268">你可以订阅此事件并添加代码，以便向列表框添加名称。</span><span class="sxs-lookup"><span data-stu-id="83258-268">You can subscribe to this event and add code to add a name to the list box.</span></span> <span data-ttu-id="83258-269">就像通过添加 XAML 特性在控件上设置属性一样，你可以使用 XAML 特性来订阅事件。</span><span class="sxs-lookup"><span data-stu-id="83258-269">Just like you set a property on a control by adding a XAML attribute, you can use a XAML attribute to subscribe to an event.</span></span> <span data-ttu-id="83258-270">将 `Click` 特性设置为 `ButtonAddName_Click`</span><span class="sxs-lookup"><span data-stu-id="83258-270">Set the `Click` attribute to `ButtonAddName_Click`</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls3.xaml" id="ButtonEvent" highlight="3":::

<span data-ttu-id="83258-271">现在，你需要生成处理程序代码。</span><span class="sxs-lookup"><span data-stu-id="83258-271">Now you need to generate the handler code.</span></span> <span data-ttu-id="83258-272">右键单击 `ButtonAddName_Click`，然后选择“转到定义”。</span><span class="sxs-lookup"><span data-stu-id="83258-272">Right-click on `ButtonAddName_Click` and select **Go To Definition**.</span></span> <span data-ttu-id="83258-273">这将在代码隐藏中为你生成一个与你输入的处理程序名称匹配的方法。</span><span class="sxs-lookup"><span data-stu-id="83258-273">This will generate a method in the code behind for you that matches the handler name you've entered.</span></span>

:::code language="csharp" source="snippets/create-app-visual-studio/csharp/MoreControls3.xaml.cs" id="ButtonEvent":::
:::code language="vb" source="snippets/create-app-visual-studio/vb/MoreControls3.xaml.vb" id="ButtonEvent":::

<span data-ttu-id="83258-274">接下来，添加以下代码以执行这三个步骤：</span><span class="sxs-lookup"><span data-stu-id="83258-274">Next, add the following code to do these three steps:</span></span>

01. <span data-ttu-id="83258-275">确保文本框包含名称。</span><span class="sxs-lookup"><span data-stu-id="83258-275">Make sure that the text box contains a name.</span></span>
01. <span data-ttu-id="83258-276">验证文本框中输入的名称是否已经存在。</span><span class="sxs-lookup"><span data-stu-id="83258-276">Validate that the name entered in the text box doesn't already exist.</span></span>
01. <span data-ttu-id="83258-277">将名称添加到列表框。</span><span class="sxs-lookup"><span data-stu-id="83258-277">Add the name to the list box.</span></span>

:::code language="csharp" source="snippets/create-app-visual-studio/csharp/Final.xaml.cs" id="FinalCode":::
:::code language="vb" source="snippets/create-app-visual-studio/vb/Final.xaml.vb" id="FinalCode":::

## <a name="run-the-app"></a><span data-ttu-id="83258-278">运行应用</span><span class="sxs-lookup"><span data-stu-id="83258-278">Run the app</span></span>

<span data-ttu-id="83258-279">现在已对事件进行编码，可以通过按 <kbd>F5</kbd> 键或从菜单中选择“调试” > “开始调试”来运行应用 。</span><span class="sxs-lookup"><span data-stu-id="83258-279">Now that the event has been coded, you can run the app by pressing the <kbd>F5</kbd> key or by selecting **Debug** > **Start Debugging** from the menu.</span></span> <span data-ttu-id="83258-280">随即显示窗口，可以在文本框中输入名称，然后通过单击按钮添加该名称。</span><span class="sxs-lookup"><span data-stu-id="83258-280">The window is displayed and you can enter a name in the textbox and then add it by clicking the button.</span></span>

:::image type="content" source="media/create-app-visual-studio/app-finished.png" alt-text="正在运行适用于 .NET 的 Windows Presentation Foundation (WPF) 应用。":::

## <a name="next-steps"></a><span data-ttu-id="83258-282">后续步骤</span><span class="sxs-lookup"><span data-stu-id="83258-282">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="83258-283">详细了解 Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="83258-283">Learn more about Windows Presentation Foundation</span></span>](../overview/index.md)
