---
title: 使用 Visual Studio 创建新应用教程
description: 遵循本教程，了解如何使用 Visual Studio 2019 创建适用于 .NET 的新 Windows 窗体应用。
ms.date: 10/26/2020
ms.topic: tutorial
dev_langs:
- csharp
- vb
ms.openlocfilehash: db0712aa642e54373f686fdd24a4747bf2d195e3
ms.sourcegitcommit: e8e3f6f23b5ddf9f5c4fe1ec5f6e0a8a609d49c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "97004727"
---
# <a name="tutorial-create-a-new-winforms-app-windows-forms-net"></a><span data-ttu-id="3155d-103">教程：创建新的 WinForms 应用（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="3155d-103">Tutorial: Create a new WinForms app (Windows Forms .NET)</span></span>

<span data-ttu-id="3155d-104">本简短教程将介绍如何使用 Visual Studio 创建新的 Windows 窗体 (WinForms) 应用。</span><span class="sxs-lookup"><span data-stu-id="3155d-104">In this short tutorial, you'll learn how to create a new Windows Forms (WinForms) app with Visual Studio.</span></span> <span data-ttu-id="3155d-105">生成初始应用后，你将了解如何添加控件以及如何处理事件。</span><span class="sxs-lookup"><span data-stu-id="3155d-105">Once the initial app has been generated, you'll learn how to add controls and how to handle events.</span></span> <span data-ttu-id="3155d-106">学完本教程后，你将拥有一个可将名称添加到列表框的简单应用。</span><span class="sxs-lookup"><span data-stu-id="3155d-106">By the end of this tutorial, you'll have a simple app that adds names to a list box.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="3155d-107">在本教程中，你将了解如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3155d-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="3155d-108">创建新的 WinForms 应用</span><span class="sxs-lookup"><span data-stu-id="3155d-108">Create a new WinForms app</span></span>
> - <span data-ttu-id="3155d-109">将控件添加到窗体</span><span class="sxs-lookup"><span data-stu-id="3155d-109">Add controls to a form</span></span>
> - <span data-ttu-id="3155d-110">处理控制事件以提供应用功能</span><span class="sxs-lookup"><span data-stu-id="3155d-110">Handle control events to provide app functionality</span></span>
> - <span data-ttu-id="3155d-111">运行应用</span><span class="sxs-lookup"><span data-stu-id="3155d-111">Run the app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3155d-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="3155d-112">Prerequisites</span></span>

