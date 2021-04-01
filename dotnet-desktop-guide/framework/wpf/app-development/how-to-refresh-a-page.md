---
title: 如何：刷新页
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], refreshing
- refreshing pages [WPF]
ms.assetid: 06dd1bbd-81c4-40ad-ac0d-7a5b326b1465
ms.openlocfilehash: 71a71c91384a8905413358d023531afec23f2d41
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973822"
---
# <a name="how-to-refresh-a-page"></a>如何：刷新页
此示例演示如何调用 <xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> 方法来刷新中的当前内容 <xref:System.Windows.Navigation.NavigationWindow> 。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> 刷新要从源中重新加载的中的当前内容 <xref:System.Windows.Navigation.NavigationWindow> 。  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateRefreshCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigaterefreshcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateRefreshCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigaterefreshcode)]
