---
title: 开发一个简单的控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms]
- custom controls [Windows Forms], creating simple controls using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
ms.openlocfilehash: af8ba82cc5699a4b6a12eaf921dd9f4cbf3cecd1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971200"
---
# <a name="how-to-develop-a-simple-windows-forms-control"></a>如何：开发简单的 Windows 窗体控件

本部分演示创建自定义 Windows 窗体控件的关键步骤。 本演练中开发的简单控件允许更改其属性的对齐方式 <xref:System.Windows.Forms.Control.Text%2A> 。 它不会引发或处理事件。

### <a name="to-create-a-simple-custom-control"></a>创建简单的自定义控件

1. 定义一个从 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 派生的类。

    ```vb
    Public Class FirstControl
       Inherits Control

    End Class
    ```

    ```csharp
    public class FirstControl:Control {}
    ```

2. 定义属性。  (不需要定义属性，因为控件继承类中的多个属性 <xref:System.Windows.Forms.Control> ，但大多数自定义控件通常会定义其他属性。 ) 下面的代码段定义了一个名为 `TextAlignment` 的属性，该属性 `FirstControl` 使用来设置 <xref:System.Windows.Forms.Control.Text%2A> 从继承的属性的显示格式。 <xref:System.Windows.Forms.Control> 有关定义属性的详细信息，请参阅[属性概述](/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120))。

     [!code-csharp[System.Windows.Forms.FirstControl#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]

     设置更改控件可视显示的属性时，必须调用 <xref:System.Windows.Forms.Control.Invalidate%2A> 方法以重绘控件。 <xref:System.Windows.Forms.Control.Invalidate%2A> 是在基类中定义的 <xref:System.Windows.Forms.Control> 。

3. 重写从继承的受保护的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法，以便为 <xref:System.Windows.Forms.Control> 您的控件提供呈现逻辑。 如果不进行重写 <xref:System.Windows.Forms.Control.OnPaint%2A> ，则控件将无法绘制自身。 在下面的代码段中， <xref:System.Windows.Forms.Control.OnPaint%2A> 方法显示 <xref:System.Windows.Forms.Control.Text%2A> 从继承的属性 <xref:System.Windows.Forms.Control> 和字段指定的对齐方式 `alignmentValue` 。

     [!code-csharp[System.Windows.Forms.FirstControl#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]

4. 为控件提供属性。 特性让视觉设计器能够在设计时适当显示控件及其属性和事件。 以下代码片段将特性应用于 `TextAlignment` 属性。 在 Visual Studio 之类的设计器中，" <xref:System.ComponentModel.CategoryAttribute.Category%2A> 代码片段" 中显示的属性 () 使该属性显示在逻辑类别下。 <xref:System.ComponentModel.DescriptionAttribute.Description%2A>选择属性时，属性会导致在 "**属性**" 窗口的底部显示描述性字符串 `TextAlignment` 。 有关属性的详细信息，请参阅[组件的设计时属性](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))。

     [!code-csharp[System.Windows.Forms.FirstControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]

5. （可选）为控件提供资源。 可通过使用编译器选项（对于 C#，为 `/res`）将资源和控件进行打包，从而为控件提供资源（如位图）。 在运行时，可以使用类的方法来检索资源 <xref:System.Resources.ResourceManager> 。 有关创建和使用资源的详细信息，请参阅[桌面应用中的资源](/dotnet/framework/resources/index)。

6. 编译和部署控件。 要编译和部署 `FirstControl,`，请执行以下步骤：

    1. 将以下示例中的代码保存到源文件（如 FirstControl.cs 或 FirstControl.vb）。

    2. 将源代码编译成程序集并将其保存在应用程序的目录中。 要完成此操作，请从包含源文件的目录执行以下命令。

        ```console
        vbc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.vb
        ```

        ```console
        csc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.cs
        ```

         `/t:library` 编译器选项会告知编译器正在创建的程序集是库（而不是可执行文件）。 `/out` 选项指定程序集的路径和名称。 `/r` 选项提供代码引用的程序集的名称。 在此示例中，将创建只有你的应用程序可以使用的私有程序集。 因此，必须将其保存在应用程序的目录中。 有关打包和部署控件以进行分发的详细信息，请参阅[部署](/dotnet/framework/deployment/index)。

此示例演示了 `FirstControl` 的代码。 控件包含在命名空间 `CustomWinControls` 中。 命名空间提供相关类型的逻辑分组。 可在新的或现有命名空间中创建控件。 在 C# 中，`using` 声明（在 Visual Basic 中，为 `Imports`）允许从命名空间访问类型，而无需使用类型的完全限定名称。 在下面的示例中， `using` 声明只允许代码访问类， <xref:System.Windows.Forms.Control> <xref:System.Windows.Forms?displayProperty=nameWithType> <xref:System.Windows.Forms.Control> 而不必使用完全限定的名称 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。

[!code-csharp[System.Windows.Forms.FirstControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
[!code-vb[System.Windows.Forms.FirstControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]

## <a name="using-the-custom-control-on-a-form"></a>在窗体上使用自定义控件

以下示例显示使用 `FirstControl` 的简单窗体。 它会创建 `FirstControl` 的三个实例，每个实例具有一个不同的 `TextAlignment` 属性值。

#### <a name="to-compile-and-run-this-sample"></a>编译和运行此示例

1. 将以下示例中的代码保存到源文件（SimpleForm.cs 或 SimpleForms.vb）。

2. 通过从包含源文件的目录执行以下命令，将源代码编译成可执行程序集。

    ```console
    vbc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.vb
    ```

    ```console
    csc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.cs
    ```

     CustomWinControls.dll 是包含类的程序集 `FirstControl` 。 此程序集必须与访问程序集的窗体的源文件（SimpleForm.cs或SimpleForms.vb）位于同一目录中。

3. 使用以下命令执行 SimpleForm.exe。

    ```console
    SimpleForm
    ```

[!code-csharp[System.Windows.Forms.FirstControl#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
[!code-vb[System.Windows.Forms.FirstControl#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]

## <a name="see-also"></a>另请参阅

- [Windows 窗体控件中的属性](properties-in-windows-forms-controls.md)
- [Windows 窗体控件中的事件](events-in-windows-forms-controls.md)
