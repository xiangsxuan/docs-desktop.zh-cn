---
title: 如何：在 DHTML 代码和客户端应用程序代码之间实现双向通信
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.ObjectForScripting
- WebBrowser.Document
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- communications [Windows Forms], DHTML and client applications
- examples [Windows Forms], WebBrowser control
- WebBrowser control [Windows Forms], communication between DHTML and client application
- DHTML [Windows Forms], embedding in Windows Forms
ms.assetid: 55353a32-b09e-4479-a521-ff3a5ff9a708
ms.openlocfilehash: c047f8de55ad7b66a6bc417db1a2678dc87b59c1
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957261"
---
# <a name="how-to-implement-two-way-communication-between-dhtml-code-and-client-application-code"></a><span data-ttu-id="7ea7d-102">如何：在 DHTML 代码和客户端应用程序代码之间实现双向通信</span><span class="sxs-lookup"><span data-stu-id="7ea7d-102">How to: Implement Two-Way Communication Between DHTML Code and Client Application Code</span></span>

<span data-ttu-id="7ea7d-103">可使用 <xref:System.Windows.Forms.WebBrowser> 控件将现有的动态 HTML (DHTML) Web 应用程序代码添加到 Windows 窗体客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to add existing dynamic HTML (DHTML) Web application code to your Windows Forms client applications.</span></span> <span data-ttu-id="7ea7d-104">如果已投入大量的开发时间用于创建基于 DHTML 的控件，并且想要利用 Windows 窗体丰富的用户界面功能，而无需重写现有代码，这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-104">This is useful when you have invested significant development time in creating DHTML-based controls and you want to take advantage of the rich user interface capabilities of Windows Forms without having to rewrite existing code.</span></span>

<span data-ttu-id="7ea7d-105"><xref:System.Windows.Forms.WebBrowser> 控件使你通过 <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> 和 <xref:System.Windows.Forms.WebBrowser.Document%2A> 属性可以实现客户端应用程序代码和 Web 页的脚本代码间的双向通信。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-105">The <xref:System.Windows.Forms.WebBrowser> control lets you implement two-way communication between your client application code and your Web page scripting code through the <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> and <xref:System.Windows.Forms.WebBrowser.Document%2A> properties.</span></span> <span data-ttu-id="7ea7d-106">此外，还可以配置 <xref:System.Windows.Forms.WebBrowser> 控件，以便 Web 控件与应用程序窗体上的其他控件的无缝混合，从而隐藏其 DHTML 实现。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-106">Additionally, you can configure the <xref:System.Windows.Forms.WebBrowser> control so that your Web controls blend seamlessly with other controls on your application form, hiding their DHTML implementation.</span></span> <span data-ttu-id="7ea7d-107">若要无缝地混合控件，需格式化显示的页面，使其背景色和视觉样式可匹配窗体中的其余部分，并使用 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>、<xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A>和 <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> 属性禁用标准的浏览器功能。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-107">To seamlessly blend the controls, format the page displayed so that its background color and visual style match the rest of the form, and use the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>, <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A>, and <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> properties to disable standard browser features.</span></span>

## <a name="to-embed-dhtml-in-your-windows-forms-application"></a><span data-ttu-id="7ea7d-108">若要在 Windows 窗体应用程序中嵌入 DHTML</span><span class="sxs-lookup"><span data-stu-id="7ea7d-108">To embed DHTML in your Windows Forms application</span></span>

1. <span data-ttu-id="7ea7d-109">需将 <xref:System.Windows.Forms.WebBrowser> 控件的 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> 属性设置为 `false`，以防止 <xref:System.Windows.Forms.WebBrowser> 控件打开放到其上的文件。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-109">Set the <xref:System.Windows.Forms.WebBrowser> control's <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#1)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#1)]

2. <span data-ttu-id="7ea7d-110">将控件的 <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> 属性设置为 `false`，以防止 <xref:System.Windows.Forms.WebBrowser> 控件在用户进行右键单击时，显示其快捷方式菜单。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-110">Set the control's <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from displaying its shortcut menu when the user right-clicks it.</span></span>

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#2)]

3. <span data-ttu-id="7ea7d-111">将控件的 <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> 属性设置为 `false`，以防止 <xref:System.Windows.Forms.WebBrowser> 控件响应快捷键。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-111">Set the control's <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from responding to shortcut keys.</span></span>

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#3)]

4. <span data-ttu-id="7ea7d-112"><xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>在窗体的构造函数中设置属性，或重写 <xref:System.Windows.Forms.Form.OnLoad%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-112">Set the <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> property in the form's constructor or override the <xref:System.Windows.Forms.Form.OnLoad%2A> method.</span></span>

     <span data-ttu-id="7ea7d-113">以下代码将窗体类自身用于脚本对象。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-113">The following code uses the form class itself for the scripting object.</span></span>

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#4)]

