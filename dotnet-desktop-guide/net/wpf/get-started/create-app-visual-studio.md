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
# <a name="tutorial-create-a-new-wpf-app-wpf-net"></a>教程：创建新的 WPF 应用 (WPF .NET)

本简短教程将介绍如何使用 Visual Studio 创建新的 Windows Presentation Foundation (WPF) 应用。 生成初始应用后，你将了解如何添加控件以及如何处理事件。 学完本教程后，你将拥有一个可将名称添加到列表框的简单应用。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

在本教程中，你将了解如何执行以下操作：

> [!div class="checklist"]
>
> - 创建新的 WPF 应用
> - 将控件添加到窗体
> - 处理控制事件以提供应用功能
> - 运行应用

下面是按照本教程生成的应用的预览：

:::image type="content" source="media/create-app-visual-studio/app-finished.png" alt-text="已完成的 WPF 示例应用教程":::

## <a name="prerequisites"></a>先决条件

- [Visual Studio 2019 版本 16.8.4 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+wpf)
  - 选择 [Visual Studio Desktop 工作负载](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)
  - 选择 [.NET 5 单个组件](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)

## <a name="create-a-wpf-app"></a>创建 WPF 应用

创建新应用的第一步是打开 Visual Studio 并通过模板生成应用。

01. 打开 Visual Studio。
01. 选择“创建新项目”。

    :::image type="content" source="media/create-app-visual-studio/vs-create-new-project.png" alt-text="在 Visual Studio 2019 中创建适用于 .NET 的新 WPF 项目":::

01. 在“搜索模板”框中，键入“wpf”，然后按 <kbd>Enter</kbd> 。
01. 在“代码语言”下拉列表中，选择“C#”或“Visual Basic”  。
01. 在模板列表中，选择“WPF 应用程序”，然后选择“下一步”。

    > [!IMPORTANT]
    > 请勿选择“WPF 应用程序(.NET Framework)”模板。

    :::image type="content" source="media/create-app-visual-studio/vs-template-search-16.8.png" alt-text="在 Visual Studio 2019 中搜索适用于 .NET 的 WPF 模板":::

01. 在“配置新项目”窗口中，执行以下操作：

    01. 在“项目名称”框中，输入“Names”。
    01. 选中“将解决方案和项目放在同一目录中”复选框。
    01. （可选）选择其他位置以保存代码。
    01. 选择“创建”按钮。

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project-16.8.png" alt-text="在 Visual Studio 2019 中配置适用于 .NET 的新 WPF 项目":::

<!-- THIS IS FOR 16.9 when it's released. Also, change the last child step of the previous step to **Next**

01. In the **Additional information** window, select **.NET 5.0 (Current)** for **Target Framework** and make sure that the **Run on .NET Framework** check box is cleared. Select the **Create** button.

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project-next.png" alt-text="Select target framework for new WPF project in Visual Studio 2019 for .NET":::
-->

生成应用后，Visual Studio 应会打开默认窗口 MainWindow 的 XAML 设计器窗格。 如果看不到设计器，请在“解决方案资源管理器”窗格中双击 MainWindow.xaml 文件以打开设计器。

### <a name="important-parts-of-visual-studio"></a>Visual Studio 的重要部分

Visual Studio 中对 WPF 的支持包含五个在创建应用时你将与之交互的重要组件：

:::image type="content" source="media/create-app-visual-studio/vs-main-window.png" alt-text="创建适用于 .NET 的 WPF 项目时应了解的 Visual Studio 重要组件":::

01. 解决方案资源管理器

    所有项目文件、代码、窗口、资源都将显示在此窗格中。

02. 属性

    此窗格显示可以基于所选项进行配置的属性设置。 例如，如果从“解决方案资源管理器”中选择一个项，你会看到与该文件相关的属性设置。 如果在“设计器”中选择一个对象，你会看到该项目的设置。

03. 工具箱

    工具箱包含可添加到窗体的所有控件。 若要将控件添加到当前窗体，请双击控件或拖放控件。

