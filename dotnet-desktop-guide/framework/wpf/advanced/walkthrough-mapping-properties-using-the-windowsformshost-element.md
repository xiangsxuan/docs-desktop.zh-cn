---
title: 演练：使用 WindowsFormsHost 元素映射属性
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: 90101f76438f93e830d32e2e865b19a1f3feb0f9
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667273"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="0a772-102">演练：使用 WindowsFormsHost 元素映射属性</span><span class="sxs-lookup"><span data-stu-id="0a772-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>

<span data-ttu-id="0a772-103">本演练演示如何使用 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> 属性将 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 属性映射到寄宿 Windows 窗体控件上的相应属性。</span><span class="sxs-lookup"><span data-stu-id="0a772-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted Windows Forms control.</span></span>

<span data-ttu-id="0a772-104">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="0a772-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="0a772-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="0a772-105">Creating the project.</span></span>

- <span data-ttu-id="0a772-106">定义应用程序布局。</span><span class="sxs-lookup"><span data-stu-id="0a772-106">Defining the application layout.</span></span>

- <span data-ttu-id="0a772-107">定义新的属性映射。</span><span class="sxs-lookup"><span data-stu-id="0a772-107">Defining a new property mapping.</span></span>

- <span data-ttu-id="0a772-108">删除默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="0a772-108">Removing a default property mapping.</span></span>

- <span data-ttu-id="0a772-109">替换默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="0a772-109">Replacing a default property mapping.</span></span>

- <span data-ttu-id="0a772-110">扩展默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="0a772-110">Extending a default property mapping.</span></span>

<span data-ttu-id="0a772-111">完成后，可以将 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 属性映射到寄宿 Windows 窗体控件上的相应属性。</span><span class="sxs-lookup"><span data-stu-id="0a772-111">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted Windows Forms control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0a772-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="0a772-112">Prerequisites</span></span>

<span data-ttu-id="0a772-113">您需要满足以下条件才能完成本演练：</span><span class="sxs-lookup"><span data-stu-id="0a772-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="0a772-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="0a772-114">Visual Studio 2017</span></span>

## <a name="create-and-set-up-the-project"></a><span data-ttu-id="0a772-115">创建和设置项目</span><span class="sxs-lookup"><span data-stu-id="0a772-115">Create and set up the project</span></span>

1. <span data-ttu-id="0a772-116">创建一个名为的 **WPF 应用程序** 项目 `PropertyMappingWithWfhSample` 。</span><span class="sxs-lookup"><span data-stu-id="0a772-116">Create a **WPF App** project named `PropertyMappingWithWfhSample`.</span></span>

2. <span data-ttu-id="0a772-117">在 **解决方案资源管理器** 中，添加对名为 WindowsFormsIntegration.dll 的 WindowsFormsIntegration 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="0a772-117">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="0a772-118">在 **解决方案资源管理器** 中，添加对 System.web 和 system.web 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="0a772-118">In **Solution Explorer**, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="defining-the-application-layout"></a><span data-ttu-id="0a772-119">定义应用程序布局</span><span class="sxs-lookup"><span data-stu-id="0a772-119">Defining the Application Layout</span></span>

