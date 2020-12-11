---
title: 如何：创建返回 UI 的外接程序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
ms.openlocfilehash: 8e26a77fcf0d265444316ee374d835791a10749e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973895"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="297d1-102">如何：创建返回 UI 的外接程序</span><span class="sxs-lookup"><span data-stu-id="297d1-102">How to: Create an Add-In That Returns a UI</span></span>

<span data-ttu-id="297d1-103">此示例演示如何创建一个外接程序，该外接程序将 Windows Presentation Foundation (WPF) 返回到宿主 WPF 独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="297d1-103">This example shows how to create an add-in that returns a Windows Presentation Foundation (WPF) to a host WPF standalone application.</span></span>  
  
 <span data-ttu-id="297d1-104">外接程序返回作为 WPF 用户控件的 UI。</span><span class="sxs-lookup"><span data-stu-id="297d1-104">The add-in returns a UI that is a WPF user control.</span></span> <span data-ttu-id="297d1-105">用户控件的内容是单个按钮，单击时会显示消息框。</span><span class="sxs-lookup"><span data-stu-id="297d1-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="297d1-106">WPF 独立应用程序承载外接程序，并将外接程序返回的用户控件 (显示) 作为主应用程序窗口的内容。</span><span class="sxs-lookup"><span data-stu-id="297d1-106">The WPF standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="297d1-107">**先决条件**</span><span class="sxs-lookup"><span data-stu-id="297d1-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="297d1-108">此示例突出显示了支持此方案的 .NET Framework 外接程序模型的 WPF 扩展，并假设以下内容：</span><span class="sxs-lookup"><span data-stu-id="297d1-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="297d1-109">.NET Framework 外接程序模型（包括管道、外接程序和主机开发）的知识。</span><span class="sxs-lookup"><span data-stu-id="297d1-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="297d1-110">如果不熟悉这些概念，请参阅 [外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))。</span><span class="sxs-lookup"><span data-stu-id="297d1-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="297d1-111">有关演示管道、外接程序和主机应用程序实现的教程，请参阅 [演练：创建可扩展的应用程序](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))。</span><span class="sxs-lookup"><span data-stu-id="297d1-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).</span></span>  
  
