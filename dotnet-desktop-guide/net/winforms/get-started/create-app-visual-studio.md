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
# <a name="tutorial-create-a-new-winforms-app-windows-forms-net"></a>教程：创建新的 WinForms 应用（Windows 窗体 .NET）

本简短教程将介绍如何使用 Visual Studio 创建新的 Windows 窗体 (WinForms) 应用。 生成初始应用后，你将了解如何添加控件以及如何处理事件。 学完本教程后，你将拥有一个可将名称添加到列表框的简单应用。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

在本教程中，你将了解如何执行以下操作：

> [!div class="checklist"]
>
> - 创建新的 WinForms 应用
> - 将控件添加到窗体
> - 处理控制事件以提供应用功能
> - 运行应用

## <a name="prerequisites"></a>先决条件

- [Visual Studio 2019 版本 16.8 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms)
  - 选择 [Visual Studio Desktop 工作负载](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)
  - 选择 [.NET 5 单个组件](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)

## <a name="create-a-winforms-app"></a>创建 WinForms 应用

创建新应用的第一步是打开 Visual Studio 并通过模板生成应用。

01. 打开 Visual Studio。
01. 选择“创建新项目”。

    :::image type="content" source="media/create-app-visual-studio/vs-create-new-project.png" alt-text="在 Visual Studio 2019 中创建适用于 .NET 的新 Windows 窗体项目":::

01. 在“搜索模板”框中，键入“winforms”，然后按 <kbd>Enter</kbd> 。
01. 在“代码语言”下拉列表中，选择“C#”或“Visual Basic”  。
01. 在模板列表中，选择“Windows 窗体应用 (.NET)”，然后单击“下一步” 。

    > [!IMPORTANT]
    > 请勿选择“Windows 窗体应用 (.NET Framework)”模板。

    :::image type="content" source="media/create-app-visual-studio/vs-template-search.png" alt-text="在 Visual Studio 2019 中搜索适用于 .NET 的 Windows 窗体模板":::

01. 在“配置新项目”窗口中，将“项目名称”设置为“Names”，然后单击“创建”   。

    还可以通过调整“位置”设置将项目保存到其他文件夹。

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project.png" alt-text="在 Visual Studio 2019 中配置适用于 .NET 的新 Windows 窗体项目":::

生成应用后，Visual Studio 应会打开默认窗体 Form1 的设计器窗格。 如果看不到窗体设计器，请在“解决方案资源管理器”窗格中双击该窗体以打开设计器窗口。

### <a name="important-parts-of-visual-studio"></a>Visual Studio 的重要部分

Visual Studio 中对 WinForms 的支持包含四个在创建应用时你将与之交互的重要组件：

:::image type="content" source="media/create-app-visual-studio/vs-main-window.png" alt-text="创建适用于 .NET 的 Windows 窗体项目时应了解的 Visual Studio 重要组件":::

01. “解决方案资源管理器”

    所有项目文件、代码、窗体、资源都将显示在此窗格中。

02. 属性

    此窗格显示可以基于所选项进行配置的属性设置。 例如，如果从“解决方案资源管理器”中选择一个项，你会看到与该文件相关的属性设置。 如果在“设计器”中选择一个对象，你会看到控件或窗体的设置。

03. 窗体设计器

    这是窗体的设计器。 它是交互式的，可以从“工具箱”拖放对象。 通过在设计器中选择和移动项，可以直观地为应用构建用户界面 (UI)。

04. 工具箱

    工具箱包含可添加到窗体的所有控件。 若要将控件添加到当前窗体，请双击控件或拖放控件。

## <a name="add-controls-to-the-form"></a>向窗体添加控件

当 Form1 窗体设计器处于打开状态时，使用“工具箱”窗格将以下控件添加到窗体：

- Label
- Button
- Listbox
- 文本框

可以根据以下设置定位控件并设置其大小。 以直观方式移动这些控件以匹配下面的屏幕截图，或者单击每个控件并在“属性”窗格中配置设置。 还可以单击窗体标题区域来选择窗体：

| 对象      | 设置  | 值      |
|-------------|----------|------------|
| **形式**    | 文本     | `Names`    |
|             | 大小     | `268, 180` |
|             |          |            |
| **Label**   | 位置 | `12, 9`    |
|             | 文本     | `Names`    |
|             |          |            |
| **Listbox** | 名称     | `lstNames` |
|             | 位置 | `12, 27`   |
|             | 大小     | `120, 94`  |
|             |          |            |
| **文本框** | 名称     | `txtName`  |
|             | 位置 | `138, 26`  |
|             | 大小     | `100, 23`  |
|             |          |            |
| **Button**  | 名称     | `btnAdd`   |
|             | 位置 | `138, 55`  |
|             | 大小     | `100, 23`  |
|             | 文本     | `Add Name` |

设计器中应显示类似于以下内容的窗体：

:::image type="content" source="media/create-app-visual-studio/vs-form-preview.png" alt-text="Visual Studio 2019 设计器，其“适用于 .NET 的 Windows 窗体”窗体处于打开状态":::

## <a name="handle-events"></a>处理事件

现在，窗体已布置好所有控件，你需要处理控件的事件以响应用户输入。 在窗体设计器仍处于打开状态下，请执行以下步骤：

01. 选择窗体上的按钮控件。
01. 在“属性”窗格中，单击事件图标 :::image type="icon" source="media/create-app-visual-studio/icon-events.png" border="false"::: 以列出按钮的事件。
01. 找到“单击”事件，然后双击它以生成事件处理程序。

    此操作将以下代码添加到窗体：

    ```csharp
    private void btnAdd_Click(object sender, EventArgs e)
    {

    }
    ```

    ```vb
    Private Sub btnAdd_Click(sender As Object, e As EventArgs) Handles btnAdd.Click

    End Sub
    ```

    将放入此处理程序的代码会将 `txtName` 文本框控件指定的名称添加到 `lstNames` 列表框控件中。 但是，若要添加名称，需要满足两个条件：提供的名称不能为空，且该名称不能已存在。

01. 以下代码演示如何将名称添加到 `lstNames` 控件：

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

## <a name="run-the-app"></a>运行应用

现在已对事件进行编码，可以通过按 <kbd>F5</kbd> 键或从菜单中选择“调试” > “开始调试”来运行应用 。 随即显示窗体，可以在文本框中输入名称，然后通过单击按钮添加该名称。

:::image type="content" source="media/create-app-visual-studio/app-running.png" alt-text="运行适用于 .NET 的 Windows 窗体应用。":::

## <a name="next-steps"></a>后续步骤

> [!div class="nextstepaction"]
> [详细了解 Windows 窗体](../overview/index.md)
