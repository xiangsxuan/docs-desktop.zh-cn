---
title: 不使用用户界面而添加控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: c1ab1ec848b4c7a19ed9a65b67e17679bac215cd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971787"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a>如何：向 Windows 窗体添加无用户界面的控件

 (或组件) 的非可视控件向您的应用程序提供功能。 与其他控件不同，组件并不为用户提供用户界面，因此不需要在 Windows 窗体设计器表面上显示。 将组件添加到窗体时，Windows 窗体设计器将在显示所有组件的窗体底部显示可调整大小的托盘。 将控件添加到组件栏后，您可以选择该组件并设置其属性，就像对窗体上的任何其他控件一样。

## <a name="add-a-component-to-a-windows-form"></a>将组件添加到 Windows 窗体

1. 在 Visual Studio 中打开窗体。 有关详细信息，请参阅 [如何：在设计器中显示 Windows 窗体](/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))。

2. 在 " **工具箱**" 中，单击某个组件，然后将其拖到窗体上。

     组件将出现在组件栏中。

此外，可以在运行时将组件添加到窗体中。 这是一个常见方案，尤其是因为组件没有可视表达式，这不同于具有用户界面的控件。 在下面的示例中，将 <xref:System.Windows.Forms.Timer> 在运行时添加组件。  (请注意，Visual Studio 包含许多不同的计时器;在这种情况下，请使用 Windows 窗体 <xref:System.Windows.Forms.Timer> 组件。 有关 Visual Studio 中不同计时器的详细信息，请参阅 [Server-Based 计时器简介](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))。 ) 

> [!CAUTION]
> 组件通常具有特定于控件的属性，必须对其进行设置，组件才能有效工作。 对于 <xref:System.Windows.Forms.Timer> 下面的组件，请设置 `Interval` 属性。 在将组件添加到项目时，请确保为该组件设置必要的属性。

## <a name="add-a-component-to-a-windows-form-programmatically"></a>以编程方式向 Windows 窗体添加组件

1. <xref:System.Windows.Forms.Timer>在代码中创建类的实例。

2. 设置 `Interval` 属性以确定计时器计时周期之间的时间。

3. 配置组件的任何其他必要属性。

     下面的代码演示如何创建 <xref:System.Windows.Forms.Timer> 具有其 `Interval` 属性集的。

    ```vb
    Public Sub CreateTimer()
       Dim timerKeepTrack As New System.Windows.Forms.Timer
       timerKeepTrack.Interval = 1000
    End Sub
    ```

    ```csharp
    public void createTimer()
    {
       System.Windows.Forms.Timer timerKeepTrack = new
           System.Windows.Forms.Timer();
       timerKeepTrack.Interval = 1000;
    }
    ```

    ```cpp
    public:
       void createTimer()
       {
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew
             System::Windows::Forms::Timer();
          timerKeepTrack->Interval = 1000;
       }
    ```

    > [!IMPORTANT]
    > 通过引用恶意用户，你可以通过网络将你的本地计算机泄露给安全风险。 这只是在恶意用户创建有破坏性的自定义控件时，然后错误地将其添加到项目中时需要注意的问题。

## <a name="see-also"></a>另请参阅

- [Windows 窗体控件](index.md)
- [如何：向 Windows 窗体添加控件](how-to-add-controls-to-windows-forms.md)
- [如何：向 Windows 窗体添加 ActiveX 控件](how-to-add-activex-controls-to-windows-forms.md)
- [将控件放在 Windows 窗体上](putting-controls-on-windows-forms.md)
- [标记单个 Windows 窗体控件并提供它们的快捷方式](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
- [根据功能列出的 Windows 窗体控件](windows-forms-controls-by-function.md)
