---
title: 如何：创作复合控件
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
ms.openlocfilehash: 96704b4acbba8c0e466e8d3ef4d2f569e1d1c7fb
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98956962"
---
# <a name="how-to-author-composite-controls"></a>如何：创作复合控件

可通过多种方式使用复合控件。 可将其作为 Windows 桌面应用程序项目的一部分创作，并只在该项目的窗体上使用它们。 或者，可在 Windows 控件库项目中创作它们，将该项目编译为程序集，在其他项目中使用这些控件。 甚至可以从它们继承，并使用可视继承快速自定义它们以用于特殊用途。

## <a name="to-author-a-composite-control"></a>创作复合控件

1. 在 Visual Studio 中，创建一个新的 **Windows 应用程序** 项目，并将其命名为 **DemoControlHost**。

2. 在 **“项目”** 菜单上，单击 **“添加用户控件”**。

3. 在“添加新项”对话框中，为类文件（.vb 或 .cs 文件）提供希望复合控件具有的名称。

4. 选择 " **添加** " 按钮，为复合控件创建类文件。

5. 将控件从“工具箱”添加到复合控件表面。

6. 将代码置于事件过程中，处理由复合控件或其构成控件所引发的事件。

7. 关闭复合控件的设计器，并在出现提示时保存文件。

8. 在 **“生成”** 菜单上，单击 **“生成解决方案”** 。

     必须生成项目，自定义控件才可在“工具箱”中显示。

9. 使用“工具箱”的“DemoControlHost”选项卡将控件的实例添加到 `Form1`。

## <a name="to-author-a-control-class-library"></a>创作控件类库

1. 打开新的“Windows 控件库”项目。

     默认情况下，项目包含一个复合控件。

2. 按照上述步骤中的说明添加控件和代码。

3. 选择不想继承类更改的控件，并将此控件的“Modifiers”属性设置为“专用”。

4. 生成 DLL。

## <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a>从控件类库中的复合控件中继承

1. 在“文件”菜单上，指向“添加”并选择“新建项目”，将新的“Windows 应用程序”项目添加到解决方案中。

2. 在“解决方案资源管理器”中，右键单击新项目的“引用”文件夹，并选择“添加引用”以打开“添加引用”对话框。

3. 选择“项目”选项卡，然后双击控件库项目。

4. 在 **“生成”** 菜单上，单击 **“生成解决方案”** 。

5. 在“解决方案资源管理器”中，右键单击控件库项目并从快捷菜单中选择“添加新项”。

6. 从“添加新项目”对话框中选择“继承的用户控件”模板。

7. 在“继承选择器”对话框中，双击要继承的控件。

     已将新控件添加到你的项目。

8. 打开新控件的可视化设计器，并添加其他构成控件。

     可看到从 DLL 中的复合控件继承的构成控件，还可以更改“Modifiers”属性为“Public”的控件的属性。 但不能更改“Modifiers”属性为“Private”的控件的属性。

## <a name="see-also"></a>另请参阅

- [演练：创作复合控件](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [演练：从 Windows 窗体控件继承](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
- [控件类型建议](control-type-recommendations.md)
- [如何：创作 Windows 窗体的控件](how-to-author-controls-for-windows-forms.md)
- [各种自定义控件](varieties-of-custom-controls.md)
