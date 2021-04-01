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
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a>如何：从页面设置窗口标题
此示例演示如何设置承载的窗口的标题 <xref:System.Windows.Controls.Page> 。  
  
## <a name="example"></a>示例  
 页面可以通过设置属性来更改承载它的窗口的标题 <xref:System.Windows.Controls.Page.WindowTitle%2A> ，如下所示：  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
> 设置 <xref:System.Windows.Controls.Page.Title%2A> 页的属性不会更改窗口标题的值。 而是 <xref:System.Windows.Controls.Page.Title%2A> 指定导航历史记录中的页面条目的名称。
