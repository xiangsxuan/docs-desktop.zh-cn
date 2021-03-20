---
title: 演练：使用 ElementHost 控件映射属性
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 764d133a259e4f000f40362b3236c18d905228ff
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665219"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="21218-102">演练：使用 ElementHost 控件映射属性</span><span class="sxs-lookup"><span data-stu-id="21218-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>

<span data-ttu-id="21218-103">本演练演示如何使用 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> 属性将 Windows 窗体属性映射到寄宿元素上的相应属性 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="21218-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map Windows Forms properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>

<span data-ttu-id="21218-104">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="21218-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="21218-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="21218-105">Creating the project.</span></span>

- <span data-ttu-id="21218-106">定义新的属性映射。</span><span class="sxs-lookup"><span data-stu-id="21218-106">Defining a new property mapping.</span></span>

- <span data-ttu-id="21218-107">删除默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="21218-107">Removing a default property mapping.</span></span>

- <span data-ttu-id="21218-108">扩展默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="21218-108">Extending a default property mapping.</span></span>

<span data-ttu-id="21218-109">完成后，你将能够将 Windows 窗体属性映射到 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 寄宿元素上的相应属性。</span><span class="sxs-lookup"><span data-stu-id="21218-109">When you are finished, you will be able to map Windows Forms properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="21218-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="21218-110">Prerequisites</span></span>

<span data-ttu-id="21218-111">您需要满足以下条件才能完成本演练：</span><span class="sxs-lookup"><span data-stu-id="21218-111">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="21218-112">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="21218-112">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="21218-113">创建项目</span><span class="sxs-lookup"><span data-stu-id="21218-113">Creating the Project</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="21218-114">创建项目</span><span class="sxs-lookup"><span data-stu-id="21218-114">To create the project</span></span>

1. <span data-ttu-id="21218-115">创建一个名为的 **Windows 窗体应用程序** 项目 `PropertyMappingWithElementHost` 。</span><span class="sxs-lookup"><span data-stu-id="21218-115">Create a **Windows Forms App** project named `PropertyMappingWithElementHost`.</span></span>

2. <span data-ttu-id="21218-116">在 **解决方案资源管理器** 中，添加对以下 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="21218-116">In **Solution Explorer**, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>

    - <span data-ttu-id="21218-117">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="21218-117">PresentationCore</span></span>

    - <span data-ttu-id="21218-118">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="21218-118">PresentationFramework</span></span>

    - <span data-ttu-id="21218-119">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="21218-119">WindowsBase</span></span>

    - <span data-ttu-id="21218-120">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="21218-120">WindowsFormsIntegration</span></span>

3. <span data-ttu-id="21218-121">将以下代码复制到代码文件的顶部 `Form1` 。</span><span class="sxs-lookup"><span data-stu-id="21218-121">Copy the following code into the top of the `Form1` code file.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. <span data-ttu-id="21218-122">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="21218-122">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="21218-123">双击窗体，为事件添加事件处理程序 <xref:System.Windows.Forms.Form.Load> 。</span><span class="sxs-lookup"><span data-stu-id="21218-123">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>

