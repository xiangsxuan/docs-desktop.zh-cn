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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973895"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>如何：创建返回 UI 的外接程序

此示例演示如何创建一个外接程序，该外接程序将 Windows Presentation Foundation (WPF) 返回到宿主 WPF 独立应用程序。  
  
 外接程序返回作为 WPF 用户控件的 UI。 用户控件的内容是单个按钮，单击时会显示消息框。 WPF 独立应用程序承载外接程序，并将外接程序返回的用户控件 (显示) 作为主应用程序窗口的内容。  
  
 **必备条件**  
  
 此示例突出显示了支持此方案的 .NET Framework 外接程序模型的 WPF 扩展，并假设以下内容：  
  
- .NET Framework 外接程序模型（包括管道、外接程序和主机开发）的知识。 如果不熟悉这些概念，请参阅 [外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))。 有关演示管道、外接程序和主机应用程序实现的教程，请参阅 [演练：创建可扩展的应用程序](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))。  
  
- 了解 .NET Framework 外接程序模型的 WPF 扩展，可在以下位置找到： [wpf Add-Ins 概述](wpf-add-ins-overview.md)。  
  
## <a name="example"></a>示例  

 若要创建返回 WPF UI 的外接程序，需要每个管道段、外接程序和宿主应用程序的特定代码。  

<a name="Contract"></a>

## <a name="implementing-the-contract-pipeline-segment"></a>实现协定管道段  

 方法必须由协定定义以返回 UI，并且其返回值的类型必须为 <xref:System.AddIn.Contract.INativeHandleContract> 。 `GetAddInUI`下面的代码中的协定方法对此进行了演示 `IWPFAddInContract` 。  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>

## <a name="implementing-the-add-in-view-pipeline-segment"></a>实现外接程序视图管道段  

 由于外接程序实现它作为的子类提供的 Ui <xref:System.Windows.FrameworkElement> ，因此关联到的外接程序视图上的方法 `IWPFAddInView.GetAddInUI` 必须返回类型为的值 <xref:System.Windows.FrameworkElement> 。 以下代码显示作为接口实现的协定的外接程序视图。  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>

## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>实现外接程序端适配器管道段  

 协定方法返回 <xref:System.AddIn.Contract.INativeHandleContract> ，但外接程序按 <xref:System.Windows.FrameworkElement> 外接程序视图) 指定的方式返回 (。 因此， <xref:System.Windows.FrameworkElement> 必须在 <xref:System.AddIn.Contract.INativeHandleContract> 越过隔离边界之前转换为。 此工作由外接程序端适配器通过调用执行 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> ，如以下代码所示。  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>

## <a name="implementing-the-host-view-pipeline-segment"></a>实现主机视图管道段  

 由于宿主应用程序将显示，因此与 <xref:System.Windows.FrameworkElement> 关联的宿主视图上的方法 `IWPFAddInHostView.GetAddInUI` 必须返回类型的值 <xref:System.Windows.FrameworkElement> 。 以下代码显示作为接口实现的协定的主机视图。  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>

## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>实现主机端适配器管道段  

 协定方法返回 <xref:System.AddIn.Contract.INativeHandleContract> ，但宿主应用程序需要 <xref:System.Windows.FrameworkElement> (由主机视图) 指定。 因此， <xref:System.AddIn.Contract.INativeHandleContract> 必须在 <xref:System.Windows.FrameworkElement> 跨越隔离边界之后将转换为。 此工作由主机端适配器通过调用执行 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> ，如以下代码所示。  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>

## <a name="implementing-the-add-in"></a>实现外接程序  

 创建外接程序端适配器和外接程序视图后，外接程序 (`WPFAddIn1.AddIn`) 必须实现 `IWPFAddInView.GetAddInUI` 方法才能返回 <xref:System.Windows.FrameworkElement> (<xref:System.Windows.Controls.UserControl> 此示例) 中的对象。 <xref:System.Windows.Controls.UserControl>下面的代码显示了的实现 `AddInUI` 。  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 `IWPFAddInView.GetAddInUI`外接程序的实现只需返回的新实例 `AddInUI` ，如以下代码所示。  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>

## <a name="implementing-the-host-application"></a>实现主机应用程序  

 创建主机端适配器和主机视图后，宿主应用程序可以使用 .NET Framework 外接程序模型打开管道，获取外接程序的宿主视图，并调用 `IWPFAddInHostView.GetAddInUI` 方法。 这些步骤在以下代码中显示。  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>另请参阅

- [外接程序和扩展性](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [WPF 外接程序概述](wpf-add-ins-overview.md)
