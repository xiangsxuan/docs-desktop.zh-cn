---
title: 如何：设置页面的窗口宽度
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: 1e16b75ecb85550facdf24a5b9e341cf0c061178
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970237"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a><span data-ttu-id="116c4-102">如何：设置页面的窗口宽度</span><span class="sxs-lookup"><span data-stu-id="116c4-102">How to: Set the Width of a Window from a Page</span></span>
<span data-ttu-id="116c4-103">此示例演示如何从设置窗口的宽度 <xref:System.Windows.Controls.Page> 。</span><span class="sxs-lookup"><span data-stu-id="116c4-103">This example illustrates how to set the width of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="116c4-104">示例</span><span class="sxs-lookup"><span data-stu-id="116c4-104">Example</span></span>  
 <span data-ttu-id="116c4-105"><xref:System.Windows.Controls.Page>可以通过设置来设置其宿主窗口的宽度 <xref:System.Windows.Controls.Page.WindowWidth%2A> 。</span><span class="sxs-lookup"><span data-stu-id="116c4-105">A <xref:System.Windows.Controls.Page> can set the width of its host window by setting <xref:System.Windows.Controls.Page.WindowWidth%2A>.</span></span> <span data-ttu-id="116c4-106">此属性允许 <xref:System.Windows.Controls.Page> 不明确了解承载它的窗口的类型。</span><span class="sxs-lookup"><span data-stu-id="116c4-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="116c4-107">若要使用设置窗口的宽度 <xref:System.Windows.Controls.Page.WindowWidth%2A> ， <xref:System.Windows.Controls.Page> 必须是窗口的子级。</span><span class="sxs-lookup"><span data-stu-id="116c4-107">To set the width of a window using <xref:System.Windows.Controls.Page.WindowWidth%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