5. <span data-ttu-id="21218-124">返回到 Windows 窗体设计器并为窗体的事件添加事件处理程序 <xref:System.Windows.Forms.Control.Resize> 。</span><span class="sxs-lookup"><span data-stu-id="21218-124">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="21218-125">有关详细信息，请参阅 [如何：使用设计器创建事件处理程序](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="21218-125">For more information, see [How to: Create Event Handlers Using the Designer](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

6. <span data-ttu-id="21218-126">声明 <xref:System.Windows.Forms.Integration.ElementHost> 类中的字段 `Form1` 。</span><span class="sxs-lookup"><span data-stu-id="21218-126">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a><span data-ttu-id="21218-127">定义新的属性映射</span><span class="sxs-lookup"><span data-stu-id="21218-127">Defining New Property Mappings</span></span>

<span data-ttu-id="21218-128"><xref:System.Windows.Forms.Integration.ElementHost>控件提供了几个默认属性映射。</span><span class="sxs-lookup"><span data-stu-id="21218-128">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="21218-129">通过 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 对控件的调用方法，可以添加新的属性映射 <xref:System.Windows.Forms.Integration.ElementHost> <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> 。</span><span class="sxs-lookup"><span data-stu-id="21218-129">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-define-new-property-mappings"></a><span data-ttu-id="21218-130">定义新的属性映射</span><span class="sxs-lookup"><span data-stu-id="21218-130">To define new property mappings</span></span>

1. <span data-ttu-id="21218-131">将以下代码复制到类的定义中 `Form1` 。</span><span class="sxs-lookup"><span data-stu-id="21218-131">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     <span data-ttu-id="21218-132">`AddMarginMapping`方法为属性添加新的映射 <xref:System.Windows.Forms.Control.Margin%2A> 。</span><span class="sxs-lookup"><span data-stu-id="21218-132">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>

     <span data-ttu-id="21218-133">`OnMarginChange`方法将属性转换 <xref:System.Windows.Forms.Control.Margin%2A> 为 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="21218-133">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>

2. <span data-ttu-id="21218-134">将以下代码复制到类的定义中 `Form1` 。</span><span class="sxs-lookup"><span data-stu-id="21218-134">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     <span data-ttu-id="21218-135">`AddRegionMapping`方法为属性添加新的映射 <xref:System.Windows.Forms.Control.Region%2A> 。</span><span class="sxs-lookup"><span data-stu-id="21218-135">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="21218-136">`OnRegionChange`方法将属性转换 <xref:System.Windows.Forms.Control.Region%2A> 为 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="21218-136">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="21218-137">`Form1_Resize`方法处理窗体的 <xref:System.Windows.Forms.Control.Resize> 事件，并调整剪辑区域的大小以适合承载的元素。</span><span class="sxs-lookup"><span data-stu-id="21218-137">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="21218-138">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="21218-138">Removing a Default Property Mapping</span></span>

<span data-ttu-id="21218-139">通过 <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> 对控件的调用方法，删除默认属性映射 <xref:System.Windows.Forms.Integration.ElementHost> <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> 。</span><span class="sxs-lookup"><span data-stu-id="21218-139">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="21218-140">删除默认属性映射</span><span class="sxs-lookup"><span data-stu-id="21218-140">To remove a default property mapping</span></span>

- <span data-ttu-id="21218-141">将以下代码复制到类的定义中 `Form1` 。</span><span class="sxs-lookup"><span data-stu-id="21218-141">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     <span data-ttu-id="21218-142">`RemoveCursorMapping`方法删除属性的默认映射 <xref:System.Windows.Forms.Control.Cursor%2A> 。</span><span class="sxs-lookup"><span data-stu-id="21218-142">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="21218-143">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="21218-143">Extending a Default Property Mapping</span></span>

<span data-ttu-id="21218-144">可以使用默认属性映射，并使用自己的映射对其进行扩展。</span><span class="sxs-lookup"><span data-stu-id="21218-144">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="21218-145">扩展默认属性映射</span><span class="sxs-lookup"><span data-stu-id="21218-145">To extend a default property mapping</span></span>

- <span data-ttu-id="21218-146">将以下代码复制到类的定义中 `Form1` 。</span><span class="sxs-lookup"><span data-stu-id="21218-146">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     <span data-ttu-id="21218-147">`ExtendBackColorMapping`方法将自定义属性转换器添加到现有的 <xref:System.Windows.Forms.Control.BackColor%2A> 属性映射。</span><span class="sxs-lookup"><span data-stu-id="21218-147">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>

     <span data-ttu-id="21218-148">`OnBackColorChange`方法将特定的图像分配给寄宿控件的 <xref:System.Windows.Controls.Control.Background%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="21218-148">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="21218-149">在 `OnBackColorChange` 应用默认属性映射后，调用方法。</span><span class="sxs-lookup"><span data-stu-id="21218-149">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>

## <a name="initialize-your-property-mappings"></a><span data-ttu-id="21218-150">初始化属性映射</span><span class="sxs-lookup"><span data-stu-id="21218-150">Initialize your property mappings</span></span>

1. <span data-ttu-id="21218-151">将以下代码复制到类的定义中 `Form1` 。</span><span class="sxs-lookup"><span data-stu-id="21218-151">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     <span data-ttu-id="21218-152">`Form1_Load`方法处理 <xref:System.Windows.Forms.Form.Load> 事件并执行以下初始化。</span><span class="sxs-lookup"><span data-stu-id="21218-152">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>

    - <span data-ttu-id="21218-153">创建一个 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> 元素。</span><span class="sxs-lookup"><span data-stu-id="21218-153">Creates a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>

    - <span data-ttu-id="21218-154">调用先前在演练中定义的方法来设置属性映射。</span><span class="sxs-lookup"><span data-stu-id="21218-154">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="21218-155">将初始值分配给映射的属性。</span><span class="sxs-lookup"><span data-stu-id="21218-155">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="21218-156">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="21218-156">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="21218-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="21218-157">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="21218-158">Windows 窗体和 WPF 属性映射</span><span class="sxs-lookup"><span data-stu-id="21218-158">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="21218-159">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="21218-159">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="21218-160">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="21218-160">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
