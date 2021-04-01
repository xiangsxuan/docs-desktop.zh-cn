---
title: 收集数字墨迹
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
ms.openlocfilehash: 813a5313a6fbf83c36cdbed1f64ce69a217ad788
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971958"
---
# <a name="collect-ink"></a><span data-ttu-id="5f0e0-102">收集墨迹</span><span class="sxs-lookup"><span data-stu-id="5f0e0-102">Collect Ink</span></span>

<span data-ttu-id="5f0e0-103">[Windows Presentation Foundation](../index.md) 平台会收集数字墨迹，这是其功能中的核心部分之一。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-103">The [Windows Presentation Foundation](../index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="5f0e0-104">本主题讨论 Windows Presentation Foundation (WPF) 中的墨迹收集方法。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5f0e0-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="5f0e0-105">Prerequisites</span></span>

<span data-ttu-id="5f0e0-106">若要使用以下示例，必须首先安装 Visual Studio 和 Windows SDK。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-106">To use the following examples, you must first install Visual Studio and the Windows SDK.</span></span> <span data-ttu-id="5f0e0-107">还应了解如何编写 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="5f0e0-108">有关 WPF 入门的详细信息，请参阅 [演练：我的第一个 wpf 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="5f0e0-109">使用 InkCanvas 元素</span><span class="sxs-lookup"><span data-stu-id="5f0e0-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="5f0e0-110"><xref:System.Windows.Controls.InkCanvas?displayProperty=fullName>元素提供在 WPF 中收集墨迹的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="5f0e0-111">使用 <xref:System.Windows.Controls.InkCanvas> 元素接收并显示墨迹输入。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="5f0e0-112">通常使用触笔（与数字化仪交互产生墨迹笔画）输入墨迹。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="5f0e0-113">此外，还可以使用鼠标代替触笔。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="5f0e0-114">创建的笔划表示为 <xref:System.Windows.Ink.Stroke> 对象，可通过编程方式和用户输入操作。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="5f0e0-115"><xref:System.Windows.Controls.InkCanvas>允许用户选择、修改或删除现有的 <xref:System.Windows.Ink.Stroke> 。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="5f0e0-116">通过使用 XAML，可以轻松地设置墨迹收集，就像向树中添加 **InkCanvas** 元素一样。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="5f0e0-117">下面的示例将添加 <xref:System.Windows.Controls.InkCanvas> 到在 Visual Studio 中创建的默认 WPF 项目：</span><span class="sxs-lookup"><span data-stu-id="5f0e0-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="5f0e0-118">**InkCanvas** 元素还可以包含子元素，这样就可以将墨迹注释功能添加到几乎任何类型的 XAML 元素。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="5f0e0-119">例如，若要将墨迹功能添加到文本元素，只需将其设置为的子元素 <xref:System.Windows.Controls.InkCanvas> ：</span><span class="sxs-lookup"><span data-stu-id="5f0e0-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="5f0e0-120">添加对使用墨迹标记图像的支持同样简单：</span><span class="sxs-lookup"><span data-stu-id="5f0e0-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="5f0e0-121">InkCollection 模式</span><span class="sxs-lookup"><span data-stu-id="5f0e0-121">InkCollection Modes</span></span>

<span data-ttu-id="5f0e0-122"><xref:System.Windows.Controls.InkCanvas>通过其属性提供各种输入模式的支持 <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="5f0e0-123">操作墨迹</span><span class="sxs-lookup"><span data-stu-id="5f0e0-123">Manipulate Ink</span></span>

<span data-ttu-id="5f0e0-124">为 <xref:System.Windows.Controls.InkCanvas> 许多墨迹编辑操作提供支持。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="5f0e0-125">例如， <xref:System.Windows.Controls.InkCanvas> 支持笔背面擦除，无需其他代码即可将该功能添加到元素中。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="5f0e0-126">选择</span><span class="sxs-lookup"><span data-stu-id="5f0e0-126">Selection</span></span>

<span data-ttu-id="5f0e0-127">设置选择模式非常简单，只需要将 <xref:System.Windows.Controls.InkCanvasEditingMode> 属性设置为 " **选择**"。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="5f0e0-128">下面的代码基于的值设置编辑模式 <xref:System.Windows.Forms.CheckBox> ：</span><span class="sxs-lookup"><span data-stu-id="5f0e0-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="5f0e0-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="5f0e0-129">DrawingAttributes</span></span>

<span data-ttu-id="5f0e0-130">使用 <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> 属性来更改墨迹笔划的外观。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="5f0e0-131">例如，的 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> 成员 <xref:System.Windows.Ink.DrawingAttributes> 设置呈现的的颜色 <xref:System.Windows.Ink.Stroke> 。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="5f0e0-132">下面的示例将选定笔画的颜色更改为红色：</span><span class="sxs-lookup"><span data-stu-id="5f0e0-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="5f0e0-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="5f0e0-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="5f0e0-134"><xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>属性提供对要在中创建的笔划的高度、宽度和颜色等属性的访问 <xref:System.Windows.Controls.InkCanvas> 。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="5f0e0-135">更改后，在中 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 输入的所有后续笔划 <xref:System.Windows.Controls.InkCanvas> 都将呈现为新属性值。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="5f0e0-136">除了修改 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 代码隐藏文件中的以外，还可以使用 XAML 语法来指定 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="5f0e0-137">下一个示例演示如何设置 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="5f0e0-138">若要使用此代码，请在 Visual Studio 中创建一个名为 "HelloInkCanvas" 的新 WPF 项目。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="5f0e0-139">将 *mainwindow.xaml* 文件中的代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="5f0e0-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="5f0e0-140">接下来，将以下按钮事件处理程序添加到 Mainwindow.xaml 类中的代码隐藏文件：</span><span class="sxs-lookup"><span data-stu-id="5f0e0-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="5f0e0-141">复制此代码后，在 Visual Studio 中按 **F5** 以在调试器中运行该程序。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="5f0e0-142">请注意如何将 <xref:System.Windows.Controls.StackPanel> 按钮放置在顶部 <xref:System.Windows.Controls.InkCanvas> 。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="5f0e0-143">如果尝试在按钮顶部显示墨迹，则会 <xref:System.Windows.Controls.InkCanvas> 收集按钮并在其后面呈现墨迹。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="5f0e0-144">这是因为按钮是的同级，而不是 <xref:System.Windows.Controls.InkCanvas> 子级。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="5f0e0-145">此外，这些按钮的 Z 顺序较高，所以墨迹呈现在其后面。</span><span class="sxs-lookup"><span data-stu-id="5f0e0-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f0e0-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f0e0-146">See also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
