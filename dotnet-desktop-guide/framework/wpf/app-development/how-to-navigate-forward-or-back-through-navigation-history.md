---
title: 如何：在导航历史记录中前进或后退
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: 76a78debdce14123cc465ac9abf4db906fe0a2df
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973294"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>如何：在导航历史记录中前进或后退
此示例演示如何向前或向后导航到导航历史记录中的条目。  
  
## <a name="example"></a>示例  
 从以下主机的内容运行的代码可以通过导航历史记录（一次一个条目）向前或向后导航。  
  
- <xref:System.Windows.Navigation.NavigationWindow> 利用 <xref:System.Windows.Navigation.NavigationService>  
  
- <xref:System.Windows.Controls.Frame> 利用 <xref:System.Windows.Navigation.NavigationService>  
  
- Internet Explorer  
  
 在向前导航一个条目之前，必须先通过检查 **CanGoForward** 属性检查前进导航历史记录中是否存在条目。 若要向前导航一项，请调用 **GoForward** 方法。 以下示例对此进行了演示：  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 在您可以导航回一个条目之前，必须先通过检查 **CanGoBack** 属性检查后退导航历史记录中是否存在条目。 若要向后导航一个条目，请调用 **GoBack** 方法。 以下示例对此进行了演示：  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**、 **GoForward**、 **CanGoBack** 和 **GoBack** 由 <xref:System.Windows.Navigation.NavigationWindow> 、 <xref:System.Windows.Controls.Frame> 和实现 <xref:System.Windows.Navigation.NavigationService> 。  
  
> [!NOTE]
> 如果调用 **GoForward**，且前进导航历史记录中没有条目，或者如果调用 **GoBack**，并且在后端导航历史记录中没有条目， <xref:System.InvalidOperationException> 则会引发。
