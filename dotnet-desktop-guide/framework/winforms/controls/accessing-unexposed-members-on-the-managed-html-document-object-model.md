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
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a><span data-ttu-id="0612d-102">在托管 HTML 文档对象模型中访问未公开成员</span><span class="sxs-lookup"><span data-stu-id="0612d-102">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>
<span data-ttu-id="0612d-103">托管 HTML 文档对象模型 (DOM) 包含一个名为的类，该类 <xref:System.Windows.Forms.HtmlElement> 公开所有 HTML 元素共有的属性、方法和事件。</span><span class="sxs-lookup"><span data-stu-id="0612d-103">The managed HTML Document Object Model (DOM) contains a class called <xref:System.Windows.Forms.HtmlElement> that exposes the properties, methods, and events that all HTML elements have in common.</span></span> <span data-ttu-id="0612d-104">但是，有时需要访问托管接口不直接公开的成员。</span><span class="sxs-lookup"><span data-stu-id="0612d-104">Sometimes, however, you will need to access members that the managed interface does not directly expose.</span></span> <span data-ttu-id="0612d-105">本主题将介绍两种访问未公开成员的方式，包括在网页内部定义的 JScript 和 VBScript 函数。</span><span class="sxs-lookup"><span data-stu-id="0612d-105">This topic examines two ways for accessing unexposed members, including JScript and VBScript functions defined inside of a Web page.</span></span>  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a><span data-ttu-id="0612d-106">通过托管接口访问未公开成员</span><span class="sxs-lookup"><span data-stu-id="0612d-106">Accessing Unexposed Members through Managed Interfaces</span></span>  
 <span data-ttu-id="0612d-107"><xref:System.Windows.Forms.HtmlDocument> 和 <xref:System.Windows.Forms.HtmlElement> 提供了允许访问未公开成员的四种方法。</span><span class="sxs-lookup"><span data-stu-id="0612d-107"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> provide four methods that enable access to unexposed members.</span></span> <span data-ttu-id="0612d-108">下表显示了类型及其对应的方法。</span><span class="sxs-lookup"><span data-stu-id="0612d-108">The following table shows the types and their corresponding methods.</span></span>  
  
