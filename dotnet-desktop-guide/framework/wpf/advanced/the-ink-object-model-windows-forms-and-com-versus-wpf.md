---
title: 数字墨迹 Windows 窗体和 COM 与 WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling ink [WPF]
- InkCanvas control [WPF]
- ink object model [WPF]
- tablet pen [WPF], events [WPF]
- ink [WPF], enabling
- events [WPF], tablet pen
ms.assetid: 577835be-b145-4226-8570-1d309e9b3901
ms.openlocfilehash: 81b3f59c33ad2078235af9d790076dfd783da983
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664707"
---
# <a name="the-ink-object-model-windows-forms-and-com-versus-wpf"></a>墨迹对象模型：Windows 窗体和 COM 与 WPF

本质上有三个支持数字墨迹的平台： Tablet PC Windows 窗体平台、Tablet PC COM 平台和 Windows Presentation Foundation (WPF) 平台。  Windows 窗体和 COM 平台共享类似的对象模型，但 WPF 平台的对象模型差别很大。  本主题讨论了较高级别的差异，使使用一个对象模型的开发人员可以更好地理解其他对象模型。  
  
## <a name="enabling-ink-in-an-application"></a>在应用程序中启用墨迹  

 所有三个平台都提供了对象和控件，使应用程序能够从 tablet 笔接收输入。  Windows 窗体和 COM 平台附带了[InkPicture](/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90))、 [InkEdit](/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90))、InkCollector 类和[类，它们](/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90))与[](/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))类一起提供。  [InkPicture](/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) 和 [InkEdit](/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90)) 是可向应用程序添加以收集墨迹的控件。  可以将[InkCollector 和 microsoft](/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))附加到现有窗口，[使其能够](/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90))通过墨迹启用窗口和自定义控件。  
  
 WPF 平台包含 <xref:System.Windows.Controls.InkCanvas> 控件。  你可以将添加 <xref:System.Windows.Controls.InkCanvas> 到应用程序并立即开始收集墨迹。 对于 <xref:System.Windows.Controls.InkCanvas> ，用户可以复制、选择和调整墨迹大小。  您可以向中添加其他控件 <xref:System.Windows.Controls.InkCanvas> ，用户也可以在这些控件上手写。  可以通过将添加到启用了墨的自定义控件 <xref:System.Windows.Controls.InkPresenter> 并收集其触笔点来创建该控件。  
  
 下表列出了在其中了解有关在应用程序中启用墨迹的详细信息：  
  
|要实现的目的…|在 WPF 平台上 .。。|在 Windows 窗体/COM 平台上 .。。|  
|-----------------|--------------------------|------------------------------------------|  
|向应用程序添加支持墨迹的控件|请参阅 [墨迹入门](getting-started-with-ink.md)。|请参阅 [自动声明表单示例](/windows/desktop/tablet/auto-claims-form-sample)|  
|启用自定义控件上的墨迹|请参阅 [创建墨迹输入控件](creating-an-ink-input-control.md)。|请参阅 [墨迹剪贴板示例](/windows/desktop/tablet/ink-clipboard-sample)。|  
  
## <a name="ink-data"></a>墨迹数据  

 在 Windows 窗体和 COM 平台、 [InkCollector](/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))、InkEdit 和 InkPicture[上，每](/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90))个都公开了一个[](/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90))对象的[](/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90))[对象的对象](/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90))的对象。 [Microsoft ink](/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90))对象包含一个或多个[microsoft ink](/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90))对象的数据，并公开用于管理和操作这些笔划的常用方法和属性。  [Microsoft ink](/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90))对象管理其包含的笔画的生存期;[Microsoft ink](/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90))对象创建并删除它所拥有的笔划。  每个[Microsoft ink](/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90))都具有唯一的标识符，该标识符在[其父](/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90))  
  
 在 WPF 平台上， <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> 类拥有和管理其自己的生存期。 <xref:System.Windows.Ink.Stroke>可以在中同时收集一组对象 <xref:System.Windows.Ink.StrokeCollection> ，这为常见的墨迹数据管理操作（例如命中测试、擦除、转换和序列化墨迹）提供了方法。 <xref:System.Windows.Ink.Stroke>在任何给定时间，都可以属于零个、一个或多个 <xref:System.Windows.Ink.StrokeCollection> 对象。  和包含一个，而不是使用一个[Microsoft ink](/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90))对象 <xref:System.Windows.Controls.InkCanvas> 。 <xref:System.Windows.Controls.InkPresenter> <xref:System.Windows.Ink.StrokeCollection?displayProperty=nameWithType>  
  
 下面对墨迹数据对象模型进行了比较。  在 Windows 窗体和 COM 平台上， [Microsoft ink](/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) 对象限制了 [microsoft ink](/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) 对象的生存期，并且触笔数据包属于各个笔画。  两个或两个以上的笔画可以引用同一个 [DrawingAttributes](/previous-versions/dotnet/netframework-3.5/ms583636(v=vs.90)) 对象，如下图所示。  
  
 ![用于 COM&#47;Winforms 的墨迹对象模型的关系图。](./media/ink-inkownsstrokes.png "Ink_InkOwnsStrokes")  
  
 在上 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，每个 <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> 都是一个公共语言运行时对象，只要有对它的引用，就存在该对象。  每个 <xref:System.Windows.Ink.Stroke> 引用一个 <xref:System.Windows.Input.StylusPointCollection> 和 <xref:System.Windows.Ink.DrawingAttributes?displayProperty=nameWithType> 对象，它们也是公共语言运行时对象。  
  
 ![WPF 墨迹对象模型示意图。](./media/ink-wpfinkobjectmodel.png "Ink_WPFInkObjectModel")  
  
 下表比较了如何在 WPF 平台和 Windows 窗体和 COM 平台上完成一些常见任务。  
  
|任务|Windows Presentation Foundation|Windows 窗体和 COM|  
|----------|-------------------------------------|---------------------------|  
|保存墨迹|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|[Microsoft Ink. 保存](/previous-versions/dotnet/netframework-3.5/ms571335(v=vs.90))|  
|加载墨迹|<xref:System.Windows.Ink.StrokeCollection>使用 <xref:System.Windows.Ink.StrokeCollection.%23ctor%2A> 构造函数创建。|[Microsoft Ink. 加载](/previous-versions/dotnet/netframework-3.5/ms569609(v=vs.90))|  
|命中测试|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|[System.windows.media.visualtreehelper.hittest。](/previous-versions/dotnet/netframework-3.5/ms571330(v=vs.90))|  
|复制墨迹|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|[ClipboardCopy。](/previous-versions/dotnet/netframework-3.5/ms571316(v=vs.90))|  
|粘贴墨迹|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|[ClipboardPaste。](/previous-versions/dotnet/netframework-3.5/ms571318(v=vs.90))|  
|访问笔划集合上的自定义属性|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> (属性在内部存储并通过 <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> 、和访问 <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A> <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>) |请使用 [ExtendedProperties](/previous-versions/dotnet/netframework-3.5/ms582214(v=vs.90))|  
  
### <a name="sharing-ink-between-platforms"></a>在平台之间共享墨迹  

 虽然这些平台为墨迹数据提供不同的对象模型，但在平台之间共享数据非常简单。 下面的示例从 Windows 窗体应用程序保存墨迹，并将墨迹加载到 Windows Presentation Foundation 应用程序中。  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 下面的示例从 Windows Presentation Foundation 应用程序保存墨迹，并将墨迹加载到 Windows 窗体应用程序中。  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]

