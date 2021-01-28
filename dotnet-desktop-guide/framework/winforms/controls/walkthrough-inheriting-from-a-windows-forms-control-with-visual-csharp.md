---
title: 从控件继承
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
ms.openlocfilehash: e49ba47ccc37876c05b5b3440ee5febf128e925e
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957183"
---
# <a name="walkthrough-inherit-from-a-windows-forms-control-with-c"></a>演练：使用 C 从 Windows 窗体控件继承\#

使用 c #，可以通过 *继承* 来创建功能强大的自定义控件。 通过继承，可以创建不仅保留了标准 Windows 窗体控件的所有固有功能，而且还包含自定义功能的控件。 在本演练中，将创建一个名为 `ValueButton` 的简单继承控件。 此按钮将从标准 Windows 窗体控件继承功能 <xref:System.Windows.Forms.Button> ，并将公开一个名为的自定义属性 `ButtonValue` 。

## <a name="create-the-project"></a>创建项目

创建新的项目时应指定其名称，以设置根命名空间、程序集名称和项目名称，并确保默认组件将位于正确的命名空间中。

### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a>创建 ValueButtonLib 控件库和 ValueButton 控件

1. 在 Visual Studio 中，创建一个新的 **Windows 窗体控件库** 项目，并将其命名为 **ValueButtonLib**。

     默认情况下，项目名称 `ValueButtonLib` 也会分配到根命名空间中。 根命名空间用于限定程序集中的组件名。 例如，如果两个程序集都提供名为 `ValueButton` 的组件，则可以使用 `ValueButtonLib.ValueButton` 指定 `ValueButton` 组件。 有关详细信息，请参阅[命名空间](/dotnet/csharp/programming-guide/namespaces/index)。

2. 在“解决方案资源管理器”中，右键单击“UserControl1.cs”，然后从快捷菜单中选择“重命名”。 将文件名更改为 **ValueButton.cs**。 询问是否希望重命名对代码元素“**”的所有引用时，单击“是”**`UserControl1`按钮。

3. 在“解决方案资源管理器”中，右键单击“ValueButton.cs”并选择“查看代码”。

4. 找到 `class` 语句行， `public partial class ValueButton` 并将此控件继承的类型从更改 <xref:System.Windows.Forms.UserControl> 为 <xref:System.Windows.Forms.Button> 。 这允许继承的控件继承控件的所有功能 <xref:System.Windows.Forms.Button> 。

5. 在“解决方案资源管理器”中打开“ValueButton.cs”节点，以显示设计器生成的代码文件 **ValueButton.Designer.cs**。 在 **代码编辑器** 中打开此文件。

6. 找到 `InitializeComponent` 方法并删除分配属性的行 <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> 。 此属性在控件中不存在 <xref:System.Windows.Forms.Button> 。

7. 在“文件”菜单中，选择“全部保存”以保存项目。

    > [!NOTE]
    > 可视化设计器不再可用。 由于 <xref:System.Windows.Forms.Button> 控件执行其自己的绘制，因此无法在设计器中修改其外观。 其视觉对象表示形式将与它继承自 (的类的视觉对象表示形式完全相同， <xref:System.Windows.Forms.Button> 除非在代码中修改了) 。 但仍然可以向设计器图面添加不含 UI 元素的组件。

## <a name="add-a-property-to-your-inherited-control"></a>向继承的控件添加属性

继承的 Windows 窗体控件的可能用途之一是创建与标准 Windows 窗体控件的外观和感受相同、但公开自定义属性的控件。 在本节中，将向控件中添加名为 `ButtonValue` 的属性。

### <a name="to-add-the-value-property"></a>添加 Value 属性

1. 在“解决方案资源管理器”中，右键单击“ValueButton.cs”，然后从快捷菜单中单击“查看代码”。

2. 找到 `class` 语句。 紧接 `{` 之后键入以下代码：

    ```csharp
    // Creates the private variable that will store the value of your
    // property.
    private int varValue;
    // Declares the property.
    public int ButtonValue
    {
       // Sets the method for retrieving the value of your property.
       get
       {
          return varValue;
       }
       // Sets the method for setting the value of your property.
       set
       {
          varValue = value;
       }
    }
    ```

     此代码设置存储和检索 `ButtonValue` 属性的方法。 `get` 语句将返回的值设置为存储在私有变量 `varValue` 中的值，而 `set` 语句通过使用 `value` 关键字设置该私有变量的值。

3. 在“文件”菜单中，选择“全部保存”以保存项目。

## <a name="test-the-control"></a>测试控件

控件不是独立的项目，它们必须托管在容器中。 若要测试控件，必须提供一个测试项目，以使控件在其中运行。 还必须通过生成（编译）该控件使测试项目能够访问它。 在本节中，将生成控件并在 Windows 窗体中对其进行测试。

### <a name="to-build-your-control"></a>生成控件

在 **“生成”** 菜单上，单击 **“生成解决方案”** 。 生成应会成功，且没有任何编译器错误或警告。

### <a name="to-create-a-test-project"></a>创建测试项目

1. 在“文件”菜单上，指向“添加”，然后单击“新建项目”打开“添加新项目”对话框。

2. 在“Visual C#”节点下选择“Windows”节点，再单击“Windows 窗体应用程序”。

3. 在 " **名称** " 框中，输入 **Test**。

4. 在“解决方案资源管理器”中，右键单击测试项目的“引用”节点，然后从快捷菜单上选择“添加引用”以显示“添加引用”对话框。

5. 单击标记为“项目”的选项卡。 你的 ValueButtonLib 项目将在 " **项目名称**" 下列出。 双击该项目将引用添加到测试项目。

6. 在“解决方案资源管理器”中，右键单击“测试”，然后选择“生成”。

### <a name="to-add-your-control-to-the-form"></a>将控件添加到窗体

1. 在“解决方案资源管理器”中，右键单击“Form1.cs”，然后从快捷菜单中选择“视图设计器”。

2. 在 " **工具箱**" 中，选择 " **ValueButtonLib 组件**"。 双击“ValueButton”。

     窗体上将出现“ValueButton”。

3. 右键单击“ValueButton”，并从快捷菜单中选择“属性”。

4. 在“属性”窗口中，检查该控件的属性。 请注意，它们与标准按钮公开的属性相同，不同之处在于还有一个附加属性 ButtonValue。

5. 将 **ButtonValue** 属性设置为 **5**。

6. 在 "**工具箱**" 的 "**所有 Windows 窗体**" 选项卡中，双击 "**标签**" 将 <xref:System.Windows.Forms.Label> 控件添加到窗体。

7. 将标签重新定位到窗体的中央。

8. 双击 `valueButton1`。

     “代码编辑器”随即打开并显示 `valueButton1_Click` 事件。

9. 插入以下代码行。

    ```csharp
    label1.Text = valueButton1.ButtonValue.ToString();
    ```

10. 在“解决方案资源管理器”中，右键单击“测试”，然后从快捷菜单中选择“设为启动项目”。

11. 从“调试”菜单中选择“启动调试”。

     `Form1` 将出现。

12. 单击 `valueButton1`。

     `label1` 中显示数字“5”，表明继承的控件的 `ButtonValue` 属性已通过 `valueButton1_Click` 方法传递给 `label1`。 这样，`ValueButton` 控件便继承了标准 Windows 窗体按钮的所有功能，但是公开了一个附加的自定义属性。

## <a name="see-also"></a>另请参阅

- [如何：在“选择工具箱项”对话框中显示控件](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [演练：使用 Visual C# 创作复合控件](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