<span data-ttu-id="0a772-120">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]基于的应用程序使用 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素来承载 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="0a772-120">The [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a Windows Forms control.</span></span>

### <a name="to-define-the-application-layout"></a><span data-ttu-id="0a772-121">定义应用程序布局</span><span class="sxs-lookup"><span data-stu-id="0a772-121">To define the application layout</span></span>

1. <span data-ttu-id="0a772-122">在 WPF 设计器中打开 Window1.xaml。</span><span class="sxs-lookup"><span data-stu-id="0a772-122">Open Window1.xaml in the WPF Designer.</span></span>

2. <span data-ttu-id="0a772-123">用下面的代码替换现有代码。</span><span class="sxs-lookup"><span data-stu-id="0a772-123">Replace the existing code with the following code.</span></span>

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3. <span data-ttu-id="0a772-124">在代码编辑器中打开 Window1.xaml.cs。</span><span class="sxs-lookup"><span data-stu-id="0a772-124">Open Window1.xaml.cs in the Code Editor.</span></span>

4. <span data-ttu-id="0a772-125">在该文件顶部导入以下命名空间。</span><span class="sxs-lookup"><span data-stu-id="0a772-125">At the top of the file, import the following namespaces.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="0a772-126">定义新的属性映射</span><span class="sxs-lookup"><span data-stu-id="0a772-126">Defining a New Property Mapping</span></span>

<span data-ttu-id="0a772-127"><xref:System.Windows.Forms.Integration.WindowsFormsHost>元素提供多个默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="0a772-127">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="0a772-128">通过 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 对元素的调用方法，可以添加新的属性映射 <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> 。</span><span class="sxs-lookup"><span data-stu-id="0a772-128">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="0a772-129">定义新的属性映射</span><span class="sxs-lookup"><span data-stu-id="0a772-129">To define a new property mapping</span></span>

- <span data-ttu-id="0a772-130">将以下代码复制到类的定义中 `Window1` 。</span><span class="sxs-lookup"><span data-stu-id="0a772-130">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     <span data-ttu-id="0a772-131">`AddClipMapping`方法为属性添加新的映射 <xref:System.Windows.UIElement.Clip%2A> 。</span><span class="sxs-lookup"><span data-stu-id="0a772-131">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="0a772-132">`OnClipChange`方法将属性转换 <xref:System.Windows.UIElement.Clip%2A> 为 Windows 窗体 <xref:System.Windows.Forms.Control.Region%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="0a772-132">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the Windows Forms<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="0a772-133">`Window1_SizeChanged`方法处理窗口的 <xref:System.Windows.FrameworkElement.SizeChanged> 事件，并调整剪辑区域的大小以适合应用程序窗口。</span><span class="sxs-lookup"><span data-stu-id="0a772-133">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="0a772-134">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="0a772-134">Removing a Default Property Mapping</span></span>

<span data-ttu-id="0a772-135">通过 <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> 对元素的调用方法，删除默认属性映射 <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> 。</span><span class="sxs-lookup"><span data-stu-id="0a772-135">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="0a772-136">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="0a772-136">To remove a default property mapping</span></span>

- <span data-ttu-id="0a772-137">将以下代码复制到类的定义中 `Window1` 。</span><span class="sxs-lookup"><span data-stu-id="0a772-137">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     <span data-ttu-id="0a772-138">`RemoveCursorMapping`方法删除属性的默认映射 <xref:System.Windows.FrameworkElement.Cursor%2A> 。</span><span class="sxs-lookup"><span data-stu-id="0a772-138">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>

## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="0a772-139">替换默认属性映射</span><span class="sxs-lookup"><span data-stu-id="0a772-139">Replacing a Default Property Mapping</span></span>

<span data-ttu-id="0a772-140">通过删除默认映射，并 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 对元素的调用方法来替换默认属性映射 <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> 。</span><span class="sxs-lookup"><span data-stu-id="0a772-140">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="0a772-141">替换默认属性映射</span><span class="sxs-lookup"><span data-stu-id="0a772-141">To replace a default property mapping</span></span>

- <span data-ttu-id="0a772-142">将以下代码复制到类的定义中 `Window1` 。</span><span class="sxs-lookup"><span data-stu-id="0a772-142">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     <span data-ttu-id="0a772-143">`ReplaceFlowDirectionMapping`方法替换属性的默认映射 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 。</span><span class="sxs-lookup"><span data-stu-id="0a772-143">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>

     <span data-ttu-id="0a772-144">`OnFlowDirectionChange`方法将属性转换 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 为 Windows 窗体 <xref:System.Windows.Forms.Control.RightToLeft%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="0a772-144">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the Windows Forms<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>

     <span data-ttu-id="0a772-145">`cb_CheckedChanged`方法处理 <xref:System.Windows.Forms.CheckBox.CheckedChanged> 控件上的事件 <xref:System.Windows.Forms.CheckBox> 。</span><span class="sxs-lookup"><span data-stu-id="0a772-145">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="0a772-146">它 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 基于属性的值分配属性 <xref:System.Windows.Forms.CheckBox.CheckState%2A></span><span class="sxs-lookup"><span data-stu-id="0a772-146">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="0a772-147">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="0a772-147">Extending a Default Property Mapping</span></span>

<span data-ttu-id="0a772-148">可以使用默认属性映射，并使用自己的映射对其进行扩展。</span><span class="sxs-lookup"><span data-stu-id="0a772-148">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="0a772-149">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="0a772-149">To extend a default property mapping</span></span>

- <span data-ttu-id="0a772-150">将以下代码复制到类的定义中 `Window1` 。</span><span class="sxs-lookup"><span data-stu-id="0a772-150">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     <span data-ttu-id="0a772-151">`ExtendBackgroundMapping`方法将自定义属性转换器添加到现有的 <xref:System.Windows.Controls.Control.Background%2A> 属性映射。</span><span class="sxs-lookup"><span data-stu-id="0a772-151">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>

     <span data-ttu-id="0a772-152">`OnBackgroundChange`方法将特定的图像分配给寄宿控件的 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="0a772-152">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="0a772-153">在 `OnBackgroundChange` 应用默认属性映射后，调用方法。</span><span class="sxs-lookup"><span data-stu-id="0a772-153">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>

## <a name="initializing-your-property-mappings"></a><span data-ttu-id="0a772-154">初始化属性映射</span><span class="sxs-lookup"><span data-stu-id="0a772-154">Initializing Your Property Mappings</span></span>

<span data-ttu-id="0a772-155">通过在事件处理程序中调用前面所述的方法来设置属性映射 <xref:System.Windows.FrameworkElement.Loaded> 。</span><span class="sxs-lookup"><span data-stu-id="0a772-155">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="0a772-156">初始化属性映射</span><span class="sxs-lookup"><span data-stu-id="0a772-156">To initialize your property mappings</span></span>

1. <span data-ttu-id="0a772-157">将以下代码复制到类的定义中 `Window1` 。</span><span class="sxs-lookup"><span data-stu-id="0a772-157">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     <span data-ttu-id="0a772-158">`WindowLoaded`方法处理 <xref:System.Windows.FrameworkElement.Loaded> 事件并执行以下初始化。</span><span class="sxs-lookup"><span data-stu-id="0a772-158">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>

    - <span data-ttu-id="0a772-159">创建 Windows 窗体 <xref:System.Windows.Forms.CheckBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="0a772-159">Creates a Windows Forms<xref:System.Windows.Forms.CheckBox> control.</span></span>

    - <span data-ttu-id="0a772-160">调用先前在演练中定义的方法来设置属性映射。</span><span class="sxs-lookup"><span data-stu-id="0a772-160">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="0a772-161">将初始值分配给映射的属性。</span><span class="sxs-lookup"><span data-stu-id="0a772-161">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="0a772-162">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="0a772-162">Press **F5** to build and run the application.</span></span> <span data-ttu-id="0a772-163">单击该复选框可以查看映射的效果 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 。</span><span class="sxs-lookup"><span data-stu-id="0a772-163">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="0a772-164">单击复选框时，布局会反转其左右方向。</span><span class="sxs-lookup"><span data-stu-id="0a772-164">When you click the check box, the layout reverses its left-right orientation.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a772-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a772-165">See also</span></span>

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="0a772-166">Windows 窗体和 WPF 属性映射</span><span class="sxs-lookup"><span data-stu-id="0a772-166">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="0a772-167">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="0a772-167">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="0a772-168">演练：在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="0a772-168">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