04. XAML 设计器

    这是 XAML 文档的设计器。 它是交互式的，可以从“工具箱”拖放对象。 通过在设计器中选择和移动项，可以直观地为应用构建用户界面 (UI)。

    当设计器和编辑器都可见时，对设计器的更改会反映在编辑器中，反之亦然。 在设计器中选择项目时，“属性”窗格会显示有关该对象的属性和特性。

05. XAML 代码编辑器

    这是 XAML 文档的 XAML 代码编辑器。 XAML 代码编辑器是一种无需设计器即可手动创建 UI 的方法。 将控件添加到设计器中时，设计器可以推断控件上的属性值。 XAML 代码编辑器则为你提供更多控制权。

    当设计器和编辑器都可见时，对设计器的更改会反映在编辑器中，反之亦然。 在代码编辑器中导航文本插入点时，“属性”窗格会显示有关该对象的属性和特性。

## <a name="target-net-50"></a>面向 .NET 5.0

创建项目后，将目标框架更改为 .NET 5.0。 在“解决方案资源管理器”中双击“Names”项目文件。 这将打开项目文件进行编辑。 将 `<TargetFramework>` 元素设置为 `net5.0-windows`：

```xml
<TargetFramework>net5.0-windows</TargetFramework>
```

保存项目文件，然后关闭编辑器选项卡。

## <a name="examine-the-xaml"></a>检查 XAML

创建项目后，将显示 XAML 代码编辑器，并以最少的 XAML 代码显示窗口。 如果编辑器未打开，请在“解决方案资源管理器”中双击“MainWindow.xaml”项目。 你应该会看到类似于以下内容的 XAML：

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

让我们分解此 XAML 代码，以便更好地了解它。 XAML 就是可由 WPF 使用的编译器进行处理的 XML。 它描述 WPF UI 并与 .NET 代码进行交互。 若要了解 XAML，至少应熟悉 XML 的基础知识。

文档根 `<Window>` 表示 XAML 文件描述的对象的类型。 它声明八个特性，这些特性通常分为三类：

- 命名空间

  XML 命名空间为 XML 提供结构，确定允许或不允许在文件中声明的内容。

  主要 `xmlns` 特性将导入整个文件的 XML 命名空间，在本例中，将映射到 WPF 声明的类型。 其他 XML 命名空间声明一个前缀，并导入 XAML 文件的其他类型和对象。 例如，`xmlns:local` 命名空间声明 `local` 前缀，并映射到项目声明的对象，即，在 `Names` 代码命名空间中声明的对象。

- `x:Class` 特性

  此特性将 `<Window>` 映射到代码定义的类型：MainWindow.xaml.cs 或 MainWindow.xaml.vb 文件，即 `Names.MainWindow` 类。

- `Title` 特性

  在 XAML 对象上声明的任何常规特性都会设置该对象的属性。 在本例中，`Title` 特性将设置 `Window.Title` 属性。

## <a name="change-the-window"></a>更改窗口

首先，让我们运行项目并查看默认输出。 你会看到一个没有任何控件且标题为 MainWindow 的弹出窗口：

:::image type="content" source="media/create-app-visual-studio/app-default.png" alt-text="空白的 WPF 应用":::

对于我们的示例应用，此窗口太大，并且标题栏不是描述性的。 通过将 XAML 中的相应特性更改为以下值，来更改窗口的标题和大小：

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/Start.xaml" highlight="8":::

## <a name="prepare-the-layout"></a>准备布局

WPF 提供一个功能强大的布局系统，其中包含许多不同的布局控件。 布局控件可帮助放置子控件和调整其大小，甚至可以自动执行这些操作。 此 XAML 中提供给你的默认布局控件是 `<Grid>` 控件。

通过使用 `Grid` 控件，可以像定义表一样定义行和列，并将控件置于特定行和列组合的边界内。 你可以将任意数量的子控件或其他布局控件添加到 `Grid` 中。 例如，你可以在特定的行和列组合中放置另一个 `Grid` 控件，然后新的 `Grid` 可以定义更多的行和列，并拥有自己的子级。

