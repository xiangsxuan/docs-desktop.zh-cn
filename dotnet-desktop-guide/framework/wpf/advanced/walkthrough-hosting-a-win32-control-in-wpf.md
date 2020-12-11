---
title: 在 WPF 中承载 Win32 控件
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: 257e75522e598ce3eeb005290dcd0cd7d4910706
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973323"
---
# <a name="walkthrough-host-a-win32-control-in-wpf"></a>演练：在 WPF 中承载 Win32 控件
Windows Presentation Foundation (WPF) 提供了一个用于创建应用程序的丰富环境。 但是，当你在 Win32 代码中有大量投资时，在 WPF 应用程序中重复使用至少一些代码，而不是完全重新编写它，这可能更有效。 WPF 提供了一种用于在 WPF 页上承载 Win32 窗口的简单机制。  
  
 本主题将指导你完成承载 Win32 列表框控件的应用程序，该应用程序 [在 WPF 示例中承载 Win32 ListBox 控件](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)。 可以扩展此常规过程以承载任何 Win32 窗口。  

<a name="requirements"></a>
## <a name="requirements"></a>要求  
 本主题假定基本熟悉 WPF 和 Windows API 编程。 有关 WPF 编程的基本简介，请参阅 [入门](../getting-started/index.md)。 有关 Windows API 编程的简介，请参阅主题中的任意一本书，该主题 *中的 Charles* Petzold。  
  
 由于本主题附带的示例是在 c # 中实现的，因此它使用平台调用服务 (PInvoke) 来访问 Windows API。 某些对 PInvoke 的熟悉非常有用，但并不重要。  
  
> [!NOTE]
> 本主题包括来自相关示例的一些代码示例。 但是，出于可读性考虑，不包括完整的示例代码。 你可以从 [在 WPF 示例中承载 Win32 ListBox 控件](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)获取或查看完整的代码。  
  
<a name="basic_procedure"></a>
## <a name="the-basic-procedure"></a>基本过程  
 本部分概述了在 WPF 页上承载 Win32 窗口的基本过程。 其余各节介绍了每个步骤的详细内容。  
  
 基本的承载步骤如下：  
  
1. 实现 WPF 页以承载窗口。 一种方法是创建一个 <xref:System.Windows.Controls.Border> 元素，以便为所承载的窗口保留部分页面。  
  
2. 实现一个类以承载从继承的控件 <xref:System.Windows.Interop.HwndHost> 。  
  
3. 在该类中，重写 <xref:System.Windows.Interop.HwndHost> 类成员 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> 。  
  
4. 将所承载的窗口创建为包含 WPF 页的窗口的子级。 尽管传统的 WPF 编程不需要显式使用它，但宿主页是一个窗口，其中包含一个句柄 (HWND) 。 通过方法的参数接收页 HWND `hwndParent` <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> 。 应将所承载的窗口创建为此 HWND 的子窗口。  
  
5. 在创建宿主窗口之后，返回所承载的窗口的 HWND。 如果要承载一个或多个 Win32 控件，通常需要将宿主窗口创建为 HWND 的子级，并使控件成为该宿主窗口的子级。 在宿主窗口中包装控件提供了一种简单的方法，使您的 WPF 页可以从控件接收通知，这些控件处理跨 HWND 边界的通知的某些特定 Win32 问题。  
  
6. 处理发送到宿主窗口的选定消息，例如，来自子控件的通知。 可通过两种方式来执行此操作。  
  
    - 如果更喜欢处理宿主类中的消息，请重写 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 类的方法 <xref:System.Windows.Interop.HwndHost> 。  
  
    - 如果想让 WPF 处理消息，请 <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost.MessageHook> 在代码隐藏中处理类事件。 对于所承载的窗口收到的每条消息，都将发生此事件。 如果选择此选项，则仍必须重写 <xref:System.Windows.Interop.HwndHost.WndProc%2A> ，但只需要最小实现。  
  
7. 重写的 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 和 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 方法 <xref:System.Windows.Interop.HwndHost> 。 你必须重写这些方法以满足 <xref:System.Windows.Interop.HwndHost> 协定，但你可能只需要提供最小实现。  
  
8. 在代码隐藏文件中，创建控件宿主类的实例，并使其成为 <xref:System.Windows.Controls.Border> 用于承载窗口的元素的子元素。  
  
9. 通过从其子窗口发送 Microsoft Windows 消息并处理消息（例如，由控件发送的通知），与承载的窗口通信。  
  
