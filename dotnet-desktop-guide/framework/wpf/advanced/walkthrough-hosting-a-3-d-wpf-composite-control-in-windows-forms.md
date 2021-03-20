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
# <a name="walkthrough-host-a-3d-wpf-composite-control-in-windows-forms"></a>演练：在 Windows 窗体中托管 3D WPF 复合控件

本演练演示如何创建 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 复合控件，并使用控件在 Windows 窗体控件和窗体中承载它 <xref:System.Windows.Forms.Integration.ElementHost> 。

在本演练中，您将实现一个 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 包含两个子控件的。 <xref:System.Windows.Controls.UserControl>显示三维 (3d) 圆锥。 与 Windows 窗体相比，呈现3D 对象更容易 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 因此， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 在 Windows 窗体中承载类以创建三维图形是有意义的。

本演练涉及以下任务：

- 创建 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 。

- 正在创建 Windows 窗体主机项目。

- 承载的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 。

## <a name="prerequisites"></a>先决条件

您需要满足以下条件才能完成本演练：

- Visual Studio 2017

<a name="To_Create_the_UserControl"></a>

## <a name="create-the-usercontrol"></a>创建 UserControl

1. 创建一个名为的 **WPF 用户控件库** 项目 `HostingWpfUserControlInWf` 。

2. 在 WPF 设计器中打开 UserControl1。

3. 将生成的代码替换为以下代码：

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     此代码定义一个 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 包含两个子控件的。 第一个子控件是一个 <xref:System.Windows.Controls.Label?displayProperty=nameWithType> 控件; 第二个控件是 <xref:System.Windows.Controls.Viewport3D> 显示三维圆锥的控件。

<a name="To_Create_the_Windows_Forms_Host_Project"></a>

## <a name="create-the-host-project"></a>创建主机项目

1. 将名为的 **Windows 窗体应用 ( .NET Framework)** 项目添加 `WpfUserControlHost` 到解决方案中。

2. 在 **解决方案资源管理器** 中，添加对名为 WindowsFormsIntegration.dll 的 WindowsFormsIntegration 程序集的引用。

3. 添加对以下 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 程序集的引用：

    - PresentationCore

    - PresentationFramework

    - WindowsBase

4. 添加对项目的引用 `HostingWpfUserControlInWf` 。

5. 在解决方案资源管理器中，将 `WpfUserControlHost` 项目设置为 "启动项目"。

<a name="To_Host_the_Windows_Presentation_Foundation"></a>

## <a name="host-the-usercontrol"></a>承载 UserControl

1. 在 Windows 窗体设计器中，打开 "Form1"。

2. 在属性窗口中，单击 " **事件**"，然后双击 <xref:System.Windows.Forms.Form.Load> 事件以创建事件处理程序。

     "代码编辑器" 将打开新生成的 `Form1_Load` 事件处理程序。

3. 将 Form1 中的代码替换为以下代码。

     `Form1_Load`事件处理程序创建的一个实例 `UserControl1` ，并将内部 <xref:System.Windows.Forms.Integration.ElementHost> 控件的子控件集合。 <xref:System.Windows.Forms.Integration.ElementHost>控件将添加到窗体的子控件集合。

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. 按 F5 生成并运行应用程序。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [演练：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [演练：在 WPF 中托管 Windows 窗体复合控件](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [在 Windows 窗体示例中承载 WPF 复合控件](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WindowsFormsHostingWpfControl)
