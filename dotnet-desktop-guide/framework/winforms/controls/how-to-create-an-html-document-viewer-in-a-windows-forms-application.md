---
title: 在 Windows 窗体应用程序中创建 HTML 文档查看器
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 913bc86af034645b4b8cf3d69da4c9def58fc19c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971870"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a>如何：在 Windows 窗体应用程序中创建 HTML 文档查看器
可以使用 <xref:System.Windows.Forms.WebBrowser> 控件显示和打印 HTML 文档，而无需提供 Internet Web 浏览器的完整功能。 当你希望利用 HTML 的格式设置功能，但不希望你的用户加载可能包含不受信任的 Web 控件或可能是恶意脚本代码的任意网页时，这非常有用。 例如，你可能想要以 <xref:System.Windows.Forms.WebBrowser> 这种方式限制控件的功能，例如，将其用作 HTML 电子邮件查看器或在应用程序中提供 html 格式的帮助。  
  
### <a name="to-create-an-html-document-viewer"></a>创建 HTML 文档查看器  
  
1. 将 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> 属性设置为， `false` 以防止 <xref:System.Windows.Forms.WebBrowser> 控件打开拖放到其上的文件。  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. 将 <xref:System.Windows.Forms.WebBrowser.Url%2A> 属性设置为要显示的初始文件的位置。  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 名为 `webBrowser1` 的 <xref:System.Windows.Forms.WebBrowser> 控件。  
  
- 对 `System` 和 `System.Windows.Forms` 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [WebBrowser 控件概述](webbrowser-control-overview.md)
- [WebBrowser 安全](webbrowser-security.md)
- [如何：使用 WebBrowser 控件导航到 URL](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [如何：使用 WebBrowser 控件打印](how-to-print-with-a-webbrowser-control.md)
