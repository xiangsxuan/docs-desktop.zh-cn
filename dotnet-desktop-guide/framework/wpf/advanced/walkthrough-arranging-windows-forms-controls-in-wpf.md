---
title: 在 WPF 中排列 Windows 窗体控件
titleSuffix: ''
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: d77612aa4d8c38dfa3992f82a0d1e542931c967a
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664049"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="c708b-102">演练：在 WPF 中排列 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="c708b-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>

<span data-ttu-id="c708b-103">本演练演示如何使用 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 布局功能在混合应用程序中排列 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="c708b-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange Windows Forms controls in a hybrid application.</span></span>

<span data-ttu-id="c708b-104">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="c708b-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="c708b-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="c708b-105">Creating the project.</span></span>
- <span data-ttu-id="c708b-106">使用默认布局设置。</span><span class="sxs-lookup"><span data-stu-id="c708b-106">Using default layout settings.</span></span>
- <span data-ttu-id="c708b-107">根据内容调整大小。</span><span class="sxs-lookup"><span data-stu-id="c708b-107">Sizing to content.</span></span>
- <span data-ttu-id="c708b-108">使用绝对定位。</span><span class="sxs-lookup"><span data-stu-id="c708b-108">Using absolute positioning.</span></span>
- <span data-ttu-id="c708b-109">显式指定大小。</span><span class="sxs-lookup"><span data-stu-id="c708b-109">Specifying size explicitly.</span></span>
- <span data-ttu-id="c708b-110">设置布局属性。</span><span class="sxs-lookup"><span data-stu-id="c708b-110">Setting layout properties.</span></span>
- <span data-ttu-id="c708b-111">了解 Z 顺序限制。</span><span class="sxs-lookup"><span data-stu-id="c708b-111">Understanding z-order limitations.</span></span>
- <span data-ttu-id="c708b-112">停靠。</span><span class="sxs-lookup"><span data-stu-id="c708b-112">Docking.</span></span>
- <span data-ttu-id="c708b-113">设置可见性。</span><span class="sxs-lookup"><span data-stu-id="c708b-113">Setting visibility.</span></span>
- <span data-ttu-id="c708b-114">承载不拉伸的控件。</span><span class="sxs-lookup"><span data-stu-id="c708b-114">Hosting a control that does not stretch.</span></span>
- <span data-ttu-id="c708b-115">缩放。</span><span class="sxs-lookup"><span data-stu-id="c708b-115">Scaling.</span></span>
- <span data-ttu-id="c708b-116">旋转。</span><span class="sxs-lookup"><span data-stu-id="c708b-116">Rotating.</span></span>
- <span data-ttu-id="c708b-117">设置填充和边距。</span><span class="sxs-lookup"><span data-stu-id="c708b-117">Setting padding and margins.</span></span>
- <span data-ttu-id="c708b-118">使用动态布局容器。</span><span class="sxs-lookup"><span data-stu-id="c708b-118">Using dynamic layout containers.</span></span>

<span data-ttu-id="c708b-119">有关本演练中所述任务的完整代码列表，请参阅 [在 WPF 中排列 Windows 窗体控件示例](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WpfLayoutHostingWfWithXaml)。</span><span class="sxs-lookup"><span data-stu-id="c708b-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WpfLayoutHostingWfWithXaml).</span></span>

<span data-ttu-id="c708b-120">完成后，你将了解基于应用程序的 Windows 窗体布局功能 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="c708b-120">When you are finished, you will have an understanding of Windows Forms layout features in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c708b-121">必备条件</span><span class="sxs-lookup"><span data-stu-id="c708b-121">Prerequisites</span></span>

<span data-ttu-id="c708b-122">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="c708b-122">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="c708b-123">创建项目</span><span class="sxs-lookup"><span data-stu-id="c708b-123">Creating the Project</span></span>

<span data-ttu-id="c708b-124">若要创建和设置项目，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c708b-124">To create and set up the project, follow these steps:</span></span>

1. <span data-ttu-id="c708b-125">创建一个名为的 WPF 应用程序项目 `WpfLayoutHostingWf` 。</span><span class="sxs-lookup"><span data-stu-id="c708b-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>

2. <span data-ttu-id="c708b-126">在解决方案资源管理器中，添加对以下程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="c708b-126">In Solution Explorer, add references to the following assemblies:</span></span>

    - <span data-ttu-id="c708b-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="c708b-127">WindowsFormsIntegration</span></span>
    - <span data-ttu-id="c708b-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="c708b-128">System.Windows.Forms</span></span>
    - <span data-ttu-id="c708b-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="c708b-129">System.Drawing</span></span>

