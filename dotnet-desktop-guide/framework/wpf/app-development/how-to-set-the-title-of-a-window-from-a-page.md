---
title: 如何：从页面设置窗口标题
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 0f618af89965822b0df96a264997dabd9cae7608
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970238"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a><span data-ttu-id="39042-102">如何：从页面设置窗口标题</span><span class="sxs-lookup"><span data-stu-id="39042-102">How to: Set the Title of a Window from a Page</span></span>
<span data-ttu-id="39042-103">此示例演示如何设置承载的窗口的标题 <xref:System.Windows.Controls.Page> 。</span><span class="sxs-lookup"><span data-stu-id="39042-103">This example shows how to set the title of the window in which a <xref:System.Windows.Controls.Page> is hosted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39042-104">示例</span><span class="sxs-lookup"><span data-stu-id="39042-104">Example</span></span>  
 <span data-ttu-id="39042-105">页面可以通过设置属性来更改承载它的窗口的标题 <xref:System.Windows.Controls.Page.WindowTitle%2A> ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="39042-105">A page can change the title of the window that is hosting it by setting the <xref:System.Windows.Controls.Page.WindowTitle%2A> property, like so:</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
> <span data-ttu-id="39042-106">设置 <xref:System.Windows.Controls.Page.Title%2A> 页的属性不会更改窗口标题的值。</span><span class="sxs-lookup"><span data-stu-id="39042-106">Setting the <xref:System.Windows.Controls.Page.Title%2A> property of a page does not change the value of the window title.</span></span> <span data-ttu-id="39042-107">而是 <xref:System.Windows.Controls.Page.Title%2A> 指定导航历史记录中的页面条目的名称。</span><span class="sxs-lookup"><span data-stu-id="39042-107">Instead, <xref:System.Windows.Controls.Page.Title%2A> specifies the name of a page entry in navigation history.</span></span>
