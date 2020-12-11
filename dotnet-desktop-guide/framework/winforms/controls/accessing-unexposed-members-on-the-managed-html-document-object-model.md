---
title: 在托管 HTML 文档对象模型中访问未公开成员
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
ms.openlocfilehash: 525ef52ecbbc61fba787fa8286c56c638d837faf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971340"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a>在托管 HTML 文档对象模型中访问未公开成员
托管 HTML 文档对象模型 (DOM) 包含一个名为的类，该类 <xref:System.Windows.Forms.HtmlElement> 公开所有 HTML 元素共有的属性、方法和事件。 但是，有时需要访问托管接口不直接公开的成员。 本主题将介绍两种访问未公开成员的方式，包括在网页内部定义的 JScript 和 VBScript 函数。  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a>通过托管接口访问未公开成员  
 <xref:System.Windows.Forms.HtmlDocument> 和 <xref:System.Windows.Forms.HtmlElement> 提供了允许访问未公开成员的四种方法。 下表显示了类型及其对应的方法。  
  
|成员类型|方法|  
|-----------------|-----------------|  
|属性 (<xref:System.Windows.Forms.HtmlElement>) |<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|方法|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|事件 (<xref:System.Windows.Forms.HtmlDocument>) |<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|事件 (<xref:System.Windows.Forms.HtmlElement>) |<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|事件 (<xref:System.Windows.Forms.HtmlWindow>) |<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 当你使用这些方法时，假设你有一个正确的基础类型的元素。 假设你想要侦听 `Submit` `FORM` HTML 页面上某个元素的事件，以便可以在 `FORM` 用户将其提交到服务器之前对其值执行一些预处理操作。 理想情况下，如果您可以控制 HTML，则可以将定义 `FORM` 为具有唯一 `ID` 属性。  
  
```html  
<HTML>  
  
    <HEAD>  
        <TITLE>Form Page</TITLE>  
    </HEAD>  
  
    <BODY>  
        <FORM ID="form1">  
             ... form fields defined here ...  
        </FORM>  
    </BODY>  
  
</HTML>  
```  
  
 将此页加载到 <xref:System.Windows.Forms.WebBrowser> 控件中后，可以使用 <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> 方法 `FORM` 在运行时使用 `form1` 作为参数来检索。  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a>访问非托管接口  
 还可以通过使用非托管组件对象模型 (COM) 每个 DOM 类公开的接口，访问托管 HTML DOM 上未公开的成员。 如果你必须对未公开的成员进行多次调用，或者未公开成员返回托管的 HTML DOM 未包装的其他非托管接口，则建议使用此方法。  
  
 下表显示了通过托管 HTML DOM 公开的所有非托管接口。 单击每个链接以了解其用法说明和示例代码。  
  
|类型|非托管接口|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 要使用 COM 接口，最简单的方法是从应用程序中添加对非托管 HTML DOM 库的引用 ( # A0) ，不过这是不受支持的。 有关详细信息，请参阅 [知识库文章 934368](https://support.microsoft.com/kb/934368)。  
  
## <a name="accessing-script-functions"></a>访问脚本函数  
 HTML 页可以使用脚本语言（如 JScript 或 VBScript）定义一个或多个函数。 这些函数位于页面的页面内 `SCRIPT` ，可以按需运行，也可以作为对 DOM 上某个事件的响应。  
  
 您可以使用方法调用在 HTML 页中定义的任何脚本函数 <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> 。 如果脚本方法返回一个 HTML 元素，则可以使用强制转换将此返回结果转换为 <xref:System.Windows.Forms.HtmlElement> 。 有关详细信息和示例代码，请参阅 <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> 。  
  
## <a name="see-also"></a>另请参阅

- [使用托管 HTML 文档对象模型](using-the-managed-html-document-object-model.md)
