---
title: 如何：在托管 HTML 文档对象模型中访问 HTML 源
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM
- HTML [Windows Forms], accessing in Windows Forms
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
ms.openlocfilehash: 2db3e5a16268d71d972a84d65b3f0aa37771923c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971518"
---
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a>如何：在托管 HTML 文档对象模型中访问 HTML 源

<xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> 控件中的 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 和 <xref:System.Windows.Forms.WebBrowser> 属性返回当前文档的 HTML，显示方式与第一次显示的一样。 但是，如果通过使用方法和属性调用（例如 <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> 和 <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>）修改此页面，则在调用 <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> 和 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 时不会显示这些更改。 若要获得 DOM 的最新 HTML 源，必须调用 HTML 元素上的 <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> 属性。  
  
 以下过程显示了如何检索动态源并将其显示在单独的快捷菜单中。  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a>使用 OuterHtml 属性检索动态源  
  
1. 创建新的 Windows 窗体应用程序。 首先使用单个 <xref:System.Windows.Forms.Form> ，并调用它 `Form1` 。  
  
2. <xref:System.Windows.Forms.WebBrowser>在 Windows 窗体应用程序中承载该控件，并将其命名为 `WebBrowser1` 。 有关详细信息，请参阅 [如何：将 Web 浏览器功能添加到 Windows 窗体应用程序](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)。  
  
3. <xref:System.Windows.Forms.Form>在应用程序中创建另一个名为的 `CodeForm` 。  
  
4. 向添加一个 <xref:System.Windows.Forms.RichTextBox> 控件 `CodeForm` ，并将其 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为 `Fill` 。  
  
5. 创建一个名为的公共属性 `CodeForm` `Code` 。  
  
     [!code-csharp[DisplayWebBrowserCode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6. 将名为的 <xref:System.Windows.Forms.Button> 控件添加 `Button1` 到 <xref:System.Windows.Forms.Form> ，并监视 <xref:System.Windows.Forms.Control.Click> 事件。 有关监视事件的详细信息，请参阅 [事件](/dotnet/standard/events/index)。  
  
7. 将以下代码添加到 <xref:System.Windows.Forms.Control.Click> 事件处理程序中。  
  
     [!code-csharp[DisplayWebBrowserCode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a>可靠编程  

 在尝试检索 <xref:System.Windows.Forms.WebBrowser.Document%2A> 之前，应总是先测试它的值。 如果当前页未完成加载，则 <xref:System.Windows.Forms.WebBrowser.Document%2A> 或它的一个或多个子对象可能无法初始化。  
  
## <a name="see-also"></a>另请参阅

- [使用托管 HTML 文档对象模型](using-the-managed-html-document-object-model.md)
- [WebBrowser 控件概述](webbrowser-control-overview.md)
