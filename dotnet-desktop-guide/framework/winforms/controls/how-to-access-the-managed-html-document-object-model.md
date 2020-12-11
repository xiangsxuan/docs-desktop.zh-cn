---
title: 如何：访问托管 HTML 文档对象模型
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- HTML DOM [Windows Forms], accessing
- managed HTML DOM [Windows Forms], accessing
ms.assetid: 40fa5cd5-1ed8-42f6-a93f-9ac01608bbeb
ms.openlocfilehash: 42f2f4d7a518daa6341809974b10978bec99f1a8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971290"
---
# <a name="how-to-access-the-managed-html-document-object-model"></a><span data-ttu-id="3fd86-102">如何：访问托管 HTML 文档对象模型</span><span class="sxs-lookup"><span data-stu-id="3fd86-102">How to: Access the Managed HTML Document Object Model</span></span>

<span data-ttu-id="3fd86-103">可以从两种类型的应用程序访问托管 HTML 文档对象模型 (DOM)：</span><span class="sxs-lookup"><span data-stu-id="3fd86-103">You can access the managed HTML Document Object Model (DOM) from two types of applications:</span></span>  
  
- <span data-ttu-id="3fd86-104">承载了托管 <xref:System.Windows.Forms.WebBrowser> 控件的 Windows 窗体应用程序 (.exe)。</span><span class="sxs-lookup"><span data-stu-id="3fd86-104">A Windows Forms application (.exe) that hosted the managed <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="3fd86-105">这两种技术互相补充，<xref:System.Windows.Forms.WebBrowser> 控件向用户显示页面，HTML DOM 表示文档的逻辑结构。</span><span class="sxs-lookup"><span data-stu-id="3fd86-105">These two technologies complement one another, with the <xref:System.Windows.Forms.WebBrowser> control displaying the page to the user and the HTML DOM representing the document's logical structure.</span></span>  
  
- <span data-ttu-id="3fd86-106">在 Internet Explorer 内托管的 Windows 窗体 <xref:System.Windows.Forms.UserControl>。</span><span class="sxs-lookup"><span data-stu-id="3fd86-106">A Windows Forms <xref:System.Windows.Forms.UserControl> hosted within Internet Explorer.</span></span> <span data-ttu-id="3fd86-107">你可以访问表示托管你的 <xref:System.Windows.Forms.UserControl> 的页面的 HTML DOM，以更改文档结构或打开模式对话框（还有很多其他可能的操作）。</span><span class="sxs-lookup"><span data-stu-id="3fd86-107">You can access the HTML DOM representing the page on which your <xref:System.Windows.Forms.UserControl> is hosted in order to change the document's structure or open modal dialog boxes, among many other possibilities.</span></span>  
  
### <a name="to-access-dom-from-a-windows-forms-application"></a><span data-ttu-id="3fd86-108">从 Windows 窗体应用程序访问 DOM</span><span class="sxs-lookup"><span data-stu-id="3fd86-108">To access DOM from a Windows Forms application</span></span>  
  
1. <span data-ttu-id="3fd86-109">在 Windows 窗体应用程序内部托管 <xref:System.Windows.Forms.WebBrowser> 控件，并监视 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 事件。</span><span class="sxs-lookup"><span data-stu-id="3fd86-109">Host a <xref:System.Windows.Forms.WebBrowser> control within your Windows Forms application and monitor for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="3fd86-110">有关托管控件和监视事件的详细信息，请参阅[事件](/dotnet/standard/events/index)。</span><span class="sxs-lookup"><span data-stu-id="3fd86-110">For details on hosting controls and monitoring for events, see [Events](/dotnet/standard/events/index).</span></span>  
  
2. <span data-ttu-id="3fd86-111">通过访问 <xref:System.Windows.Forms.HtmlDocument> 控件的 <xref:System.Windows.Forms.WebBrowser.Document%2A> 属性，从 <xref:System.Windows.Forms.WebBrowser> 中检索当前页。</span><span class="sxs-lookup"><span data-stu-id="3fd86-111">Retrieve the <xref:System.Windows.Forms.HtmlDocument> for the current page by accessing the <xref:System.Windows.Forms.WebBrowser.Document%2A> property of the <xref:System.Windows.Forms.WebBrowser> control.</span></span>  

