---
title: 在 Win32 和 WPF 之间共享消息循环
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
ms.openlocfilehash: 029cab8971ae1a57afacb9123ce83fa182d7b083
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664920"
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>在 Win32 和 WPF 之间共享消息循环
本主题介绍如何通过 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 使用中的现有消息循环公开 <xref:System.Windows.Threading.Dispatcher> 或通过在互操作代码的 Win32 端创建单独的消息循环来实现与互操作的消息循环。  
  
## <a name="componentdispatcher-and-the-message-loop"></a>ComponentDispatcher 和消息循环  
 互操作性和键盘事件支持的普通方案是实现 <xref:System.Windows.Interop.IKeyboardInputSink> ，或从已实现的类（ <xref:System.Windows.Interop.IKeyboardInputSink> 如或）中对子类进行子类化 <xref:System.Windows.Interop.HwndSource> <xref:System.Windows.Interop.HwndHost> 。 但是，键盘接收器支持并不能解决通过互操作边界发送和接收消息时可能会遇到的所有可能的消息循环需求。 为了帮助实现应用程序消息循环体系结构的形式， [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 提供了 <xref:System.Windows.Interop.ComponentDispatcher> 类，该类定义用于消息循环的简单协议。  
  
 <xref:System.Windows.Interop.ComponentDispatcher> 是公开多个成员的静态类。 每个方法的范围都隐式绑定到调用线程。 消息循环必须在关键时间调用其中的某些 Api (如下一节) 所定义。  
  
 <xref:System.Windows.Interop.ComponentDispatcher> 提供其他组件 (如) 可以侦听的其他组件的事件。 <xref:System.Windows.Threading.Dispatcher>类以适当的顺序调用所有适当的 <xref:System.Windows.Interop.ComponentDispatcher> 方法。 如果要实现自己的消息循环，你的代码将负责 <xref:System.Windows.Interop.ComponentDispatcher> 以类似方式调用方法。  
  
 <xref:System.Windows.Interop.ComponentDispatcher>对线程调用方法只会调用在该线程上注册的事件处理程序。  
  
## <a name="writing-message-loops"></a>写入消息循环  
 下面是你 <xref:System.Windows.Interop.ComponentDispatcher> 编写自己的消息循环时将使用的成员的清单：  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>：消息循环应调用此来指示线程是模式的。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>：消息循环应调用此来指示线程已恢复到变成。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>：消息循环应调用此来指示 <xref:System.Windows.Interop.ComponentDispatcher> 应引发 <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> 事件。 <xref:System.Windows.Interop.ComponentDispatcher> 如果为，则不会引发 <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> `true` ，但消息循环可能会选择调用， <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> 即使 <xref:System.Windows.Interop.ComponentDispatcher> 在处于模式状态时无法对其作出响应。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>：消息循环应调用此来指示新消息可用。 返回值指示事件侦听器是否 <xref:System.Windows.Interop.ComponentDispatcher> 处理了该消息。 如果 <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> `true`)  (处理返回，则调度程序不应对消息进行任何进一步的处理。 如果返回值为 `false` ，则调度程序应调用 Win32 函数 `TranslateMessage` ，然后调用 `DispatchMessage` 。  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>使用 ComponentDispatcher 和现有消息处理  
 下面是 <xref:System.Windows.Interop.ComponentDispatcher> 依赖于固有消息循环时要使用的成员清单 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>：返回应用程序是否已进入模式 (例如，已将模式消息循环推送) 。 <xref:System.Windows.Interop.ComponentDispatcher> 可以跟踪此状态，因为类维护 <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> 消息循环的计数和 <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> 调用。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> 和 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> 事件遵循委托调用的标准规则。 委托按未指定的顺序进行调用，即使第一个委托将消息标记为已处理，也会调用所有委托。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>：指示执行空闲处理的适当且有效的时间 () 没有其他线程的挂起消息。 <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> 如果线程是模式的，则不会引发。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>：为消息泵处理的所有消息引发。  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>：为在期间未处理的所有消息引发 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> 。  
  
 如果在 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> 事件或 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> 事件之后， `handled` 按事件数据中的引用传递的参数为，则将消息视为已处理 `true` 。 如果为，事件处理程序应忽略该消息 `handled` `true` ，因为这意味着不同处理程序首先处理该消息。 这两个事件的事件处理程序可能会修改消息。 调度程序应调度已修改的消息，而不是原始的未更改消息。 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> 传递给所有侦听器，但体系结构目的在于，只有包含目标的 HWND 的顶级窗口才能调用代码来响应消息。  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>HwndSource 如何处理 ComponentDispatcher 事件  
 如果 <xref:System.Windows.Interop.HwndSource> 是顶级窗口 (没有父 HWND) ，则它将注册到 <xref:System.Windows.Interop.ComponentDispatcher> 。 如果 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> 引发，并且消息是针对 <xref:System.Windows.Interop.HwndSource> 或子窗口的，则 <xref:System.Windows.Interop.HwndSource> 调用其 <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A> 、 <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> 和 <xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A> 键盘接收器序列。  
  
 如果不是 <xref:System.Windows.Interop.HwndSource> (具有父 HWND) 的顶级窗口，则将不会进行任何处理。 仅顶级窗口应进行处理，并且在任何互操作方案中，都应有一个包含键盘接收器支持的顶级窗口。  
  
 如果 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 在 <xref:System.Windows.Interop.HwndSource> 调用时未首先调用适当的键盘接收器方法，应用程序将接收更高级别的键盘事件，例如 <xref:System.Windows.UIElement.KeyDown> 。 但是，将不会调用键盘接收器方法，这会绕过所需的键盘输入模型功能，如访问密钥支持。 出现这种情况的原因可能是消息循环未正确地通知上的相关线程 <xref:System.Windows.Interop.ComponentDispatcher> ，或父 HWND 未调用正确的键盘接收器响应。  
  
 如果使用方法为消息添加了挂钩，则发送到键盘接收器的消息可能不会发送到 HWND <xref:System.Windows.Interop.HwndSource.AddHook%2A> 。 消息可能已在消息泵级别直接处理，未提交给 `DispatchMessage` 函数。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Interop.ComponentDispatcher>
- <xref:System.Windows.Interop.IKeyboardInputSink>
- [WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)
- [线程模型](threading-model.md)
- [输入概述](input-overview.md)
