---
title: 如何：通过导航历史记录向后导航
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 53b32e145390d7052262042c7a793699c163b373
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973295"
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="e25f5-102">如何：通过导航历史记录向后导航</span><span class="sxs-lookup"><span data-stu-id="e25f5-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="e25f5-103">此示例说明如何导航到后退导航历史记录中的条目。</span><span class="sxs-lookup"><span data-stu-id="e25f5-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e25f5-104">示例</span><span class="sxs-lookup"><span data-stu-id="e25f5-104">Example</span></span>  
 <span data-ttu-id="e25f5-105">从、使用或 Internet Explorer 中承载的内容运行的代码 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame> <xref:System.Windows.Navigation.NavigationService> 可以通过导航历史记录（一次一个条目）导航回来。</span><span class="sxs-lookup"><span data-stu-id="e25f5-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService>, or Internet Explorer can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="e25f5-106">向后导航一个条目要求首先检查后导航历史记录中是否存在条目，方法是检查 **CanGoBack** 属性，然后通过调用 **GoBack** 方法导航回一个条目。</span><span class="sxs-lookup"><span data-stu-id="e25f5-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="e25f5-107">以下示例对此进行了演示：</span><span class="sxs-lookup"><span data-stu-id="e25f5-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="e25f5-108">**CanGoBack** 和 **GoBack** 是通过 <xref:System.Windows.Navigation.NavigationWindow> 、 <xref:System.Windows.Controls.Frame> 和实现的 <xref:System.Windows.Navigation.NavigationService> 。</span><span class="sxs-lookup"><span data-stu-id="e25f5-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e25f5-109">如果调用 **GoBack**，且后退导航历史记录中没有任何条目， <xref:System.InvalidOperationException> 则会引发。</span><span class="sxs-lookup"><span data-stu-id="e25f5-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