- <span data-ttu-id="297d1-112">了解 .NET Framework 外接程序模型的 WPF 扩展，可在以下位置找到： [wpf Add-Ins 概述](wpf-add-ins-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="297d1-112">Knowledge of the WPF extensions to the .NET Framework add-in model, which can be found here: [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="297d1-113">示例</span><span class="sxs-lookup"><span data-stu-id="297d1-113">Example</span></span>  

 <span data-ttu-id="297d1-114">若要创建返回 WPF UI 的外接程序，需要每个管道段、外接程序和宿主应用程序的特定代码。</span><span class="sxs-lookup"><span data-stu-id="297d1-114">To create an add-in that returns a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>

## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="297d1-115">实现协定管道段</span><span class="sxs-lookup"><span data-stu-id="297d1-115">Implementing the Contract Pipeline Segment</span></span>  

 <span data-ttu-id="297d1-116">方法必须由协定定义以返回 UI，并且其返回值的类型必须为 <xref:System.AddIn.Contract.INativeHandleContract> 。</span><span class="sxs-lookup"><span data-stu-id="297d1-116">A method must be defined by the contract for returning a UI, and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="297d1-117">`GetAddInUI`下面的代码中的协定方法对此进行了演示 `IWPFAddInContract` 。</span><span class="sxs-lookup"><span data-stu-id="297d1-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>

## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="297d1-118">实现外接程序视图管道段</span><span class="sxs-lookup"><span data-stu-id="297d1-118">Implementing the Add-In View Pipeline Segment</span></span>  

 <span data-ttu-id="297d1-119">由于外接程序实现它作为的子类提供的 Ui <xref:System.Windows.FrameworkElement> ，因此关联到的外接程序视图上的方法 `IWPFAddInView.GetAddInUI` 必须返回类型为的值 <xref:System.Windows.FrameworkElement> 。</span><span class="sxs-lookup"><span data-stu-id="297d1-119">Because the add-in implements the UIs it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="297d1-120">以下代码显示作为接口实现的协定的外接程序视图。</span><span class="sxs-lookup"><span data-stu-id="297d1-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>

## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="297d1-121">实现外接程序端适配器管道段</span><span class="sxs-lookup"><span data-stu-id="297d1-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  

 <span data-ttu-id="297d1-122">协定方法返回 <xref:System.AddIn.Contract.INativeHandleContract> ，但外接程序按 <xref:System.Windows.FrameworkElement> 外接程序视图) 指定的方式返回 (。</span><span class="sxs-lookup"><span data-stu-id="297d1-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="297d1-123">因此， <xref:System.Windows.FrameworkElement> 必须在 <xref:System.AddIn.Contract.INativeHandleContract> 越过隔离边界之前转换为。</span><span class="sxs-lookup"><span data-stu-id="297d1-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="297d1-124">此工作由外接程序端适配器通过调用执行 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> ，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="297d1-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>

## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="297d1-125">实现主机视图管道段</span><span class="sxs-lookup"><span data-stu-id="297d1-125">Implementing the Host View Pipeline Segment</span></span>  

 <span data-ttu-id="297d1-126">由于宿主应用程序将显示，因此与 <xref:System.Windows.FrameworkElement> 关联的宿主视图上的方法 `IWPFAddInHostView.GetAddInUI` 必须返回类型的值 <xref:System.Windows.FrameworkElement> 。</span><span class="sxs-lookup"><span data-stu-id="297d1-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="297d1-127">以下代码显示作为接口实现的协定的主机视图。</span><span class="sxs-lookup"><span data-stu-id="297d1-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>

## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="297d1-128">实现主机端适配器管道段</span><span class="sxs-lookup"><span data-stu-id="297d1-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  

 <span data-ttu-id="297d1-129">协定方法返回 <xref:System.AddIn.Contract.INativeHandleContract> ，但宿主应用程序需要 <xref:System.Windows.FrameworkElement> (由主机视图) 指定。</span><span class="sxs-lookup"><span data-stu-id="297d1-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="297d1-130">因此， <xref:System.AddIn.Contract.INativeHandleContract> 必须在 <xref:System.Windows.FrameworkElement> 跨越隔离边界之后将转换为。</span><span class="sxs-lookup"><span data-stu-id="297d1-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="297d1-131">此工作由主机端适配器通过调用执行 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> ，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="297d1-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>

## <a name="implementing-the-add-in"></a><span data-ttu-id="297d1-132">实现外接程序</span><span class="sxs-lookup"><span data-stu-id="297d1-132">Implementing the Add-In</span></span>  

 <span data-ttu-id="297d1-133">创建外接程序端适配器和外接程序视图后，外接程序 (`WPFAddIn1.AddIn`) 必须实现 `IWPFAddInView.GetAddInUI` 方法才能返回 <xref:System.Windows.FrameworkElement> (<xref:System.Windows.Controls.UserControl> 此示例) 中的对象。</span><span class="sxs-lookup"><span data-stu-id="297d1-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="297d1-134"><xref:System.Windows.Controls.UserControl>下面的代码显示了的实现 `AddInUI` 。</span><span class="sxs-lookup"><span data-stu-id="297d1-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="297d1-135">`IWPFAddInView.GetAddInUI`外接程序的实现只需返回的新实例 `AddInUI` ，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="297d1-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>

## <a name="implementing-the-host-application"></a><span data-ttu-id="297d1-136">实现主机应用程序</span><span class="sxs-lookup"><span data-stu-id="297d1-136">Implementing the Host Application</span></span>  

 <span data-ttu-id="297d1-137">创建主机端适配器和主机视图后，宿主应用程序可以使用 .NET Framework 外接程序模型打开管道，获取外接程序的宿主视图，并调用 `IWPFAddInHostView.GetAddInUI` 方法。</span><span class="sxs-lookup"><span data-stu-id="297d1-137">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="297d1-138">这些步骤在以下代码中显示。</span><span class="sxs-lookup"><span data-stu-id="297d1-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="297d1-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="297d1-139">See also</span></span>

- <span data-ttu-id="297d1-140">[外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="297d1-140">[Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="297d1-141">WPF 外接程序概述</span><span class="sxs-lookup"><span data-stu-id="297d1-141">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
