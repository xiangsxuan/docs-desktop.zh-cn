---
title: 在 WPF 中承载 ActiveX 控件
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: 4842601c23466d84fbfb2fbbd5bd9dd17eb30e5c
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664959"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a>演练：在 WPF 中承载 ActiveX 控件
若要实现与浏览器的更好交互，可以在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 基于的应用程序中使用 Microsoft ActiveX 控件。 本演练演示如何将 Microsoft Windows Media Player 作为页面上的控件进行托管 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。

 本演练涉及以下任务：

- 创建项目。

- 创建 ActiveX 控件。

- 在 WPF 页上承载 ActiveX 控件。

 完成本演练后，你将了解如何在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 基于的应用程序中使用 Microsoft ActiveX 控件。

## <a name="prerequisites"></a>先决条件
 您需要满足以下条件才能完成本演练：

- Microsoft Windows Media Player 安装在安装了 Visual Studio 的计算机上。

- Visual Studio 2010。

## <a name="creating-the-project"></a>创建项目

### <a name="to-create-and-set-up-the-project"></a>创建并设置项目

1. 创建一个名为的 WPF 应用程序项目 `HostingAxInWpf` 。

2. 将 Windows 窗体控件库项目添加到解决方案，并将项目命名为 `WmpAxLib` 。

3. 在 WmpAxLib 项目中，添加对名为 wmp.dll 的 Windows Media Player 程序集的引用。

4. 打开 **工具箱**。

5. 右键单击 " **工具箱**"，然后单击 " **选择项**"。

6. 单击 " **COM 组件** " 选项卡，选择 **Windows Media Player** 控件，然后单击 **"确定"**。

     将 Windows Media Player 控件添加到 " **工具箱**"。

7. 在解决方案资源管理器中，右键单击 **UserControl1** 文件，然后单击 " **重命名**"。

8. 将名称更改为 `WmpAxControl.vb` 或 `WmpAxControl.cs` ，具体取决于语言。

9. 如果系统提示您重命名所有引用，请单击 **"是"**。

## <a name="creating-the-activex-control"></a>创建 ActiveX 控件
将 <xref:System.Windows.Forms.AxHost> 控件添加到设计图面时，Visual Studio 会自动为 Microsoft ActiveX 控件生成包装类。 下面的过程创建一个名为 AxInterop.WMPLib.dll 的托管程序集。

### <a name="to-create-the-activex-control"></a>创建 ActiveX 控件

1. 在 Windows 窗体设计器中打开 WmpAxControl 或 WmpAxControl。

2. 从 " **工具箱**" 中，将 "Windows Media Player" 控件添加到设计图面。

3. 在属性窗口中，将 Windows Media Player 控件的属性的值设置 <xref:System.Windows.Forms.Control.Dock%2A> 为 <xref:System.Windows.Forms.DockStyle.Fill> 。

4. 生成 WmpAxLib 控件库项目。

## <a name="hosting-the-activex-control-on-a-wpf-page"></a>在 WPF 页上承载 ActiveX 控件

### <a name="to-host-the-activex-control"></a>承载 ActiveX 控件

1. 在 HostingAxInWpf 项目中，添加对生成的 ActiveX 互操作程序集的引用。

     此程序集命名为 AxInterop.WMPLib.dll，并在导入 Windows Media Player 控件时添加到 WmpAxLib 项目的 Debug 文件夹中。

2. 添加对 WindowsFormsIntegration 程序集的引用，该程序集名为 WindowsFormsIntegration.dll。

3. 向名为 System.Windows.Forms.dll 的 Windows 窗体程序集添加引用。

4. 在 WPF 设计器中打开 Mainwindow.xaml。

5. 命名 <xref:System.Windows.Controls.Grid> 元素 `grid1` 。

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. 在设计视图或 XAML 视图中，选择 <xref:System.Windows.Window> 元素。

7. 在属性窗口中，单击 " **事件** " 选项卡。

8. 双击该 <xref:System.Windows.FrameworkElement.Loaded> 事件。

9. 插入以下代码以处理 <xref:System.Windows.FrameworkElement.Loaded> 事件。

     此代码创建控件的一个实例 <xref:System.Windows.Forms.Integration.WindowsFormsHost> ，并将该控件的一个实例添加 `AxWindowsMediaPlayer` 为其子级。

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. 按 F5 生成并运行应用程序。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [演练：在 WPF 中托管 Windows 窗体复合控件](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [演练：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
