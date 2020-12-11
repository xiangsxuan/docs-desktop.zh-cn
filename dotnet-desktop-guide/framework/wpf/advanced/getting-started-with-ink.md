---
title: 在 Visual Studio 中创建 InkCanvas
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: b8087d6db04f7024b9ee48f28002bee04045a14b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973326"
---
# <a name="get-started-with-ink-in-wpf"></a>在 WPF 中开始学习墨迹

Windows Presentation Foundation (WPF) 包含一项墨迹功能，使你可以轻松地将数字墨迹合并到你的应用程序中。

## <a name="prerequisites"></a>先决条件

若要使用以下示例，请先安装 [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)。 它还有助于了解如何编写基本的 WPF 应用程序。 有关 WPF 入门的帮助，请参阅 [演练：我的第一个 wpf 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。

## <a name="quick-start"></a>快速启动

本节可帮助您编写一个收集墨迹的简单 WPF 应用程序。

### <a name="got-ink"></a>墨迹已获得？

若要创建支持墨迹的 WPF 应用，请执行以下操作：

1. 打开 Visual Studio。

2. 创建新的 **WPF 应用程序**。

   在 "**新建项目**" 对话框中，展开 "**已安装** 的  >  **Visual c #** " 或 " **Visual Basic**  >  **Windows 桌面**" 类别。 然后，选择 " **WPF 应用" ( .NET Framework)** 应用 "模板。 输入名称，然后选择 **"确定"**。

   Visual Studio 将创建项目，并在设计器中打开 *mainwindow.xaml。*

3. `<InkCanvas/>`在标记之间键入 `<Grid>` 。

   ![带有 InkCanvas 标记的 XAML 设计器](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. 按 **F5** 在调试器中启动应用程序。

5. 使用触笔或鼠标，在窗口中编写 " **hello world** "。

你已经编写了只包含12个击键的 "hello world" 应用程序的手写效果！

### <a name="spice-up-your-app"></a>情趣应用程序

让我们充分利用 WPF 的某些功能。 将开始标记和结束标记之间的所有内容替换 \<Window> 为以下标记：

```xaml
<Page>
  <InkCanvas Name="myInkCanvas" MouseRightButtonUp="RightMouseUpHandler">
    <InkCanvas.Background>
      <LinearGradientBrush>
        <GradientStop Color="Yellow" Offset="0.0" />
          <GradientStop Color="Blue" Offset="0.5" />
            <GradientStop Color="HotPink" Offset="1.0" />
              </LinearGradientBrush>
    </InkCanvas.Background>
  </InkCanvas>
</Page>
```

此 XAML 在墨迹图面上创建渐变画笔背景。

![WPF 应用中的墨迹图面上的渐变颜色](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a>在 XAML 后面添加一些代码

虽然 XAML 使得设计用户界面变得非常简单，但任何实际应用程序都需要添加代码来处理事件。 下面是一个简单的示例，它会放大墨迹，以响应鼠标右键单击。

1. `MouseRightButtonUp`在 XAML 中设置处理程序：

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. 在 **解决方案资源管理器** 中，展开 "mainwindow.xaml"，然后打开代码隐藏文件 ("MainWindow.xaml.cs" 或 "mainwindow.xaml) "。 添加以下事件处理程序代码：

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. 运行该应用程序。 添加一些墨迹，然后用鼠标右键单击或执行与触笔等效的按压操作。

   每次单击鼠标右键时，都会显示 "放大"。

### <a name="use-procedural-code-instead-of-xaml"></a>使用过程代码而不是 XAML

可以从过程代码访问所有 WPF 功能。 按照以下步骤创建用于 WPF 的 "Hello Ink World" 应用程序，该应用程序根本不使用任何 XAML。

1. 在 Visual Studio 中创建新的控制台应用程序项目。

   在 "**新建项目**" 对话框中，展开 "**已安装** 的  >  **Visual c #** " 或 " **Visual Basic**  >  **Windows 桌面**" 类别。 然后，选择 " **控制台应用" ( .NET Framework)** 应用 "模板。 输入名称，然后选择 **"确定"**。

1. 将以下代码粘贴到 Program.cs 或 Program .vb 文件中：

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. 通过在 **解决方案资源管理器** 中右键单击 "**引用**"，然后选择 "**添加引用**"，添加对 PresentationCore、PresentationFramework 和 WindowsBase 程序集的引用。

   ![显示 PresentationCore 和 PresentationFramework 的参考管理器](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. 按 **F5** 生成应用程序。

## <a name="see-also"></a>另请参阅

- [数字墨迹](digital-ink.md)
- [收集墨迹](collecting-ink.md)
- [手写识别](handwriting-recognition.md)
- [存储墨迹](storing-ink.md)
