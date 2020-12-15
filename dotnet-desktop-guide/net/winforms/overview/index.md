---
title: 什么是 Windows 窗体
description: 本文概述了 .NET Core 和 .NET 5 的 Windows 窗体。
ms.date: 10/26/2020
ms.topic: overview
ms.openlocfilehash: a0908891d9391d5820fe75cac69278ddda1b2244
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96992773"
---
# <a name="desktop-guide-windows-forms-net"></a><span data-ttu-id="ef5ee-103">桌面指南（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="ef5ee-103">Desktop Guide (Windows Forms .NET)</span></span>

<span data-ttu-id="ef5ee-104">欢迎使用 Windows 窗体的桌面指南，Windows 窗体是一个可创建适用于 Windows 的丰富桌面客户端应用的 UI 框架。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-104">Welcome to the Desktop Guide for Windows Forms, a UI framework that creates rich desktop client apps for Windows.</span></span> <span data-ttu-id="ef5ee-105">Windows 窗体开发平台支持广泛的应用开发功能，包括控件、图形、数据绑定和用户输入。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-105">The Windows Forms development platform supports a broad set of app development features, including controls, graphics, data binding, and user input.</span></span> <span data-ttu-id="ef5ee-106">Windows 窗体采用 Visual Studio 中的拖放式可视化设计器，可轻松创建 Windows 窗体应用。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-106">Windows Forms features a drag-and-drop visual designer in Visual Studio to easily create Windows Forms apps.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="ef5ee-107">Windows 窗体有两种实现：</span><span class="sxs-lookup"><span data-stu-id="ef5ee-107">There are two implementations of Windows Forms:</span></span>