`<Grid>` 控件定义控件所在的行和列。 网格始终只声明单行和单列，这意味着默认情况下，网格就是一个单元格。 这并不能让你真正灵活地放置控件。

在添加新的行和列之前，请向 `<Grid>` 元素添加一个新特性：`Margin="10"`。 这样就可以从窗口中插入网格，使它看起来更漂亮一些。

接下来，定义两行两列，将网格划分为四个单元格：

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep2.xaml" highlight="9-21":::

在 XAML 代码编辑器或 XAML 设计器中选择网格，你将看到 XAML 设计器显示每一行和每一列：

:::image type="content" source="media/create-app-visual-studio/vs-designer-grid-rows-columns.png" alt-text="在网格上设置了边距的 WPF 应用":::

## <a name="add-the-first-control"></a>添加第一个控件

现在已经创建了网格，接下来可以开始向其添加控件。 首先，从标签控件开始。 在 `<Grid>` 元素内的行定义和列定义后面创建一个新的 `<Label>` 元素，并为其指定字符串值 `Names`：

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep3.xaml" range="9-23" highlight="13":::

`<Label>Names</Label>` 定义内容 `Names`。 有些控件知道如何处理内容，有些则不知道。 控件的内容映射到 `Content` 属性。 通过 XAML 特性语法设置内容时，将使用以下格式：`<Label Content="Names" />`。 这两种方法可以实现相同的目的，即，将标签内容设置为显示文本 `Names`。

不过，我们有一个问题，由于标签是自动分配给网格的第一行和第一列的，因此它占据了半个窗口。 对于第一行，我们不需要那么多空间，因为我们只需要在这一行放置标签。 将第一个 `<RowDefinition>` 的 `Height` 特性从 `*` 更改为 `Auto`。 `Auto` 值会自动将网格行的大小调整为其内容（在本例中为标签控件）的大小。

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep4.xaml" range="11-14" highlight="2":::

请注意，设计器现在显示标签占据的可用高度较少。 现在，下一行有更多空间可用。 大多数控件会定义应该占用的最适合自己的某种高度和宽度值。 对于标签控件，其高度值可确保你可以读取它。

:::image type="content" source="media/create-app-visual-studio/vs-designer-grid-rows-columns-label.png" alt-text="在网格上设置了边距并且第一行有标签控件的 WPF 应用":::

### <a name="control-placement"></a>控件放置

让我们谈谈控件的放置。 上一部分中创建的标签已自动放置在网格的第 0 行和第 0 列。 行和列的编号从 0 开始，每新增一行或一列，编号就递增 1。 控件无法识别网格，并且不会定义任何属性来控制其在网格中的位置。 控件甚至可能放置在其他布局控件中，后者有自己的一组规则来定义如何放置控件。

当控件无法识别网格时，如何告诉控件使用其他行或列？ 附加属性！ 网格采用 WPF 提供的强大属性系统。 网格定义了子控件可以声明和使用的新属性。 控件本身其实并不存在这些属性，它们是在将控件添加到网格时由网格附加的。

网格定义两个属性来确定子控件的行和列位置：`Grid.Row` 和 `Grid.Column`。 如果控件中省略了这些属性，则意味着它们的默认值为 0，因此，控件将放置在网格的第 `0` 行和第 `0` 列。 尝试通过将 `Grid.Column` 属性设置为 `1` 来更改 `<Label>` 控件的位置：

```xaml
<Label Grid.Column="1">Names</Label>
```

注意标签现在如何移动到第二列。 你可以使用 `Grid.Row` 和 `Grid.Column` 附加属性来放置我们接下来要创建的控件。 不过现在，请将标签还原到第 0 行。

## <a name="create-the-name-list-box"></a>创建名称列表框

