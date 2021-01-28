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
ms.openlocfilehash: 3827be560c097685e1448b65704a943618b2b45d
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957196"
---
# <a name="walkthrough-debug-custom-windows-forms-controls-at-design-time"></a>演练：在设计时调试自定义 Windows 窗体控件

当您创建自定义控件时，您通常会发现有必要调试其设计时行为。 如果要为自定义控件创作自定义设计器，则这一点尤其如此。 有关详细信息，请参阅 [演练：创建利用 Visual Studio Design-Time 功能的 Windows 窗体控件](creating-a-wf-control-design-time-features.md)。

您可以使用 Visual Studio 调试自定义控件，就像调试任何其他 .NET Framework 类一样。 不同之处在于，您将调试运行您的自定义控件的代码的单独的 Visual Studio 实例。

## <a name="create-the-project"></a>创建项目

第一步是创建应用程序项目。 将使用此项目生成承载自定义控件的应用程序。

在 Visual Studio 中，创建一个 Windows 应用程序项目，并将其命名为 **DebuggingExample**。

## <a name="create-the-control-library-project"></a>创建控件库项目

1. 将 **Windows 控件库** 项目添加到解决方案。

2. 向 DebugControlLibrary 项目添加一个新的 **UserControl** 项。 将其命名为 **DebugControl**。

3. 在 **解决方案资源管理器** 中，通过删除基名称为 UserControl1 的代码文件删除项目的默认控件。

4. 生成解决方案。

## <a name="checkpoint"></a>Checkpoint

此时，您将能够在 **工具箱** 中看到您的自定义控件。

若要检查进度，请找到名为 **DebugControlLibrary** 的新选项卡，并单击以将其选中。 当它打开时，你将看到控件作为 **DebugControl** 列出，其旁边显示了默认图标。

## <a name="add-a-property-to-your-custom-control"></a>向自定义控件添加属性

为了演示自定义控件的代码在设计时运行，您将添加一个属性并在实现属性的代码中设置断点。

1. 在 **代码编辑器** 中打开 **DebugControl** 。 在类定义中添加以下代码：

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

2. 生成解决方案。

## <a name="add-your-custom-control-to-the-host-form"></a>向宿主窗体添加自定义控件

若要调试自定义控件的设计时行为，你需要将自定义控件类的实例放置在主机窗体上。

1. 在 "DebuggingExample" 项目中，在 **Windows 窗体设计器** 中打开 "Form1"。

2. 在 " **工具箱**" 中，打开 " **DebugControlLibrary 组件** " 选项卡，并将 " **DebugControl** " 实例拖到窗体上。

3. `DemoString`在 "**属性**" 窗口中查找自定义属性。 请注意，您可以像更改任何其他属性一样更改其值。 另请注意，在 `DemoString` 选择属性后，属性的说明字符串会出现在 " **属性** " 窗口的底部。

## <a name="set-up-the-project-for-design-time-debugging"></a>设置项目以进行设计时调试

若要调试自定义控件的设计时行为，您将调试运行您的自定义控件的代码的单独的 Visual Studio 实例。

1. 右键单击 "**解决方案资源管理器** 中的 **DebugControlLibrary** 项目，然后选择"**属性**"。

2. 在 **DebugControlLibrary** 属性表中，选择 " **调试** " 选项卡。

     在 " **启动操作** " 部分中，选择 " **启动外部程序**"。 你将调试一个单独的 Visual Studio 实例，因此单击 " ![ visual) studio 的属性窗口中的省略号按钮 ( ... ) " ("， ](./media/visual-studio-ellipsis-button.png) 以浏览 VISUAL studio IDE。 可执行文件的名称是 **devenv.exe** 的，如果你已安装到默认位置，则其路径为 *% ProgramFiles (x86) % \ Microsoft Visual Studio\2019 \\ \<edition> \Common7\IDE*。

3. 选择“确定”关闭对话框  。

4. 右键单击 " **DebugControlLibrary** " 项目，然后选择 " **设为启动项目** " 来启用此调试配置。

## <a name="debug-your-custom-control-at-design-time"></a>在设计时调试自定义控件

现在，你已准备好调试自定义控件，因为它在设计模式下运行。 当你启动调试会话时，将创建一个新的 Visual Studio 实例，你将使用它来加载 "DebuggingExample" 解决方案。 在 **窗体设计器** 中打开 Form1 时，将创建自定义控件的一个实例，并将开始运行。

1. 在 **代码编辑器** 中打开 **DebugControl** 源文件，并在属性的访问器上放置一个断点 `Set` `DemoString` 。

2. 按 **F5** 启动调试会话。 创建 Visual Studio 的新实例。 可以通过两种方式区分实例：

    - 调试实例的标题栏中有一个 **运行** 的词

    - 调试实例禁用了其 **调试** 工具栏上的 "**启动**" 按钮

   在调试实例中设置断点。

3. 在 Visual Studio 的新实例中，打开 "DebuggingExample" 解决方案。 通过从 "**文件**" 菜单中选择 "**最近使用的项目**"，可以轻松地找到解决方案。 "DebuggingExample" 解决方案文件将作为最近使用过的文件列出。

4. 在 **窗体设计器** 中打开 "Form1"，然后选择 " **DebugControl** " 控件。

5. 更改 `DemoString` 属性的值。 提交更改时，Visual Studio 的调试实例将获取焦点，并在断点处停止执行。 您可以单步执行属性访问器，就像对待任何其他代码一样。

6. 若要停止调试，请退出 Visual Studio 的托管实例，或在调试实例中选择 " **停止调试** " 按钮。

## <a name="next-steps"></a>后续步骤

现在你可以在设计时调试自定义控件，因此可以通过许多方式来扩展控件与 Visual Studio IDE 的交互。

- 您可以使用 <xref:System.ComponentModel.Component.DesignMode%2A> 类的属性 <xref:System.ComponentModel.Component> 来编写仅在设计时执行的代码。 有关详细信息，请参阅 <xref:System.ComponentModel.Component.DesignMode%2A>。

- 可以将多个属性应用于控件的属性，以操作自定义控件与设计器的交互。 可在命名空间中找到这些属性 <xref:System.ComponentModel?displayProperty=nameWithType> 。

- 可以编写自定义控件的自定义设计器。 这使你可以使用由 Visual Studio 公开的可扩展设计器基础结构来完全控制设计体验。 有关详细信息，请参阅 [演练：创建利用 Visual Studio Design-Time 功能的 Windows 窗体控件](creating-a-wf-control-design-time-features.md)。

## <a name="see-also"></a>另请参阅

- [演练：创建利用 Visual Studio Design-Time 功能的 Windows 窗体控件](creating-a-wf-control-design-time-features.md)
