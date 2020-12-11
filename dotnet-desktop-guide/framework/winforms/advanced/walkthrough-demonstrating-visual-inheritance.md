---
title: 演练：演示可视化继承
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
ms.openlocfilehash: af59383472ed4a5b8ca9585ba359c3bb8bb4e912
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971577"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a>演练：演示可视化继承

通过 Visual 继承，可以查看基本表单上的控件和添加新控件。 在本演练中，你将创建基窗体，并将其编译到类库。 将此类库导入另一个项目，并创建一个从基窗体继承的新窗体。 在本演练中，你将学会如何执行以下任务：

- 创建包含基窗体的类库项目。

- 添加具有可修改基窗体的派生类的属性的按钮。

- 添加基窗体的继承者无法修改的按钮。

- 创建包含从 `BaseForm` 继承的窗体的项目。

最后，本演练将显示继承的窗体上私有控件和受保护控件之间的差异。

> [!CAUTION]
> 并非所有控件都支持从基窗体执行 Visual 继承。 以下控件不支持本演练中描述的情景：
>
> - <xref:System.Windows.Forms.WebBrowser>
>
> - <xref:System.Windows.Forms.ToolStrip>
>
> - <xref:System.Windows.Forms.ToolStripPanel>
>
> - <xref:System.Windows.Forms.TableLayoutPanel>
>
> - <xref:System.Windows.Forms.FlowLayoutPanel>
>
> - <xref:System.Windows.Forms.DataGridView>
>
> 无论使用何种修饰符（`private``protected` 或 `public`），继承的窗体中的这些控件始终为只读。

## <a name="create-a-class-library-project-containing-a-base-form"></a>创建包含基窗体的类库项目

1. 在 Visual Studio 的 "**文件**" 菜单中，选择 "**新建**  >  **项目**" 以打开 "**新建项目**" 对话框。

2. 创建一个名为的 Windows 窗体应用程序 `BaseFormLibrary` 。

3. 若要创建类库而不是标准 Windows 窗体应用程序，请在 **解决方案资源管理器** 中右键单击 " **BaseFormLibrary** " 项目节点，然后选择 " **属性**"。

4. 在项目的属性中，将 "**输出类型**" 从 " **Windows 应用程序**" 更改为 **"类库"。**

5. 从 " **文件** " 菜单中，选择 " **全部保存** " 以将项目和文件保存到默认位置。

接下来的两步是将按钮添加至基窗体。 为了演示 visual 继承，请通过设置按钮的 `Modifiers` 属性为它们指定不同的访问级别。

## <a name="add-a-button-that-inheritors-of-the-base-form-can-modify"></a>添加一个按钮，使基窗体的继承者可以修改

1. 在设计器中打开“Form1”。

2. 在 "**工具箱**" 的 "**所有 Windows 窗体**" 选项卡上，双击 "**按钮**" 向窗体添加一个按钮。 使用鼠标来定位按钮和调整其大小。

3. 在“属性”窗口中，设置按钮的下列属性：

    - 将 **Text** 属性设置为 " **Hello**"。

    - 将 **(名称)** 属性设置为 " **btnProtected**"。

    - 将 " **修饰符** " 属性设置为 " **受保护**"。 这使得从 **Form1** 继承的窗体有可能修改 **btnProtected** 的属性。

4. 双击 " **朗读** " 按钮，为 **click** 事件添加事件处理程序。

5. 将以下代码行添加到事件处理程序：

    ```vb
    MessageBox.Show("Hello, World!")
    ```

    ```csharp
    MessageBox.Show("Hello, World!");
    ```

## <a name="add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a>添加基窗体的继承者无法修改的按钮

1. 通过单击代码编辑器上方的 " **Form1 [design]"、"Form1.cs [design]" 或 "Form1.jsl [设计]** " 选项卡，或者按 F7，切换到 "设计" 视图。

2. 按如下方式添加第二个按钮并设置其属性：

    - 将 **Text** 属性设置为 **再见**。

    - 将 **(名称)** 属性设置为 " **btnPrivate**"。

    - 将 " **修饰符** " 属性设置为 " **私有**"。 这使得从 **Form1** 继承的窗体无法修改 **btnPrivate** 的属性。

