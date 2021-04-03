---
title: 如何：在网格之间共享大小调整属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: d5ab2ac612d55c8cbc34ae6d7d9d63b9f8aa23e7
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974007"
---
# <a name="how-to-share-sizing-properties-between-grids"></a>如何：在网格之间共享大小调整属性
此示例演示如何在元素之间共享列和行的大小调整数据，以便 <xref:System.Windows.Controls.Grid> 保持一致的大小。  
  
## <a name="example"></a>示例  
 下面的示例将两个 <xref:System.Windows.Controls.Grid> 元素引入为父元素的子元素 <xref:System.Windows.Controls.DockPanel> 。 的 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> 附加属性 <xref:System.Windows.Controls.Grid> 是在父级上定义的 <xref:System.Windows.Controls.DockPanel> 。  
  
 该示例使用两个元素操作属性值 <xref:System.Windows.Controls.Button> ; 每个元素表示一个布尔属性值。 当 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> 属性值设置为时 `true` ，将共享大小调整信息的每个列或行成员 <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> ，而不考虑行或列的内容。  
  
 [!code-xaml[gridIssharedsizescopeProp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 下面的代码隐藏示例处理按钮 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件引发的方法。 该示例将这些方法调用的结果写入到 <xref:System.Windows.Controls.TextBlock> 使用相关 get 方法的元素，以将新属性值输出为字符串。  
  
 [!code-csharp[gridIssharedsizescopeProp#3](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [面板概述](panels-overview.md)