<a name="page_layout"></a>
## <a name="implement-the-page-layout"></a>实现页面布局  
 承载 ListBox 控件的 WPF 页的布局由两个区域组成。 页的左侧承载多个 WPF 控件，这些控件提供的可用于 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 操作 Win32 控件。 页面右上角具有一个正方形区域，用于放置所承载的 ListBox 控件。  
  
 用于实现此布局的代码非常简单。 根元素是 <xref:System.Windows.Controls.DockPanel> 具有两个子元素的。 第一个元素是 <xref:System.Windows.Controls.Border> 承载 ListBox 控件的元素。 它在该页的右上角占据了一个大小为 200x200 的正方形。 第二个 <xref:System.Windows.Controls.StackPanel> 元素是包含一组 WPF 控件的元素，这些控件显示信息，并允许您通过设置公开的互操作属性来操作 ListBox 控件。 对于作为的子级的每个元素 <xref:System.Windows.Controls.StackPanel> ，请参阅下面的示例代码中所用的各种元素的参考资料，这些元素将在下面的示例代码中列出，但不会在此处说明 (基本互操作模型不需要任何这些元素，它们用于向示例) 添加一些交互性。  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>实现类以承载 Microsoft Win32 控件  
 此示例的核心是实际承载控件的类，即 ControlHost.cs。 它继承自 <xref:System.Windows.Interop.HwndHost>。 构造函数采用两个参数： height 和 width，它们对应于承载 ListBox 控件的元素的高度和宽度 <xref:System.Windows.Controls.Border> 。 稍后将使用这些值来确保控件的大小与 <xref:System.Windows.Controls.Border> 元素匹配。  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 还有一组常量。 大多数情况下，这些常量都是从 Winuser.h 中提取的，并允许在调用 Win32 函数时使用传统名称。  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>替代 BuildWindowCore 以创建 Microsoft Win32 窗口  
 重写此方法以创建将由页面承载的 Win32 窗口，并在窗口和页面之间建立连接。 由于此示例涉及承载 ListBox 控件，因此将创建两个窗口。 第一种是由 WPF 页实际承载的窗口。 ListBox 控件被创建为该窗口的子窗口。  
  
 采用此方法的原因是为了简化接收来自控件的通知的过程。 <xref:System.Windows.Interop.HwndHost>类允许处理发送到它所承载的窗口的消息。 如果直接托管 Win32 控件，则会收到发送到控件内部消息循环的消息。 你可以显示控件并向其发送消息，但不会收到该控件发送到其父窗口的通知。 这意味你没有办法检测用户何时与该控件进行交互，以及其他更多方面。 可改为创建一个宿主窗口，并使控件成为该窗口的子窗口。 这样，你便能够处理宿主窗口的消息，包括由该控件发送给它的通知。 由于宿主窗口只是控件的一个简单包装器而已，为了方便起见，以后将把该包称为 ListBox 控件。  
  
<a name="create_the_window_and_listbox"></a>
#### <a name="create-the-host-window-and-listbox-control"></a>创建宿主窗口和 ListBox 控件  
 可以通过创建和注册窗口类等，使用 PInvoke 为控件创建宿主窗口。 但是，更简单的一种方法是使用预定义的“静态”窗口类创建窗口。 这将为你提供所需窗口步骤，以接收来自控件的通知，但需要完成最少的编码工作。  
  
 控件的 HWND 通过一个只读属性公开，以便宿主页面可使用它向控件发送消息。  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 ListBox 控件被创建为宿主窗口的子窗口。 两个窗口的高度和宽度被设置为传递给构造函数的值（前面已讨论）。 这可确保宿主窗口和控件的大小与页面上的保留区域相同。  创建 windows 后，此示例将返回一个 <xref:System.Runtime.InteropServices.HandleRef> 对象，其中包含宿主窗口的 HWND。  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>
### <a name="implement-destroywindow-and-wndproc"></a>实现 DestroyWindow 和 WndProc  
 除了之外 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> ，还必须重写的 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 和 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 方法 <xref:System.Windows.Interop.HwndHost> 。 在此示例中，控件的消息由 <xref:System.Windows.Interop.HwndHost.MessageHook> 处理程序处理，因此和的实现 <xref:System.Windows.Interop.HwndHost.WndProc%2A> <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 是最少的。 对于 <xref:System.Windows.Interop.HwndHost.WndProc%2A> ，将设置 `handled` 为 `false` 以指示消息未处理并且返回0。 对于 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> ，只需销毁窗口。  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>
