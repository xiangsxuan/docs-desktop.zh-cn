---
title: 使用 XAML 在 WPF 中承载 Windows 窗体控件
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 2b67c1c888c9f5a9845940220fe5cc042fe574d3
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665141"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a>演练：使用 XAML 在 WPF 中承载 Windows 窗体控件
[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 提供了许多具有丰富功能集的控件。 但是，有时可能需要使用页面上 Windows 窗体控件 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 例如，您可能在现有 Windows 窗体控件中有大量投资，或者您可能有一个提供独特功能的 Windows 窗体控件。  
  
 本演练演示如何 <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> 使用在页面上承载 Windows 窗体控件 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。  
  
 有关本演练中所示任务的完整代码列表，请参阅 [使用 XAML 在 WPF 中承载 Windows 窗体控件](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)。
  
## <a name="prerequisites"></a>必备条件  

若要完成本演练，必须具有 Visual Studio。  
  
## <a name="hosting-the-windows-forms-control"></a>承载 Windows 窗体控件  
  
#### <a name="to-host-the-maskedtextbox-control"></a>承载 MaskedTextBox 控件  
  
1. 创建一个名为的 WPF 应用程序项目 `HostingWfInWpfWithXaml` 。  
  
2. 添加对下列程序集的引用。  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. 在 WPF 设计器中打开 Mainwindow.xaml。  
  
4. 在 <xref:System.Windows.Window> 元素中，添加以下命名空间映射。 `wf`命名空间映射将建立对包含 Windows 窗体控件的程序集的引用。  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. 在 <xref:System.Windows.Controls.Grid> 元素中添加以下 XAML。  
  
     <xref:System.Windows.Forms.MaskedTextBox>控件将创建为控件的子控件 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 。  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. 按 F5 生成并运行应用程序。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [演练：在 WPF 中承载 Windows 窗体控件](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [演练：在 WPF 中托管 Windows 窗体复合控件](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [演练：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Windows 窗体控件和等效的 WPF 控件](windows-forms-controls-and-equivalent-wpf-controls.md)
- [使用 XAML 在 WPF 中承载 Windows 窗体控件](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)
