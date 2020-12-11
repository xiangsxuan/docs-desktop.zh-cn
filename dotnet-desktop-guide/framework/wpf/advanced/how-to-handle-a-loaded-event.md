---
title: 如何：处理 Loaded 事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: 7ca95e195792f8fb4789c481e84dda51f2910434
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971822"
---
# <a name="how-to-handle-a-loaded-event"></a>如何：处理 Loaded 事件
此示例演示如何处理 <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> 事件，并演示如何处理该事件。 在加载页面时，处理程序将创建一个 <xref:System.Windows.Controls.Button> 。  
  
## <a name="example"></a>示例  
 下面的示例将 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 与代码隐藏文件一起使用。  
  
 [!code-xaml[FELoaded#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.FrameworkElement>
- [对象生存期事件](object-lifetime-events.md)
- [路由事件概述](routed-events-overview.md)
- [操作指南主题](base-elements-how-to-topics.md)
