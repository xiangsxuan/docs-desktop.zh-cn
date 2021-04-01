---
title: 如何：创建作为 UI 的外接程序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: fd37e651dc94485becf972533bc095f9ad253335
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973029"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a><span data-ttu-id="b88d1-102">如何：创建作为 UI 的外接程序</span><span class="sxs-lookup"><span data-stu-id="b88d1-102">How to: Create an Add-In That Is a UI</span></span>

<span data-ttu-id="b88d1-103">此示例演示如何创建一个外接程序，该外接程序是由 WPF 独立应用程序承载的 (WPF) Windows Presentation Foundation。</span><span class="sxs-lookup"><span data-stu-id="b88d1-103">This example shows how to create an add-in that is a Windows Presentation Foundation (WPF) which is hosted by a WPF standalone application.</span></span>  
  
 <span data-ttu-id="b88d1-104">外接程序是一个用户界面，它是一个 WPF 用户控件。</span><span class="sxs-lookup"><span data-stu-id="b88d1-104">The add-in is a UI that is a WPF user control.</span></span> <span data-ttu-id="b88d1-105">用户控件的内容是单个按钮，单击时会显示消息框。</span><span class="sxs-lookup"><span data-stu-id="b88d1-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="b88d1-106">WPF 独立应用程序承载外接程序 UI 作为主应用程序窗口的内容。</span><span class="sxs-lookup"><span data-stu-id="b88d1-106">The WPF standalone application hosts the add-in UI as the content of the main application window.</span></span>  
  
 <span data-ttu-id="b88d1-107">**必备条件**</span><span class="sxs-lookup"><span data-stu-id="b88d1-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="b88d1-108">此示例突出显示了支持此方案的 .NET Framework 外接程序模型的 WPF 扩展，并假设以下内容：</span><span class="sxs-lookup"><span data-stu-id="b88d1-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="b88d1-109">.NET Framework 外接程序模型（包括管道、外接程序和主机开发）的知识。</span><span class="sxs-lookup"><span data-stu-id="b88d1-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="b88d1-110">如果不熟悉这些概念，请参阅 [外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))。</span><span class="sxs-lookup"><span data-stu-id="b88d1-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="b88d1-111">有关演示管道、外接程序和主机应用程序实现的教程，请参阅 [演练：创建可扩展的应用程序](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))。</span><span class="sxs-lookup"><span data-stu-id="b88d1-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).</span></span>  
  
