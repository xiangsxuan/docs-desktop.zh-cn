---
title: 外接程序概述
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- add-ins and XAML browser applications [WPF]
- add-ins overview [WPF]
- add-ins [WPF], performance
- add-ins [WPF], benefits
- .NET Framework add-in model [WPF]
- add-ins [WPF], user interface
- add-ins and the user interface [WPF]
- add-ins [WPF], architecture
- add-ins [WPF], limitations
ms.assetid: 00b4c776-29a8-4dba-b603-280a0cdc2ade
ms.openlocfilehash: 5847542a1f51312d525d4939d4b21d11b1a70113
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972965"
---
# <a name="wpf-add-ins-overview"></a><span data-ttu-id="cb178-102">WPF 外接程序概述</span><span class="sxs-lookup"><span data-stu-id="cb178-102">WPF Add-Ins Overview</span></span>

<a name="Introduction"></a> <span data-ttu-id="cb178-103">.NET Framework 包含外接程序模型，开发人员可以使用该模型来创建支持外接程序扩展性的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cb178-103">The .NET Framework includes an add-in model that developers can use to create applications that support add-in extensibility.</span></span> <span data-ttu-id="cb178-104">借助此外接程序模型，可以创建与应用程序功能集成并进行扩展的外接程序。</span><span class="sxs-lookup"><span data-stu-id="cb178-104">This add-in model allows the creation of add-ins that integrate with and extend application functionality.</span></span> <span data-ttu-id="cb178-105">在某些情况下，应用程序还需要显示外接程序提供的用户界面。本主题演示 WPF 如何补充 .NET Framework 外接程序模型，以实现这些方案、其背后的体系结构、其优点和其局限性。</span><span class="sxs-lookup"><span data-stu-id="cb178-105">In some scenarios, applications also need to display user interfaces that are provided by add-ins. This topic shows how WPF augments the .NET Framework add-in model to enable these scenarios, the architecture behind it, its benefits, and its limitations.</span></span>

<a name="Requirements"></a>

## <a name="prerequisites"></a><span data-ttu-id="cb178-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="cb178-106">Prerequisites</span></span>