## <a name="events-from-the-tablet-pen"></a>来自 Tablet 笔的事件  

 Windows 窗体和 COM 平台上的[InkCollector](/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))和[InkPicture](/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90))将在用户输入笔数据时接收[事件，并](/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90))在这些平台上收到事件。 将[InkCollector](/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))附加到窗口或控件中，并且可以订阅由 tablet 输入数据引发的事件，从而进行[订阅。](/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) 发生这些事件的线程取决于事件是使用笔、鼠标还是以编程方式引发。 有关线程处理与这些事件相关的详细信息，请参阅 [常规线程注意事项](/windows/desktop/tablet/general-threading-considerations) 和 [可以触发事件的线程](/windows/desktop/tablet/threads-on-which-an-event-can-fire)。  
  
 在 Windows Presentation Foundation 平台上， <xref:System.Windows.UIElement> 类具有用于笔输入的事件。 这意味着每个控件都公开一组完整的触笔事件。  触笔事件具有隧道/冒泡事件对，并且始终在应用程序线程上发生。  有关详细信息，请参阅[路由事件概述](routed-events-overview.md)。  
  
 下图显示了引发触笔事件的类的对象模型。 Windows Presentation Foundation 对象模型仅显示冒泡事件，而不显示隧道事件对应项。  
  
 ![WPF 与 Winforms 中的触笔事件对比示意图。](./media/ink-stylusevents.png "Ink_StylusEvents")  
  
## <a name="pen-data"></a>笔数据  

 这三种平台为您提供了截获和处理来自 tablet 笔的数据的方法。  在 Windows 窗体和 COM 平台上，这是通过以下方式实现的：创建 [StylusInput](/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90))，将窗口或控件附加到它，并创建实现 [StylusInput](/previous-versions/dotnet/netframework-3.5/ms575201(v=vs.90)) 或 [StylusInput](/previous-versions/dotnet/netframework-3.5/ms575194(v=vs.90)) 接口的类。 然后，将自定义插件添加到 [StylusInput](/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90))的插件集合。 有关此对象模型的详细信息，请参阅 [StylusInput api 的体系结构](/windows/desktop/tablet/architecture-of-the-stylusinput-apis)。  
  
 在 WPF 平台上， <xref:System.Windows.UIElement> 类公开插件的集合，在设计上类似于 [StylusInput](/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90))。  若要截获笔数据，请创建一个继承自的类， <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 并将该对象添加到 <xref:System.Windows.UIElement.StylusPlugIns%2A> 的集合中 <xref:System.Windows.UIElement> 。 有关此交互的详细信息，请参阅 [截获触笔输入](intercepting-input-from-the-stylus.md)。  
  
 在所有平台上，线程池通过触笔事件接收墨迹数据并将其发送到应用程序线程。  有关 COM 和 Windows 平台上的线程处理的详细信息，请参阅 [StylusInput api 的线程注意事项](/windows/desktop/tablet/threading-considerations-for-the-stylusinput-apis)。  有关 Windows Presentation 软件上的线程处理的详细信息，请参阅 [墨迹线程处理模型](the-ink-threading-model.md)。  
  
 下图比较了用于在笔线程池上接收笔数据的类的对象模型。  
  
 ![WPF 与 Winforms 中的 StylusPlugin 模型对比示意图。](./media/ink-stylusplugins.png "Ink_StylusPlugins")
