---
title: 截获触笔输入
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
ms.openlocfilehash: f05a3c25a61e90ec91cd1db725ba9a40763f0a7f
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970470"
---
# <a name="intercepting-input-from-the-stylus"></a>截获触笔输入

该 <xref:System.Windows.Input.StylusPlugIns> 体系结构提供了一种机制，用于实现对 <xref:System.Windows.Input.Stylus> 输入和数字墨迹对象创建的低级别控制 <xref:System.Windows.Ink.Stroke> 。 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>类提供一种机制，用于实现自定义行为，并将其应用于来自触笔设备的数据流，以获得最佳性能。  
  
 本主题包含以下小节：  
  
- [体系结构](#Architecture)  
  
- [实现触笔插件](#ImplementingStylusPlugins)  
  
- [将插件添加到 InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
- [结束语](#Conclusion)  
  
<a name="Architecture"></a>

## <a name="architecture"></a>体系结构  

 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>是[StylusInput](/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) api 的发展，如[访问和操作笔输入](/previous-versions/ms818317(v%3dmsdn.10))中所述。  
  
 每个 <xref:System.Windows.UIElement> 都有一个的 <xref:System.Windows.UIElement.StylusPlugIns%2A> 属性 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 。 可以向 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 元素的属性添加， <xref:System.Windows.UIElement.StylusPlugIns%2A> 以便在生成数据时对数据进行操作 <xref:System.Windows.Input.StylusPoint> 。 <xref:System.Windows.Input.StylusPoint> 数据包含系统数字化器支持的所有属性，包括 <xref:System.Windows.Input.StylusPoint.X%2A> 和 <xref:System.Windows.Input.StylusPoint.Y%2A> 点数据以及 <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> 数据。  
  
 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.Input.Stylus> 当你将添加到属性中时，你的对象将直接插入来自设备的数据流 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.UIElement.StylusPlugIns%2A> 。 插件添加到集合中的顺序 <xref:System.Windows.UIElement.StylusPlugIns%2A> 指示它们将接收数据的顺序 <xref:System.Windows.Input.StylusPoint> 。 例如，如果添加一个筛选器插件，该插件将输入限制为特定区域，然后添加一个可在写入时识别手势的插件，则识别手势的插件将接收筛选的 <xref:System.Windows.Input.StylusPoint> 数据。  
  
<a name="ImplementingStylusPlugins"></a>

## <a name="implementing-stylus-plug-ins"></a>实现触笔插件  

 若要实现某个插件，请从派生一个类 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 。 此类应用于从传入的数据流的输出 <xref:System.Windows.Input.Stylus> 。 在此类中，您可以修改数据的值 <xref:System.Windows.Input.StylusPoint> 。  
  
> [!CAUTION]
> 如果 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 引发或导致异常，应用程序将关闭。 你应全面测试使用的控件， <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 并且仅当你确定 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 不会引发异常时，才使用控件。  
  
 下面的示例演示一个插件，该插件通过修改数据中来自设备的和值来限制触笔输入 <xref:System.Windows.Input.StylusPoint.X%2A> <xref:System.Windows.Input.StylusPoint.Y%2A> <xref:System.Windows.Input.StylusPoint> <xref:System.Windows.Input.Stylus> 。  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>

## <a name="adding-your-plug-in-to-an-inkcanvas"></a>将插件添加到 InkCanvas  

 使用自定义插件的最简单方法是实现从 InkCanvas 派生的类并将其添加到 <xref:System.Windows.UIElement.StylusPlugIns%2A> 属性。  
  
 下面的示例演示 <xref:System.Windows.Controls.InkCanvas> 用于筛选墨迹的自定义。  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 如果你将添加 `FilterInkCanvas` 到应用程序并运行它，你会注意到，在用户完成笔划之前，不会将墨迹限制在某个区域。 这是因为 <xref:System.Windows.Controls.InkCanvas> 具有一个 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 属性，该属性是 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> ，并且已经是集合的成员 <xref:System.Windows.UIElement.StylusPlugIns%2A> 。 添加到集合中的自定义接收 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> <xref:System.Windows.UIElement.StylusPlugIns%2A> <xref:System.Windows.Input.StylusPoint> 数据后接收数据 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 。 因此，在 <xref:System.Windows.Input.StylusPoint> 用户将笔提起到结束笔划之前，将不会对数据进行筛选。 若要在用户绘制墨迹时筛选墨迹，必须在之前插入 `FilterPlugin` <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 。  
  
 下面的 c # 代码演示了一个自定义，它在 <xref:System.Windows.Controls.InkCanvas> 绘制时筛选墨迹。  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>

## <a name="conclusion"></a>结束语  

 通过派生你自己的 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 类并将它们插入到 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 集合中，你可以极大地增强数字墨迹的行为。 您可以在生成数据时对其进行访问 <xref:System.Windows.Input.StylusPoint> ，从而为您提供自定义输入的机会 <xref:System.Windows.Input.Stylus> 。 由于你对数据具有这样的低级别访问权限 <xref:System.Windows.Input.StylusPoint> ，因此你可以实现墨迹收集并使用应用程序的最佳性能进行呈现。  
  
## <a name="see-also"></a>请参阅

- [高级墨迹处理](advanced-ink-handling.md)
- [访问和操作笔输入](/previous-versions/ms818317(v%3dmsdn.10))