3. <span data-ttu-id="c708b-130">双击 " *mainwindow.xaml* " 以在 xaml 视图中打开它。</span><span class="sxs-lookup"><span data-stu-id="c708b-130">Double-click *MainWindow.xaml* to open it in XAML view.</span></span>

4. <span data-ttu-id="c708b-131">在 <xref:System.Windows.Window> 元素中，添加以下 Windows 窗体命名空间映射。</span><span class="sxs-lookup"><span data-stu-id="c708b-131">In the <xref:System.Windows.Window> element, add the following Windows Forms namespace mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="c708b-132">在元素中， <xref:System.Windows.Controls.Grid> 将 <xref:System.Windows.Controls.Grid.ShowGridLines%2A> 属性设置为 `true` ，并定义五行和三列。</span><span class="sxs-lookup"><span data-stu-id="c708b-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a><span data-ttu-id="c708b-133">使用默认布局设置</span><span class="sxs-lookup"><span data-stu-id="c708b-133">Using Default Layout Settings</span></span>

<span data-ttu-id="c708b-134">默认情况下， <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素处理承载 Windows 窗体控件的布局。</span><span class="sxs-lookup"><span data-stu-id="c708b-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted Windows Forms control.</span></span>

<span data-ttu-id="c708b-135">若要使用默认布局设置，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c708b-135">To use default layout settings, follow these steps:</span></span>

1. <span data-ttu-id="c708b-136">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：</span><span class="sxs-lookup"><span data-stu-id="c708b-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. <span data-ttu-id="c708b-137">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c708b-137">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="c708b-138">Windows 窗体 <xref:System.Windows.Forms.Button?displayProperty=nameWithType> 控件将显示在中 <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="c708b-138">The Windows Forms <xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="c708b-139">承载的控件根据其内容调整大小，并 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 调整元素大小以容纳承载的控件。</span><span class="sxs-lookup"><span data-stu-id="c708b-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>

## <a name="sizing-to-content"></a><span data-ttu-id="c708b-140">按内容调整大小</span><span class="sxs-lookup"><span data-stu-id="c708b-140">Sizing to Content</span></span>

<span data-ttu-id="c708b-141"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素确保所承载的控件的大小调整为正确显示其内容。</span><span class="sxs-lookup"><span data-stu-id="c708b-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>

<span data-ttu-id="c708b-142">若要调整内容的大小，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c708b-142">To size to content, follow these steps:</span></span>

1. <span data-ttu-id="c708b-143">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：</span><span class="sxs-lookup"><span data-stu-id="c708b-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. <span data-ttu-id="c708b-144">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c708b-144">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="c708b-145">这两个新按钮控件的大小调整为正确显示较长的文本字符串和更大的字号，并 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 调整元素的大小以容纳所承载的控件。</span><span class="sxs-lookup"><span data-stu-id="c708b-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>

## <a name="using-absolute-positioning"></a><span data-ttu-id="c708b-146">使用绝对定位</span><span class="sxs-lookup"><span data-stu-id="c708b-146">Using Absolute Positioning</span></span>

<span data-ttu-id="c708b-147">可以使用绝对定位将 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素放在用户界面中的任何位置 (UI) 。</span><span class="sxs-lookup"><span data-stu-id="c708b-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>

<span data-ttu-id="c708b-148">若要使用绝对定位，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c708b-148">To use absolute positioning, follow these steps:</span></span>

1. <span data-ttu-id="c708b-149">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：</span><span class="sxs-lookup"><span data-stu-id="c708b-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. <span data-ttu-id="c708b-150">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c708b-150">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="c708b-151">将 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素置于网格单元顶部20个像素的位置，左侧20个像素。</span><span class="sxs-lookup"><span data-stu-id="c708b-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>

## <a name="specifying-size-explicitly"></a><span data-ttu-id="c708b-152">显式指定大小</span><span class="sxs-lookup"><span data-stu-id="c708b-152">Specifying Size Explicitly</span></span>

<span data-ttu-id="c708b-153">您可以 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 使用和属性指定元素的大小 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> 。</span><span class="sxs-lookup"><span data-stu-id="c708b-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>

<span data-ttu-id="c708b-154">若要显式指定大小，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c708b-154">To specify size explicitly, follow these steps:</span></span>

