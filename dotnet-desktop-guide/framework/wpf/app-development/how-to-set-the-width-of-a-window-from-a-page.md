---
title: 如何：设置页面的窗口宽度
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: 1e16b75ecb85550facdf24a5b9e341cf0c061178
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970237"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a>如何：设置页面的窗口宽度
此示例演示如何从设置窗口的宽度 <xref:System.Windows.Controls.Page> 。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.Page>可以通过设置来设置其宿主窗口的宽度 <xref:System.Windows.Controls.Page.WindowWidth%2A> 。 此属性允许 <xref:System.Windows.Controls.Page> 不明确了解承载它的窗口的类型。  
  
> [!NOTE]
> 若要使用设置窗口的宽度 <xref:System.Windows.Controls.Page.WindowWidth%2A> ， <xref:System.Windows.Controls.Page> 必须是窗口的子级。  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
