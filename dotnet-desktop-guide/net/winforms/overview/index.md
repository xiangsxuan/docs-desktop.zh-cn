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
# <a name="desktop-guide-windows-forms-net"></a>桌面指南（Windows 窗体 .NET）

欢迎使用 Windows 窗体的桌面指南，Windows 窗体是一个可创建适用于 Windows 的丰富桌面客户端应用的 UI 框架。 Windows 窗体开发平台支持广泛的应用开发功能，包括控件、图形、数据绑定和用户输入。 Windows 窗体采用 Visual Studio 中的拖放式可视化设计器，可轻松创建 Windows 窗体应用。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

Windows 窗体有两种实现：

01. 托管于 [GitHub](https://github.com/dotnet/winforms) 上的开放源代码实现。

    此版本在 .NET 5 和 .NET Core 3.1 上运行。 Windows 窗体可视化设计器最低要求 [Visual Studio 2019 版本 16.8 预览版](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms)。

01. 受 Visual Studio 2019 和 Visual Studio 2017 支持的 .NET Framework 4 实现。

    .NET Framework 4 是仅限 Windows 的 .NET 版本，被视为一个 Windows 操作系统组件。 此版本的 Windows 窗体随 .NET Framework 一起分发。

本桌面指南适用于 .NET 5 上的 Windows 窗体。 有关 Windows 窗体的 .NET Framework 版本的详细信息，请参阅 [.NET Framework 的 Windows 窗体](../../../framework/winforms/index.yml?view=netframeworkdesktop-4.8&preserve-view=true)。

## <a name="introduction"></a>简介

Windows 窗体是用于生成 Windows 桌面应用的 UI 框架。 它提供了一种基于 Visual Studio 中提供的可视化设计器创建桌面应用的高效方法。 利用视觉对象控件的拖放放置等功能，可以轻松生成桌面应用。

使用 Windows 窗体，可以开发包含丰富图形的应用，这些应用易于部署和更新，并且在脱机状态下或连接到 Internet 时都可正常工作。 Windows 窗体应用可以访问运行应用的计算机的本地硬件和文件系统。

要了解如何创建 Windows 窗体应用，请参阅[教程：创建新的 WinForms 应用（Windows 窗体 .NET）](../get-started/create-app-visual-studio.md)。

## <a name="why-migrate-from-net-framework"></a>为什么要从 .NET Framework 迁移

.NET 5.0 的 Windows 窗体提供优于 .NET Framework 的新功能和增强功能。 有关详细信息，请参阅 [.NET 5 的 Windows 窗体中的新增功能](../whats-new/index.md)。 要了解如何迁移应用，请参阅[如何将 Windows 窗体桌面应用迁移到 .NET 5](../migration/index.md)。

## <a name="build-rich-interactive-user-interfaces"></a>生成丰富的交互式用户界面

Windows 窗体是用于 .NET 的 UI 技术，是一组简化读取和写入文件系统等常见应用任务的托管库。 使用类似于 Visual Studio 的开发环境时，可以创建 Windows 窗体智能客户端应用，该应用可显示信息、请求来自用户的输入以及通过网络与远程计算机通信。

在 Windows 窗体中，窗体是一种可视图面，可在其上对用户显示信息。 通常情况下，通过向窗体添加控件和开发对用户操作（如点击鼠标或按键）的响应来生成 Windows 窗体应用。 控件是离散的 UI 元素，用于显示数据或接受数据输入。

当用户对你的窗体或一个窗体控件执行了某个操作，该操作将生成一个事件。 应用通过代码对这些事件做出反应，并在事件发生时对其进行处理。<!-- TODO  For more information, see [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md).-->

Windows 窗体包含各种可以向窗体添加的控件：显示文本框、按钮、下拉框、单选按钮甚至网页的控件。<!-- TODO For a list of all the controls you can use on a form, see [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).--> 如果某个现有控件不满足你的需要，Windows 窗体还支持使用 <xref:System.Windows.Forms.UserControl> 类创建自己的自定义控件。

Windows 窗体具有丰富的 UI 控件，这些控件可模拟 Microsoft Office 等高端应用中的功能。 使用 <xref:System.Windows.Forms.ToolStrip> 和 <xref:System.Windows.Forms.MenuStrip> 控件时，可以创建包含文本和图像的工具栏和菜单、显示子菜单和托管其他控件（如文本框和组合框）。

借助 Visual Studio中的拖放式 Windows 窗体设计器，可以轻松创建 Windows 窗体应用。 只需用光标选中控件，然后将它们放置到窗体中所需的位置即可。 设计器提供诸如网格线和对齐线的工具，以便简化对齐控件的操作。 可以使用 <xref:System.Windows.Forms.FlowLayoutPanel>、<xref:System.Windows.Forms.TableLayoutPanel> 和 <xref:System.Windows.Forms.SplitContainer> 控件在更短的时间内创建高级窗体布局。

最后，如果必须创建自己的自定义用户界面元素，<xref:System.Drawing> 命名空间包含各种类，可用以直接在窗体上呈现线条、圆形和其他形状。

### <a name="create-forms-and-controls"></a>创建窗体和控件

如需了解如何使用这些功能的步骤信息，请参阅以下“帮助”主题。

- [如何向项目添加窗体](../forms/how-to-add.md)
- [如何向窗体添加控件](../controls/how-to-add-to-a-form.md)

<!-- TODO
| Using the <xref:System.Windows.Forms.ToolStrip> Control | [How to: Create a Basic ToolStrip with Standard Items Using the Designer](./controls/create-a-basic-wf-toolstrip-with-standard-items-using-the-designer.md) |
| Creating graphics with <xref:System.Drawing> | [Getting Started with Graphics Programming](./advanced/getting-started-with-graphics-programming.md)  |
| Creating custom controls                     | [How to: Inherit from the UserControl Class](./controls/how-to-inherit-from-the-usercontrol-class.md) |
-->

## <a name="display-and-manipulate-data"></a>显示和操纵数据

许多应用必须显示数据库、XML 文件、JSON 文件、Web 服务或其他数据源中的数据。 Windows 窗体提供了一个灵活的控件（名为 <xref:System.Windows.Forms.DataGridView> 控件），用于以传统的行和列格式显示此类表格数据，以便使每段数据块均占据其自己的单元格。 使用 <xref:System.Windows.Forms.DataGridView> 时，可以自定义各个单元格的外观，将任意行和列锁定在所需位置，在单元格内部显示复杂控件，此外还具有其他功能。

通过网络连接到数据源对于 Windows 窗体而言是一个简单的任务。 <xref:System.Windows.Forms.BindingSource> 组件表示与数据源的连接，并公开完成以下操作的方法：将数据绑定到控件、导航到上一个和下一个记录、编辑记录，以及将更改保存回原始源。 <xref:System.Windows.Forms.BindingNavigator> 控件通过 <xref:System.Windows.Forms.BindingSource> 组件提供一个简单界面，可供用户在记录间导航。

可以使用 Visual Studio 中的“数据源”窗口轻松创建数据绑定控件。 窗口显示数据源，如数据库、Web 服务和项目中的对象。 可以通过将此窗口中的项拖动到项目中的窗体上来创建数据绑定控件。 还可以通过将对象从“数据源”窗口拖动到现有控件上来将现有控件与数据进行数据绑定。

可在 Windows 窗体中管理的另一类数据绑定是“设置”。 大多数应用均必须保留有关其运行时状态的某些信息（例如窗体的最后已知大小）以及用户首选项数据（例如保存的文件的默认位置）。 “应用程序设置”功能通过提供一种在客户端计算机上存储两种类型的设置的简单方法来满足这些要求。 通过使用 Visual Studio 或代码编辑器定义这些设置后，这些设置便作为 XML保留并自动在运行时读取回内存中。

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

## <a name="deploy-apps-to-client-computers"></a>将应用部署到客户端计算机

编写了应用后，必须将应用发送给用户，以便他们可以在自己的客户端计算机上安装和运行此应用。 使用 ClickOnce 技术时，只需进行几次点击便可以从 Visual Studio 内部署应用，然后向用户提供指向 Web 上的应用的 URL。 ClickOnce 可管理应用中的所有元素和依赖项，并确保应用正确安装到客户端计算机上。

ClickOnce 应用可以配置为仅在用户连接到网络时运行，或配置为联机和脱机时均可运行。 如果指定应用支持脱机操作，则 ClickOnce 会在用户的“开始”菜单中添加一个指向应用的链接。 然后用户便可以打开应用，而无需使用此 URL。

如果你更新应用，则会同时向你的 Web 服务器发布一个新的部署清单和应用的一个新副本。 ClickOnce 将检测到有可用更新并将升级用户的安装。 更新旧应用无需进行自定义编程。

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

## <a name="see-also"></a>另请参阅

- [教程：创建新的 WinForms 应用（Windows 窗体 .NET）](../get-started/create-app-visual-studio.md)
- [如何向项目添加窗体（Windows 窗体 .NET）](../forms/how-to-add.md)
- [添加控件（Windows 窗体 .NET）](../controls/how-to-add-to-a-form.md)