1. <span data-ttu-id="c708b-155">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：</span><span class="sxs-lookup"><span data-stu-id="c708b-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. <span data-ttu-id="c708b-156">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c708b-156">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="c708b-157"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素的大小设置为50像素宽 x 70 像素高，小于默认布局设置。</span><span class="sxs-lookup"><span data-stu-id="c708b-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="c708b-158">Windows 窗体控件的内容会相应地重新排列。</span><span class="sxs-lookup"><span data-stu-id="c708b-158">The content of the Windows Forms control is rearranged accordingly.</span></span>

## <a name="setting-layout-properties"></a><span data-ttu-id="c708b-159">设置布局属性</span><span class="sxs-lookup"><span data-stu-id="c708b-159">Setting Layout Properties</span></span>

<span data-ttu-id="c708b-160">始终使用元素的属性设置承载控件上与布局相关的属性 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。</span><span class="sxs-lookup"><span data-stu-id="c708b-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="c708b-161">直接对承载控件设置布局属性会产生意外结果。</span><span class="sxs-lookup"><span data-stu-id="c708b-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>

 <span data-ttu-id="c708b-162">在中的托管控件上设置与布局相关的属性 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 不起作用。</span><span class="sxs-lookup"><span data-stu-id="c708b-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>

<span data-ttu-id="c708b-163">若要查看在承载控件上设置属性的效果，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c708b-163">To see the effects of setting properties on the hosted control, follow these steps:</span></span>

1. <span data-ttu-id="c708b-164">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：</span><span class="sxs-lookup"><span data-stu-id="c708b-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. <span data-ttu-id="c708b-165">在 **解决方案资源管理器** 中，双击 " *mainwindow.xaml* " 或 " *Mainwindow.xaml* " 以在代码编辑器中将其打开。</span><span class="sxs-lookup"><span data-stu-id="c708b-165">In **Solution Explorer**, double-click *MainWindow.xaml.vb* or *MainWindow.xaml.cs* to open it in the Code Editor.</span></span>

3. <span data-ttu-id="c708b-166">将以下代码复制到 `MainWindow` 类定义中：</span><span class="sxs-lookup"><span data-stu-id="c708b-166">Copy the following code into the `MainWindow` class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="c708b-167">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c708b-167">Press <kbd>F5</kbd> to build and run the application.</span></span>

5. <span data-ttu-id="c708b-168">单击 " **单击** 此按钮"。</span><span class="sxs-lookup"><span data-stu-id="c708b-168">Click the **Click me** button.</span></span> <span data-ttu-id="c708b-169">`button1_Click`事件处理程序在 <xref:System.Windows.Forms.Control.Top%2A> <xref:System.Windows.Forms.Control.Left%2A> 承载控件上设置和属性。</span><span class="sxs-lookup"><span data-stu-id="c708b-169">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="c708b-170">这会导致在元素内重新定位承载的控件 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。</span><span class="sxs-lookup"><span data-stu-id="c708b-170">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="c708b-171">宿主保持相同的屏幕区域，但承载控件被剪裁。</span><span class="sxs-lookup"><span data-stu-id="c708b-171">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="c708b-172">托管控件应始终填充 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素。</span><span class="sxs-lookup"><span data-stu-id="c708b-172">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="c708b-173">了解 Z 顺序限制</span><span class="sxs-lookup"><span data-stu-id="c708b-173">Understanding Z-Order Limitations</span></span>

<span data-ttu-id="c708b-174">可见 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素始终在其他 WPF 元素之上绘制，并且不受 z 顺序的影响。</span><span class="sxs-lookup"><span data-stu-id="c708b-174">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="c708b-175">若要查看此 z 顺序行为，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c708b-175">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="c708b-176">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：</span><span class="sxs-lookup"><span data-stu-id="c708b-176">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="c708b-177">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c708b-177">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="c708b-178"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素在标签元素上绘制。</span><span class="sxs-lookup"><span data-stu-id="c708b-178">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="c708b-179">停靠</span><span class="sxs-lookup"><span data-stu-id="c708b-179">Docking</span></span>

<span data-ttu-id="c708b-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素支持 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 停靠。</span><span class="sxs-lookup"><span data-stu-id="c708b-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="c708b-181">设置 <xref:System.Windows.Controls.DockPanel.Dock%2A> 附加属性以将承载的控件停靠在 <xref:System.Windows.Controls.DockPanel> 元素中。</span><span class="sxs-lookup"><span data-stu-id="c708b-181">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

<span data-ttu-id="c708b-182">若要停靠托管控件，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c708b-182">To dock a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="c708b-183">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：</span><span class="sxs-lookup"><span data-stu-id="c708b-183">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="c708b-184">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c708b-184">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="c708b-185"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素停靠在元素的右侧 <xref:System.Windows.Controls.DockPanel> 。</span><span class="sxs-lookup"><span data-stu-id="c708b-185">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="c708b-186">设置可见性</span><span class="sxs-lookup"><span data-stu-id="c708b-186">Setting Visibility</span></span>

