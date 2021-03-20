---
title: 墨迹线程处理模型
ms.date: 03/30/2017
helpviewer_keywords:
- application user interface thread [WPF]
- stylus plug-in
- ink threading model [WPF]
- ink [WPF], rendering
- pen thread [WPF]
- threading model [WPF]
- rendering ink [WPF]
- dynamic rendering thread [WPF]
- ink collection plug-in
- plug-ins [WPF], for ink
ms.assetid: c85fcad1-cb50-4431-847c-ac4145a35c89
ms.openlocfilehash: 397013eba82ac2d1a3918456b9b492272dfa4272
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664771"
---
# <a name="the-ink-threading-model"></a>墨迹线程处理模型
在 Tablet PC 上，墨迹的优点之一就是，它很喜欢用常规笔和纸张书写。  为实现此目的，tablet 笔以比鼠标更高的速率收集输入数据，并在用户写入时呈现墨迹。  应用程序的用户界面 (UI) 线程不足以收集笔数据和呈现墨迹，因为它可能会被阻止。  若要解决此 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 情况，应用程序会在用户写入墨迹时使用另外两个线程。  
  
 下面的列表介绍了收集和呈现数字墨迹的线程：  
  
- "笔线程"-采用触笔输入的线程。   (事实上，这是一个线程池，但本主题将其称为笔线程。 )   
  
- 应用程序用户界面线程-控制应用程序的用户界面的线程。  
  
- 动态呈现线程-用户绘制笔划时呈现墨迹的线程。 动态呈现线程不同于呈现应用程序的其他 UI 元素的线程，如 Window Presentation Foundation [线程模型](threading-model.md)中所述。  
  
 无论应用程序使用的是 <xref:System.Windows.Controls.InkCanvas> 还是与 [创建墨迹输入控件](creating-an-ink-input-control.md)中的控件类似的自定义控件，墨迹模型都是相同的。  尽管本主题讨论了中的线程处理 <xref:System.Windows.Controls.InkCanvas> ，但在创建自定义控件时，相同的概念也同样适用。  
  
## <a name="threading-overview"></a>线程处理概述  
 下图演示了用户绘制笔画时的线程处理模型：  
  
 ![绘制笔画时的线程处理模型。](./media/inkthreading-drawingink.png "InkThreading_DrawingInk")  
  
1. 用户绘制笔划时发生的操作  
  
    1. 当用户绘制笔画时，触笔接触点将进入笔线程。  触笔插件（包括 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> ）接受触笔线程上的触笔接触点，并且有机会在接收它们之前修改它们 <xref:System.Windows.Controls.InkCanvas> 。  
  
    2. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>呈现动态呈现线程上的触笔接触点。 这与上一步相同。  
  
    3. <xref:System.Windows.Controls.InkCanvas>接收 UI 线程上的触笔接触点。  
  
2. 用户结束笔画后发生的操作  
  
    1. 当用户完成绘制笔划后，将 <xref:System.Windows.Controls.InkCanvas> 创建一个 <xref:System.Windows.Ink.Stroke> 对象，并将其添加到 <xref:System.Windows.Controls.InkPresenter> 中以静态方式呈现该对象。  
  
    2. UI 线程会发出通知， <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 指示笔划是以静态方式呈现的，因此删除了笔划的 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 视觉表示形式。  
  
## <a name="ink-collection-and-stylus-plug-ins"></a>墨迹收集和触笔插件  
 每个 <xref:System.Windows.UIElement> 都有一个 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 。  <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>接收和中的对象 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 可以修改笔线程上的触笔接触点。 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>对象根据其在中的顺序接收触笔接触点 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 。  
  
 下图说明了的 <xref:System.Windows.UIElement.StylusPlugIns%2A> 集合的集合 <xref:System.Windows.UIElement> ，其中包含 `stylusPlugin1` 、 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 和 `stylusPlugin2` 的假设情况。  
  
 ![触笔插件影响输出的顺序。](./media/inkthreading-pluginorder.png "InkThreading_PluginOrder")  
  
 在上图中，将发生以下行为：  
  
1. `StylusPlugin1` 修改 x 和 y 的值。  
  
2. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 接收经过修改的触笔接触点，并将其呈现在动态呈现线程上。  
  
3. `StylusPlugin2` 接收经过修改的触笔接触点，并进一步修改 x 和 y 的值。  
  
4. 应用程序收集触笔接触点，当用户完成笔划时，静态呈现笔画。  
  
 假设 `stylusPlugin1` 将触笔指向矩形，并将 `stylusPlugin2` 触笔点向右平移。  在前面的方案中， <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 会接收受限制的触笔接触点，但不接收已平移的触笔接触点。  当用户绘制笔划时，笔划将呈现在矩形的边界内，但在用户将笔提起之前，笔划不会转换。  
  
### <a name="performing-operations-with-a-stylus-plug-in-on-the-ui-thread"></a>在 UI 线程上使用触笔插件执行操作  
 由于无法对笔线程执行准确的命中测试，某些元素可能偶尔接收到用于其他元素的触笔输入。 如果在执行操作之前需要确保正确路由输入，请在 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A> 、或方法中订阅并执行该操作 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A> <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A> 。 执行准确的命中测试后，应用程序线程会调用这些方法。 若要订阅这些方法，请 <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> 在笔线程上出现的方法中调用方法。  
  
 下图演示了与的触笔事件相关的笔线程和 UI 线程之间的关系 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 。  
  
 ![&#40;UI 和笔&#41;的墨迹线程模型 ](./media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")  
  
## <a name="rendering-ink"></a>呈现墨迹  
 当用户绘制笔画时，将 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 在单独的线程上呈现墨迹，以便即使在 UI 线程繁忙的情况下，墨迹仍会显示为 "流"。  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>当收集触笔接触点时，会在动态呈现线程上生成一个可视化树。  当用户完成笔划时，将在 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 应用程序执行下一次呈现时通知请求。  在应用程序完成下一次呈现过程后，将 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 清理其可视化树。  下图演示了此过程。  
  
 ![墨迹线程处理示意图](./media/inkthreading-visualtree.png "InkThreading_VisualTree")  
  
1. 用户开始描边。  
  
    1. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>创建可视化树。  
  
2. 用户正在绘制笔划。  
  
    1. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>生成可视化树。  
  
3. 用户结束笔画。  
  
    1. 将 <xref:System.Windows.Controls.InkPresenter> 笔画添加到其可视化树中。  
  
    2. 媒体集成层 (MIL) 静态呈现笔画。  
  
    3. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>清除视觉对象。
