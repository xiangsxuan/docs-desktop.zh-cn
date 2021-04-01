---
title: 如何：按名称查找元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements [WPF], finding by name
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
ms.openlocfilehash: d8f5e9077400d460e2e42638a534bacc656db22f
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973479"
---
# <a name="how-to-find-an-element-by-its-name"></a>如何：按名称查找元素
此示例说明如何使用 <xref:System.Windows.FrameworkElement.FindName%2A> 方法通过其值查找元素 <xref:System.Windows.FrameworkElement.Name%2A> 。  
  
## <a name="example"></a>示例  
 在此示例中，按其名称查找特定元素的方法被编写为按钮的事件处理程序。 `stackPanel` 是 <xref:System.Windows.FrameworkElement.Name%2A> 要搜索的根的 <xref:System.Windows.FrameworkElement> ，然后该示例方法通过将其强制转换为 <xref:System.Windows.Controls.TextBlock> 并更改某个可见的属性，直观地指示找到的元素 <xref:System.Windows.Controls.TextBlock> [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 。  
  
 [!code-csharp[FEFindName#Find](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]