## <a name="host-the-control-on-the-page"></a>在页面上承载控件  
 若要在页面上承载控件，请首先创建类的新实例 `ControlHost` 。 `ControlHostElement`向构造函数传递包含控件 () 的边框元素的高度和宽度 `ControlHost` 。 这可确保 ListBox 具有正确的大小。 然后，通过将 `ControlHost` 对象分配给宿主的属性，在页面上承载控件 <xref:System.Windows.Controls.Decorator.Child%2A> <xref:System.Windows.Controls.Border> 。  
  
 该示例将一个处理程序附加到 <xref:System.Windows.Interop.HwndHost.MessageHook> 的事件， `ControlHost` 以接收来自控件的消息。 对于每条发送到宿主窗口的消息，都将引发此事件。 在这种情况下，这些消息是发送到包装实际 ListBox 控件的窗口的消息，其中包括来自控件的通知。 此示例将调用 SendMessage 以从控件获取信息并修改其内容。 下一节将详细介绍页面如何与控件通信。  
  
> [!NOTE]
> 请注意，SendMessage 有两个 PInvoke 声明。 这是必需的，因为一个使用 `wParam` 参数传递字符串，另一个参数用于传递整数。 对于每个签名，都需要一个单独的声明，以确保正确封送数据。  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>
## <a name="implement-communication-between-the-control-and-the-page"></a>在控件和页面之间的实现通信  
 通过向控件发送 Windows 消息来操作控件。 当用户与控件交互时，控件会通过向其宿主窗口发送通知来通知你。 [在 WPF 中承载 Win32 ListBox 控件](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)示例包含一个 UI，该 UI 提供了如何实现此操作的几个示例：  
  
- 向列表中追加项。  
  
- 从列表中删除选定项  
  
- 显示当前选定项的文本。  
  
- 显示列表中的项数。  
  
 用户还可以通过单击列表框中的项来选择该项，就像在传统的 Win32 应用程序中一样。 每当用户通过选择、添加或追加项来更改列表框的状态时，都将更新所显示的数据。  
  
 若要追加项，请发送列表框一[ `LB_ADDSTRING` 条消息](/windows/desktop/Controls/lb-addstring)。 若要删除项目，请发送 [`LB_GETCURSEL`](/windows/desktop/Controls/lb-getcursel) 以获取当前所选内容的索引，然后 [`LB_DELETESTRING`](/windows/desktop/Controls/lb-deletestring) 删除该项目。 该示例还发送 [`LB_GETCOUNT`](/windows/desktop/Controls/lb-getcount) ，并使用返回的值更新显示项数的显示内容。 这两个实例都 [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) 使用上一节中讨论的某个 PInvoke 声明。  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 当用户选择某一项或更改其选择时，该控件将通过向宿主窗口发送[ `WM_COMMAND` 消息](/windows/desktop/menurc/wm-command)来通知宿主窗口，这会引发 <xref:System.Windows.Interop.HwndHost.MessageHook> 该页的事件。 处理程序将接收到与宿主窗口的主窗口过程相同的信息。 它还传递对布尔值的引用 `handled` 。 您将设置 `handled` 为， `true` 以指示您已经处理了该消息，并且不需要进一步的处理。  
  
 [`WM_COMMAND`](/windows/desktop/menurc/wm-command) 出于多种原因而发送，因此您必须检查通知 ID 以确定它是否是您要处理的事件。 此 ID 包含在参数的高位字中 `wParam` 。 该示例使用按位运算符提取 ID。 如果用户已做出或更改了其选择，则 ID 将为 [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange) 。  
  
 [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange)接收到后，该示例通过向控件发送[ `LB_GETCURSEL` 消息](/windows/desktop/Controls/lb-getcursel)来获取选定项的索引。 若要获取文本，首先要创建一个 <xref:System.Text.StringBuilder> 。 然后向控件发送[ `LB_GETTEXT` 消息](/windows/desktop/Controls/lb-gettext)。 将空 <xref:System.Text.StringBuilder> 对象作为参数传递 `wParam` 。 当 [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) 返回时， <xref:System.Text.StringBuilder> 将包含选定项的文本。 的这种用法 [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) 还需要另一个 PInvoke 声明。  
  
 最后，将设置 `handled` 为 `true` 以指示消息已处理。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Interop.HwndHost>
- [WPF 和 Win32 互操作](wpf-and-win32-interoperation.md)
- [演练：我的第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
