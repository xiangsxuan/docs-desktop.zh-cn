---
title: 如何：导航到页面
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 25a0dbbc609c7b6f8f2878d2068e61e492a59c7e
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974071"
---
# <a name="how-to-navigate-to-a-page"></a><span data-ttu-id="40315-102">如何：导航到页面</span><span class="sxs-lookup"><span data-stu-id="40315-102">How to: Navigate to a Page</span></span>
<span data-ttu-id="40315-103">此示例演示了通过多种方式从中导航页面的方法 <xref:System.Windows.Navigation.NavigationWindow> 。</span><span class="sxs-lookup"><span data-stu-id="40315-103">This example illustrates several ways in which a page can be navigated to from a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40315-104">示例</span><span class="sxs-lookup"><span data-stu-id="40315-104">Example</span></span>  
 <span data-ttu-id="40315-105"><xref:System.Windows.Navigation.NavigationWindow>使用以下方法之一可以导航到某个页面：</span><span class="sxs-lookup"><span data-stu-id="40315-105">It is possible for a <xref:System.Windows.Navigation.NavigationWindow> to navigate to a page using one of the following:</span></span>  
  
- <span data-ttu-id="40315-106"><xref:System.Windows.Navigation.NavigationWindow.Source%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="40315-106">The <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property.</span></span>  
  
- <span data-ttu-id="40315-107"><xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="40315-107">The <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> method.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
> <span data-ttu-id="40315-108">统一资源标识符 (Uri) 可以是相对的，也可以是绝对的。</span><span class="sxs-lookup"><span data-stu-id="40315-108">Uniform resource identifiers (URIs) can be either relative or absolute.</span></span> <span data-ttu-id="40315-109">有关详细信息，请参阅 [WPF 中的 Pack URI](pack-uris-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="40315-109">For more information, see [Pack URIs in WPF](pack-uris-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40315-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40315-110">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