<span data-ttu-id="cb178-107">熟悉 .NET Framework 外接程序模型是必需的。</span><span class="sxs-lookup"><span data-stu-id="cb178-107">Familiarity with the .NET Framework add-in model is required.</span></span> <span data-ttu-id="cb178-108">有关详细信息，请参阅[外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))。</span><span class="sxs-lookup"><span data-stu-id="cb178-108">For more information, see [Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span>

<a name="AddInsOverview"></a>

## <a name="add-ins-overview"></a><span data-ttu-id="cb178-109">外接程序概述</span><span class="sxs-lookup"><span data-stu-id="cb178-109">Add-Ins Overview</span></span>

<span data-ttu-id="cb178-110">为了需要对应用程序重新编译和重新部署才能引入新功能这一复杂过程，应用程序实现了扩展机制，使开发者（包括第一方和第三方）能够创建与应用程序集成的其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="cb178-110">In order to avoid the complexities of application recompilation and redeployment to incorporate new functionality, applications implement extensibility mechanisms that allow developers (both first-party and third-party) to create other applications that integrate with them.</span></span> <span data-ttu-id="cb178-111">支持此扩展性类型的最常见方式是，使用外接程序（也称为“加载项”和“插件”）。</span><span class="sxs-lookup"><span data-stu-id="cb178-111">The most common way to support this type of extensibility is through the use of add-ins (also known as "add-ons" and "plug-ins").</span></span> <span data-ttu-id="cb178-112">通过外接程序公开扩展性的实际应用程序示例包括：</span><span class="sxs-lookup"><span data-stu-id="cb178-112">Examples of real-world applications that expose extensibility with add-ins include:</span></span>

- <span data-ttu-id="cb178-113">Internet Explorer 加载项。</span><span class="sxs-lookup"><span data-stu-id="cb178-113">Internet Explorer add-ons.</span></span>

- <span data-ttu-id="cb178-114">Windows Media Player 插件。</span><span class="sxs-lookup"><span data-stu-id="cb178-114">Windows Media Player plug-ins.</span></span>

- <span data-ttu-id="cb178-115">Visual Studio 外接程序。</span><span class="sxs-lookup"><span data-stu-id="cb178-115">Visual Studio add-ins.</span></span>

<span data-ttu-id="cb178-116">例如，通过 Windows Media Player 外接程序模型，第三方开发人员可以实现“插件”，从而以各种方式对 Windows Media Player 进行扩展，包括为 Windows Media Player 本身不支持的媒体格式（例如 DVD、MP3）创建解码器和编码器，创建音频效果和外观。</span><span class="sxs-lookup"><span data-stu-id="cb178-116">For example, the Windows Media Player add-in model allows third-party developers to implement "plug-ins" that extend Windows Media Player in a variety of ways, including creating decoders and encoders for media formats that are not supported natively by Windows Media Player (for example, DVD, MP3), audio effects, and skins.</span></span> <span data-ttu-id="cb178-117">尽管有一些实体和行为是所有外接程序模型共有的，但会生成每个外接程序模型以公开某个应用程序的特有功能。</span><span class="sxs-lookup"><span data-stu-id="cb178-117">Each add-in model is built to expose the functionality that is unique to an application, although there are several entities and behaviors that are common to all add-in models.</span></span>

<span data-ttu-id="cb178-118">典型外接程序扩展性解决方案的三大实体是“协定”、“外接程序”和“主机应用程序”。</span><span class="sxs-lookup"><span data-stu-id="cb178-118">The three main entities of typical add-in extensibility solutions are *contracts*, *add-ins*, and *host applications*.</span></span> <span data-ttu-id="cb178-119">协定会定义外接程序与主机应用程序之间的两种集成方式：</span><span class="sxs-lookup"><span data-stu-id="cb178-119">Contracts define how add-ins integrate with host applications in two ways:</span></span>

- <span data-ttu-id="cb178-120">外接程序集成主机应用程序所实现的功能。</span><span class="sxs-lookup"><span data-stu-id="cb178-120">Add-ins integrate with functionality that is implemented by host applications.</span></span>

- <span data-ttu-id="cb178-121">主机应用程序公开供外接程序集成的功能。</span><span class="sxs-lookup"><span data-stu-id="cb178-121">Host applications expose functionality for add-ins to integrate with.</span></span>

<span data-ttu-id="cb178-122">为了使外接程序能发挥作用，主机应用程序需要在运行时找到它们并进行加载。</span><span class="sxs-lookup"><span data-stu-id="cb178-122">In order for add-ins to be used, host applications need to find them and load them at run time.</span></span> <span data-ttu-id="cb178-123">因此，支持外接程序的应用程序需要承担以下附加的职责：</span><span class="sxs-lookup"><span data-stu-id="cb178-123">Consequently, applications that support add-ins have the following additional responsibilities:</span></span>

- <span data-ttu-id="cb178-124">**发现**：查找遵循主机应用程序所支持的协定的外接程序。</span><span class="sxs-lookup"><span data-stu-id="cb178-124">**Discovery**: Finding add-ins that adhere to contracts supported by host applications.</span></span>

- <span data-ttu-id="cb178-125">**激活**：加载和运行外接程序并与它们建立通信。</span><span class="sxs-lookup"><span data-stu-id="cb178-125">**Activation**: Loading, running, and establishing communication with add-ins.</span></span>

- <span data-ttu-id="cb178-126">**隔离**：使用应用程序域或进程建立隔离边界，以保护应用程序不受外接程序潜在安全问题和执行问题的影响。</span><span class="sxs-lookup"><span data-stu-id="cb178-126">**Isolation**: Using either application domains or processes to establish isolation boundaries that protect applications from potential security and execution problems with add-ins.</span></span>

- <span data-ttu-id="cb178-127">**通信**：通过调用方法和传递数据，允许外接程序和主机应用程序跨过隔离边界相互通信。</span><span class="sxs-lookup"><span data-stu-id="cb178-127">**Communication**: Allowing add-ins and host applications to communicate with each other across isolation boundaries by calling methods and passing data.</span></span>

- <span data-ttu-id="cb178-128">**生存期管理**：通过可预测的干净方式来加载和卸载应用程序域和进程（请参阅 [应用程序域](/dotnet/framework/app-domains/application-domains)）。</span><span class="sxs-lookup"><span data-stu-id="cb178-128">**Lifetime Management**: Loading and unloading application domains and processes in a clean, predictable manner (see [Application Domains](/dotnet/framework/app-domains/application-domains)).</span></span>

- <span data-ttu-id="cb178-129">**版本管理**：确保在创建主机应用程序或外接程序的新版本后，它们仍可进行通信。</span><span class="sxs-lookup"><span data-stu-id="cb178-129">**Versioning**: Ensuring that host applications and add-ins can still communicate when new versions of either are created.</span></span>

<span data-ttu-id="cb178-130">总之，开发一个可靠的外接程序模型不是一项简单的任务。</span><span class="sxs-lookup"><span data-stu-id="cb178-130">Ultimately, developing a robust add-in model is a non-trivial undertaking.</span></span> <span data-ttu-id="cb178-131">出于此原因，.NET Framework 提供了一个用于生成外接程序模型的基础结构。</span><span class="sxs-lookup"><span data-stu-id="cb178-131">For this reason, the .NET Framework provides an infrastructure for building add-in models.</span></span>

> [!NOTE]
> <span data-ttu-id="cb178-132">有关外接程序的更多详细信息，请参阅[外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))。</span><span class="sxs-lookup"><span data-stu-id="cb178-132">For more detailed information on add-ins, see [Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span>

<a name="NETFrameworkAddInModelOverview"></a>

## <a name="net-framework-add-in-model-overview"></a><span data-ttu-id="cb178-133">.NET Framework 外接程序模型概述</span><span class="sxs-lookup"><span data-stu-id="cb178-133">.NET Framework Add-In Model Overview</span></span>

<span data-ttu-id="cb178-134">命名空间中的 .NET Framework 外接程序模型 <xref:System.AddIn> 包含一组类型，这些类型旨在简化外接程序扩展性的开发。</span><span class="sxs-lookup"><span data-stu-id="cb178-134">The .NET Framework add-in model, found in the <xref:System.AddIn> namespace, contains a set of types that are designed to simplify the development of add-in extensibility.</span></span> <span data-ttu-id="cb178-135">.NET Framework 外接程序模型的基本单位为协定，该 *协定* 定义主机应用程序和外接程序之间的通信方式。</span><span class="sxs-lookup"><span data-stu-id="cb178-135">The fundamental unit of the .NET Framework add-in model is the *contract*, which defines how a host application and an add-in communicate with each other.</span></span> <span data-ttu-id="cb178-136">会使用特定于主机应用程序的协定 *视图* 向主机应用程序公开协定。</span><span class="sxs-lookup"><span data-stu-id="cb178-136">A contract is exposed to a host application using a host-application-specific *view* of the contract.</span></span> <span data-ttu-id="cb178-137">同样，向外接程序公开特定于外接程序的协定 *视图*。</span><span class="sxs-lookup"><span data-stu-id="cb178-137">Likewise, an add-in-specific *view* of the contract is exposed to the add-in.</span></span> <span data-ttu-id="cb178-138">使用 *适配器*，主机应用程序和外接程序可以在它们各自的协定视图之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="cb178-138">An *adapter* is used to allow a host application and an add-in to communicate between their respective views of the contract.</span></span> <span data-ttu-id="cb178-139">协定、视图和适配器称为管道段，一组相关的管道段组成一条 *管道*。</span><span class="sxs-lookup"><span data-stu-id="cb178-139">Contracts, views, and adapters are referred to as segments, and a set of related segments constitutes a *pipeline*.</span></span> <span data-ttu-id="cb178-140">管道是 .NET Framework 外接程序模型支持发现、激活、安全隔离、执行隔离 (使用应用程序域和进程) 、通信、生存期管理和版本控制的基础。</span><span class="sxs-lookup"><span data-stu-id="cb178-140">Pipelines are the foundation upon which the .NET Framework add-in model supports discovery, activation, security isolation, execution isolation (using both application domains and processes), communication, lifetime management, and versioning.</span></span>

<span data-ttu-id="cb178-141">所有这些支持使得开发人员能够生成与主机应用程序的功能相集成的外接程序。</span><span class="sxs-lookup"><span data-stu-id="cb178-141">The sum of this support allows developers to build add-ins that integrate with the functionality of a host application.</span></span> <span data-ttu-id="cb178-142">不过，某些方案需要宿主应用程序显示外接程序提供的用户界面。由于 .NET Framework 中的每个表示技术都有自己的模型来实现用户界面，.NET Framework 外接程序模型不支持任何特定的表示技术。</span><span class="sxs-lookup"><span data-stu-id="cb178-142">However, some scenarios require host applications to display user interfaces provided by add-ins. Because each presentation technology in the .NET Framework has its own model for implementing user interfaces, the .NET Framework add-in model does not support any particular presentation technology.</span></span> <span data-ttu-id="cb178-143">而 WPF 却扩展了 .NET Framework 外接程序模型，其中包含外接程序的 UI 支持。</span><span class="sxs-lookup"><span data-stu-id="cb178-143">Instead, WPF extends the .NET Framework add-in model with UI support for add-ins.</span></span>

<a name="WPFAddInModel"></a>

## <a name="wpf-add-ins"></a><span data-ttu-id="cb178-144">WPF 外接程序</span><span class="sxs-lookup"><span data-stu-id="cb178-144">WPF Add-Ins</span></span>

<span data-ttu-id="cb178-145">WPF 与 .NET Framework 外接程序模型一起使用，可以解决需要宿主应用程序从外接程序显示用户界面的各种方案。具体而言，WPF 使用以下两种编程模型解决了这些方案：</span><span class="sxs-lookup"><span data-stu-id="cb178-145">WPF, in conjunction with the .NET Framework add-in model, allows you to address a wide variety of scenarios that require host applications to display user interfaces from add-ins. In particular, these scenarios are addressed by WPF with the following two programming models:</span></span>

1. <span data-ttu-id="cb178-146">**外接程序返回 UI**。</span><span class="sxs-lookup"><span data-stu-id="cb178-146">**The add-in returns a UI**.</span></span> <span data-ttu-id="cb178-147">外接程序通过方法调用向宿主应用程序返回一个 UI，由协定定义。</span><span class="sxs-lookup"><span data-stu-id="cb178-147">An add-in returns a UI to the host application via a method call, as defined by the contract.</span></span> <span data-ttu-id="cb178-148">此方案可用于以下情况：</span><span class="sxs-lookup"><span data-stu-id="cb178-148">This scenario is used in the following cases:</span></span>

    - <span data-ttu-id="cb178-149">外接程序返回的 UI 的外观依赖于只在运行时存在的数据或条件，如动态生成的报表。</span><span class="sxs-lookup"><span data-stu-id="cb178-149">The appearance of a UI that is returned by an add-in is dependent on either data or conditions that exist only at run time, such as dynamically generated reports.</span></span>

    - <span data-ttu-id="cb178-150">外接程序提供的服务的 UI 不同于可以使用外接程序的宿主应用程序的 UI。</span><span class="sxs-lookup"><span data-stu-id="cb178-150">The UI for services provided by an add-in differs from the UI of the host applications that can use the add-in.</span></span>

    - <span data-ttu-id="cb178-151">外接程序主要为主机应用程序执行服务，并使用 UI 向主机应用程序报告状态。</span><span class="sxs-lookup"><span data-stu-id="cb178-151">The add-in primarily performs a service for the host application, and reports status to the host application with a UI.</span></span>

2. <span data-ttu-id="cb178-152">**外接程序为 UI**。</span><span class="sxs-lookup"><span data-stu-id="cb178-152">**The add-in is a UI**.</span></span> <span data-ttu-id="cb178-153">外接程序是由协定定义的 UI。</span><span class="sxs-lookup"><span data-stu-id="cb178-153">An add-in is a UI, as defined by the contract.</span></span> <span data-ttu-id="cb178-154">此方案可用于以下情况：</span><span class="sxs-lookup"><span data-stu-id="cb178-154">This scenario is used in the following cases:</span></span>

    - <span data-ttu-id="cb178-155">外接程序提供的服务都需要显示，例如广告。</span><span class="sxs-lookup"><span data-stu-id="cb178-155">An add-in doesn't provide services other than being displayed, such as an advertisement.</span></span>

    - <span data-ttu-id="cb178-156">外接程序提供的服务的 UI 对于所有可使用该外接程序的宿主应用程序（如计算器或颜色选取器）都是通用的。</span><span class="sxs-lookup"><span data-stu-id="cb178-156">The UI for services provided by an add-in is common to all host applications that can use that add-in, such as a calculator or color picker.</span></span>

<span data-ttu-id="cb178-157">这些方案要求可以在主机应用程序和外接程序应用程序域之间传递 UI 对象。</span><span class="sxs-lookup"><span data-stu-id="cb178-157">These scenarios require that UI objects can be passed between host application and add-in application domains.</span></span> <span data-ttu-id="cb178-158">由于 .NET Framework 外接程序模型依赖于远程处理来在应用程序域之间进行通信，因此在它们之间传递的对象必须是可远程处理的。</span><span class="sxs-lookup"><span data-stu-id="cb178-158">Since the .NET Framework add-in model relies on remoting to communicate between application domains, the objects that are passed between them must be remotable.</span></span>

<span data-ttu-id="cb178-159">可远程处理的对象是某个类的实例，并执行以下一个或多个任务：</span><span class="sxs-lookup"><span data-stu-id="cb178-159">A remotable object is an instance of a class that does one or more of the following:</span></span>

- <span data-ttu-id="cb178-160">派生自 <xref:System.MarshalByRefObject> 类。</span><span class="sxs-lookup"><span data-stu-id="cb178-160">Derives from the <xref:System.MarshalByRefObject> class.</span></span>

- <span data-ttu-id="cb178-161">实现 <xref:System.Runtime.Serialization.ISerializable> 接口。</span><span class="sxs-lookup"><span data-stu-id="cb178-161">Implements the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>

- <span data-ttu-id="cb178-162">应用了 <xref:System.SerializableAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="cb178-162">Has the <xref:System.SerializableAttribute> attribute applied.</span></span>

> [!NOTE]
> <span data-ttu-id="cb178-163">有关创建可远程处理 .NET Framework 对象的详细信息，请参阅 [使对象可远程](/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100))处理。</span><span class="sxs-lookup"><span data-stu-id="cb178-163">For more information regarding the creation of remotable .NET Framework objects, see [Making Objects Remotable](/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100)).</span></span>