3. 双击 "向 **再见** " 按钮，为 **click** 事件添加事件处理程序。 将以下代码行放入事件过程：

    ```vb
    MessageBox.Show("Goodbye!")
    ```

    ```csharp
    MessageBox.Show("Goodbye!");
    ```

4. 在 " **生成** " 菜单中，选择 " **生成 BaseForm 库** " 以生成类库。

     构建库后，可创建从刚创建的窗体继承的新项目。

## <a name="create-a-project-containing-a-form-that-inherits-from-the-base-form"></a>创建一个包含继承自基窗体的窗体的项目

1. 从 " **文件** " 菜单中，依次选择 " **添加** "、" **新建项目** "，以打开 " **添加新项目** " 对话框。

2. 创建一个名为的 Windows 窗体应用程序 `InheritanceTest` 。

## <a name="add-an-inherited-form"></a>添加继承的窗体

1. 在 **解决方案资源管理器** 中，右键单击 **InheritanceTest** 项目，选择 " **添加**"，然后选择 " **新建项**"。

2. 在 " **添加新项** " 对话框中，选择 " **Windows 窗体** " 类别 (如果有类别列表) 然后选择 "继承的 **窗体** " 模板。

3. 保留的默认名称 `Form2` ，然后单击 " **添加**"。

4. 在 "**继承选择器**" 对话框中，从 **BaseFormLibrary** 项目中选择 **Form1** 作为要从其继承的表单，然后单击 **"确定"**。

     这会在 **InheritanceTest** 项目中创建一个从 **BaseFormLibrary** 中的表单派生的窗体。

5. 通过双击继承窗体 (**Form2**) 在设计器中将其打开（如果尚未打开）。

    在设计器中，继承的按钮具有符号 (![Visual Basic 继承符号的屏幕截图。](./media/walkthrough-demonstrating-visual-inheritance/visual-basic-inheritance-glyph.gif)) 在其上角，指示它们是继承的。

6. 选择 " **Hello** " 按钮，并观察调整大小控点。 由于此按钮受保护，继承者可以对其进行移动、调整大小、更改标题和进行其他修改。

7. 选择 "私有" 表示 " **再见** " 按钮，请注意，它没有调整大小控点。 此外，在 " **属性** " 窗口中，此按钮的属性将灰显，指示无法修改它们。

8. 如果使用的是 Visual c #：

    1. 在 **解决方案资源管理器** 中，右键单击 **InheritanceTest** 项目中的 " **Form1** "，然后选择 "**删除**"。 在出现的消息框中，单击 **"确定"** 以确认删除。

    2. 打开 Program.cs 文件并将 `Application.Run(new Form1());` 行更改为 `Application.Run(new Form2());`。

9. 在 **解决方案资源管理器** 中，右键单击 **InheritanceTest** 项目，然后选择 " **设为启动项目**"。

10. 在 **解决方案资源管理器** 中，右键单击 **InheritanceTest** 项目，然后选择 " **属性**"。

11. 在 **InheritanceTest** 属性页中，将 **启动对象** 设置为 (**Form2**) 的继承窗体。

12. 按 **F5** 运行应用程序，并观察继承窗体的行为。

## <a name="next-steps"></a>后续步骤

用户控件的继承方式大致相同。 打开新的类库项目并添加用户控件。 在其上放置构成控件，然后编译项目。 打开另一个新的类库项目，并添加对已编译的类库的引用。 同时，尝试通过 " **添加新项** " 对话框 (添加继承的控件，) 添加到项目中并使用 **继承选择器**。 添加用户控件，并 `Inherits` `:` 在 Visual c # ) 语句中更改 (。 有关详细信息，请参阅 how [to： Inherit Windows 窗体](how-to-inherit-windows-forms.md)。

## <a name="see-also"></a>另请参阅

- [如何：继承 Windows 窗体](how-to-inherit-windows-forms.md)
- [Windows 窗体可视化继承](windows-forms-visual-inheritance.md)
- [Windows 窗体](../index.yml)
