---
title: 如何：从页面设置窗口的高度
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c1041af88241011b51c96d7b61423344a32b25ca
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970241"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a>如何：从页面设置窗口的高度
此示例演示如何从设置窗口的高度 <xref:System.Windows.Controls.Page> 。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.Page>可以通过设置来设置其宿主窗口的高度 <xref:System.Windows.Controls.Page.WindowHeight%2A> 。 此属性允许 <xref:System.Windows.Controls.Page> 不明确了解承载它的窗口的类型。  
  
> [!NOTE]
> 若要使用设置窗口的高度 <xref:System.Windows.Controls.Page.WindowHeight%2A> ， <xref:System.Windows.Controls.Page> 必须是窗口的子级。  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