<span data-ttu-id="cb178-164">WPF UI 类型不能远程处理。</span><span class="sxs-lookup"><span data-stu-id="cb178-164">The WPF UI types are not remotable.</span></span> <span data-ttu-id="cb178-165">为了解决此问题，WPF 扩展了 .NET Framework 外接程序模型，以允许从主机应用程序显示外接程序创建的 WPF UI。</span><span class="sxs-lookup"><span data-stu-id="cb178-165">To solve the problem, WPF extends the .NET Framework add-in model to enable WPF UI created by add-ins to be displayed from host applications.</span></span> <span data-ttu-id="cb178-166">此支持由 WPF 通过两种类型提供： <xref:System.AddIn.Contract.INativeHandleContract> 由类实现的接口和两个静态方法 <xref:System.AddIn.Pipeline.FrameworkElementAdapters> ： <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 和 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 。</span><span class="sxs-lookup"><span data-stu-id="cb178-166">This support is provided by WPF by two types: the <xref:System.AddIn.Contract.INativeHandleContract> interface and two static methods implemented by the <xref:System.AddIn.Pipeline.FrameworkElementAdapters> class: <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> and <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.</span></span> <span data-ttu-id="cb178-167">从较高层面来看，这些类型和方法按以下方式使用：</span><span class="sxs-lookup"><span data-stu-id="cb178-167">At a high level, these types and methods are used in the following manner:</span></span>

1. <span data-ttu-id="cb178-168">WPF 要求外接程序提供的用户界面是直接或间接从派生的类 <xref:System.Windows.FrameworkElement> ，如形状、控件、用户控件、布局面板和页面。</span><span class="sxs-lookup"><span data-stu-id="cb178-168">WPF requires that user interfaces provided by add-ins are classes that derive directly or indirectly from <xref:System.Windows.FrameworkElement>, such as shapes, controls, user controls, layout panels, and pages.</span></span>

2. <span data-ttu-id="cb178-169">无论协定声明在外接程序和宿主应用程序之间传递 UI，都必须将其声明为 <xref:System.AddIn.Contract.INativeHandleContract> (而不是 <xref:System.Windows.FrameworkElement>) ; <xref:System.AddIn.Contract.INativeHandleContract> 是可在隔离边界之间传递的外接程序 UI 的可远程表示形式。</span><span class="sxs-lookup"><span data-stu-id="cb178-169">Wherever the contract declares that a UI will be passed between the add-in and the host application, it must be declared as an <xref:System.AddIn.Contract.INativeHandleContract> (not a <xref:System.Windows.FrameworkElement>); <xref:System.AddIn.Contract.INativeHandleContract> is a remotable representation of the add-in UI that can be passed across isolation boundaries.</span></span>

3. <span data-ttu-id="cb178-170">在从外接程序的应用程序域中传递时， <xref:System.Windows.FrameworkElement> 通过调用将作为打包成 <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 。</span><span class="sxs-lookup"><span data-stu-id="cb178-170">Before being passed from the add-in's application domain, a <xref:System.Windows.FrameworkElement> is packaged as an <xref:System.AddIn.Contract.INativeHandleContract> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.</span></span>

4. <span data-ttu-id="cb178-171">向宿主应用程序的应用程序域传递后， <xref:System.AddIn.Contract.INativeHandleContract> 必须通过调用将重新打包为 <xref:System.Windows.FrameworkElement> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 。</span><span class="sxs-lookup"><span data-stu-id="cb178-171">After being passed to the host application's application domain, the <xref:System.AddIn.Contract.INativeHandleContract> must be repackaged as a <xref:System.Windows.FrameworkElement> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.</span></span>

<span data-ttu-id="cb178-172">如何 <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 使用、、和 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 取决于具体的方案。</span><span class="sxs-lookup"><span data-stu-id="cb178-172">How <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, and <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> are used depends on the specific scenario.</span></span> <span data-ttu-id="cb178-173">下面几节介绍每个编程模型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cb178-173">The following sections provide details for each programming model.</span></span>

<a name="ReturnUIFromAddInContract"></a>

## <a name="add-in-returns-a-user-interface"></a><span data-ttu-id="cb178-174">外接程序返回用户界面</span><span class="sxs-lookup"><span data-stu-id="cb178-174">Add-In Returns a User Interface</span></span>

<span data-ttu-id="cb178-175">若要使外接程序向宿主应用程序返回 UI，需要满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="cb178-175">For an add-in to return a UI to a host application, the following are required:</span></span>

1. <span data-ttu-id="cb178-176">必须创建宿主应用程序、外接程序和管道，如 .NET Framework [外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) 文档中所述。</span><span class="sxs-lookup"><span data-stu-id="cb178-176">The host application, add-in, and pipeline must be created, as described by the .NET Framework [Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) documentation.</span></span>

2. <span data-ttu-id="cb178-177">协定必须实现 <xref:System.AddIn.Contract.IContract> 并返回 UI，协定必须使用类型为的返回值声明方法 <xref:System.AddIn.Contract.INativeHandleContract> 。</span><span class="sxs-lookup"><span data-stu-id="cb178-177">The contract must implement <xref:System.AddIn.Contract.IContract> and, to return a UI, the contract must declare a method with a return value of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span>

3. <span data-ttu-id="cb178-178">在外接程序和宿主应用程序之间传递的 UI 必须直接或间接从派生 <xref:System.Windows.FrameworkElement> 。</span><span class="sxs-lookup"><span data-stu-id="cb178-178">The UI that is passed between the add-in and the host application must directly or indirectly derive from <xref:System.Windows.FrameworkElement>.</span></span>

4. <span data-ttu-id="cb178-179">必须先将外接程序返回的 UI 从转换为 <xref:System.Windows.FrameworkElement> ， <xref:System.AddIn.Contract.INativeHandleContract> 然后才能跨越隔离边界。</span><span class="sxs-lookup"><span data-stu-id="cb178-179">The UI that is returned by the add-in must be converted from a <xref:System.Windows.FrameworkElement> to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span>