现在已经正确调整了网格的大小并创建了标签，接下来，在标签下方的行中添加一个列表框控件。 列表框将位于第 `1` 行和第 `0` 列。 我们还将此控件命名为 `lstNames`。 为控件命名后，即可在代码隐藏中对其进行引用。 该名称通过 `x:Name` 特性分配给控件。

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls1.xaml" range="9-24" highlight="14":::

## <a name="add-the-remaining-controls"></a>添加其余控件

我们将添加的最后两个控件是一个文本框和一个按钮，用户将使用它们来输入要添加到列表框中的名称。 但是，我们没有尝试为网格创建更多行和列，而是将这些控件放入 `<StackPanel>` 布局控件中。

堆叠面板与网格的不同之处在于控件的放置方式。 你告诉网格你希望使用 `Grid.Row` 和 `Grid.Column` 附加属性将控件放置在哪个位置，堆叠面板则自动按以下方式运行：先放置第一个控件，然后将下一个控件置于其后，一直到所有控件都放置完毕。 它将每个控件“堆叠”在另一个控件之下。

在列表框后创建 `<StackPanel>` 控件，并将其放在网格的第 `1` 行、第 `1` 列。 另外添加一个名为 `Margin` 且值为 `5,0,0,0` 的特性：

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls2.xaml" id="StackPanel1":::

之前在网格上使用了 `Margin` 特性，但我们只输入了一个值 (`10`)。 现在，我们在堆叠面板上使用了值 `5,0,0,0`。 边距是 `Thickness` 类型，可以解释这两个值。 粗细定义矩形框每条边（分别为左、顶、右、底）周围的空间。 如果边距的值是单一值，则四条边均使用该值。

接下来，在 `<StackPanel>` 中创建 `<TextBox>` 和 `<Button>` 控件。

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls2.xaml" id="StackPanel2":::

窗口的布局已完成。 但是，我们的应用不包含任何逻辑，无法真正发挥作用。 接下来，我们需要将控件事件挂钩到代码，让应用能够实际派上用场。

## <a name="add-code-for-the-click-event"></a>为 Click 事件添加代码

我们创建的 `<Button>` 具有一个 `Click` 事件，该事件在用户按下按钮时引发。 你可以订阅此事件并添加代码，以便向列表框添加名称。 就像通过添加 XAML 特性在控件上设置属性一样，你可以使用 XAML 特性来订阅事件。 将 `Click` 特性设置为 `ButtonAddName_Click`

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls3.xaml" id="ButtonEvent" highlight="3":::

现在，你需要生成处理程序代码。 右键单击 `ButtonAddName_Click`，然后选择“转到定义”。 这将在代码隐藏中为你生成一个与你输入的处理程序名称匹配的方法。

:::code language="csharp" source="snippets/create-app-visual-studio/csharp/MoreControls3.xaml.cs" id="ButtonEvent":::
:::code language="vb" source="snippets/create-app-visual-studio/vb/MoreControls3.xaml.vb" id="ButtonEvent":::

接下来，添加以下代码以执行这三个步骤：

01. 确保文本框包含名称。
01. 验证文本框中输入的名称是否已经存在。
01. 将名称添加到列表框。

:::code language="csharp" source="snippets/create-app-visual-studio/csharp/Final.xaml.cs" id="FinalCode":::
:::code language="vb" source="snippets/create-app-visual-studio/vb/Final.xaml.vb" id="FinalCode":::

## <a name="run-the-app"></a>运行应用

现在已对事件进行编码，可以通过按 <kbd>F5</kbd> 键或从菜单中选择“调试” > “开始调试”来运行应用 。 随即显示窗口，可以在文本框中输入名称，然后通过单击按钮添加该名称。

:::image type="content" source="media/create-app-visual-studio/app-finished.png" alt-text="正在运行适用于 .NET 的 Windows Presentation Foundation (WPF) 应用。":::

## <a name="next-steps"></a>后续步骤

> [!div class="nextstepaction"]
> [详细了解 Windows Presentation Foundation](../overview/index.md)