- <span data-ttu-id="b88d1-112">了解 .NET Framework 外接程序模型的 WPF 扩展。</span><span class="sxs-lookup"><span data-stu-id="b88d1-112">Knowledge of the WPF extensions to the .NET Framework add-in model.</span></span> <span data-ttu-id="b88d1-113">请参阅 [WPF Add-Ins 概述](wpf-add-ins-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b88d1-113">See [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b88d1-114">示例</span><span class="sxs-lookup"><span data-stu-id="b88d1-114">Example</span></span>  

 <span data-ttu-id="b88d1-115">若要创建作为 WPF UI 的外接程序，需要每个管道段、外接程序和宿主应用程序的特定代码。</span><span class="sxs-lookup"><span data-stu-id="b88d1-115">To create an add-in that is a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>

## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="b88d1-116">实现协定管道段</span><span class="sxs-lookup"><span data-stu-id="b88d1-116">Implementing the Contract Pipeline Segment</span></span>

<span data-ttu-id="b88d1-117">当外接程序是 UI 时，外接程序的协定必须实现 <xref:System.AddIn.Contract.INativeHandleContract> 。</span><span class="sxs-lookup"><span data-stu-id="b88d1-117">When an add-in is a UI, the contract for the add-in must implement <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="b88d1-118">在此示例中， `IWPFAddInContract` 实现 <xref:System.AddIn.Contract.INativeHandleContract> ，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="b88d1-118">In the example, `IWPFAddInContract` implements <xref:System.AddIn.Contract.INativeHandleContract>, as shown in the following code.</span></span>  
  
[!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
[!code-vb[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]

<a name="AddInViewPipeline"></a>

## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="b88d1-119">实现外接程序视图管道段</span><span class="sxs-lookup"><span data-stu-id="b88d1-119">Implementing the Add-In View Pipeline Segment</span></span>

<span data-ttu-id="b88d1-120">由于外接程序作为类型的子类实现 <xref:System.Windows.FrameworkElement> ，外接程序视图还必须是子类 <xref:System.Windows.FrameworkElement> 。</span><span class="sxs-lookup"><span data-stu-id="b88d1-120">Because the add-in is implemented as a subclass of the <xref:System.Windows.FrameworkElement> type, the add-in view must also subclass <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="b88d1-121">下面的代码演示作为类实现的协定的外接程序视图 `WPFAddInView` 。</span><span class="sxs-lookup"><span data-stu-id="b88d1-121">The following code shows the add-in view of the contract, implemented as the `WPFAddInView` class.</span></span>  
  
[!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
[!code-vb[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInViews/WPFAddInView.vb#AddInViewCode)]  
  
<span data-ttu-id="b88d1-122">此处，外接程序视图派生自 <xref:System.Windows.Controls.UserControl> 。</span><span class="sxs-lookup"><span data-stu-id="b88d1-122">Here, the add-in view is derived from <xref:System.Windows.Controls.UserControl>.</span></span> <span data-ttu-id="b88d1-123">因此，外接程序 UI 还应派生自 <xref:System.Windows.Controls.UserControl> 。</span><span class="sxs-lookup"><span data-stu-id="b88d1-123">Consequently, the add-in UI should also derive from <xref:System.Windows.Controls.UserControl>.</span></span>  
  
<a name="AddInSideAdapter"></a>

## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="b88d1-124">实现外接程序端适配器管道段</span><span class="sxs-lookup"><span data-stu-id="b88d1-124">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>

<span data-ttu-id="b88d1-125">当协定为时 <xref:System.AddIn.Contract.INativeHandleContract> ，外接程序为外接程序 <xref:System.Windows.FrameworkElement> 视图管道段指定的 () 。</span><span class="sxs-lookup"><span data-stu-id="b88d1-125">While the contract is an <xref:System.AddIn.Contract.INativeHandleContract>, the add-in is a <xref:System.Windows.FrameworkElement> (as specified by the add-in view pipeline segment).</span></span> <span data-ttu-id="b88d1-126">因此， <xref:System.Windows.FrameworkElement> 必须先将转换为， <xref:System.AddIn.Contract.INativeHandleContract> 然后才能跨越隔离边界。</span><span class="sxs-lookup"><span data-stu-id="b88d1-126">Therefore, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="b88d1-127">此工作由外接程序端适配器通过调用执行 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> ，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="b88d1-127">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
[!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
[!code-vb[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]

<span data-ttu-id="b88d1-128">在加载项返回 UI 的外接程序模型中 (参见 [创建返回 ui](how-to-create-an-add-in-that-returns-a-ui.md)) 的 Add-In，外接程序适配器 <xref:System.Windows.FrameworkElement> 通过调用将转换为 <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b88d1-128">In the add-in model where an add-in returns a UI (see [Create an Add-In That Returns a UI](how-to-create-an-add-in-that-returns-a-ui.md)), the add-in adapter converted the <xref:System.Windows.FrameworkElement> to an <xref:System.AddIn.Contract.INativeHandleContract> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.</span></span> <span data-ttu-id="b88d1-129"><xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 还必须在此模型中调用，不过，您需要实现一个方法，通过该方法可以编写代码来调用它。</span><span class="sxs-lookup"><span data-stu-id="b88d1-129"><xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> must also be called in this model, although you need to implement a method from which to write the code to call it.</span></span> <span data-ttu-id="b88d1-130">为此，可以重写 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 和实现调用的代码（ <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 如果调用的代码 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 应 <xref:System.AddIn.Contract.INativeHandleContract> 为）。</span><span class="sxs-lookup"><span data-stu-id="b88d1-130">You do this by overriding <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> and implementing the code that calls <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> if the code that is calling <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> is expecting an <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="b88d1-131">在此情况下，调用方将为主机端适配器，这在后续子节中有所介绍。</span><span class="sxs-lookup"><span data-stu-id="b88d1-131">In this case, the caller will be the host-side adapter, which is covered in a subsequent subsection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b88d1-132">还需要 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 在此模型中重写，以便在宿主应用程序 ui 和外接程序 ui 之间启用 tab 键切换。</span><span class="sxs-lookup"><span data-stu-id="b88d1-132">You also need to override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> in this model to enable tabbing between host application UI and add-in UI.</span></span> <span data-ttu-id="b88d1-133">有关详细信息，请参阅 Wpf 中的 "WPF Add-In 限制" [Add-Ins 概述](wpf-add-ins-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b88d1-133">For more information, see "WPF Add-In Limitations" in [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
<span data-ttu-id="b88d1-134">由于外接程序端适配器实现了一个派生自的接口 <xref:System.AddIn.Contract.INativeHandleContract> ，因此您还需要实现 <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A> ，但在重写时，将忽略此情况 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b88d1-134">Because the add-in-side adapter implements an interface that derives from <xref:System.AddIn.Contract.INativeHandleContract>, you also need to implement <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, although this is ignored when <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> is overridden.</span></span>  
  
<a name="HostViewPipeline"></a>

## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="b88d1-135">实现主机视图管道段</span><span class="sxs-lookup"><span data-stu-id="b88d1-135">Implementing the Host View Pipeline Segment</span></span>

<span data-ttu-id="b88d1-136">在此模型中，主机应用程序通常要求主机视图为 <xref:System.Windows.FrameworkElement> 子类。</span><span class="sxs-lookup"><span data-stu-id="b88d1-136">In this model, the host application typically expects the host view to be a <xref:System.Windows.FrameworkElement> subclass.</span></span> <span data-ttu-id="b88d1-137">宿主端适配器必须在 <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.Windows.FrameworkElement> 跨越隔离边界之后将转换为 <xref:System.AddIn.Contract.INativeHandleContract> 。</span><span class="sxs-lookup"><span data-stu-id="b88d1-137">The host-side adapter must convert the <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> after the <xref:System.AddIn.Contract.INativeHandleContract> crosses the isolation boundary.</span></span> <span data-ttu-id="b88d1-138">由于宿主应用程序未调用方法来获取 <xref:System.Windows.FrameworkElement> ，因此宿主视图必须 <xref:System.Windows.FrameworkElement> 通过包含它来 "返回"。</span><span class="sxs-lookup"><span data-stu-id="b88d1-138">Because a method isn't being called by the host application to get the <xref:System.Windows.FrameworkElement>, the host view must "return" the <xref:System.Windows.FrameworkElement> by containing it.</span></span> <span data-ttu-id="b88d1-139">因此，宿主视图必须派生自 <xref:System.Windows.FrameworkElement> 可包含其他 ui 的子类，如 <xref:System.Windows.Controls.UserControl> 。</span><span class="sxs-lookup"><span data-stu-id="b88d1-139">Consequently, the host view must derive from a subclass of <xref:System.Windows.FrameworkElement> that can contain other UIs, such as <xref:System.Windows.Controls.UserControl>.</span></span> <span data-ttu-id="b88d1-140">下面的代码演示作为类实现的协定的主机视图 `WPFAddInHostView` 。</span><span class="sxs-lookup"><span data-stu-id="b88d1-140">The following code shows the host view of the contract, implemented as the `WPFAddInHostView` class.</span></span>  

[!code-csharp[WPFAddInHostView class](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostViews/WPFAddInHostView.cs#HostViewCode)]
[!code-vb[WPFAddInHostView class](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostViews/WPFAddInHostView.vb#HostViewCode)]

<a name="HostSideAdapter"></a>

## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="b88d1-141">实现主机端适配器管道段</span><span class="sxs-lookup"><span data-stu-id="b88d1-141">Implementing the Host-Side Adapter Pipeline Segment</span></span>

<span data-ttu-id="b88d1-142">当协定是时 <xref:System.AddIn.Contract.INativeHandleContract> ，主机应用程序需要 <xref:System.Windows.Controls.UserControl> 由宿主视图) 指定的 (。</span><span class="sxs-lookup"><span data-stu-id="b88d1-142">While the contract is an <xref:System.AddIn.Contract.INativeHandleContract>, the host application expects a <xref:System.Windows.Controls.UserControl> (as specified by the host view).</span></span> <span data-ttu-id="b88d1-143">因此， <xref:System.AddIn.Contract.INativeHandleContract> 必须在 <xref:System.Windows.FrameworkElement> 越过隔离边界之后将转换为，然后才能将设置为宿主视图的内容， (从 <xref:System.Windows.Controls.UserControl>) 派生。</span><span class="sxs-lookup"><span data-stu-id="b88d1-143">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary, before being set as content of the host view (which derives from <xref:System.Windows.Controls.UserControl>).</span></span>  
  
<span data-ttu-id="b88d1-144">这一工作由主机端适配器执行，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="b88d1-144">This work is performed by the host-side adapter, as shown in the following code.</span></span>  

[!code-csharp[Host-side adapter](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#HostSideAdapterCode)]
[!code-vb[Host-side adapter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#HostSideAdapterCode)]

<span data-ttu-id="b88d1-145">如您所见，主机端适配器 <xref:System.AddIn.Contract.INativeHandleContract> 通过调用外接程序端适配器的方法获取， <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> (这是 <xref:System.AddIn.Contract.INativeHandleContract> 跨越隔离边界) 的点。</span><span class="sxs-lookup"><span data-stu-id="b88d1-145">As you can see, the host-side adapter acquires the <xref:System.AddIn.Contract.INativeHandleContract> by calling the add-in-side adapter's <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> method (this is the point where the <xref:System.AddIn.Contract.INativeHandleContract> crosses the isolation boundary).</span></span>  
  
<span data-ttu-id="b88d1-146">然后，宿主端适配器 <xref:System.AddIn.Contract.INativeHandleContract> 通过调用将转换为 <xref:System.Windows.FrameworkElement> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b88d1-146">The host-side adapter then converts the <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.</span></span> <span data-ttu-id="b88d1-147">最后，将 <xref:System.Windows.FrameworkElement> 设置为宿主视图的内容。</span><span class="sxs-lookup"><span data-stu-id="b88d1-147">Finally, the <xref:System.Windows.FrameworkElement> is set as the content of the host view.</span></span>  
  
<a name="AddIn"></a>

## <a name="implementing-the-add-in"></a><span data-ttu-id="b88d1-148">实现外接程序</span><span class="sxs-lookup"><span data-stu-id="b88d1-148">Implementing the Add-In</span></span>

<span data-ttu-id="b88d1-149">外接程序端适配器和外接程序视图就位后，外接程序就可以通过派生自外接程序视图来实现，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="b88d1-149">With the add-in-side adapter and add-in view in place, the add-in can be implemented by deriving from the add-in view, as shown in the following code.</span></span>  

[!code-csharp[Add-in implementation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#AddInCodeBehind)]
[!code-vb[Add-in implementation](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#AddInCodeBehind)]

<span data-ttu-id="b88d1-150">在此示例中，你可以看到此模型的一个有趣的优点：外接程序开发人员只需实现外接程序， (因为它是 UI，而不是加载项类和外接程序 UI) 。</span><span class="sxs-lookup"><span data-stu-id="b88d1-150">From this example, you can see one interesting benefit of this model: add-in developers only need to implement the add-in (since it is the UI as well), rather than both an add-in class and an add-in UI.</span></span>  
  
<a name="HostApp"></a>

## <a name="implementing-the-host-application"></a><span data-ttu-id="b88d1-151">实现主机应用程序</span><span class="sxs-lookup"><span data-stu-id="b88d1-151">Implementing the Host Application</span></span>

<span data-ttu-id="b88d1-152">创建主机端适配器和主机视图后，宿主应用程序可以使用 .NET Framework 外接程序模型打开管道并获取外接程序的宿主视图。</span><span class="sxs-lookup"><span data-stu-id="b88d1-152">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline and acquire a host view of the add-in.</span></span> <span data-ttu-id="b88d1-153">这些步骤在以下代码中显示。</span><span class="sxs-lookup"><span data-stu-id="b88d1-153">These steps are shown in the following code.</span></span>  

[!code-csharp[Acquiring a host view of the add-in](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Host/MainWindow.xaml.cs#GetUICode)]
[!code-vb[Acquiring a host view of the add-in](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Host/MainWindow.xaml.vb#GetUICode)]

<span data-ttu-id="b88d1-154">宿主应用程序使用典型 .NET Framework 外接程序模型代码激活外接程序，该外接程序将宿主视图隐式返回到主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="b88d1-154">The host application uses typical .NET Framework add-in model code to activate the add-in, which implicitly returns the host view to the host application.</span></span> <span data-ttu-id="b88d1-155">宿主应用程序随后会显示宿主视图 (这是中的一个 <xref:System.Windows.Controls.UserControl>) <xref:System.Windows.Controls.Grid> 。</span><span class="sxs-lookup"><span data-stu-id="b88d1-155">The host application subsequently displays the host view (which is a <xref:System.Windows.Controls.UserControl>) from a <xref:System.Windows.Controls.Grid>.</span></span>  
  
 <span data-ttu-id="b88d1-156">用于处理与外接程序 UI 交互的代码在外接程序的应用程序域中运行。</span><span class="sxs-lookup"><span data-stu-id="b88d1-156">The code for processing interactions with the add-in UI runs in the add-in's application domain.</span></span> <span data-ttu-id="b88d1-157">这些交互包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="b88d1-157">These interactions include the following:</span></span>  
  
- <span data-ttu-id="b88d1-158">处理 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件。</span><span class="sxs-lookup"><span data-stu-id="b88d1-158">Handling the <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
- <span data-ttu-id="b88d1-159">显示 <xref:System.Windows.MessageBox> 。</span><span class="sxs-lookup"><span data-stu-id="b88d1-159">Showing the <xref:System.Windows.MessageBox>.</span></span>  
  
 <span data-ttu-id="b88d1-160">此活动完全独立于主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="b88d1-160">This activity is completely isolated from the host application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b88d1-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="b88d1-161">See also</span></span>

- <span data-ttu-id="b88d1-162">[外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="b88d1-162">[Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="b88d1-163">WPF 外接程序概述</span><span class="sxs-lookup"><span data-stu-id="b88d1-163">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