<span data-ttu-id="c708b-187">可以通过在元素上设置属性，使 Windows 窗体控件不可见或折叠 <xref:System.Windows.UIElement.Visibility%2A> <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。</span><span class="sxs-lookup"><span data-stu-id="c708b-187">You can make your Windows Forms control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="c708b-188">当控件不可见时，控件不会显示，但会占据布局空间。</span><span class="sxs-lookup"><span data-stu-id="c708b-188">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="c708b-189">当控件处于折叠状态时，控件不会显示，也不会占据布局空间。</span><span class="sxs-lookup"><span data-stu-id="c708b-189">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

<span data-ttu-id="c708b-190">若要设置寄宿的控件的可见性，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c708b-190">To set the visibility of a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="c708b-191">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：</span><span class="sxs-lookup"><span data-stu-id="c708b-191">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="c708b-192">在 *mainwindow.xaml* 或 *mainwindow.xaml* 中，将以下代码复制到类定义中：</span><span class="sxs-lookup"><span data-stu-id="c708b-192">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="c708b-193">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c708b-193">Press <kbd>F5</kbd> to build and run the application.</span></span>

4. <span data-ttu-id="c708b-194">单击 " **单击以使不可见** " 按钮，使 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素不可见。</span><span class="sxs-lookup"><span data-stu-id="c708b-194">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="c708b-195">单击 " **单击以折叠** " 按钮可 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 完全隐藏布局中的元素。</span><span class="sxs-lookup"><span data-stu-id="c708b-195">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="c708b-196">折叠 Windows 窗体控件时，会重新排列周围的元素以占用其空间。</span><span class="sxs-lookup"><span data-stu-id="c708b-196">When the Windows Forms control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="c708b-197">承载不拉伸的控件</span><span class="sxs-lookup"><span data-stu-id="c708b-197">Hosting a Control That Does Not Stretch</span></span>

<span data-ttu-id="c708b-198">某些 Windows 窗体控件具有固定大小，且不会拉伸以填充布局中的可用空间。</span><span class="sxs-lookup"><span data-stu-id="c708b-198">Some Windows Forms controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="c708b-199">例如， <xref:System.Windows.Forms.MonthCalendar> 控件在固定空间中显示月份。</span><span class="sxs-lookup"><span data-stu-id="c708b-199">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

<span data-ttu-id="c708b-200">若要承载不拉伸的控件，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c708b-200">To host a control that does not stretch, follow these steps:</span></span>

1. <span data-ttu-id="c708b-201">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：</span><span class="sxs-lookup"><span data-stu-id="c708b-201">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="c708b-202">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c708b-202">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="c708b-203"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素在网格行中居中，但不拉伸以填充可用空间。</span><span class="sxs-lookup"><span data-stu-id="c708b-203">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="c708b-204">如果窗口足够大，则可能会看到由寄宿控件显示的两个或多个月份 <xref:System.Windows.Forms.MonthCalendar> ，但这两个月居中显示在行中。</span><span class="sxs-lookup"><span data-stu-id="c708b-204">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="c708b-205">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]布局引擎中心元素无法调整大小以填充可用空间。</span><span class="sxs-lookup"><span data-stu-id="c708b-205">The [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="c708b-206">扩展</span><span class="sxs-lookup"><span data-stu-id="c708b-206">Scaling</span></span>

<span data-ttu-id="c708b-207">与 WPF 元素不同，大多数 Windows 窗体控件不是持续缩放的。</span><span class="sxs-lookup"><span data-stu-id="c708b-207">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="c708b-208">若要提供自定义缩放，请重写 <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="c708b-208">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="c708b-209">若要使用默认行为缩放托管控件，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c708b-209">To scale a hosted control by using the default behavior, follow these steps:</span></span>

1. <span data-ttu-id="c708b-210">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：</span><span class="sxs-lookup"><span data-stu-id="c708b-210">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="c708b-211">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c708b-211">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="c708b-212">承载控件及其周围元素按 0.5 的比例进行缩放。</span><span class="sxs-lookup"><span data-stu-id="c708b-212">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="c708b-213">但是，承载控件的字体不缩放。</span><span class="sxs-lookup"><span data-stu-id="c708b-213">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="c708b-214">旋转</span><span class="sxs-lookup"><span data-stu-id="c708b-214">Rotating</span></span>

