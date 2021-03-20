---
title: 在 Windows 窗体中托管 3D WPF 复合控件
titleSuffix: ''
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: 17225e27f2ef856c023423bbfeb18cc16128a9b3
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665154"
---
# <a name="walkthrough-host-a-3d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="560e7-102">演练：在 Windows 窗体中托管 3D WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="560e7-102">Walkthrough: Host a 3D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="560e7-103">本演练演示如何创建 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 复合控件，并使用控件在 Windows 窗体控件和窗体中承载它 <xref:System.Windows.Forms.Integration.ElementHost> 。</span><span class="sxs-lookup"><span data-stu-id="560e7-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in Windows Forms controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="560e7-104">在本演练中，您将实现一个 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 包含两个子控件的。</span><span class="sxs-lookup"><span data-stu-id="560e7-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="560e7-105"><xref:System.Windows.Controls.UserControl>显示三维 (3d) 圆锥。</span><span class="sxs-lookup"><span data-stu-id="560e7-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3D) cone.</span></span> <span data-ttu-id="560e7-106">与 Windows 窗体相比，呈现3D 对象更容易 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="560e7-106">Rendering 3D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] than with Windows Forms.</span></span> <span data-ttu-id="560e7-107">因此， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 在 Windows 窗体中承载类以创建三维图形是有意义的。</span><span class="sxs-lookup"><span data-stu-id="560e7-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3D graphics in Windows Forms.</span></span>

<span data-ttu-id="560e7-108">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="560e7-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="560e7-109">创建 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 。</span><span class="sxs-lookup"><span data-stu-id="560e7-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

- <span data-ttu-id="560e7-110">正在创建 Windows 窗体主机项目。</span><span class="sxs-lookup"><span data-stu-id="560e7-110">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="560e7-111">承载的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 。</span><span class="sxs-lookup"><span data-stu-id="560e7-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="560e7-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="560e7-112">Prerequisites</span></span>

<span data-ttu-id="560e7-113">您需要满足以下条件才能完成本演练：</span><span class="sxs-lookup"><span data-stu-id="560e7-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="560e7-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="560e7-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>

## <a name="create-the-usercontrol"></a><span data-ttu-id="560e7-115">创建 UserControl</span><span class="sxs-lookup"><span data-stu-id="560e7-115">Create the UserControl</span></span>

1. <span data-ttu-id="560e7-116">创建一个名为的 **WPF 用户控件库** 项目 `HostingWpfUserControlInWf` 。</span><span class="sxs-lookup"><span data-stu-id="560e7-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="560e7-117">在 WPF 设计器中打开 UserControl1。</span><span class="sxs-lookup"><span data-stu-id="560e7-117">Open UserControl1.xaml in the WPF Designer.</span></span>

3. <span data-ttu-id="560e7-118">将生成的代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="560e7-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="560e7-119">此代码定义一个 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 包含两个子控件的。</span><span class="sxs-lookup"><span data-stu-id="560e7-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="560e7-120">第一个子控件是一个 <xref:System.Windows.Controls.Label?displayProperty=nameWithType> 控件; 第二个控件是 <xref:System.Windows.Controls.Viewport3D> 显示三维圆锥的控件。</span><span class="sxs-lookup"><span data-stu-id="560e7-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>

## <a name="create-the-host-project"></a><span data-ttu-id="560e7-121">创建主机项目</span><span class="sxs-lookup"><span data-stu-id="560e7-121">Create the host project</span></span>

1. <span data-ttu-id="560e7-122">将名为的 **Windows 窗体应用 ( .NET Framework)** 项目添加 `WpfUserControlHost` 到解决方案中。</span><span class="sxs-lookup"><span data-stu-id="560e7-122">Add a **Windows Forms App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span>

2. <span data-ttu-id="560e7-123">在 **解决方案资源管理器** 中，添加对名为 WindowsFormsIntegration.dll 的 WindowsFormsIntegration 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="560e7-123">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="560e7-124">添加对以下 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="560e7-124">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    - <span data-ttu-id="560e7-125">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="560e7-125">PresentationCore</span></span>

    - <span data-ttu-id="560e7-126">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="560e7-126">PresentationFramework</span></span>

    - <span data-ttu-id="560e7-127">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="560e7-127">WindowsBase</span></span>

4. <span data-ttu-id="560e7-128">添加对项目的引用 `HostingWpfUserControlInWf` 。</span><span class="sxs-lookup"><span data-stu-id="560e7-128">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="560e7-129">在解决方案资源管理器中，将 `WpfUserControlHost` 项目设置为 "启动项目"。</span><span class="sxs-lookup"><span data-stu-id="560e7-129">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>

## <a name="host-the-usercontrol"></a><span data-ttu-id="560e7-130">承载 UserControl</span><span class="sxs-lookup"><span data-stu-id="560e7-130">Host the UserControl</span></span>

1. <span data-ttu-id="560e7-131">在 Windows 窗体设计器中，打开 "Form1"。</span><span class="sxs-lookup"><span data-stu-id="560e7-131">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="560e7-132">在属性窗口中，单击 " **事件**"，然后双击 <xref:System.Windows.Forms.Form.Load> 事件以创建事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="560e7-132">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="560e7-133">"代码编辑器" 将打开新生成的 `Form1_Load` 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="560e7-133">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="560e7-134">将 Form1 中的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="560e7-134">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="560e7-135">`Form1_Load`事件处理程序创建的一个实例 `UserControl1` ，并将内部 <xref:System.Windows.Forms.Integration.ElementHost> 控件的子控件集合。</span><span class="sxs-lookup"><span data-stu-id="560e7-135">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="560e7-136"><xref:System.Windows.Forms.Integration.ElementHost>控件将添加到窗体的子控件集合。</span><span class="sxs-lookup"><span data-stu-id="560e7-136">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="560e7-137">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="560e7-137">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="560e7-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="560e7-138">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="560e7-139">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="560e7-139">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="560e7-140">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="560e7-140">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="560e7-141">演练：在 WPF 中托管 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="560e7-141">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="560e7-142">在 Windows 窗体示例中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="560e7-142">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WindowsFormsHostingWpfControl)