|<span data-ttu-id="0612d-109">成员类型</span><span class="sxs-lookup"><span data-stu-id="0612d-109">Member Type</span></span>|<span data-ttu-id="0612d-110">方法</span><span class="sxs-lookup"><span data-stu-id="0612d-110">Method(s)</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="0612d-111">属性 (<xref:System.Windows.Forms.HtmlElement>) </span><span class="sxs-lookup"><span data-stu-id="0612d-111">Properties (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|<span data-ttu-id="0612d-112">方法</span><span class="sxs-lookup"><span data-stu-id="0612d-112">Methods</span></span>|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|<span data-ttu-id="0612d-113">事件 (<xref:System.Windows.Forms.HtmlDocument>) </span><span class="sxs-lookup"><span data-stu-id="0612d-113">Events (<xref:System.Windows.Forms.HtmlDocument>)</span></span>|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|<span data-ttu-id="0612d-114">事件 (<xref:System.Windows.Forms.HtmlElement>) </span><span class="sxs-lookup"><span data-stu-id="0612d-114">Events (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|<span data-ttu-id="0612d-115">事件 (<xref:System.Windows.Forms.HtmlWindow>) </span><span class="sxs-lookup"><span data-stu-id="0612d-115">Events (<xref:System.Windows.Forms.HtmlWindow>)</span></span>|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 <span data-ttu-id="0612d-116">当你使用这些方法时，假设你有一个正确的基础类型的元素。</span><span class="sxs-lookup"><span data-stu-id="0612d-116">When you use these methods, it is assumed that you have an element of the correct underlying type.</span></span> <span data-ttu-id="0612d-117">假设你想要侦听 `Submit` `FORM` HTML 页面上某个元素的事件，以便可以在 `FORM` 用户将其提交到服务器之前对其值执行一些预处理操作。</span><span class="sxs-lookup"><span data-stu-id="0612d-117">Suppose that you want to listen to the `Submit` event of a `FORM` element on an HTML page, so that you can perform some pre-processing on the `FORM`'s values before the user submits them to the server.</span></span> <span data-ttu-id="0612d-118">理想情况下，如果您可以控制 HTML，则可以将定义 `FORM` 为具有唯一 `ID` 属性。</span><span class="sxs-lookup"><span data-stu-id="0612d-118">Ideally, if you have control over the HTML, you would define the `FORM` to have a unique `ID` attribute.</span></span>  
  
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
  
 <span data-ttu-id="0612d-119">将此页加载到 <xref:System.Windows.Forms.WebBrowser> 控件中后，可以使用 <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> 方法 `FORM` 在运行时使用 `form1` 作为参数来检索。</span><span class="sxs-lookup"><span data-stu-id="0612d-119">After you load this page into the <xref:System.Windows.Forms.WebBrowser> control, you can use the <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> method to retrieve the `FORM` at run time using `form1` as the argument.</span></span>  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a><span data-ttu-id="0612d-120">访问非托管接口</span><span class="sxs-lookup"><span data-stu-id="0612d-120">Accessing Unmanaged Interfaces</span></span>  
 <span data-ttu-id="0612d-121">还可以通过使用非托管组件对象模型 (COM) 每个 DOM 类公开的接口，访问托管 HTML DOM 上未公开的成员。</span><span class="sxs-lookup"><span data-stu-id="0612d-121">You can also access unexposed members on the managed HTML DOM by using the unmanaged Component Object Model (COM) interfaces exposed by each DOM class.</span></span> <span data-ttu-id="0612d-122">如果你必须对未公开的成员进行多次调用，或者未公开成员返回托管的 HTML DOM 未包装的其他非托管接口，则建议使用此方法。</span><span class="sxs-lookup"><span data-stu-id="0612d-122">This is recommended if you have to make several calls against unexposed members, or if the unexposed members return other unmanaged interfaces not wrapped by the managed HTML DOM.</span></span>  
  
 <span data-ttu-id="0612d-123">下表显示了通过托管 HTML DOM 公开的所有非托管接口。</span><span class="sxs-lookup"><span data-stu-id="0612d-123">The following table shows all of the unmanaged interfaces exposed through the managed HTML DOM.</span></span> <span data-ttu-id="0612d-124">单击每个链接以了解其用法说明和示例代码。</span><span class="sxs-lookup"><span data-stu-id="0612d-124">Click on each link for an explanation of its usage and for example code.</span></span>  
  
|<span data-ttu-id="0612d-125">类型</span><span class="sxs-lookup"><span data-stu-id="0612d-125">Type</span></span>|<span data-ttu-id="0612d-126">非托管接口</span><span class="sxs-lookup"><span data-stu-id="0612d-126">Unmanaged Interface</span></span>|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 <span data-ttu-id="0612d-127">要使用 COM 接口，最简单的方法是从应用程序中添加对非托管 HTML DOM 库的引用 ( # A0) ，不过这是不受支持的。</span><span class="sxs-lookup"><span data-stu-id="0612d-127">The easiest way to use the COM interfaces is to add a reference to the unmanaged HTML DOM library (MSHTML.dll) from your application, although this is unsupported.</span></span> <span data-ttu-id="0612d-128">有关详细信息，请参阅 [知识库文章 934368](https://support.microsoft.com/kb/934368)。</span><span class="sxs-lookup"><span data-stu-id="0612d-128">For more information, see [Knowledge Base Article 934368](https://support.microsoft.com/kb/934368).</span></span>  
  
## <a name="accessing-script-functions"></a><span data-ttu-id="0612d-129">访问脚本函数</span><span class="sxs-lookup"><span data-stu-id="0612d-129">Accessing Script Functions</span></span>  
 <span data-ttu-id="0612d-130">HTML 页可以使用脚本语言（如 JScript 或 VBScript）定义一个或多个函数。</span><span class="sxs-lookup"><span data-stu-id="0612d-130">An HTML page can define one or more functions by using a scripting language such as JScript or VBScript.</span></span> <span data-ttu-id="0612d-131">这些函数位于页面的页面内 `SCRIPT` ，可以按需运行，也可以作为对 DOM 上某个事件的响应。</span><span class="sxs-lookup"><span data-stu-id="0612d-131">These functions are placed inside of a `SCRIPT` page in the page, and can be run on demand or in response to an event on the DOM.</span></span>  
  
 <span data-ttu-id="0612d-132">您可以使用方法调用在 HTML 页中定义的任何脚本函数 <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> 。</span><span class="sxs-lookup"><span data-stu-id="0612d-132">You can call any script functions you define in an HTML page using the <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> method.</span></span> <span data-ttu-id="0612d-133">如果脚本方法返回一个 HTML 元素，则可以使用强制转换将此返回结果转换为 <xref:System.Windows.Forms.HtmlElement> 。</span><span class="sxs-lookup"><span data-stu-id="0612d-133">If the script method returns an HTML element, you can use a cast to convert this return result to an <xref:System.Windows.Forms.HtmlElement>.</span></span> <span data-ttu-id="0612d-134">有关详细信息和示例代码，请参阅 <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> 。</span><span class="sxs-lookup"><span data-stu-id="0612d-134">For details and example code, see <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0612d-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0612d-135">See also</span></span>

- [<span data-ttu-id="0612d-136">使用托管 HTML 文档对象模型</span><span class="sxs-lookup"><span data-stu-id="0612d-136">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)