<span data-ttu-id="c708b-215">与 WPF 元素不同，Windows 窗体控件不支持旋转。</span><span class="sxs-lookup"><span data-stu-id="c708b-215">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="c708b-216"><xref:System.Windows.Forms.Integration.WindowsFormsHost>应用旋转转换后，元素不会随其他 WPF 元素一起旋转。</span><span class="sxs-lookup"><span data-stu-id="c708b-216">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="c708b-217">180度以外的任何旋转值都会引发 <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> 事件。</span><span class="sxs-lookup"><span data-stu-id="c708b-217">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

<span data-ttu-id="c708b-218">若要查看混合应用程序中的旋转效果，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c708b-218">To see the effect of rotation in a hybrid application, follow these steps:</span></span>

1. <span data-ttu-id="c708b-219">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：</span><span class="sxs-lookup"><span data-stu-id="c708b-219">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="c708b-220">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c708b-220">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="c708b-221">承载控件不旋转，但是它周围的元素旋转 180 度。</span><span class="sxs-lookup"><span data-stu-id="c708b-221">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="c708b-222">可能必须调整窗口大小才能看到这些元素。</span><span class="sxs-lookup"><span data-stu-id="c708b-222">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="c708b-223">设置填充和边距</span><span class="sxs-lookup"><span data-stu-id="c708b-223">Setting Padding and Margins</span></span>

<span data-ttu-id="c708b-224">布局中的填充和边距 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 类似于 Windows 窗体中的填充和边距。</span><span class="sxs-lookup"><span data-stu-id="c708b-224">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in Windows Forms.</span></span> <span data-ttu-id="c708b-225">只需 <xref:System.Windows.Controls.Control.Padding%2A> <xref:System.Windows.FrameworkElement.Margin%2A> 在元素上设置和属性即可 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。</span><span class="sxs-lookup"><span data-stu-id="c708b-225">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

<span data-ttu-id="c708b-226">若要为承载的控件设置填充和边距，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c708b-226">To set padding and margins for a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="c708b-227">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：</span><span class="sxs-lookup"><span data-stu-id="c708b-227">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="c708b-228">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c708b-228">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="c708b-229">填充和边距设置将以应用于 Windows 窗体中应用的相同方式应用于承载 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="c708b-229">The padding and margin settings are applied to the hosted Windows Forms controls in the same way they would be applied in Windows Forms.</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="c708b-230">使用动态布局容器</span><span class="sxs-lookup"><span data-stu-id="c708b-230">Using Dynamic Layout Containers</span></span>

<span data-ttu-id="c708b-231">Windows 窗体提供了两个动态布局容器： <xref:System.Windows.Forms.FlowLayoutPanel> 和 <xref:System.Windows.Forms.TableLayoutPanel> 。</span><span class="sxs-lookup"><span data-stu-id="c708b-231">Windows Forms provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="c708b-232">你还可以在布局中使用这些容器 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="c708b-232">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

<span data-ttu-id="c708b-233">若要使用动态布局容器，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c708b-233">To use a dynamic layout container, follow these steps:</span></span>

1. <span data-ttu-id="c708b-234">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素中：</span><span class="sxs-lookup"><span data-stu-id="c708b-234">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="c708b-235">在 *mainwindow.xaml* 或 *mainwindow.xaml* 中，将以下代码复制到类定义中：</span><span class="sxs-lookup"><span data-stu-id="c708b-235">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="c708b-236">`InitializeFlowLayoutPanel`在构造函数中添加对方法的调用：</span><span class="sxs-lookup"><span data-stu-id="c708b-236">Add a call to the `InitializeFlowLayoutPanel` method in the constructor:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. <span data-ttu-id="c708b-237">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c708b-237">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="c708b-238"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素填充 <xref:System.Windows.Controls.DockPanel> ，并 <xref:System.Windows.Forms.FlowLayoutPanel> 将其子控件排列为默认值 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> 。</span><span class="sxs-lookup"><span data-stu-id="c708b-238">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="c708b-239">请参阅</span><span class="sxs-lookup"><span data-stu-id="c708b-239">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="c708b-240">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="c708b-240">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="c708b-241">WindowsFormsHost 元素的布局注意事项</span><span class="sxs-lookup"><span data-stu-id="c708b-241">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="c708b-242">有关在 WPF 中排列 Windows 窗体控件的示例</span><span class="sxs-lookup"><span data-stu-id="c708b-242">Arranging Windows Forms Controls in WPF Sample</span></span>](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WpfLayoutHostingWfWithXaml)
- [<span data-ttu-id="c708b-243">演练：在 WPF 中托管 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="c708b-243">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="c708b-244">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="c708b-244">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
