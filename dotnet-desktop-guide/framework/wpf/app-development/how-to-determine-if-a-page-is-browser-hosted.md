---
title: 如何：确定是否已承载浏览器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosted pages in browser [WPF]
- pages [WPF], hosted in browser
ms.assetid: 737e0f26-8371-49b4-9579-70879e51e1aa
ms.openlocfilehash: c4cb1065807d16c1d1f5a95c8ac9c9cbe5a0fdab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972705"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a><span data-ttu-id="d3661-102">如何：确定是否已承载浏览器</span><span class="sxs-lookup"><span data-stu-id="d3661-102">How to: Determine If a Page is Browser Hosted</span></span>
<span data-ttu-id="d3661-103">此示例演示如何确定 <xref:System.Windows.Controls.Page> 是否承载于浏览器中。</span><span class="sxs-lookup"><span data-stu-id="d3661-103">This example demonstrates how to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3661-104">示例</span><span class="sxs-lookup"><span data-stu-id="d3661-104">Example</span></span>  
 <span data-ttu-id="d3661-105"><xref:System.Windows.Controls.Page>可以是不可知的，因此，可以将其加载到几种不同类型的主机中，包括 <xref:System.Windows.Controls.Frame> 、 <xref:System.Windows.Navigation.NavigationWindow> 或浏览器。</span><span class="sxs-lookup"><span data-stu-id="d3661-105">A <xref:System.Windows.Controls.Page> can be host agnostic and, consequently, can be loaded into several different types of hosts, including a <xref:System.Windows.Controls.Frame>, a <xref:System.Windows.Navigation.NavigationWindow>, or a browser.</span></span> <span data-ttu-id="d3661-106">如果有一个库程序集包含一个或多个页面，并且有多个独立的可浏览 (XAML 浏览器应用程序 (XBAP) # A3 主机应用程序，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="d3661-106">This can happen when you have a library assembly that contains one or more pages, and which is referenced by multiple standalone and browsable (XAML browser application (XBAP)) host applications.</span></span>  
  
 <span data-ttu-id="d3661-107">下面的示例演示如何使用 <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> 来确定 <xref:System.Windows.Controls.Page> 是否承载于浏览器中。</span><span class="sxs-lookup"><span data-stu-id="d3661-107">The following example demonstrates how to use <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> to determine if a <xref:System.Windows.Controls.Page> is hosted in a browser.</span></span>  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a><span data-ttu-id="d3661-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3661-108">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