5. <span data-ttu-id="cb178-180"><xref:System.AddIn.Contract.INativeHandleContract> <xref:System.Windows.FrameworkElement> 在跨越隔离边界之后，必须将返回的 UI 从转换为。</span><span class="sxs-lookup"><span data-stu-id="cb178-180">The UI that is returned must be converted from an <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span>

6. <span data-ttu-id="cb178-181">宿主应用程序将显示返回的 <xref:System.Windows.FrameworkElement> 。</span><span class="sxs-lookup"><span data-stu-id="cb178-181">The host application displays the returned <xref:System.Windows.FrameworkElement>.</span></span>

<span data-ttu-id="cb178-182">有关演示如何实现返回 UI 的外接程序的示例，请参阅 [创建返回 Ui 的 Add-In](how-to-create-an-add-in-that-returns-a-ui.md)。</span><span class="sxs-lookup"><span data-stu-id="cb178-182">For an example that demonstrates how to implement an add-in that returns a UI, see [Create an Add-In That Returns a UI](how-to-create-an-add-in-that-returns-a-ui.md).</span></span>

<a name="AddInIsAUI"></a>

## <a name="add-in-is-a-user-interface"></a><span data-ttu-id="cb178-183">外接程序为用户界面</span><span class="sxs-lookup"><span data-stu-id="cb178-183">Add-In Is a User Interface</span></span>

<span data-ttu-id="cb178-184">当外接程序为 UI 时，需要以下各项：</span><span class="sxs-lookup"><span data-stu-id="cb178-184">When an add-in is a UI, the following are required:</span></span>

1. <span data-ttu-id="cb178-185">必须创建宿主应用程序、外接程序和管道，如 .NET Framework [外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) 文档中所述。</span><span class="sxs-lookup"><span data-stu-id="cb178-185">The host application, add-in, and pipeline must be created, as described by the .NET Framework [Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) documentation.</span></span>

2. <span data-ttu-id="cb178-186">外接程序的协定接口必须实现 <xref:System.AddIn.Contract.INativeHandleContract> 。</span><span class="sxs-lookup"><span data-stu-id="cb178-186">The contract interface for the add-in must implement <xref:System.AddIn.Contract.INativeHandleContract>.</span></span>

3. <span data-ttu-id="cb178-187">传递到主机应用程序的外接程序必须直接或间接从派生 <xref:System.Windows.FrameworkElement> 。</span><span class="sxs-lookup"><span data-stu-id="cb178-187">The add-in that is passed to the host application must directly or indirectly derive from <xref:System.Windows.FrameworkElement>.</span></span>

4. <span data-ttu-id="cb178-188">在 <xref:System.Windows.FrameworkElement> <xref:System.AddIn.Contract.INativeHandleContract> 越过隔离边界之前，外接程序必须从转换为。</span><span class="sxs-lookup"><span data-stu-id="cb178-188">The add-in must be converted from a <xref:System.Windows.FrameworkElement> to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span>

5. <span data-ttu-id="cb178-189">在 <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.Windows.FrameworkElement> 越过隔离边界后，外接程序必须从转换为。</span><span class="sxs-lookup"><span data-stu-id="cb178-189">The add-in must be converted from an <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span>

6. <span data-ttu-id="cb178-190">宿主应用程序将显示返回的 <xref:System.Windows.FrameworkElement> 。</span><span class="sxs-lookup"><span data-stu-id="cb178-190">The host application displays the returned <xref:System.Windows.FrameworkElement>.</span></span>

<span data-ttu-id="cb178-191">有关演示如何实现作为 UI 的外接程序的示例，请参阅 [创建作为 ui 的 Add-In](how-to-create-an-add-in-that-is-a-ui.md)。</span><span class="sxs-lookup"><span data-stu-id="cb178-191">For an example that demonstrates how to implement an add-in that is a UI, see [Create an Add-In That Is a UI](how-to-create-an-add-in-that-is-a-ui.md).</span></span>

<a name="ReturningMultipleUIsFromAnAddIn"></a>

## <a name="returning-multiple-uis-from-an-add-in"></a><span data-ttu-id="cb178-192">从外接程序返回多个 UI</span><span class="sxs-lookup"><span data-stu-id="cb178-192">Returning Multiple UIs from an Add-In</span></span>