### <a name="to-access-dom-from-a-usercontrol-hosted-in-internet-explorer"></a><span data-ttu-id="3fd86-112">从在 Internet Explorer 中托管的 UserControl 访问 DOM</span><span class="sxs-lookup"><span data-stu-id="3fd86-112">To access DOM from a UserControl hosted in Internet Explorer</span></span>  
  
1. <span data-ttu-id="3fd86-113">从 <xref:System.Windows.Forms.UserControl> 类创建你自己的自定义派生类。</span><span class="sxs-lookup"><span data-stu-id="3fd86-113">Create your own custom derived class of the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="3fd86-114">有关详细信息，请参阅[如何：创作复合控件](how-to-author-composite-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="3fd86-114">For more information, see [How to: Author Composite Controls](how-to-author-composite-controls.md).</span></span>  
  
2. <span data-ttu-id="3fd86-115">将以下代码放置在你的 <xref:System.Windows.Forms.UserControl> 的 Load 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="3fd86-115">Place the following code inside of your Load event handler for your <xref:System.Windows.Forms.UserControl>:</span></span>  
  
 [!code-csharp[AccessHTMLDOMControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/AccessHTMLDOMControl/cs/UserControl1.cs#1)]
 [!code-vb[AccessHTMLDOMControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/AccessHTMLDOMControl/vb/UserControl1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="3fd86-116">可靠编程</span><span class="sxs-lookup"><span data-stu-id="3fd86-116">Robust Programming</span></span>  
  
1. <span data-ttu-id="3fd86-117">通过 <xref:System.Windows.Forms.WebBrowser> 控件使用 DOM 时，总是应等到 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 事件发生之后，再尝试访问 <xref:System.Windows.Forms.WebBrowser.Document%2A> 控件的 <xref:System.Windows.Forms.WebBrowser> 属性。</span><span class="sxs-lookup"><span data-stu-id="3fd86-117">When using the DOM through the <xref:System.Windows.Forms.WebBrowser> control, you should always wait until the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event occurs before attempting to access the <xref:System.Windows.Forms.WebBrowser.Document%2A> property of the <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="3fd86-118">加载整个文档之后会引发 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 事件；如果你在此之前用过 DOM，则有导致应用程序中出现运行时异常的风险。</span><span class="sxs-lookup"><span data-stu-id="3fd86-118">The <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event is raised after the entire document has loaded; if you use the DOM before then, you risk causing a run-time exception in your application.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="3fd86-119">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="3fd86-119">.NET Framework Security</span></span>  
  
1. <span data-ttu-id="3fd86-120">你的应用程序或 <xref:System.Windows.Forms.UserControl> 将需要完全信任，才能访问托管 HTML DOM。</span><span class="sxs-lookup"><span data-stu-id="3fd86-120">Your application or <xref:System.Windows.Forms.UserControl> will require full trust in order to access the managed HTML DOM.</span></span> <span data-ttu-id="3fd86-121">如果使用 ClickOnce 部署 Windows 窗体应用程序，则可以使用权限提升或受信任的应用程序部署来请求完全信任;有关详细信息，请参阅 [保护 ClickOnce 应用程序](/visualstudio/deployment/securing-clickonce-applications) 。</span><span class="sxs-lookup"><span data-stu-id="3fd86-121">If you are deploying a Windows Forms application using ClickOnce, you can request full trust using either Permission Elevation or Trusted Application Deployment; see [Securing ClickOnce Applications](/visualstudio/deployment/securing-clickonce-applications) for details.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fd86-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3fd86-122">See also</span></span>

- [<span data-ttu-id="3fd86-123">使用托管 HTML 文档对象模型</span><span class="sxs-lookup"><span data-stu-id="3fd86-123">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)
