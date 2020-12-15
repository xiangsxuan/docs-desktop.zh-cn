---
title: 应用程序开发
description: 了解如何使用 Windows Presentation Foundation (WPF) 框架生成各种应用程序。
ms.date: 01/26/2018
helpviewer_keywords:
- WPF [WPF], about application development
- application development [WPF], about
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
ms.openlocfilehash: af60a75736dd85c8dd94e7ee051e801e8aa66684
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96992751"
---
# <a name="application-development"></a><span data-ttu-id="7a48a-103">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="7a48a-103">Application Development</span></span>
<a name="introduction"></a> <span data-ttu-id="7a48a-104">Windows Presentation Foundation (WPF) 是一个演示框架，可用于开发以下类型的应用程序：</span><span class="sxs-lookup"><span data-stu-id="7a48a-104">Windows Presentation Foundation (WPF) is a presentation framework that can be used to develop the following types of applications:</span></span>  
  
- <span data-ttu-id="7a48a-105">独立应用程序（传统风格的 Windows 应用程序，这些应用程序作为要安装到客户端计算机并从客户端计算机运行的可执行程序集来生成）。</span><span class="sxs-lookup"><span data-stu-id="7a48a-105">Standalone Applications (traditional style Windows applications built as executable assemblies that are installed to and run from the client computer).</span></span>  
  
- <span data-ttu-id="7a48a-106">XAML 浏览器应用程序 (XBAP)（由导航页组成的应用程序，这些应用程序作为可执行程序集生成并由 Microsoft Internet Explorer 或 Mozilla Firefox 等 Web 浏览器托管）。</span><span class="sxs-lookup"><span data-stu-id="7a48a-106">XAML browser applications (XBAPs) (applications composed of navigation pages that are built as executable assemblies and hosted by Web browsers such as Microsoft Internet Explorer or Mozilla Firefox).</span></span>  
  
- <span data-ttu-id="7a48a-107">自定义控件库（包含可重用控件的非可执行程序集）。</span><span class="sxs-lookup"><span data-stu-id="7a48a-107">Custom Control Libraries (non-executable assemblies containing reusable controls).</span></span>  
  
- <span data-ttu-id="7a48a-108">类库（包含可重用类的非可执行程序集）。</span><span class="sxs-lookup"><span data-stu-id="7a48a-108">Class Libraries (non-executable assemblies that contain reusable classes).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a48a-109">强烈建议不要在 Windows 服务中使用 WPF 类型。</span><span class="sxs-lookup"><span data-stu-id="7a48a-109">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="7a48a-110">如果尝试在 Windows 服务中使用这些功能，这些功能可能无法按预期工作。</span><span class="sxs-lookup"><span data-stu-id="7a48a-110">If you attempt to use these features in a Windows service, they may not work as expected.</span></span>  
  
 <span data-ttu-id="7a48a-111">为了生成这样一组应用程序，WPF 要实现众多服务。</span><span class="sxs-lookup"><span data-stu-id="7a48a-111">To build this set of applications, WPF implements a host of services.</span></span> <span data-ttu-id="7a48a-112">本主题对这些服务以及在何处可以找到更多相关信息进行了概述。</span><span class="sxs-lookup"><span data-stu-id="7a48a-112">This topic provides an overview of these services and where to find more information.</span></span>  

<a name="Application_Management"></a>
## <a name="application-management"></a><span data-ttu-id="7a48a-113">应用程序管理</span><span class="sxs-lookup"><span data-stu-id="7a48a-113">Application Management</span></span>  
 <span data-ttu-id="7a48a-114">可执行的 WPF 应用程序通常需要一组核心功能，其中包括：</span><span class="sxs-lookup"><span data-stu-id="7a48a-114">Executable WPF applications commonly require a core set of functionality that includes the following:</span></span>  
  
- <span data-ttu-id="7a48a-115">创建和管理常见的应用程序基础结构（包括创建入口点方法和 Windows 消息循环，以接收系统和输入消息）。</span><span class="sxs-lookup"><span data-stu-id="7a48a-115">Creating and managing common application infrastructure (including creating an entry point method and a Windows message loop to receive system and input messages).</span></span>  
  