<span data-ttu-id="cb178-193">外接程序通常为宿主应用程序提供多个用户界面以显示。</span><span class="sxs-lookup"><span data-stu-id="cb178-193">Add-ins often provide multiple user interfaces for host applications to display.</span></span> <span data-ttu-id="cb178-194">例如，请考虑作为 UI 的外接程序，该外接程序还向宿主应用程序提供状态信息。</span><span class="sxs-lookup"><span data-stu-id="cb178-194">For example, consider an add-in that is a UI that also provides status information to the host application, also as a UI.</span></span> <span data-ttu-id="cb178-195">此类外接程序可以通过结合使用[外接程序返回用户界面](#ReturnUIFromAddInContract)和[外接程序为用户界面](#AddInIsAUI)模型中的技术来实现。</span><span class="sxs-lookup"><span data-stu-id="cb178-195">An add-in like this can be implemented by using a combination of techniques from both the [Add-In Returns a User Interface](#ReturnUIFromAddInContract) and [Add-In Is a User Interface](#AddInIsAUI) models.</span></span>

<a name="AddInsAndXBAPs"></a>

## <a name="add-ins-and-xaml-browser-applications"></a><span data-ttu-id="cb178-196">外接程序和 XAML 浏览器应用程序</span><span class="sxs-lookup"><span data-stu-id="cb178-196">Add-Ins and XAML Browser Applications</span></span>

<span data-ttu-id="cb178-197">到目前为止，示例中的主机应用程序都安装为独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="cb178-197">In the examples so far, the host application has been an installed standalone application.</span></span> <span data-ttu-id="cb178-198">但 XAML 浏览器应用程序 (Xbap) 也可以承载外接程序，但有以下额外的生成和实现要求：</span><span class="sxs-lookup"><span data-stu-id="cb178-198">But XAML browser applications (XBAPs) can also host add-ins, albeit with the following additional build and implementation requirements:</span></span>

- <span data-ttu-id="cb178-199">XBAP 应用程序清单必须经过专门配置，以将管道 (文件夹和程序集) 和外接程序程序集下载到客户端计算机上的 ClickOnce 应用程序缓存中，即 XBAP 所在的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cb178-199">The XBAP application manifest must be configured specially to download the pipeline (folders and assemblies) and add-in assembly to the ClickOnce application cache on the client machine, in the same folder as the XBAP.</span></span>

- <span data-ttu-id="cb178-200">用于发现和加载外接程序的 XBAP 代码必须使用 XBAP 的 ClickOnce 应用程序缓存作为管道和外接程序位置。</span><span class="sxs-lookup"><span data-stu-id="cb178-200">The XBAP code to discover and load add-ins must use the ClickOnce application cache for the XBAP as the pipeline and add-in location.</span></span>

- <span data-ttu-id="cb178-201">如果外接程序引用位于源站点的松散文件，XBAP 必须将外接程序加载到特殊安全上下文中;当由 Xbap 承载时，外接程序只能引用位于主机应用程序源站点的松散文件。</span><span class="sxs-lookup"><span data-stu-id="cb178-201">The XBAP must load the add-in into a special security context if the add-in references loose files that are located at the site of origin; when hosted by XBAPs, add-ins can only reference loose files that are located at the host application's site of origin.</span></span>

<span data-ttu-id="cb178-202">下面几个小节将详细介绍这些任务。</span><span class="sxs-lookup"><span data-stu-id="cb178-202">These tasks are described in detail in the following subsections.</span></span>

### <a name="configuring-the-pipeline-and-add-in-for-clickonce-deployment"></a><span data-ttu-id="cb178-203">配置用于 ClickOnce 部署的管道和外接程序</span><span class="sxs-lookup"><span data-stu-id="cb178-203">Configuring the Pipeline and Add-In for ClickOnce Deployment</span></span>

<span data-ttu-id="cb178-204">Xbap 将下载到并从 ClickOnce 部署缓存中的一个安全文件夹运行。</span><span class="sxs-lookup"><span data-stu-id="cb178-204">XBAPs are downloaded to and run from a safe folder in the ClickOnce deployment cache.</span></span> <span data-ttu-id="cb178-205">为了使 XBAP 承载外接程序，还必须将管道和外接程序程序集下载到 safe 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cb178-205">In order for an XBAP to host an add-in, the pipeline and add-in assembly must also be downloaded to the safe folder.</span></span> <span data-ttu-id="cb178-206">为此，需要将应用程序清单配置为包含要下载的管道和外接程序程序集。</span><span class="sxs-lookup"><span data-stu-id="cb178-206">To achieve this, you need to configure the application manifest to include both the pipeline and add-in assembly for download.</span></span> <span data-ttu-id="cb178-207">尽管管道和外接程序程序集需要位于主机 XBAP 项目的根文件夹中，但对于 Visual Studio 检测管道程序集，但这在 Visual Studio 中最容易实现。</span><span class="sxs-lookup"><span data-stu-id="cb178-207">This is most easily done in Visual Studio, although the pipeline and add-in assembly needs to be in the host XBAP project's root folder in order for Visual Studio to detect the pipeline assemblies.</span></span>

<span data-ttu-id="cb178-208">因此，第一步是通过设置每个管道程序集和外接程序程序集项目的生成输出，将管道和外接程序程序集生成到 XBAP 项目的根。</span><span class="sxs-lookup"><span data-stu-id="cb178-208">Consequently, the first step is to build the pipeline and add-in assembly to the XBAP project's root by setting the build output of each pipeline assembly and add-in assembly projects.</span></span> <span data-ttu-id="cb178-209">下表显示了管道程序集项目和外接程序程序集项目的生成输出路径，该程序集项目位于与宿主 XBAP 项目相同的解决方案和根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cb178-209">The following table shows the build output paths for pipeline assembly projects and add-in assembly project that are in the same solution and root folder as the host XBAP project.</span></span>

<span data-ttu-id="cb178-210">表 1：XBAP 承载的管道程序集的生成输出路径</span><span class="sxs-lookup"><span data-stu-id="cb178-210">Table 1: Build Output Paths for the Pipeline Assemblies That Are Hosted by an XBAP</span></span>

|<span data-ttu-id="cb178-211">管道程序集项目</span><span class="sxs-lookup"><span data-stu-id="cb178-211">Pipeline assembly project</span></span>|<span data-ttu-id="cb178-212">生成输出路径</span><span class="sxs-lookup"><span data-stu-id="cb178-212">Build output path</span></span>|
|-------------------------------|-----------------------|
|<span data-ttu-id="cb178-213">合约</span><span class="sxs-lookup"><span data-stu-id="cb178-213">Contract</span></span>|`..\HostXBAP\Contracts\`|
|<span data-ttu-id="cb178-214">加载项视图</span><span class="sxs-lookup"><span data-stu-id="cb178-214">Add-In View</span></span>|`..\HostXBAP\AddInViews\`|
|<span data-ttu-id="cb178-215">加载项方适配器</span><span class="sxs-lookup"><span data-stu-id="cb178-215">Add-In-Side Adapter</span></span>|`..\HostXBAP\AddInSideAdapters\`|
|<span data-ttu-id="cb178-216">宿主端适配器</span><span class="sxs-lookup"><span data-stu-id="cb178-216">Host-Side Adapter</span></span>|`..\HostXBAP\HostSideAdapters\`|
|<span data-ttu-id="cb178-217">外接程序</span><span class="sxs-lookup"><span data-stu-id="cb178-217">Add-In</span></span>|`..\HostXBAP\AddIns\WPFAddIn1`|

<span data-ttu-id="cb178-218">下一步是通过执行以下操作，将管道程序集和外接程序程序集指定为 Visual Studio 中的 Xbap 内容文件：</span><span class="sxs-lookup"><span data-stu-id="cb178-218">The next step is to specify the pipeline assemblies and add-in assembly as the XBAPs content files in Visual Studio by doing the following:</span></span>

1. <span data-ttu-id="cb178-219">通过在“解决方案资源管理器”中右键单击每个管道文件夹，然后选择“包括在项目中”，将管道和外接程序程序集包括在项目中。</span><span class="sxs-lookup"><span data-stu-id="cb178-219">Including the pipeline and add-in assembly in the project by right-clicking each pipeline folder in Solution Explorer and choosing **Include In Project**.</span></span>

2. <span data-ttu-id="cb178-220">在“属性”窗口中，将每个管道程序集和外接程序程序集的“生成操作”都设置为“内容”。</span><span class="sxs-lookup"><span data-stu-id="cb178-220">Setting the **Build Action** of each pipeline assembly and add-in assembly to **Content** from the **Properties** window.</span></span>

<span data-ttu-id="cb178-221">最后一步是配置应用程序清单，以包含要下载的管道程序集文件和外接程序程序集文件。</span><span class="sxs-lookup"><span data-stu-id="cb178-221">The final step is to configure the application manifest to include the pipeline assembly files and add-in assembly file for download.</span></span> <span data-ttu-id="cb178-222">文件应位于 XBAP 应用程序所占用的 ClickOnce 缓存中文件夹根目录的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cb178-222">The files should be located in folders at the root of the folder in the ClickOnce cache that the XBAP application occupies.</span></span> <span data-ttu-id="cb178-223">通过执行以下操作，可以在 Visual Studio 中实现该配置：</span><span class="sxs-lookup"><span data-stu-id="cb178-223">The configuration can be achieved in Visual Studio by doing the following:</span></span>

1. <span data-ttu-id="cb178-224">右键单击 XBAP 项目，单击 " **属性**"，单击 " **发布**"，然后单击 " **应用程序文件** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="cb178-224">Right-click the XBAP project, click **Properties**, click **Publish**, and then click the **Application Files** button.</span></span>

2. <span data-ttu-id="cb178-225">在“应用程序文件”对话框中，将每个管道和外接程序 DLL 的“发布状态”都设置为“包括(自动)”，并将每个管道和外接程序 DLL 的“下载组”都设置为“(必需)”。</span><span class="sxs-lookup"><span data-stu-id="cb178-225">In the **Application Files** dialog, set the **Publish Status** of each pipeline and add-in DLL to **Include (Auto)**, and set the **Download Group** for each pipeline and add-in DLL to **(Required)**.</span></span>

### <a name="using-the-pipeline-and-add-in-from-the-application-base"></a><span data-ttu-id="cb178-226">从应用程序基使用管道和外接程序</span><span class="sxs-lookup"><span data-stu-id="cb178-226">Using the Pipeline and Add-In from the Application Base</span></span>

<span data-ttu-id="cb178-227">为 ClickOnce 部署配置管道和外接程序时，会将它们下载到与 XBAP 相同的 ClickOnce 缓存文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cb178-227">When the pipeline and add-in are configured for ClickOnce deployment, they are downloaded to the same ClickOnce cache folder as the XBAP.</span></span> <span data-ttu-id="cb178-228">若要从 XBAP 使用管道和外接程序，XBAP 代码必须从应用程序基获取它们。</span><span class="sxs-lookup"><span data-stu-id="cb178-228">To use the pipeline and add-in from the XBAP, the XBAP code must get them from the application base.</span></span> <span data-ttu-id="cb178-229">使用管道和外接程序的 .NET Framework 外接程序模型的各种类型和成员为此方案提供特殊支持。</span><span class="sxs-lookup"><span data-stu-id="cb178-229">The various types and members of the .NET Framework add-in model for using pipelines and add-ins provide special support for this scenario.</span></span> <span data-ttu-id="cb178-230">首先，路径由 <xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase> 枚举值标识。</span><span class="sxs-lookup"><span data-stu-id="cb178-230">Firstly, the path is identified by the <xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase> enumeration value.</span></span> <span data-ttu-id="cb178-231">将此值用于使用管道的相关外接程序成员的重载，这些成员包括：</span><span class="sxs-lookup"><span data-stu-id="cb178-231">You use this value with overloads of the pertinent add-in members for using pipelines that include the following:</span></span>

- <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

- <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>

### <a name="accessing-the-hosts-site-of-origin"></a><span data-ttu-id="cb178-232">访问宿主的源站点</span><span class="sxs-lookup"><span data-stu-id="cb178-232">Accessing the Host's Site of Origin</span></span>

<span data-ttu-id="cb178-233">为确保外接程序可以引用源站点的文件，必须使用等效于主机应用程序的安全隔离来加载外接程序。</span><span class="sxs-lookup"><span data-stu-id="cb178-233">To ensure that an add-in can reference files from the site of origin, the add-in must be loaded with security isolation that is equivalent to the host application.</span></span> <span data-ttu-id="cb178-234">此安全级别由 <xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType> 枚举值标识，并在激活外接程序 <xref:System.AddIn.Hosting.AddInToken.Activate%2A> 时传递给方法。</span><span class="sxs-lookup"><span data-stu-id="cb178-234">This security level is identified by the <xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType> enumeration value, and passed to the <xref:System.AddIn.Hosting.AddInToken.Activate%2A> method when an add-in is activated.</span></span>

<a name="WPFAddInModelArchitecture"></a>

## <a name="wpf-add-in-architecture"></a><span data-ttu-id="cb178-235">WPF 外接程序体系结构</span><span class="sxs-lookup"><span data-stu-id="cb178-235">WPF Add-In Architecture</span></span>

<span data-ttu-id="cb178-236">如我们所见，在最高级别，WPF 允许 .NET Framework 外接程序 <xref:System.Windows.FrameworkElement> 使用、和从) 实现直接或间接派生的用户界面 <xref:System.AddIn.Contract.INativeHandleContract> (<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 。</span><span class="sxs-lookup"><span data-stu-id="cb178-236">At the highest level, as we've seen, WPF enables .NET Framework add-ins to implement user interfaces (that derive directly or indirectly from <xref:System.Windows.FrameworkElement>) using <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> and <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.</span></span> <span data-ttu-id="cb178-237">结果是，主机应用程序返回了一个 <xref:System.Windows.FrameworkElement> ，它从主机应用程序的 UI 中显示。</span><span class="sxs-lookup"><span data-stu-id="cb178-237">The result is that the host application is returned a <xref:System.Windows.FrameworkElement> that is displayed from UI in the host application.</span></span>

<span data-ttu-id="cb178-238">对于简单的 UI 外接程序方案，这是开发人员所需的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cb178-238">For simple UI add-in scenarios, this is as much detail as a developer needs.</span></span> <span data-ttu-id="cb178-239">对于更复杂的方案（尤其是那些尝试使用其他 WPF 服务（如布局、资源和数据绑定）的情况，需要 WPF 如何扩展带有 UI 支持的 .NET Framework 外接程序模型，以了解其优点和局限性。</span><span class="sxs-lookup"><span data-stu-id="cb178-239">For more complex scenarios, particularly those that try to utilize additional WPF services such as layout, resources, and data binding, more detailed knowledge of how WPF extends the .NET Framework add-in model with UI support is required to understand its benefits and limitations.</span></span>

<span data-ttu-id="cb178-240">从根本上讲，WPF 不会将 UI 从外接程序传递到主机应用程序;而是使用 WPF 互操作性为 UI 传递 Win32 窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="cb178-240">Fundamentally, WPF doesn't pass a UI from an add-in to a host application; instead, WPF passes the Win32 window handle for the UI by using WPF interoperability.</span></span> <span data-ttu-id="cb178-241">因此，当外接程序中的 UI 被传递到主机应用程序时，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="cb178-241">As such, when a UI from an add-in is passed to a host application, the following occurs:</span></span>

- <span data-ttu-id="cb178-242">在外接程序端，WPF 会为将由主机应用程序显示的 UI 获取一个窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="cb178-242">On the add-in side, WPF acquires a window handle for the UI that will be displayed by the host application.</span></span> <span data-ttu-id="cb178-243">窗口句柄由派生自并实现的内部 WPF 类封装 <xref:System.Windows.Interop.HwndSource> <xref:System.AddIn.Contract.INativeHandleContract> 。</span><span class="sxs-lookup"><span data-stu-id="cb178-243">The window handle is encapsulated by an internal WPF class that derives from <xref:System.Windows.Interop.HwndSource> and implements <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="cb178-244">此类的实例由返回 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> ，并从外接程序的应用程序域封送到主机应用程序的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="cb178-244">An instance of this class is returned by <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> and is marshaled from the add-in's application domain to the host application's application domain.</span></span>

- <span data-ttu-id="cb178-245">在宿主应用程序端，WPF 将 <xref:System.Windows.Interop.HwndSource> 作为从派生并使用的内部 WPF 类重新打包 <xref:System.Windows.Interop.HwndHost> <xref:System.AddIn.Contract.INativeHandleContract> 。</span><span class="sxs-lookup"><span data-stu-id="cb178-245">On the host application side, WPF repackages the <xref:System.Windows.Interop.HwndSource> as an internal WPF class that derives from <xref:System.Windows.Interop.HwndHost> and consumes <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="cb178-246">此类的实例由 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 向宿主应用程序返回。</span><span class="sxs-lookup"><span data-stu-id="cb178-246">An instance of this class is returned by <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> to the host application.</span></span>

<span data-ttu-id="cb178-247"><xref:System.Windows.Interop.HwndHost> 存在，用于显示 WPF 用户界面中由窗口句柄标识的用户界面。</span><span class="sxs-lookup"><span data-stu-id="cb178-247"><xref:System.Windows.Interop.HwndHost> exists to display user interfaces, identified by window handles, from WPF user interfaces.</span></span> <span data-ttu-id="cb178-248">有关详细信息，请参阅 [WPF 和 Win32 互操作](../advanced/wpf-and-win32-interoperation.md)。</span><span class="sxs-lookup"><span data-stu-id="cb178-248">For more information, see [WPF and Win32 Interoperation](../advanced/wpf-and-win32-interoperation.md).</span></span>

<span data-ttu-id="cb178-249">摘要、、 <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 和存在， <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 以允许将 WPF UI 的窗口句柄从外接程序传递到主机应用程序，在该应用程序中，它由进行封装 <xref:System.Windows.Interop.HwndHost> 并显示宿主应用程序的 UI。</span><span class="sxs-lookup"><span data-stu-id="cb178-249">In summary, <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, and <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> exist to allow the window handle for a WPF UI to be passed from an add-in to a host application, where it is encapsulated by a <xref:System.Windows.Interop.HwndHost> and displayed the host application's UI.</span></span>

> [!NOTE]
> <span data-ttu-id="cb178-250">由于宿主应用程序获取 <xref:System.Windows.Interop.HwndHost> ，因此主机应用程序无法将返回的对象转换 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> 为它作为该外接程序实现的类型 (例如， <xref:System.Windows.Controls.UserControl>) 。</span><span class="sxs-lookup"><span data-stu-id="cb178-250">Because the host application gets an <xref:System.Windows.Interop.HwndHost>, the host application cannot convert the object that is returned by <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> to the type it is implemented as by the add-in (for example, a <xref:System.Windows.Controls.UserControl>).</span></span>

<span data-ttu-id="cb178-251">本质上， <xref:System.Windows.Interop.HwndHost> 具有某些限制，它们会影响主机应用程序使用它们的方式。</span><span class="sxs-lookup"><span data-stu-id="cb178-251">By its nature, <xref:System.Windows.Interop.HwndHost> has certain limitations that affect how host applications can use them.</span></span> <span data-ttu-id="cb178-252">不过，WPF 扩展 <xref:System.Windows.Interop.HwndHost> 了多个外接程序方案的功能。</span><span class="sxs-lookup"><span data-stu-id="cb178-252">However, WPF extends <xref:System.Windows.Interop.HwndHost> with several capabilities for add-in scenarios.</span></span> <span data-ttu-id="cb178-253">下面介绍这些优点和限制。</span><span class="sxs-lookup"><span data-stu-id="cb178-253">These benefits and limitations are described below.</span></span>

<a name="WPFAddInModelBenefits"></a>

## <a name="wpf-add-in-benefits"></a><span data-ttu-id="cb178-254">WPF 外接程序的优点</span><span class="sxs-lookup"><span data-stu-id="cb178-254">WPF Add-In Benefits</span></span>

<span data-ttu-id="cb178-255">因为 WPF 外接程序用户界面是使用派生自的内部类从主机应用程序显示的 <xref:System.Windows.Interop.HwndHost> ，所以这些用户界面受 <xref:System.Windows.Interop.HwndHost> 与 WPF UI 服务（如布局、呈现、数据绑定、样式、模板和资源）有关的功能的限制。</span><span class="sxs-lookup"><span data-stu-id="cb178-255">Because WPF add-in user interfaces are displayed from host applications using an internal class that derives from <xref:System.Windows.Interop.HwndHost>, those user interfaces are constrained by the capabilities of <xref:System.Windows.Interop.HwndHost> with respect to WPF UI services such as layout, rendering, data binding, styles, templates, and resources.</span></span> <span data-ttu-id="cb178-256">不过，WPF 通过其他功能增强了其内部 <xref:System.Windows.Interop.HwndHost> 子类，其中包括：</span><span class="sxs-lookup"><span data-stu-id="cb178-256">However, WPF augments its internal <xref:System.Windows.Interop.HwndHost> subclass with additional capabilities that include the following:</span></span>

- <span data-ttu-id="cb178-257">在宿主应用程序的 UI 和外接程序的 UI 之间进行 tab 键切换。</span><span class="sxs-lookup"><span data-stu-id="cb178-257">Tabbing between a host application's UI and an add-in's UI.</span></span> <span data-ttu-id="cb178-258">请注意，"外接程序是 UI" 编程模型要求外接程序端适配器进行重写 <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> ，以启用 tab 键切换，无论外接程序是完全信任的还是部分信任的。</span><span class="sxs-lookup"><span data-stu-id="cb178-258">Note that the "add-in is a UI" programming model requires the add-in-side adapter to override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> to enable tabbing, whether the add-in is fully trusted or partially trusted.</span></span>

- <span data-ttu-id="cb178-259">满足从主机应用程序用户界面中显示的外接程序用户界面的辅助功能要求。</span><span class="sxs-lookup"><span data-stu-id="cb178-259">Honoring accessibility requirements for add-in user interfaces that are displayed from host application user interfaces.</span></span>

- <span data-ttu-id="cb178-260">允许 WPF 应用程序在多个应用程序域方案中安全运行。</span><span class="sxs-lookup"><span data-stu-id="cb178-260">Enabling WPF applications to run safely in multiple application domain scenarios.</span></span>

- <span data-ttu-id="cb178-261">当外接程序使用安全隔离运行时，阻止对外接程序 UI 窗口句柄进行非法访问 (即部分信任的安全沙箱) 。</span><span class="sxs-lookup"><span data-stu-id="cb178-261">Preventing illegal access to add-in UI window handles when add-ins run with security isolation (that is, a partial-trust security sandbox).</span></span> <span data-ttu-id="cb178-262">调用 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 可确保安全：</span><span class="sxs-lookup"><span data-stu-id="cb178-262">Calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> ensures this security:</span></span>

  - <span data-ttu-id="cb178-263">对于 "外接程序返回 UI" 编程模型，传递跨隔离边界的外接程序 UI 的窗口句柄的唯一方法是调用 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 。</span><span class="sxs-lookup"><span data-stu-id="cb178-263">For the "add-in returns a UI" programming model, the only way to pass the window handle for an add-in UI across the isolation boundary is to call <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.</span></span>

  - <span data-ttu-id="cb178-264">对于 "外接程序是 UI" 编程模型， <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 在外接程序端适配器上重写并调用 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> (如前面的示例所示) 是必需的，正如从宿主端适配器调用外接程序端适配器的 `QueryContract` 实现一样。</span><span class="sxs-lookup"><span data-stu-id="cb178-264">For the "add-in is a UI" programming model, overriding <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> on the add-in-side adapter and calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> (as shown in the preceding examples) is required, as is calling the add-in-side adapter's `QueryContract` implementation from the host-side adapter.</span></span>

- <span data-ttu-id="cb178-265">提供多个应用程序域执行保护。</span><span class="sxs-lookup"><span data-stu-id="cb178-265">Providing multiple application domain execution protection.</span></span> <span data-ttu-id="cb178-266">由于应用程序域的限制，因此即使存在隔离边界，外接程序应用程序域中引发的未经处理的异常也会导致整个应用程序出现故障。</span><span class="sxs-lookup"><span data-stu-id="cb178-266">Due to limitations with application domains, unhandled exceptions that are thrown in add-in application domains cause the entire application to crash, even though the isolation boundary exists.</span></span> <span data-ttu-id="cb178-267">不过，WPF 和 .NET Framework 外接程序模型提供一种简单的方法来解决此问题并提高应用程序的稳定性。</span><span class="sxs-lookup"><span data-stu-id="cb178-267">However, WPF and the .NET Framework add-in model provide a simple way to work around this problem and improve application stability.</span></span> <span data-ttu-id="cb178-268">如果主机应用程序是 WPF 应用程序，则显示 UI 的 WPF 外接程序将 <xref:System.Windows.Threading.Dispatcher> 为运行应用程序域的线程创建。</span><span class="sxs-lookup"><span data-stu-id="cb178-268">A WPF add-in that displays a UI creates a <xref:System.Windows.Threading.Dispatcher> for the thread that the application domain runs on, if the host application is a WPF application.</span></span> <span data-ttu-id="cb178-269">通过处理 WPF 外接程序的事件，可以检测应用程序域中发生的所有未经处理的异常 <xref:System.Windows.Threading.Dispatcher.UnhandledException> <xref:System.Windows.Threading.Dispatcher> 。</span><span class="sxs-lookup"><span data-stu-id="cb178-269">You can detect all unhandled exceptions that occur in the application domain by handling the <xref:System.Windows.Threading.Dispatcher.UnhandledException> event of the WPF add-in's <xref:System.Windows.Threading.Dispatcher>.</span></span> <span data-ttu-id="cb178-270">可以 <xref:System.Windows.Threading.Dispatcher> 从 <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A> 属性获取。</span><span class="sxs-lookup"><span data-stu-id="cb178-270">You can get the <xref:System.Windows.Threading.Dispatcher> from the <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A> property.</span></span>

<a name="WPFAddInModelLimitations"></a>

## <a name="wpf-add-in-limitations"></a><span data-ttu-id="cb178-271">WPF 外接程序限制</span><span class="sxs-lookup"><span data-stu-id="cb178-271">WPF Add-In Limitations</span></span>

<span data-ttu-id="cb178-272">除了 WPF 添加到 <xref:System.Windows.Interop.HwndSource> 、和窗口句柄提供的默认行为以外 <xref:System.Windows.Interop.HwndHost> ，还存在从主机应用程序显示的外接程序用户界面的限制：</span><span class="sxs-lookup"><span data-stu-id="cb178-272">Beyond the benefits that WPF adds to the default behaviors supplied by <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost>, and window handles, there are also limitations for add-in user interfaces that are displayed from host applications:</span></span>

- <span data-ttu-id="cb178-273">宿主应用程序显示的外接程序用户界面不遵守主机应用程序的剪辑行为。</span><span class="sxs-lookup"><span data-stu-id="cb178-273">Add-in user interfaces displayed from a host application do not respect the host application's clipping behavior.</span></span>

- <span data-ttu-id="cb178-274">互操作性方案中的“空域”概念也适用于外接程序（请参阅[技术区概述](../advanced/technology-regions-overview.md)）。</span><span class="sxs-lookup"><span data-stu-id="cb178-274">The concept of *airspace* in interoperability scenarios also applies to add-ins (see [Technology Regions Overview](../advanced/technology-regions-overview.md)).</span></span>

- <span data-ttu-id="cb178-275">宿主应用程序的 UI 服务（如资源继承、数据绑定和命令）不会自动提供给外接程序用户界面。</span><span class="sxs-lookup"><span data-stu-id="cb178-275">A host application's UI services, such as resource inheritance, data binding, and commanding, are not automatically available to add-in user interfaces.</span></span> <span data-ttu-id="cb178-276">若要向外接程序提供这些服务，需要更新管道。</span><span class="sxs-lookup"><span data-stu-id="cb178-276">To provide these services to the add-in, you need to update the pipeline.</span></span>

- <span data-ttu-id="cb178-277">外接程序 UI 不能旋转、缩放、倾斜或以其他方式受转换影响 (请参阅 [转换概述](../graphics-multimedia/transforms-overview.md)) 。</span><span class="sxs-lookup"><span data-stu-id="cb178-277">An add-in UI cannot be rotated, scaled, skewed, or otherwise affected by a transformation (see [Transforms Overview](../graphics-multimedia/transforms-overview.md)).</span></span>

- <span data-ttu-id="cb178-278">由命名空间的绘图操作呈现的外接程序用户界面内的内容 <xref:System.Drawing> 可以包含 alpha 混合。</span><span class="sxs-lookup"><span data-stu-id="cb178-278">Content inside add-in user interfaces that is rendered by drawing operations from the <xref:System.Drawing> namespace can include alpha blending.</span></span> <span data-ttu-id="cb178-279">但是，加载项 UI 和包含它的主机应用程序 UI 必须是100% 不透明;换言之， `Opacity` 两者上的属性必须设置为1。</span><span class="sxs-lookup"><span data-stu-id="cb178-279">However, both an add-in UI and the host application UI that contains it must be 100% opaque; in other words, the `Opacity` property on both must be set to 1.</span></span>

- <span data-ttu-id="cb178-280">如果 <xref:System.Windows.Window.AllowsTransparency%2A> 宿主应用程序中包含外接程序 UI 的窗口的属性设置为，则外接程序将不 `true` 可见。</span><span class="sxs-lookup"><span data-stu-id="cb178-280">If the <xref:System.Windows.Window.AllowsTransparency%2A> property of a window in the host application that contains an add-in UI is set to `true`, the add-in is invisible.</span></span> <span data-ttu-id="cb178-281">即使外接程序 UI 为100% 不透明 (也是如此，属性的值为 `Opacity` 1) 。</span><span class="sxs-lookup"><span data-stu-id="cb178-281">This is true even if the add-in UI is 100% opaque (that is, the `Opacity` property has a value of 1).</span></span>

- <span data-ttu-id="cb178-282">外接程序 UI 必须出现在同一顶级窗口中的其他 WPF 元素之上。</span><span class="sxs-lookup"><span data-stu-id="cb178-282">An add-in UI must appear on top of other WPF elements in the same top-level window.</span></span>

- <span data-ttu-id="cb178-283">外接程序的 UI 不能使用呈现 <xref:System.Windows.Media.VisualBrush> 。</span><span class="sxs-lookup"><span data-stu-id="cb178-283">No portion of an add-in's UI can be rendered using a <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="cb178-284">相反，外接程序可能会拍摄生成的 UI 的快照，以创建一个可以使用协定所定义的方法传递到主机应用程序的位图。</span><span class="sxs-lookup"><span data-stu-id="cb178-284">Instead, the add-in may take a snapshot of the generated UI to create a bitmap that can be passed to the host application using methods defined by the contract.</span></span>

- <span data-ttu-id="cb178-285"><xref:System.Windows.Controls.MediaElement>在外接程序 UI 中，无法从中播放媒体文件。</span><span class="sxs-lookup"><span data-stu-id="cb178-285">Media files cannot be played from a <xref:System.Windows.Controls.MediaElement> in an add-in UI.</span></span>

- <span data-ttu-id="cb178-286">为外接程序 UI 生成的鼠标事件既不是由宿主应用程序接收也不会引发， `IsMouseOver` 主机应用程序 ui 的属性的值为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="cb178-286">Mouse events generated for the add-in UI are neither received nor raised by the host application, and the `IsMouseOver` property for host application UI has a value of `false`.</span></span>

- <span data-ttu-id="cb178-287">当焦点在外接程序 UI 中的控件之间移动时， `GotFocus` 和 `LostFocus` 事件既不会接收，也不会由主机应用程序引发。</span><span class="sxs-lookup"><span data-stu-id="cb178-287">When focus shifts between controls in an add-in UI, the `GotFocus` and `LostFocus` events are neither received nor raised by the host application.</span></span>

- <span data-ttu-id="cb178-288">在打印时，包含外接程序 UI 的主机应用程序部分显示为白色。</span><span class="sxs-lookup"><span data-stu-id="cb178-288">The portion of a host application that contains an add-in UI appears white when printed.</span></span>

- <span data-ttu-id="cb178-289"><xref:System.Windows.Threading.Dispatcher>如果主机应用程序继续执行，则在卸载 owner 外接程序之前，必须手动关闭所有调度程序 (查看由外接程序 UI 创建) 。</span><span class="sxs-lookup"><span data-stu-id="cb178-289">All dispatchers (see <xref:System.Windows.Threading.Dispatcher>) created by the add-in UI must be shut down manually before the owner add-in is unloaded if the host application continues execution.</span></span> <span data-ttu-id="cb178-290">协定可以实现一些方法，这些方法允许主机应用程序在外接程序卸载之前通知外接程序，从而允许外接程序 UI 关闭其调度程序。</span><span class="sxs-lookup"><span data-stu-id="cb178-290">The contract can implement methods that allow the host application to signal the add-in before the add-in is unloaded, thereby allowing the add-in UI to shut down its dispatchers.</span></span>

- <span data-ttu-id="cb178-291">如果外接程序 UI 是 <xref:System.Windows.Controls.InkCanvas> 或包含 <xref:System.Windows.Controls.InkCanvas> ，则不能卸载外接程序。</span><span class="sxs-lookup"><span data-stu-id="cb178-291">If an add-in UI is an <xref:System.Windows.Controls.InkCanvas> or contains an <xref:System.Windows.Controls.InkCanvas>, you cannot unload the add-in.</span></span>

<a name="PerformanceOptimization"></a>

## <a name="performance-optimization"></a><span data-ttu-id="cb178-292">性能优化</span><span class="sxs-lookup"><span data-stu-id="cb178-292">Performance Optimization</span></span>

<span data-ttu-id="cb178-293">默认情况下，当使用多个应用程序域时，每个应用程序所需的各种 .NET Framework 程序集都将加载到该应用程序的域中。</span><span class="sxs-lookup"><span data-stu-id="cb178-293">By default, when multiple application domains are used, the various .NET Framework assemblies required by each application are all loaded into that application's domain.</span></span> <span data-ttu-id="cb178-294">因此，创建新应用程序域和在应用程序域中启动应用程序所需的时间可能会影响性能。</span><span class="sxs-lookup"><span data-stu-id="cb178-294">As a result, the time required for creating new application domains and starting applications in them might affect performance.</span></span> <span data-ttu-id="cb178-295">不过，通过指示应用程序在已加载的应用程序域之间共享程序集，.NET Framework 提供了一种减少开始时间的方法。</span><span class="sxs-lookup"><span data-stu-id="cb178-295">However, the .NET Framework provides a way for you to reduce start times by instructing applications to share assemblies across application domains if they are already loaded.</span></span> <span data-ttu-id="cb178-296">为此，需要使用 <xref:System.LoaderOptimizationAttribute> 属性，该属性必须应用于入口点方法 (`Main`) 。</span><span class="sxs-lookup"><span data-stu-id="cb178-296">You do this by using the <xref:System.LoaderOptimizationAttribute> attribute, which must be applied to the entry point method (`Main`).</span></span> <span data-ttu-id="cb178-297">这种情况下，只能使用代码来实现应用程序定义（请参阅[应用程序管理概述](application-management-overview.md)）。</span><span class="sxs-lookup"><span data-stu-id="cb178-297">In this case, you must use only code to implement your application definition (see [Application Management Overview](application-management-overview.md)).</span></span>

## <a name="see-also"></a><span data-ttu-id="cb178-298">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb178-298">See also</span></span>

- <xref:System.LoaderOptimizationAttribute>
- <span data-ttu-id="cb178-299">[外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="cb178-299">[Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="cb178-300">应用程序域</span><span class="sxs-lookup"><span data-stu-id="cb178-300">Application Domains</span></span>](/dotnet/framework/app-domains/application-domains)
- <span data-ttu-id="cb178-301">[.NET Framework 远程处理概述](/previous-versions/dotnet/netframework-4.0/kwdt6w2k(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cb178-301">[.NET Framework Remoting Overview](/previous-versions/dotnet/netframework-4.0/kwdt6w2k(v=vs.100))</span></span>
- <span data-ttu-id="cb178-302">[使对象可远程处理](/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cb178-302">[Making Objects Remotable](/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100))</span></span>
- [<span data-ttu-id="cb178-303">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="cb178-303">How-to Topics</span></span>](how-to-topics.md)