5. <span data-ttu-id="7ea7d-114">实现脚本对象。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-114">Implement your scripting object.</span></span>

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#5)]

6. <span data-ttu-id="7ea7d-115">在脚本代码中使用 `window.external` 对象来访问指定对象的公共属性和方法。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-115">Use the `window.external` object in your scripting code to access public properties and methods of the specified object.</span></span>

     <span data-ttu-id="7ea7d-116">以下 HTML 代码演示如何通过单击按钮对脚本对象调用方法。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-116">The following HTML code demonstrates how to call a method on the scripting object from a button click.</span></span> <span data-ttu-id="7ea7d-117">将此代码复制到 HTML 文档的 BODY 元素中，该文档为使用控件的 <xref:System.Windows.Forms.WebBrowser.Navigate%2A> 方法所加载的文档，或将其分配到控件的 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 属性的文档。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-117">Copy this code into the BODY element of an HTML document that you load using the control's <xref:System.Windows.Forms.WebBrowser.Navigate%2A> method or that you assign to the control's <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property.</span></span>

    ```html
    <button onclick="window.external.Test('called from script code')">
        call client code from script code
    </button>
    ```

7. <span data-ttu-id="7ea7d-118">实现应用程序代码将使用的脚本代码中的函数。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-118">Implement functions in your script code that your application code will use.</span></span>

     <span data-ttu-id="7ea7d-119">以下 HTML SCRIPT 元素提供了示例函数。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-119">The following HTML SCRIPT element provides an example function.</span></span> <span data-ttu-id="7ea7d-120">将此代码复制到 HTML 文档的 HEAD 元素中，该文档为使用控件的 <xref:System.Windows.Forms.WebBrowser.Navigate%2A> 方法所加载的文档，或将其分配到控件的 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 属性的文档。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-120">Copy this code into the HEAD element of an HTML document that you load using the control's <xref:System.Windows.Forms.WebBrowser.Navigate%2A> method or that you assign to the control's <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property.</span></span>

    ```html
    <script>
    function test(message) {
        alert(message);
    }
    </script>
    ```

8. <span data-ttu-id="7ea7d-121">使用 <xref:System.Windows.Forms.WebBrowser.Document%2A> 属性访问客户端应用程序代码中的脚本代码。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-121">Use the <xref:System.Windows.Forms.WebBrowser.Document%2A> property to access the script code from your client application code.</span></span>

     <span data-ttu-id="7ea7d-122">例如，将以下代码添加到按钮 <xref:System.Windows.Forms.Control.Click> 事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-122">For example, add the following code to a button <xref:System.Windows.Forms.Control.Click> event handler.</span></span>

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#8)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#8)]

9. <span data-ttu-id="7ea7d-123">完成 DHTML 调试后，将控件的 <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A> 属性设置为 `true`，以防止 <xref:System.Windows.Forms.WebBrowser> 控件显示脚本代码问题的错误消息。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-123">When you are finished debugging your DHTML, set the control's <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A> property to `true` to prevent the <xref:System.Windows.Forms.WebBrowser> control from displaying error messages for script code problems.</span></span>

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#9)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#9)]

## <a name="example"></a><span data-ttu-id="7ea7d-124">示例</span><span class="sxs-lookup"><span data-stu-id="7ea7d-124">Example</span></span>

<span data-ttu-id="7ea7d-125">以下完整的代码示例将提供演示应用程序，以方便用于理解此功能。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-125">The following complete code example provides a demonstration application that you can use to understand this feature.</span></span> <span data-ttu-id="7ea7d-126">HTML 代码将通过 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 属性加载到 <xref:System.Windows.Forms.WebBrowser> 控件中，而不是从单独的 HTML 文件进行加载。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-126">The HTML code is loaded into the <xref:System.Windows.Forms.WebBrowser> control through the <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> property instead of being loaded from a separate HTML file.</span></span>

[!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="7ea7d-127">编译代码</span><span class="sxs-lookup"><span data-stu-id="7ea7d-127">Compiling the Code</span></span>

<span data-ttu-id="7ea7d-128">此代码需要：</span><span class="sxs-lookup"><span data-stu-id="7ea7d-128">This code requires:</span></span>

- <span data-ttu-id="7ea7d-129">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="7ea7d-129">References to the System and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ea7d-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ea7d-130">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.Document%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7ea7d-131">WebBrowser 控件</span><span class="sxs-lookup"><span data-stu-id="7ea7d-131">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