- [<span data-ttu-id="3155d-113">Visual Studio 2019 版本 16.8 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3155d-113">Visual Studio 2019 version 16.8 or later versions</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms)
  - <span data-ttu-id="3155d-114">选择 [Visual Studio Desktop 工作负载](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)</span><span class="sxs-lookup"><span data-stu-id="3155d-114">Select the [Visual Studio Desktop workload](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)</span></span>
  - <span data-ttu-id="3155d-115">选择 [.NET 5 单个组件](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)</span><span class="sxs-lookup"><span data-stu-id="3155d-115">Select the [.NET 5 individual component](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)</span></span>

## <a name="create-a-winforms-app"></a><span data-ttu-id="3155d-116">创建 WinForms 应用</span><span class="sxs-lookup"><span data-stu-id="3155d-116">Create a WinForms app</span></span>

<span data-ttu-id="3155d-117">创建新应用的第一步是打开 Visual Studio 并通过模板生成应用。</span><span class="sxs-lookup"><span data-stu-id="3155d-117">The first step to creating a new app is opening Visual Studio and generating the app from a template.</span></span>

01. <span data-ttu-id="3155d-118">打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="3155d-118">Open Visual Studio.</span></span>
01. <span data-ttu-id="3155d-119">选择“创建新项目”。</span><span class="sxs-lookup"><span data-stu-id="3155d-119">Select **Create a new project**.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-create-new-project.png" alt-text="在 Visual Studio 2019 中创建适用于 .NET 的新 Windows 窗体项目":::

01. <span data-ttu-id="3155d-121">在“搜索模板”框中，键入“winforms”，然后按 <kbd>Enter</kbd> 。</span><span class="sxs-lookup"><span data-stu-id="3155d-121">In the **Search for templates** box, type **winforms**, and then press <kbd>Enter</kbd>.</span></span>
01. <span data-ttu-id="3155d-122">在“代码语言”下拉列表中，选择“C#”或“Visual Basic”  。</span><span class="sxs-lookup"><span data-stu-id="3155d-122">In the **code language** dropdown, choose **C#** or **Visual Basic**.</span></span>
01. <span data-ttu-id="3155d-123">在模板列表中，选择“Windows 窗体应用 (.NET)”，然后单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="3155d-123">In the templates list, select **Windows Forms App (.NET)** and then click **Next**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3155d-124">请勿选择“Windows 窗体应用 (.NET Framework)”模板。</span><span class="sxs-lookup"><span data-stu-id="3155d-124">Don't select the **Windows Forms App (.NET _Framework_)** template.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-template-search.png" alt-text="在 Visual Studio 2019 中搜索适用于 .NET 的 Windows 窗体模板":::

01. <span data-ttu-id="3155d-126">在“配置新项目”窗口中，将“项目名称”设置为“Names”，然后单击“创建”   。</span><span class="sxs-lookup"><span data-stu-id="3155d-126">In the **Configure your new project** window, set the **Project name** to **Names** and click **Create**.</span></span>

    <span data-ttu-id="3155d-127">还可以通过调整“位置”设置将项目保存到其他文件夹。</span><span class="sxs-lookup"><span data-stu-id="3155d-127">You can also save your project to a different folder by adjusting the **Location** setting.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project.png" alt-text="在 Visual Studio 2019 中配置适用于 .NET 的新 Windows 窗体项目":::

<span data-ttu-id="3155d-129">生成应用后，Visual Studio 应会打开默认窗体 Form1 的设计器窗格。</span><span class="sxs-lookup"><span data-stu-id="3155d-129">Once the app is generated, Visual Studio should open the designer pane for the default form, _Form1_.</span></span> <span data-ttu-id="3155d-130">如果看不到窗体设计器，请在“解决方案资源管理器”窗格中双击该窗体以打开设计器窗口。</span><span class="sxs-lookup"><span data-stu-id="3155d-130">If the form designer isn't visible, double-click on the form in the **Solution Explorer** pane to open the designer window.</span></span>

### <a name="important-parts-of-visual-studio"></a><span data-ttu-id="3155d-131">Visual Studio 的重要部分</span><span class="sxs-lookup"><span data-stu-id="3155d-131">Important parts of Visual Studio</span></span>

<span data-ttu-id="3155d-132">Visual Studio 中对 WinForms 的支持包含四个在创建应用时你将与之交互的重要组件：</span><span class="sxs-lookup"><span data-stu-id="3155d-132">Support for WinForms in Visual Studio has four important components that you'll interact with as you create an app:</span></span>

:::image type="content" source="media/create-app-visual-studio/vs-main-window.png" alt-text="创建适用于 .NET 的 Windows 窗体项目时应了解的 Visual Studio 重要组件":::

01. <span data-ttu-id="3155d-134">“解决方案资源管理器”</span><span class="sxs-lookup"><span data-stu-id="3155d-134">Solution Explorer</span></span>

    <span data-ttu-id="3155d-135">所有项目文件、代码、窗体、资源都将显示在此窗格中。</span><span class="sxs-lookup"><span data-stu-id="3155d-135">All if your project files, code, forms, resources, will appear in this pane.</span></span>

02. <span data-ttu-id="3155d-136">属性</span><span class="sxs-lookup"><span data-stu-id="3155d-136">Properties</span></span>

    <span data-ttu-id="3155d-137">此窗格显示可以基于所选项进行配置的属性设置。</span><span class="sxs-lookup"><span data-stu-id="3155d-137">This pane shows property settings you can configure based on the item selected.</span></span> <span data-ttu-id="3155d-138">例如，如果从“解决方案资源管理器”中选择一个项，你会看到与该文件相关的属性设置。</span><span class="sxs-lookup"><span data-stu-id="3155d-138">For example, if you select an item from **Solution Explorer**, you'll see property settings related to the file.</span></span> <span data-ttu-id="3155d-139">如果在“设计器”中选择一个对象，你会看到控件或窗体的设置。</span><span class="sxs-lookup"><span data-stu-id="3155d-139">If you select an object in the **Designer**, you'll see settings for the control or form.</span></span>

03. <span data-ttu-id="3155d-140">窗体设计器</span><span class="sxs-lookup"><span data-stu-id="3155d-140">Form Designer</span></span>

    <span data-ttu-id="3155d-141">这是窗体的设计器。</span><span class="sxs-lookup"><span data-stu-id="3155d-141">This is the designer for the form.</span></span> <span data-ttu-id="3155d-142">它是交互式的，可以从“工具箱”拖放对象。</span><span class="sxs-lookup"><span data-stu-id="3155d-142">It's interactive and you can drag-and-drop objects from the **Toolbox**.</span></span> <span data-ttu-id="3155d-143">通过在设计器中选择和移动项，可以直观地为应用构建用户界面 (UI)。</span><span class="sxs-lookup"><span data-stu-id="3155d-143">By selecting and moving items in the designer, you can visually compose the user interface (UI) for your app.</span></span>

04. <span data-ttu-id="3155d-144">工具箱</span><span class="sxs-lookup"><span data-stu-id="3155d-144">Toolbox</span></span>

    <span data-ttu-id="3155d-145">工具箱包含可添加到窗体的所有控件。</span><span class="sxs-lookup"><span data-stu-id="3155d-145">The toolbox contains all of the controls you can add to a form.</span></span> <span data-ttu-id="3155d-146">若要将控件添加到当前窗体，请双击控件或拖放控件。</span><span class="sxs-lookup"><span data-stu-id="3155d-146">To add a control to the current form, double-click a control or drag-and-drop the control.</span></span>

## <a name="add-controls-to-the-form"></a><span data-ttu-id="3155d-147">向窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="3155d-147">Add controls to the form</span></span>

<span data-ttu-id="3155d-148">当 Form1 窗体设计器处于打开状态时，使用“工具箱”窗格将以下控件添加到窗体：</span><span class="sxs-lookup"><span data-stu-id="3155d-148">With the _Form1_ form designer open, use the **Toolbox** pane to add the following controls to the form:</span></span>

- <span data-ttu-id="3155d-149">Label</span><span class="sxs-lookup"><span data-stu-id="3155d-149">Label</span></span>
- <span data-ttu-id="3155d-150">Button</span><span class="sxs-lookup"><span data-stu-id="3155d-150">Button</span></span>
- <span data-ttu-id="3155d-151">Listbox</span><span class="sxs-lookup"><span data-stu-id="3155d-151">Listbox</span></span>
- <span data-ttu-id="3155d-152">文本框</span><span class="sxs-lookup"><span data-stu-id="3155d-152">Textbox</span></span>

<span data-ttu-id="3155d-153">可以根据以下设置定位控件并设置其大小。</span><span class="sxs-lookup"><span data-stu-id="3155d-153">You can position and size the controls according to the following settings.</span></span> <span data-ttu-id="3155d-154">以直观方式移动这些控件以匹配下面的屏幕截图，或者单击每个控件并在“属性”窗格中配置设置。</span><span class="sxs-lookup"><span data-stu-id="3155d-154">Either visually move them to match the screenshot that follows, or click on each control and configure the settings in the **Properties** pane.</span></span> <span data-ttu-id="3155d-155">还可以单击窗体标题区域来选择窗体：</span><span class="sxs-lookup"><span data-stu-id="3155d-155">You can also click on the form title area to select the form:</span></span>

| <span data-ttu-id="3155d-156">对象</span><span class="sxs-lookup"><span data-stu-id="3155d-156">Object</span></span>      | <span data-ttu-id="3155d-157">设置</span><span class="sxs-lookup"><span data-stu-id="3155d-157">Setting</span></span>  | <span data-ttu-id="3155d-158">值</span><span class="sxs-lookup"><span data-stu-id="3155d-158">Value</span></span>      |
|-------------|----------|------------|
| <span data-ttu-id="3155d-159">**形式**</span><span class="sxs-lookup"><span data-stu-id="3155d-159">**Form**</span></span>    | <span data-ttu-id="3155d-160">文本</span><span class="sxs-lookup"><span data-stu-id="3155d-160">Text</span></span>     | `Names`    |
|             | <span data-ttu-id="3155d-161">大小</span><span class="sxs-lookup"><span data-stu-id="3155d-161">Size</span></span>     | `268, 180` |
|             |          |            |
| <span data-ttu-id="3155d-162">**Label**</span><span class="sxs-lookup"><span data-stu-id="3155d-162">**Label**</span></span>   | <span data-ttu-id="3155d-163">位置</span><span class="sxs-lookup"><span data-stu-id="3155d-163">Location</span></span> | `12, 9`    |
|             | <span data-ttu-id="3155d-164">文本</span><span class="sxs-lookup"><span data-stu-id="3155d-164">Text</span></span>     | `Names`    |
|             |          |            |
| <span data-ttu-id="3155d-165">**Listbox**</span><span class="sxs-lookup"><span data-stu-id="3155d-165">**Listbox**</span></span> | <span data-ttu-id="3155d-166">名称</span><span class="sxs-lookup"><span data-stu-id="3155d-166">Name</span></span>     | `lstNames` |
|             | <span data-ttu-id="3155d-167">位置</span><span class="sxs-lookup"><span data-stu-id="3155d-167">Location</span></span> | `12, 27`   |
|             | <span data-ttu-id="3155d-168">大小</span><span class="sxs-lookup"><span data-stu-id="3155d-168">Size</span></span>     | `120, 94`  |
|             |          |            |
| <span data-ttu-id="3155d-169">**文本框**</span><span class="sxs-lookup"><span data-stu-id="3155d-169">**Textbox**</span></span> | <span data-ttu-id="3155d-170">名称</span><span class="sxs-lookup"><span data-stu-id="3155d-170">Name</span></span>     | `txtName`  |
|             | <span data-ttu-id="3155d-171">位置</span><span class="sxs-lookup"><span data-stu-id="3155d-171">Location</span></span> | `138, 26`  |
|             | <span data-ttu-id="3155d-172">大小</span><span class="sxs-lookup"><span data-stu-id="3155d-172">Size</span></span>     | `100, 23`  |
|             |          |            |
| <span data-ttu-id="3155d-173">**Button**</span><span class="sxs-lookup"><span data-stu-id="3155d-173">**Button**</span></span>  | <span data-ttu-id="3155d-174">名称</span><span class="sxs-lookup"><span data-stu-id="3155d-174">Name</span></span>     | `btnAdd`   |
|             | <span data-ttu-id="3155d-175">位置</span><span class="sxs-lookup"><span data-stu-id="3155d-175">Location</span></span> | `138, 55`  |
|             | <span data-ttu-id="3155d-176">大小</span><span class="sxs-lookup"><span data-stu-id="3155d-176">Size</span></span>     | `100, 23`  |
|             | <span data-ttu-id="3155d-177">文本</span><span class="sxs-lookup"><span data-stu-id="3155d-177">Text</span></span>     | `Add Name` |

<span data-ttu-id="3155d-178">设计器中应显示类似于以下内容的窗体：</span><span class="sxs-lookup"><span data-stu-id="3155d-178">You should have a form in the designer that looks similar to the following:</span></span>

:::image type="content" source="media/create-app-visual-studio/vs-form-preview.png" alt-text="Visual Studio 2019 设计器，其“适用于 .NET 的 Windows 窗体”窗体处于打开状态":::

## <a name="handle-events"></a><span data-ttu-id="3155d-180">处理事件</span><span class="sxs-lookup"><span data-stu-id="3155d-180">Handle events</span></span>

<span data-ttu-id="3155d-181">现在，窗体已布置好所有控件，你需要处理控件的事件以响应用户输入。</span><span class="sxs-lookup"><span data-stu-id="3155d-181">Now that the form has all of its controls laid out, you need to handle the events of the controls to respond to user input.</span></span> <span data-ttu-id="3155d-182">在窗体设计器仍处于打开状态下，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3155d-182">With the form designer still open, perform the following steps:</span></span>

01. <span data-ttu-id="3155d-183">选择窗体上的按钮控件。</span><span class="sxs-lookup"><span data-stu-id="3155d-183">Select the button control on the form.</span></span>
01. 在“属性”窗格中，单击事件图标 :::image type="icon" source="media/create-app-visual-studio/icon-events.png" border="false"::: 以列出按钮的事件。
01. <span data-ttu-id="3155d-185">找到“单击”事件，然后双击它以生成事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="3155d-185">Find the **Click** event and double-click it to generate an event handler.</span></span>

    <span data-ttu-id="3155d-186">此操作将以下代码添加到窗体：</span><span class="sxs-lookup"><span data-stu-id="3155d-186">This action adds the following code to the the form:</span></span>

    ```csharp
    private void btnAdd_Click(object sender, EventArgs e)
    {

    }
    ```

    ```vb
    Private Sub btnAdd_Click(sender As Object, e As EventArgs) Handles btnAdd.Click

    End Sub
    ```

    <span data-ttu-id="3155d-187">将放入此处理程序的代码会将 `txtName` 文本框控件指定的名称添加到 `lstNames` 列表框控件中。</span><span class="sxs-lookup"><span data-stu-id="3155d-187">The code we'll put in this handler will add the name specified by the `txtName` textbox control to the `lstNames` listbox control.</span></span> <span data-ttu-id="3155d-188">但是，若要添加名称，需要满足两个条件：提供的名称不能为空，且该名称不能已存在。</span><span class="sxs-lookup"><span data-stu-id="3155d-188">However, we want there to be two conditions to adding the name: the name provided must not be blank, and the name must not already exist.</span></span>

01. <span data-ttu-id="3155d-189">以下代码演示如何将名称添加到 `lstNames` 控件：</span><span class="sxs-lookup"><span data-stu-id="3155d-189">The following code demonstrates adding a name to the `lstNames` control:</span></span>

    ```csharp
    private void btnAdd_Click(object sender, EventArgs e)
    {
        if (!string.IsNullOrWhiteSpace(txtName.Text) && !lstNames.Items.Contains(txtName.Text))
            lstNames.Items.Add(txtName.Text);
    }
    ```

    ```vb
    Private Sub btnAdd_Click(sender As Object, e As EventArgs) Handles btnAdd.Click
        If Not String.IsNullOrWhiteSpace(txtName.Text) And Not lstNames.Items.Contains(txtName.Text) Then
            lstNames.Items.Add(txtName.Text)
        End If
    End Sub
    ```

## <a name="run-the-app"></a><span data-ttu-id="3155d-190">运行应用</span><span class="sxs-lookup"><span data-stu-id="3155d-190">Run the app</span></span>

<span data-ttu-id="3155d-191">现在已对事件进行编码，可以通过按 <kbd>F5</kbd> 键或从菜单中选择“调试” > “开始调试”来运行应用 。</span><span class="sxs-lookup"><span data-stu-id="3155d-191">Now that the event has been coded, you can run the app by pressing the <kbd>F5</kbd> key or by selecting **Debug** > **Start Debugging** from the menu.</span></span> <span data-ttu-id="3155d-192">随即显示窗体，可以在文本框中输入名称，然后通过单击按钮添加该名称。</span><span class="sxs-lookup"><span data-stu-id="3155d-192">The form displays and you can enter a name in the textbox and then add it by clicking the button.</span></span>

:::image type="content" source="media/create-app-visual-studio/app-running.png" alt-text="运行适用于 .NET 的 Windows 窗体应用。":::

## <a name="next-steps"></a><span data-ttu-id="3155d-194">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3155d-194">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3155d-195">详细了解 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="3155d-195">Learn more about Windows Forms</span></span>](../overview/index.md)
