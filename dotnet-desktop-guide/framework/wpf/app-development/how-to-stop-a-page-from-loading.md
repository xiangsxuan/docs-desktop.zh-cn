---
title: 如何：停止加载页面
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], stopping from loading
- methods [WPF], Stoploading
- events [WPF], NavigationStopped
- NavigationStopped properties [WPF]
- stopping pages from loading [WPF]
- loading [WPF], stopping
ms.assetid: e2b695b0-517e-462c-8ccf-90cc8d6ba864
ms.openlocfilehash: c5694bb2cb6c618cd84bad3dc893ae3855e44892
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970234"
---
# <a name="how-to-stop-a-page-from-loading"></a><span data-ttu-id="a1b6d-102">如何：停止加载页面</span><span class="sxs-lookup"><span data-stu-id="a1b6d-102">How to: Stop a Page from Loading</span></span>
<span data-ttu-id="a1b6d-103">此示例演示如何调用 <xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> 方法，以在下载完成前停止导航到内容。</span><span class="sxs-lookup"><span data-stu-id="a1b6d-103">This example shows how to call the <xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> method to stop navigation to content before it has finished being downloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1b6d-104">示例</span><span class="sxs-lookup"><span data-stu-id="a1b6d-104">Example</span></span>  
 <span data-ttu-id="a1b6d-105"><xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> 停止下载请求的内容，并 <xref:System.Windows.Navigation.NavigationWindow.NavigationStopped> 引发事件。</span><span class="sxs-lookup"><span data-stu-id="a1b6d-105"><xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> stops the download of the requested content, and causes the <xref:System.Windows.Navigation.NavigationWindow.NavigationStopped> event to be raised.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateStopLoadingCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatestoploadingcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateStopLoadingCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatestoploadingcode)]