01. <span data-ttu-id="ef5ee-108">托管于 [GitHub](https://github.com/dotnet/winforms) 上的开放源代码实现。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-108">The open-source implementation hosted on [GitHub](https://github.com/dotnet/winforms).</span></span>

    <span data-ttu-id="ef5ee-109">此版本在 .NET 5 和 .NET Core 3.1 上运行。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-109">This version runs on .NET 5 and .NET Core 3.1.</span></span> <span data-ttu-id="ef5ee-110">Windows 窗体可视化设计器最低要求 [Visual Studio 2019 版本 16.8 预览版](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms)。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-110">The Windows Forms Visual Designer requires, at a minimum, [Visual Studio 2019 version 16.8 Preview](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms).</span></span>

01. <span data-ttu-id="ef5ee-111">受 Visual Studio 2019 和 Visual Studio 2017 支持的 .NET Framework 4 实现。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-111">The .NET Framework 4 implementation that's supported by Visual Studio 2019 and Visual Studio 2017.</span></span>

    <span data-ttu-id="ef5ee-112">.NET Framework 4 是仅限 Windows 的 .NET 版本，被视为一个 Windows 操作系统组件。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-112">.NET Framework 4 is a Windows-only version of .NET and is considered a Windows Operating System component.</span></span> <span data-ttu-id="ef5ee-113">此版本的 Windows 窗体随 .NET Framework 一起分发。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-113">This version of Windows Forms is distributed with .NET Framework.</span></span>

<span data-ttu-id="ef5ee-114">本桌面指南适用于 .NET 5 上的 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-114">This Desktop Guide is written for Windows Forms on .NET 5.</span></span> <span data-ttu-id="ef5ee-115">有关 Windows 窗体的 .NET Framework 版本的详细信息，请参阅 [.NET Framework 的 Windows 窗体](../../../framework/winforms/index.yml?view=netframeworkdesktop-4.8&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-115">For more information about the .NET Framework version of Windows Forms, see [Windows Forms for .NET Framework](../../../framework/winforms/index.yml?view=netframeworkdesktop-4.8&preserve-view=true).</span></span>

## <a name="introduction"></a><span data-ttu-id="ef5ee-116">简介</span><span class="sxs-lookup"><span data-stu-id="ef5ee-116">Introduction</span></span>

<span data-ttu-id="ef5ee-117">Windows 窗体是用于生成 Windows 桌面应用的 UI 框架。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-117">Windows Forms is a UI framework for building Windows desktop apps.</span></span> <span data-ttu-id="ef5ee-118">它提供了一种基于 Visual Studio 中提供的可视化设计器创建桌面应用的高效方法。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-118">It provides one of the most productive ways to create desktop apps based on the visual designer provided in Visual Studio.</span></span> <span data-ttu-id="ef5ee-119">利用视觉对象控件的拖放放置等功能，可以轻松生成桌面应用。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-119">Functionality such as drag-and-drop placement of visual controls makes it easy to build desktop apps.</span></span>

<span data-ttu-id="ef5ee-120">使用 Windows 窗体，可以开发包含丰富图形的应用，这些应用易于部署和更新，并且在脱机状态下或连接到 Internet 时都可正常工作。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-120">With Windows Forms, you develop graphically rich apps that are easy to deploy, update, and work while offline or while connected to the internet.</span></span> <span data-ttu-id="ef5ee-121">Windows 窗体应用可以访问运行应用的计算机的本地硬件和文件系统。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-121">Windows Forms apps can access the local hardware and file system of the computer where the app is running.</span></span>

<span data-ttu-id="ef5ee-122">要了解如何创建 Windows 窗体应用，请参阅[教程：创建新的 WinForms 应用（Windows 窗体 .NET）](../get-started/create-app-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-122">To learn how to create a Windows Forms app, see [Tutorial: Create a new WinForms app (Windows Forms .NET)](../get-started/create-app-visual-studio.md).</span></span>

## <a name="why-migrate-from-net-framework"></a><span data-ttu-id="ef5ee-123">为什么要从 .NET Framework 迁移</span><span class="sxs-lookup"><span data-stu-id="ef5ee-123">Why migrate from .NET Framework</span></span>

<span data-ttu-id="ef5ee-124">.NET 5.0 的 Windows 窗体提供优于 .NET Framework 的新功能和增强功能。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-124">Windows Forms for .NET 5.0 provides new features and enhancements over .NET Framework.</span></span> <span data-ttu-id="ef5ee-125">有关详细信息，请参阅 [.NET 5 的 Windows 窗体中的新增功能](../whats-new/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-125">For more information, see [What's new in Windows Forms for .NET 5](../whats-new/index.md).</span></span> <span data-ttu-id="ef5ee-126">要了解如何迁移应用，请参阅[如何将 Windows 窗体桌面应用迁移到 .NET 5](../migration/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-126">To learn how to migrate an app, see [How to migrate a Windows Forms desktop app to .NET 5](../migration/index.md).</span></span>

## <a name="build-rich-interactive-user-interfaces"></a><span data-ttu-id="ef5ee-127">生成丰富的交互式用户界面</span><span class="sxs-lookup"><span data-stu-id="ef5ee-127">Build rich, interactive user interfaces</span></span>

<span data-ttu-id="ef5ee-128">Windows 窗体是用于 .NET 的 UI 技术，是一组简化读取和写入文件系统等常见应用任务的托管库。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-128">Windows Forms is a UI technology for .NET, a set of managed libraries that simplify common app tasks such as reading and writing to the file system.</span></span> <span data-ttu-id="ef5ee-129">使用类似于 Visual Studio 的开发环境时，可以创建 Windows 窗体智能客户端应用，该应用可显示信息、请求来自用户的输入以及通过网络与远程计算机通信。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-129">When you use a development environment like Visual Studio, you can create Windows Forms smart-client apps that display information, request input from users, and communicate with remote computers over a network.</span></span>

<span data-ttu-id="ef5ee-130">在 Windows 窗体中，窗体是一种可视图面，可在其上对用户显示信息。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-130">In Windows Forms, a *form* is a visual surface on which you display information to the user.</span></span> <span data-ttu-id="ef5ee-131">通常情况下，通过向窗体添加控件和开发对用户操作（如点击鼠标或按键）的响应来生成 Windows 窗体应用。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-131">You ordinarily build Windows Forms apps by adding controls to forms and developing responses to user actions, such as mouse clicks or key presses.</span></span> <span data-ttu-id="ef5ee-132">控件是离散的 UI 元素，用于显示数据或接受数据输入。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-132">A *control* is a discrete UI element that displays data or accepts data input.</span></span>

<span data-ttu-id="ef5ee-133">当用户对你的窗体或一个窗体控件执行了某个操作，该操作将生成一个事件。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-133">When a user does something to your form or one of its controls, the action generates an event.</span></span> <span data-ttu-id="ef5ee-134">应用通过代码对这些事件做出反应，并在事件发生时对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-134">Your app reacts to these events with code, and processes the events when they occur.</span></span><!-- TODO  For more information, see [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md).-->

<span data-ttu-id="ef5ee-135">Windows 窗体包含各种可以向窗体添加的控件：显示文本框、按钮、下拉框、单选按钮甚至网页的控件。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-135">Windows Forms contains a variety of controls that you can add to forms: controls that display text boxes, buttons, drop-down boxes, radio buttons, and even webpages.</span></span><!-- TODO For a list of all the controls you can use on a form, see [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).--> <span data-ttu-id="ef5ee-136">如果某个现有控件不满足你的需要，Windows 窗体还支持使用 <xref:System.Windows.Forms.UserControl> 类创建自己的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-136">If an existing control doesn't meet your needs, Windows Forms also supports creating your own custom controls using the <xref:System.Windows.Forms.UserControl> class.</span></span>

<span data-ttu-id="ef5ee-137">Windows 窗体具有丰富的 UI 控件，这些控件可模拟 Microsoft Office 等高端应用中的功能。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-137">Windows Forms has rich UI controls that emulate features in high-end apps like Microsoft Office.</span></span> <span data-ttu-id="ef5ee-138">使用 <xref:System.Windows.Forms.ToolStrip> 和 <xref:System.Windows.Forms.MenuStrip> 控件时，可以创建包含文本和图像的工具栏和菜单、显示子菜单和托管其他控件（如文本框和组合框）。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-138">When you use the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip> controls, you can create toolbars and menus that contain text and images, display submenus, and host other controls such as text boxes and combo boxes.</span></span>

<span data-ttu-id="ef5ee-139">借助 Visual Studio中的拖放式 Windows 窗体设计器，可以轻松创建 Windows 窗体应用。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-139">With the drag-and-drop **Windows Forms Designer** in Visual Studio, you can easily create Windows Forms apps.</span></span> <span data-ttu-id="ef5ee-140">只需用光标选中控件，然后将它们放置到窗体中所需的位置即可。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-140">Just select the controls with your cursor and place them where you want on the form.</span></span> <span data-ttu-id="ef5ee-141">设计器提供诸如网格线和对齐线的工具，以便简化对齐控件的操作。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-141">The designer provides tools such as gridlines and snap lines to take the hassle out of aligning controls.</span></span> <span data-ttu-id="ef5ee-142">可以使用 <xref:System.Windows.Forms.FlowLayoutPanel>、<xref:System.Windows.Forms.TableLayoutPanel> 和 <xref:System.Windows.Forms.SplitContainer> 控件在更短的时间内创建高级窗体布局。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-142">You can use the <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel>, and <xref:System.Windows.Forms.SplitContainer> controls to create advanced form layouts in less time.</span></span>

<span data-ttu-id="ef5ee-143">最后，如果必须创建自己的自定义用户界面元素，<xref:System.Drawing> 命名空间包含各种类，可用以直接在窗体上呈现线条、圆形和其他形状。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-143">Finally, if you must create your own custom UI elements, the <xref:System.Drawing> namespace contains a large selection of classes to render lines, circles, and other shapes directly on a form.</span></span>

### <a name="create-forms-and-controls"></a><span data-ttu-id="ef5ee-144">创建窗体和控件</span><span class="sxs-lookup"><span data-stu-id="ef5ee-144">Create forms and controls</span></span>

<span data-ttu-id="ef5ee-145">如需了解如何使用这些功能的步骤信息，请参阅以下“帮助”主题。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-145">For step-by-step information about how to use these features, see the following Help topics.</span></span>

- [<span data-ttu-id="ef5ee-146">如何向项目添加窗体</span><span class="sxs-lookup"><span data-stu-id="ef5ee-146">How to add a form to a project</span></span>](../forms/how-to-add.md)
- [<span data-ttu-id="ef5ee-147">如何向窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="ef5ee-147">How to add Controls to to a form</span></span>](../controls/how-to-add-to-a-form.md)

<!-- TODO
| Using the <xref:System.Windows.Forms.ToolStrip> Control | [How to: Create a Basic ToolStrip with Standard Items Using the Designer](./controls/create-a-basic-wf-toolstrip-with-standard-items-using-the-designer.md) |
| Creating graphics with <xref:System.Drawing> | [Getting Started with Graphics Programming](./advanced/getting-started-with-graphics-programming.md)  |
| Creating custom controls                     | [How to: Inherit from the UserControl Class](./controls/how-to-inherit-from-the-usercontrol-class.md) |
-->

## <a name="display-and-manipulate-data"></a><span data-ttu-id="ef5ee-148">显示和操纵数据</span><span class="sxs-lookup"><span data-stu-id="ef5ee-148">Display and manipulate data</span></span>

<span data-ttu-id="ef5ee-149">许多应用必须显示数据库、XML 文件、JSON 文件、Web 服务或其他数据源中的数据。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-149">Many apps must display data from a database, XML or JSON file, web service, or other data source.</span></span> <span data-ttu-id="ef5ee-150">Windows 窗体提供了一个灵活的控件（名为 <xref:System.Windows.Forms.DataGridView> 控件），用于以传统的行和列格式显示此类表格数据，以便使每段数据块均占据其自己的单元格。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-150">Windows Forms provides a flexible control that is named the <xref:System.Windows.Forms.DataGridView> control for displaying such tabular data in a traditional row and column format, so that every piece of data occupies its own cell.</span></span> <span data-ttu-id="ef5ee-151">使用 <xref:System.Windows.Forms.DataGridView> 时，可以自定义各个单元格的外观，将任意行和列锁定在所需位置，在单元格内部显示复杂控件，此外还具有其他功能。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-151">When you use <xref:System.Windows.Forms.DataGridView>, you can customize the appearance of individual cells, lock arbitrary rows and columns in place, and display complex controls inside cells, among other features.</span></span>

<span data-ttu-id="ef5ee-152">通过网络连接到数据源对于 Windows 窗体而言是一个简单的任务。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-152">Connecting to data sources over a network is a simple task with Windows Forms.</span></span> <span data-ttu-id="ef5ee-153"><xref:System.Windows.Forms.BindingSource> 组件表示与数据源的连接，并公开完成以下操作的方法：将数据绑定到控件、导航到上一个和下一个记录、编辑记录，以及将更改保存回原始源。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-153">The <xref:System.Windows.Forms.BindingSource> component represents a connection to a data source, and exposes methods for binding data to controls, navigating to the previous and next records, editing records, and saving changes back to the original source.</span></span> <span data-ttu-id="ef5ee-154"><xref:System.Windows.Forms.BindingNavigator> 控件通过 <xref:System.Windows.Forms.BindingSource> 组件提供一个简单界面，可供用户在记录间导航。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-154">The <xref:System.Windows.Forms.BindingNavigator> control provides a simple interface over the <xref:System.Windows.Forms.BindingSource> component for users to navigate between records.</span></span>

<span data-ttu-id="ef5ee-155">可以使用 Visual Studio 中的“数据源”窗口轻松创建数据绑定控件。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-155">You can create data-bound controls easily by using the Data Sources window in Visual Studio.</span></span> <span data-ttu-id="ef5ee-156">窗口显示数据源，如数据库、Web 服务和项目中的对象。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-156">The window displays data sources such as databases, web services, and objects in your project.</span></span> <span data-ttu-id="ef5ee-157">可以通过将此窗口中的项拖动到项目中的窗体上来创建数据绑定控件。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-157">You can create data-bound controls by dragging items from this window onto forms in your project.</span></span> <span data-ttu-id="ef5ee-158">还可以通过将对象从“数据源”窗口拖动到现有控件上来将现有控件与数据进行数据绑定。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-158">You can also data-bind existing controls to data by dragging objects from the Data Sources window onto existing controls.</span></span>

<span data-ttu-id="ef5ee-159">可在 Windows 窗体中管理的另一类数据绑定是“设置”。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-159">Another type of data binding you can manage in Windows Forms is *settings*.</span></span> <span data-ttu-id="ef5ee-160">大多数应用均必须保留有关其运行时状态的某些信息（例如窗体的最后已知大小）以及用户首选项数据（例如保存的文件的默认位置）。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-160">Most apps must retain some information about their run-time state, such as the last-known size of forms, and retain user preference data, such as default locations for saved files.</span></span> <span data-ttu-id="ef5ee-161">“应用程序设置”功能通过提供一种在客户端计算机上存储两种类型的设置的简单方法来满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-161">The Application Settings feature addresses these requirements by providing an easy way to store both types of settings on the client computer.</span></span> <span data-ttu-id="ef5ee-162">通过使用 Visual Studio 或代码编辑器定义这些设置后，这些设置便作为 XML保留并自动在运行时读取回内存中。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-162">After you define these settings by using either Visual Studio or a code editor, the settings are persisted as XML and automatically read back into memory at run time.</span></span>

<!-- TODO
### Display and manipulate data

For step-by-step information about how to use these features, see the following Help topics.

| Description                                                   | Help topic                                                                                                                                                        |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Using the <xref:System.Windows.Forms.BindingSource> component | [How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer](./controls/bind-wf-controls-with-the-bindingsource.md)                  |
| Working with ADO.NET data sources                             | [How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component](./controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md) |
| Using the Data Sources window                                 | [Bind Windows Forms controls to data in Visual Studio](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)                             |
| Using app settings                                            | [How to: Create Application Settings](./advanced/how-to-create-application-settings.md)                                                                           |

-->

## <a name="deploy-apps-to-client-computers"></a><span data-ttu-id="ef5ee-163">将应用部署到客户端计算机</span><span class="sxs-lookup"><span data-stu-id="ef5ee-163">Deploy apps to client computers</span></span>

<span data-ttu-id="ef5ee-164">编写了应用后，必须将应用发送给用户，以便他们可以在自己的客户端计算机上安装和运行此应用。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-164">After you have written your app, you must send the app to your users so that they can install and run it on their own client computers.</span></span> <span data-ttu-id="ef5ee-165">使用 ClickOnce 技术时，只需进行几次点击便可以从 Visual Studio 内部署应用，然后向用户提供指向 Web 上的应用的 URL。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-165">When you use the ClickOnce technology, you can deploy your apps from within Visual Studio by using just a few clicks, and provide your users with a URL pointing to your app on the web.</span></span> <span data-ttu-id="ef5ee-166">ClickOnce 可管理应用中的所有元素和依赖项，并确保应用正确安装到客户端计算机上。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-166">ClickOnce manages all the elements and dependencies in your app, and ensures that the app is correctly installed on the client computer.</span></span>

<span data-ttu-id="ef5ee-167">ClickOnce 应用可以配置为仅在用户连接到网络时运行，或配置为联机和脱机时均可运行。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-167">ClickOnce apps can be configured to run only when the user is connected to the network, or to run both online and offline.</span></span> <span data-ttu-id="ef5ee-168">如果指定应用支持脱机操作，则 ClickOnce 会在用户的“开始”菜单中添加一个指向应用的链接。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-168">When you specify that an app should support offline operation, ClickOnce adds a link to your app in the user's **Start** menu.</span></span> <span data-ttu-id="ef5ee-169">然后用户便可以打开应用，而无需使用此 URL。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-169">The user can then open the app without using the URL.</span></span>

<span data-ttu-id="ef5ee-170">如果你更新应用，则会同时向你的 Web 服务器发布一个新的部署清单和应用的一个新副本。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-170">When you update your app, you publish a new deployment manifest and a new copy of your app to your web server.</span></span> <span data-ttu-id="ef5ee-171">ClickOnce 将检测到有可用更新并将升级用户的安装。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-171">ClickOnce will detect that there is an update available and upgrade the user's installation.</span></span> <span data-ttu-id="ef5ee-172">更新旧应用无需进行自定义编程。</span><span class="sxs-lookup"><span data-stu-id="ef5ee-172">No custom programming is required to update old apps.</span></span>

<!-- TODO

### Deploy ClickOnce apps

For a full introduction to ClickOnce, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment). For step-by-step information about how to use these features, see the following Help topics,

|Description|Help topic|
|-----------------|----------------|
|Deploying an app by using ClickOnce|[How to: Publish a ClickOnce Application using the Publish Wizard](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Walkthrough: Manually Deploying a ClickOnce Application](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|Updating a ClickOnce deployment|[How to: Manage Updates for a ClickOnce Application](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|Managing security with ClickOnce|[How to: Enable ClickOnce Security Settings](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|
-->

<!-- TODO
## Other controls and features

There are many other features in Windows Forms that make implementing common tasks fast and easy, such as support for creating dialog boxes, printing, adding help and documentation, and localizing your app to multiple languages.

### Implement other controls and features

For step-by-step information about how to use these features, see the following Help topics.

| Description | Help topic |
|-------------|------------|
|Printing the contents of a form | [How to: Print Graphics in Windows Forms](./advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [How to: Print a Multi-Page Text File in Windows Forms](./advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md) |
|Learn more about Windows Forms security | [Security in Windows Forms Overview](security-in-windows-forms-overview.md) |
-->

## <a name="see-also"></a><span data-ttu-id="ef5ee-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef5ee-173">See also</span></span>

- [<span data-ttu-id="ef5ee-174">教程：创建新的 WinForms 应用（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="ef5ee-174">Tutorial: Create a new WinForms app (Windows Forms .NET)</span></span>](../get-started/create-app-visual-studio.md)
- [<span data-ttu-id="ef5ee-175">如何向项目添加窗体（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="ef5ee-175">How to add a form to a project (Windows Forms .NET)</span></span>](../forms/how-to-add.md)
- [<span data-ttu-id="ef5ee-176">添加控件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="ef5ee-176">Add a control (Windows Forms .NET)</span></span>](../controls/how-to-add-to-a-form.md)
