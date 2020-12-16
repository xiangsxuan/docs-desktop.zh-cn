---
title: 向项目添加窗体
description: 在 Visual Studio 中向 .NET Windows 窗体项目添加新窗体
ms.date: 10/26/2020
helpviewer_keywords:
- Windows Forms, create add form
ms.openlocfilehash: fb35c1b62ca0b7a21581c350ddca7f21f45ec27f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941955"
---
# <a name="how-to-add-a-form-to-a-project-windows-forms-net"></a>如何向项目添加窗体（Windows 窗体 .NET）

在 Visual Studio 中向项目添加窗体。 如果应用具有多个窗体，你可以选择哪个作为应用的启动窗体，并且可以同时显示多个窗体。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="add-a-new-form"></a>添加新窗体

在 Visual Studio 中添加新窗体。

01. 在 Visual Studio 中，找到“项目资源管理器”窗格。 右键单击项目，然后选择“添加” > “窗体(Windows 窗体)” 。

    :::image type="content" source="media/how-to-add/right-click.png" alt-text="右键单击解决方案资源管理器，将新窗体添加到 Windows 窗体项目中":::

01. 在“名称”框中键入窗体的名称，例如 MyNewForm。 Visual Studio 将提供一个默认名称，这也是你可以使用的唯一名称。

    :::image type="content" source="media/how-to-add/new-form-dialog.png" alt-text="在 Visual Studio 中为 Windows 窗体添加项目对话框":::

添加窗体后，Visual Studio 将打开窗体的窗体设计器。

## <a name="add-a-project-reference-to-a-form"></a>向窗体添加项目引用

如果源文件包含在窗体中，则可以通过将文件复制到项目所在文件夹来将窗体添加到项目。 项目会自动引用项目的同一文件夹或子文件夹中的所有代码文件。

窗体由两个同名文件构成：form2.cs（form2 是文件名的示例）和 form2.Designer.cs  。 有时会存在同名资源文件，即 form2.resx。 在上一个示例中，form2 表示基本文件名。 建议将所有相关文件复制到项目文件夹。

也可使用 Visual Studio 将文件导入项目。 将现有文件添加到项目时，该文件将复制到项目所在文件夹。

01. 在 Visual Studio 中，找到“项目资源管理器”窗格。 右键单击项目，然后选择“添加” > “现有项” 。

    :::image type="content" source="media/how-to-add/existing-right-click.png" alt-text="右键单击解决方案资源管理器，将现有窗体添加到 Windows 窗体项目中":::

02. 导航到包含窗体文件的文件夹。

03. 选择 form2.cs 文件，其中 form2 是相关窗体文件的基本文件名 。 请勿选择其他文件，例如 form2.Designer.cs。

## <a name="see-also"></a>另请参阅

- [如何定位窗体并重设其大小（Windows 窗体 .NET）](how-to-position-and-resize.md)
- [事件概述（Windows 窗体 .NET）](events.md)
- [控件的位置和布局（Windows 窗体 .NET）](../controls/layout.md)