- <span data-ttu-id="7a48a-116">对应用程序的生存期进行跟踪并与之进行交互。</span><span class="sxs-lookup"><span data-stu-id="7a48a-116">Tracking and interacting with the lifetime of an application.</span></span>  
  
- <span data-ttu-id="7a48a-117">检索和处理命令行参数。</span><span class="sxs-lookup"><span data-stu-id="7a48a-117">Retrieving and processing command-line parameters.</span></span>  
  
- <span data-ttu-id="7a48a-118">共享应用程序范围的属性和 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 资源。</span><span class="sxs-lookup"><span data-stu-id="7a48a-118">Sharing application-scope properties and [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] resources.</span></span>  
  
- <span data-ttu-id="7a48a-119">检测和处理未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="7a48a-119">Detecting and processing unhandled exceptions.</span></span>  
  
- <span data-ttu-id="7a48a-120">返回退出代码。</span><span class="sxs-lookup"><span data-stu-id="7a48a-120">Returning exit codes.</span></span>  
  
- <span data-ttu-id="7a48a-121">管理独立应用程序中的窗口。</span><span class="sxs-lookup"><span data-stu-id="7a48a-121">Managing windows in standalone applications.</span></span>  
  
- <span data-ttu-id="7a48a-122">跟踪 XAML 浏览器应用程序 (XBAP) 以及使用导航窗口和框架的独立应用程序中的导航。</span><span class="sxs-lookup"><span data-stu-id="7a48a-122">Tracking navigation in XAML browser applications (XBAPs), and standalone applications with navigation windows and frames.</span></span>  
  
 <span data-ttu-id="7a48a-123">以上功能由通过 *应用程序定义* 添加到应用程序的 <xref:System.Windows.Application> 类来实现。</span><span class="sxs-lookup"><span data-stu-id="7a48a-123">These capabilities are implemented by the <xref:System.Windows.Application> class, which you add to your applications using an *application definition*.</span></span>  
  
 <span data-ttu-id="7a48a-124">有关详细信息，请参阅[应用程序管理概述](application-management-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7a48a-124">For more information, see [Application Management Overview](application-management-overview.md).</span></span>  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>
## <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="7a48a-125">WPF 应用程序资源、内容和数据文件</span><span class="sxs-lookup"><span data-stu-id="7a48a-125">WPF Application Resource, Content, and Data Files</span></span>  
 <span data-ttu-id="7a48a-126">通过为以下三类非可执行数据文件提供支持，WPF 扩展了 Microsoft .NET Framework 对于嵌入资源的核心支持：资源、内容和数据。</span><span class="sxs-lookup"><span data-stu-id="7a48a-126">WPF extends the core support in the Microsoft .NET Framework for embedded resources with support for three kinds of non-executable data files: resource, content, and data.</span></span> <span data-ttu-id="7a48a-127">有关详细信息，请参阅 [WPF 应用程序资源、内容和数据文件](wpf-application-resource-content-and-data-files.md)。</span><span class="sxs-lookup"><span data-stu-id="7a48a-127">For more information, see [WPF Application Resource, Content, and Data Files](wpf-application-resource-content-and-data-files.md).</span></span>  
  
 <span data-ttu-id="7a48a-128">在对于 WPF 非可执行数据文件的众多支持中，其中的一项重要支持就是能够通过唯一的 URI 来识别和加载这些文件。</span><span class="sxs-lookup"><span data-stu-id="7a48a-128">A key component of the support for WPF non-executable data files is the ability to identify and load them using a unique URI.</span></span> <span data-ttu-id="7a48a-129">有关详细信息，请参阅 [WPF 中的 Pack URI](pack-uris-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="7a48a-129">For more information, see [Pack URIs in WPF](pack-uris-in-wpf.md).</span></span>  
  
<a name="Windows_and_Dialog_Boxes"></a>
## <a name="windows-and-dialog-boxes"></a><span data-ttu-id="7a48a-130">窗口和对话框</span><span class="sxs-lookup"><span data-stu-id="7a48a-130">Windows and Dialog Boxes</span></span>  
 <span data-ttu-id="7a48a-131">用户通过窗口与 WPF 独立应用程序交互。</span><span class="sxs-lookup"><span data-stu-id="7a48a-131">Users interact with WPF standalone applications through windows.</span></span> <span data-ttu-id="7a48a-132">窗口旨在托管应用程序内容并提供通常允许用户与内容交互的应用程序功能。</span><span class="sxs-lookup"><span data-stu-id="7a48a-132">The purpose of a window is to host application content and expose application functionality that usually allows users to interact with the content.</span></span> <span data-ttu-id="7a48a-133">在 WPF 中，通过 <xref:System.Windows.Window> 类封装窗口，该类支持：</span><span class="sxs-lookup"><span data-stu-id="7a48a-133">In WPF, windows are encapsulated by the <xref:System.Windows.Window> class, which supports:</span></span>  
  
- <span data-ttu-id="7a48a-134">创建和显示窗口。</span><span class="sxs-lookup"><span data-stu-id="7a48a-134">Creating and showing windows.</span></span>  
  
- <span data-ttu-id="7a48a-135">建立所有者/所拥有窗口关系。</span><span class="sxs-lookup"><span data-stu-id="7a48a-135">Establishing owner/owned window relationships.</span></span>  
  
- <span data-ttu-id="7a48a-136">配置窗口外观（例如，大小、位置、图标、标题栏文本、边框）。</span><span class="sxs-lookup"><span data-stu-id="7a48a-136">Configuring window appearance (for example, size, location, icons, title bar text, border).</span></span>  
  
- <span data-ttu-id="7a48a-137">对窗口的生存期进行跟踪并与之进行交互。</span><span class="sxs-lookup"><span data-stu-id="7a48a-137">Tracking and interacting with the lifetime of a window.</span></span>  
  
 <span data-ttu-id="7a48a-138">有关详细信息，请参阅 [WPF 窗口概述](wpf-windows-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7a48a-138">For more information, see [WPF Windows Overview](wpf-windows-overview.md).</span></span>  
  
 <span data-ttu-id="7a48a-139"><xref:System.Windows.Window> 支持用于创建被称为对话框的特殊窗口类型的功能。</span><span class="sxs-lookup"><span data-stu-id="7a48a-139"><xref:System.Windows.Window> supports the ability to create a special type of window known as a dialog box.</span></span> <span data-ttu-id="7a48a-140">可以创建两种类型的对话框，即模式和无模式对话框。</span><span class="sxs-lookup"><span data-stu-id="7a48a-140">Both modal and modeless types of dialog boxes can be created.</span></span>  
  
 <span data-ttu-id="7a48a-141">为了方便起见，也为了享受可重用性所带来的益处，以及在应用程序间实现一致的用户体验，WPF 提供了三种常用的 Windows 对话框：<xref:Microsoft.Win32.OpenFileDialog>、<xref:Microsoft.Win32.SaveFileDialog> 和 <xref:System.Windows.Controls.PrintDialog>。</span><span class="sxs-lookup"><span data-stu-id="7a48a-141">For convenience, and the benefits of reusability and a consistent user experience across applications, WPF exposes three of the common Windows dialog boxes: <xref:Microsoft.Win32.OpenFileDialog>, <xref:Microsoft.Win32.SaveFileDialog>, and <xref:System.Windows.Controls.PrintDialog>.</span></span>  
  
 <span data-ttu-id="7a48a-142">消息框是一种特殊类型的对话框，用于向用户显示重要的文本信息并询问简单的“是/否/确定/取消”问题。</span><span class="sxs-lookup"><span data-stu-id="7a48a-142">A message box is a special type of dialog box for showing important textual information to users, and for asking simple Yes/No/OK/Cancel questions.</span></span> <span data-ttu-id="7a48a-143">使用 <xref:System.Windows.MessageBox> 类创建并显示消息框。</span><span class="sxs-lookup"><span data-stu-id="7a48a-143">You use the <xref:System.Windows.MessageBox> class to create and show message boxes.</span></span>  
  
 <span data-ttu-id="7a48a-144">有关详细信息，请参阅[对话框概述](dialog-boxes-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7a48a-144">For more information, see [Dialog Boxes Overview](dialog-boxes-overview.md).</span></span>  
  
<a name="Navigation"></a>
## <a name="navigation"></a><span data-ttu-id="7a48a-145">导航</span><span class="sxs-lookup"><span data-stu-id="7a48a-145">Navigation</span></span>  
 <span data-ttu-id="7a48a-146">WPF 支持使用页面 (<xref:System.Windows.Controls.Page>) 和超链接 (<xref:System.Windows.Documents.Hyperlink>) 进行Web 式导航。</span><span class="sxs-lookup"><span data-stu-id="7a48a-146">WPF supports Web-style navigation using pages (<xref:System.Windows.Controls.Page>) and hyperlinks (<xref:System.Windows.Documents.Hyperlink>).</span></span> <span data-ttu-id="7a48a-147">导航可以通过多种方式来实现，其中包括：</span><span class="sxs-lookup"><span data-stu-id="7a48a-147">Navigation can be implemented in a variety of ways that include the following:</span></span>  
  
- <span data-ttu-id="7a48a-148">在 Web 浏览器中承载的独立页面。</span><span class="sxs-lookup"><span data-stu-id="7a48a-148">Standalone pages that are hosted in a Web browser.</span></span>  
  
- <span data-ttu-id="7a48a-149">被编译到 XBAP 中并在 Web 浏览器中托管的页面。</span><span class="sxs-lookup"><span data-stu-id="7a48a-149">Pages compiled into an XBAP that is hosted in a Web browser.</span></span>  
  
- <span data-ttu-id="7a48a-150">被编译到独立应用程序中并由导航窗口 (<xref:System.Windows.Navigation.NavigationWindow>) 承载的页面。</span><span class="sxs-lookup"><span data-stu-id="7a48a-150">Pages compiled into a standalone application and hosted by a navigation window (<xref:System.Windows.Navigation.NavigationWindow>).</span></span>  
  
- <span data-ttu-id="7a48a-151">由框架 (<xref:System.Windows.Controls.Frame>) 托管的页面（可能在独立页面中托管），或是被编译到 XBAP 或独立应用程序中的页面。</span><span class="sxs-lookup"><span data-stu-id="7a48a-151">Pages that are hosted by a frame (<xref:System.Windows.Controls.Frame>), which may be hosted in a standalone page, or a page compiled into either an XBAP or a standalone application.</span></span>  
  
 <span data-ttu-id="7a48a-152">为了便于导航，WPF 实现了：</span><span class="sxs-lookup"><span data-stu-id="7a48a-152">To facilitate navigation, WPF implements the following:</span></span>  
  
- <span data-ttu-id="7a48a-153"><xref:System.Windows.Navigation.NavigationService>，供 <xref:System.Windows.Controls.Frame>、<xref:System.Windows.Navigation.NavigationWindow> 和 XBAP 用于处理导航请求以支持应用程序内导航的共享导航引擎。</span><span class="sxs-lookup"><span data-stu-id="7a48a-153"><xref:System.Windows.Navigation.NavigationService>, the shared navigation engine for processing navigation requests that is used by <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>, and XBAPs to support intra-application navigation.</span></span>  
  
- <span data-ttu-id="7a48a-154">用于启动导航的导航方法。</span><span class="sxs-lookup"><span data-stu-id="7a48a-154">Navigation methods to initiate navigation.</span></span>  
  
- <span data-ttu-id="7a48a-155">各种导航事件，用于对导航的生存期进行跟踪并与之进行交互。</span><span class="sxs-lookup"><span data-stu-id="7a48a-155">Navigation events to track and interact with navigation lifetime.</span></span>  
  
- <span data-ttu-id="7a48a-156">记住通过日志实现的后向和前向导航，还可以检查和操控这些导航。</span><span class="sxs-lookup"><span data-stu-id="7a48a-156">Remembering back and forward navigation using a journal, which can also be inspected and manipulated.</span></span>  
  
 <span data-ttu-id="7a48a-157">有关信息，请参阅[导航概述](navigation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7a48a-157">For information, see [Navigation Overview](navigation-overview.md).</span></span>  
  
 <span data-ttu-id="7a48a-158">WPF 还支持一种被称为结构化导航的特殊导航类型。</span><span class="sxs-lookup"><span data-stu-id="7a48a-158">WPF also supports a special type of navigation known as structured navigation.</span></span> <span data-ttu-id="7a48a-159">结构化导航可用于调用一个或多个页面，这些页面能以结构化的可预测方式返回与调用函数一致的数据。</span><span class="sxs-lookup"><span data-stu-id="7a48a-159">Structured navigation can be used to call one or more pages that return data in a structured and predictable way that is consistent with calling functions.</span></span> <span data-ttu-id="7a48a-160">此功能将取决于 <xref:System.Windows.Navigation.PageFunction%601> 类；有关该类的进一步描述，请参阅[结构化导航概述](structured-navigation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7a48a-160">This capability depends on the <xref:System.Windows.Navigation.PageFunction%601> class, which is described further in [Structured Navigation Overview](structured-navigation-overview.md).</span></span> <span data-ttu-id="7a48a-161"><xref:System.Windows.Navigation.PageFunction%601> 还可用于简化[导航拓扑概述](navigation-topologies-overview.md)中所述的复杂导航拓扑的创建。</span><span class="sxs-lookup"><span data-stu-id="7a48a-161"><xref:System.Windows.Navigation.PageFunction%601> also serves to simplify the creation of complex navigation topologies, which are described in [Navigation Topologies Overview](navigation-topologies-overview.md).</span></span>  
  
<a name="Hosting"></a>
## <a name="hosting"></a><span data-ttu-id="7a48a-162">Hosting</span><span class="sxs-lookup"><span data-stu-id="7a48a-162">Hosting</span></span>  
 <span data-ttu-id="7a48a-163">XBAP 可托管在 Microsoft Internet Explorer 或 Firefox 中。</span><span class="sxs-lookup"><span data-stu-id="7a48a-163">XBAPs can be hosted in Microsoft Internet Explorer or Firefox.</span></span> <span data-ttu-id="7a48a-164">每个承载模型都有各自的一些注意事项和约束，这些内容在[承载](hosting-wpf-applications.md)中均有涵盖。</span><span class="sxs-lookup"><span data-stu-id="7a48a-164">Each hosting model has its own set of considerations and constraints that are covered in [Hosting](hosting-wpf-applications.md).</span></span>  
  
<a name="Build_and_Deploy"></a>
## <a name="build-and-deploy"></a><span data-ttu-id="7a48a-165">生成和部署</span><span class="sxs-lookup"><span data-stu-id="7a48a-165">Build and Deploy</span></span>  
 <span data-ttu-id="7a48a-166">尽管简单的 WPF 应用程序可以在命令提示符下使用命令行编译器来生成，但 WPF 仍与 Visual Studio 实现了集成以提供简化了开发和生成过程的额外支持。</span><span class="sxs-lookup"><span data-stu-id="7a48a-166">Although simple WPF applications can be built from a command prompt using command-line compilers, WPF integrates with Visual Studio to provide additional support that simplified the development and build process.</span></span> <span data-ttu-id="7a48a-167">有关详细信息，请参阅[生成 WPF 应用程序](building-a-wpf-application-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="7a48a-167">For more information, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
 <span data-ttu-id="7a48a-168">根据所生成的应用程序类型，会有一个或多个部署选项可供选择。</span><span class="sxs-lookup"><span data-stu-id="7a48a-168">Depending on the type of application you build, there are one or more deployment options to choose from.</span></span> <span data-ttu-id="7a48a-169">有关详细信息，请参阅[部署 WPF 应用程序](deploying-a-wpf-application-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="7a48a-169">For more information, see [Deploying a WPF Application](deploying-a-wpf-application-wpf.md).</span></span>  
  
<a name="related_topics"></a>
## <a name="related-topics"></a><span data-ttu-id="7a48a-170">相关主题</span><span class="sxs-lookup"><span data-stu-id="7a48a-170">Related Topics</span></span>  
  
|<span data-ttu-id="7a48a-171">Title</span><span class="sxs-lookup"><span data-stu-id="7a48a-171">Title</span></span>|<span data-ttu-id="7a48a-172">描述</span><span class="sxs-lookup"><span data-stu-id="7a48a-172">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7a48a-173">应用程序管理概述</span><span class="sxs-lookup"><span data-stu-id="7a48a-173">Application Management Overview</span></span>](application-management-overview.md)|<span data-ttu-id="7a48a-174">简要介绍 <xref:System.Windows.Application> 类，包括管理应用程序生存期、窗口、应用程序资源和导航。</span><span class="sxs-lookup"><span data-stu-id="7a48a-174">Provides an overview of the <xref:System.Windows.Application> class including managing application lifetime, windows, application resources, and navigation.</span></span>|  
|[<span data-ttu-id="7a48a-175">WPF 中的窗口</span><span class="sxs-lookup"><span data-stu-id="7a48a-175">Windows in WPF</span></span>](windows-in-wpf-applications.md)|<span data-ttu-id="7a48a-176">详细介绍如何在应用程序中管理窗口，包括如何使用 <xref:System.Windows.Window> 类和对话框。</span><span class="sxs-lookup"><span data-stu-id="7a48a-176">Provides details of managing windows in your application including how to use the <xref:System.Windows.Window> class and dialog boxes.</span></span>|  
|[<span data-ttu-id="7a48a-177">导航概述</span><span class="sxs-lookup"><span data-stu-id="7a48a-177">Navigation Overview</span></span>](navigation-overview.md)|<span data-ttu-id="7a48a-178">概述如何管理应用程序的各个页面间的导航。</span><span class="sxs-lookup"><span data-stu-id="7a48a-178">Provides an overview of managing navigation between pages of your application.</span></span>|  
|[<span data-ttu-id="7a48a-179">承载</span><span class="sxs-lookup"><span data-stu-id="7a48a-179">Hosting</span></span>](hosting-wpf-applications.md)|<span data-ttu-id="7a48a-180">概述了 XAML 浏览器应用程序 (XBAP)。</span><span class="sxs-lookup"><span data-stu-id="7a48a-180">Provides an overview of XAML browser applications (XBAPs).</span></span>|  
|[<span data-ttu-id="7a48a-181">生成和部署</span><span class="sxs-lookup"><span data-stu-id="7a48a-181">Build and Deploy</span></span>](building-and-deploying-wpf-applications.md)|<span data-ttu-id="7a48a-182">描述如何生成和部署 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a48a-182">Describes how to build and deploy your WPF application.</span></span>|  
|[<span data-ttu-id="7a48a-183">Visual Studio 中的 WPF 简介</span><span class="sxs-lookup"><span data-stu-id="7a48a-183">Introduction to WPF in Visual Studio</span></span>](../getting-started/introduction-to-wpf-in-vs.md)|<span data-ttu-id="7a48a-184">介绍 WPF 的主要功能。</span><span class="sxs-lookup"><span data-stu-id="7a48a-184">Describes the main features of WPF.</span></span>|  
|[<span data-ttu-id="7a48a-185">演练：我的第一个 WPF 桌面应用程序</span><span class="sxs-lookup"><span data-stu-id="7a48a-185">Walkthrough: My first WPF desktop application</span></span>](../getting-started/walkthrough-my-first-wpf-desktop-application.md)|<span data-ttu-id="7a48a-186">一项演练，用于演示如何使用页面导航、布局、控件、图像、样式和绑定来创建 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a48a-186">A walkthrough that shows how to create a WPF application using page navigation, layout, controls, images, styles, and binding.</span></span>|
