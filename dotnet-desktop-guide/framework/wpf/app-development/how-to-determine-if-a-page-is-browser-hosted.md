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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972705"
---
# <a name="how-to-determine-if-a-page-is-browser-hosted"></a>如何：确定是否已承载浏览器
此示例演示如何确定 <xref:System.Windows.Controls.Page> 是否承载于浏览器中。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.Page>可以是不可知的，因此，可以将其加载到几种不同类型的主机中，包括 <xref:System.Windows.Controls.Frame> 、 <xref:System.Windows.Navigation.NavigationWindow> 或浏览器。 如果有一个库程序集包含一个或多个页面，并且有多个独立的可浏览 (XAML 浏览器应用程序 (XBAP) ) 主机应用程序，则可能会发生这种情况。  
  
 下面的示例演示如何使用 <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> 来确定 <xref:System.Windows.Controls.Page> 是否承载于浏览器中。  
  
 [!code-csharp[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/CSharp/Page1.xaml.cs#isbrowserhostedcode)]
 [!code-vb[HOWTOBrowserInteropHelperSnippets#IsBrowserHostedCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOBrowserInteropHelperSnippets/visualbasic/page1.xaml.vb#isbrowserhostedcode)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
