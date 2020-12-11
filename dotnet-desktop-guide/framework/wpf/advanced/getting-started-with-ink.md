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
# <a name="get-started-with-ink-in-wpf"></a><span data-ttu-id="e4ee1-102">在 WPF 中开始学习墨迹</span><span class="sxs-lookup"><span data-stu-id="e4ee1-102">Get Started with Ink in WPF</span></span>

<span data-ttu-id="e4ee1-103">Windows Presentation Foundation (WPF) 包含一项墨迹功能，使你可以轻松地将数字墨迹合并到你的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-103">Windows Presentation Foundation (WPF) has an ink feature that makes it easy to incorporate digital ink into your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e4ee1-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="e4ee1-104">Prerequisites</span></span>

<span data-ttu-id="e4ee1-105">若要使用以下示例，请先安装 [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-105">To use the following examples, first install [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span></span> <span data-ttu-id="e4ee1-106">它还有助于了解如何编写基本的 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-106">It also helps to know how to write basic WPF apps.</span></span> <span data-ttu-id="e4ee1-107">有关 WPF 入门的帮助，请参阅 [演练：我的第一个 wpf 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-107">For help getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="quick-start"></a><span data-ttu-id="e4ee1-108">快速启动</span><span class="sxs-lookup"><span data-stu-id="e4ee1-108">Quick Start</span></span>

<span data-ttu-id="e4ee1-109">本节可帮助您编写一个收集墨迹的简单 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-109">This section helps you write a simple WPF application that collects ink.</span></span>

### <a name="got-ink"></a><span data-ttu-id="e4ee1-110">墨迹已获得？</span><span class="sxs-lookup"><span data-stu-id="e4ee1-110">Got Ink?</span></span>

<span data-ttu-id="e4ee1-111">若要创建支持墨迹的 WPF 应用，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e4ee1-111">To create a WPF app that supports ink:</span></span>

1. <span data-ttu-id="e4ee1-112">打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-112">Open Visual Studio.</span></span>

2. <span data-ttu-id="e4ee1-113">创建新的 **WPF 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-113">Create a new **WPF App**.</span></span>

   <span data-ttu-id="e4ee1-114">在 "**新建项目**" 对话框中，展开 "**已安装** 的  >  **Visual c #** " 或 " **Visual Basic**  >  **Windows 桌面**" 类别。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-114">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="e4ee1-115">然后，选择 " **WPF 应用" ( .NET Framework)** 应用 "模板。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-115">Then, select the **WPF App (.NET Framework)** app template.</span></span> <span data-ttu-id="e4ee1-116">输入名称，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-116">Enter a name, and then select **OK**.</span></span>

   <span data-ttu-id="e4ee1-117">Visual Studio 将创建项目，并在设计器中打开 *mainwindow.xaml。*</span><span class="sxs-lookup"><span data-stu-id="e4ee1-117">Visual Studio creates the project, and *MainWindow.xaml* opens in the designer.</span></span>

3. <span data-ttu-id="e4ee1-118">`<InkCanvas/>`在标记之间键入 `<Grid>` 。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-118">Type `<InkCanvas/>` between the `<Grid>` tags.</span></span>

   ![带有 InkCanvas 标记的 XAML 设计器](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. <span data-ttu-id="e4ee1-120">按 **F5** 在调试器中启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-120">Press **F5** to launch your application in the debugger.</span></span>

5. <span data-ttu-id="e4ee1-121">使用触笔或鼠标，在窗口中编写 " **hello world** "。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-121">Using a stylus or mouse, write **hello world** in the window.</span></span>

<span data-ttu-id="e4ee1-122">你已经编写了只包含12个击键的 "hello world" 应用程序的手写效果！</span><span class="sxs-lookup"><span data-stu-id="e4ee1-122">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>

### <a name="spice-up-your-app"></a><span data-ttu-id="e4ee1-123">情趣应用程序</span><span class="sxs-lookup"><span data-stu-id="e4ee1-123">Spice Up Your App</span></span>

<span data-ttu-id="e4ee1-124">让我们充分利用 WPF 的某些功能。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-124">Let’s take advantage of some features of the WPF.</span></span> <span data-ttu-id="e4ee1-125">将开始标记和结束标记之间的所有内容替换 \<Window> 为以下标记：</span><span class="sxs-lookup"><span data-stu-id="e4ee1-125">Replace everything between the opening and closing \<Window> tags with the following markup:</span></span>

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

<span data-ttu-id="e4ee1-126">此 XAML 在墨迹图面上创建渐变画笔背景。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-126">This XAML creates a gradient brush background on your inking surface.</span></span>

![WPF 应用中的墨迹图面上的渐变颜色](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a><span data-ttu-id="e4ee1-128">在 XAML 后面添加一些代码</span><span class="sxs-lookup"><span data-stu-id="e4ee1-128">Add Some Code Behind the XAML</span></span>

<span data-ttu-id="e4ee1-129">虽然 XAML 使得设计用户界面变得非常简单，但任何实际应用程序都需要添加代码来处理事件。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-129">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="e4ee1-130">下面是一个简单的示例，它会放大墨迹，以响应鼠标右键单击。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-130">Here is a simple example that zooms in on the ink in response to a right-click from a mouse.</span></span>

1. <span data-ttu-id="e4ee1-131">`MouseRightButtonUp`在 XAML 中设置处理程序：</span><span class="sxs-lookup"><span data-stu-id="e4ee1-131">Set the `MouseRightButtonUp` handler in your XAML:</span></span>

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. <span data-ttu-id="e4ee1-132">在 **解决方案资源管理器** 中，展开 "mainwindow.xaml"，然后打开代码隐藏文件 ("MainWindow.xaml.cs" 或 "mainwindow.xaml) "。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-132">In **Solution Explorer**, expand MainWindow.xaml and open the code-behind file (MainWindow.xaml.cs or MainWindow.xaml.vb).</span></span> <span data-ttu-id="e4ee1-133">添加以下事件处理程序代码：</span><span class="sxs-lookup"><span data-stu-id="e4ee1-133">Add the following event handler code:</span></span>

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. <span data-ttu-id="e4ee1-134">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-134">Run the application.</span></span> <span data-ttu-id="e4ee1-135">添加一些墨迹，然后用鼠标右键单击或执行与触笔等效的按压操作。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-135">Add some ink, and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>

   <span data-ttu-id="e4ee1-136">每次单击鼠标右键时，都会显示 "放大"。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-136">The display zooms in each time you click with the right mouse button.</span></span>

### <a name="use-procedural-code-instead-of-xaml"></a><span data-ttu-id="e4ee1-137">使用过程代码而不是 XAML</span><span class="sxs-lookup"><span data-stu-id="e4ee1-137">Use Procedural Code Instead of XAML</span></span>

<span data-ttu-id="e4ee1-138">可以从过程代码访问所有 WPF 功能。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-138">You can access all WPF features from procedural code.</span></span> <span data-ttu-id="e4ee1-139">按照以下步骤创建用于 WPF 的 "Hello Ink World" 应用程序，该应用程序根本不使用任何 XAML。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-139">Follow these steps to create a "Hello Ink World" application for WPF that doesn’t use any XAML at all.</span></span>

1. <span data-ttu-id="e4ee1-140">在 Visual Studio 中创建新的控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-140">Create a new console application project in Visual Studio.</span></span>

   <span data-ttu-id="e4ee1-141">在 "**新建项目**" 对话框中，展开 "**已安装** 的  >  **Visual c #** " 或 " **Visual Basic**  >  **Windows 桌面**" 类别。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-141">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="e4ee1-142">然后，选择 " **控制台应用" ( .NET Framework)** 应用 "模板。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-142">Then, select the **Console App (.NET Framework)** app template.</span></span> <span data-ttu-id="e4ee1-143">输入名称，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-143">Enter a name, and then select **OK**.</span></span>

1. <span data-ttu-id="e4ee1-144">将以下代码粘贴到 Program.cs 或 Program .vb 文件中：</span><span class="sxs-lookup"><span data-stu-id="e4ee1-144">Paste the following code into the Program.cs or Program.vb file:</span></span>

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. <span data-ttu-id="e4ee1-145">通过在 **解决方案资源管理器** 中右键单击 "**引用**"，然后选择 "**添加引用**"，添加对 PresentationCore、PresentationFramework 和 WindowsBase 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-145">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies by right-clicking on **References** in **Solution Explorer** and choosing **Add Reference**.</span></span>

   ![显示 PresentationCore 和 PresentationFramework 的参考管理器](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. <span data-ttu-id="e4ee1-147">按 **F5** 生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4ee1-147">Build the application by pressing **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4ee1-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4ee1-148">See also</span></span>

- [<span data-ttu-id="e4ee1-149">数字墨迹</span><span class="sxs-lookup"><span data-stu-id="e4ee1-149">Digital Ink</span></span>](digital-ink.md)
- [<span data-ttu-id="e4ee1-150">收集墨迹</span><span class="sxs-lookup"><span data-stu-id="e4ee1-150">Collecting Ink</span></span>](collecting-ink.md)
- [<span data-ttu-id="e4ee1-151">手写识别</span><span class="sxs-lookup"><span data-stu-id="e4ee1-151">Handwriting Recognition</span></span>](handwriting-recognition.md)
- [<span data-ttu-id="e4ee1-152">存储墨迹</span><span class="sxs-lookup"><span data-stu-id="e4ee1-152">Storing Ink</span></span>](storing-ink.md)
