---
title: 如何：创建网格元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
ms.openlocfilehash: c87ca1d6642bd18fa85806c92caab049d259d45e
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973974"
---
# <a name="how-to-create-a-grid-element"></a>如何：创建网格元素
## <a name="example"></a>示例  
 下面的示例演示如何 <xref:System.Windows.Controls.Grid> 使用或代码创建和使用的实例 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。 此示例使用三个 <xref:System.Windows.Controls.ColumnDefinition> 对象和三个 <xref:System.Windows.Controls.RowDefinition> 对象创建一个具有九个单元的网格，如在工作表中。 每个单元格 <xref:System.Windows.Controls.TextBlock> 都包含一个表示数据的元素，第一行包含一个 <xref:System.Windows.Controls.TextBlock> 应用了属性的 <xref:System.Windows.Controls.Grid.ColumnSpan%2A> 。 若要显示每个单元格的边界，请 <xref:System.Windows.Controls.Grid.ShowGridLines%2A> 启用属性。  
  
 [!code-csharp[Grid#3](~/samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](~/samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
  这两种方法都将生成一个与下面类似的用户界面。

  ![屏幕截图描述了一个 WPF 用户界面，其中包含一个分为三列的网格。  这种情况下，标题为 "2018 Products" 的数据跨越了顶行的所有列，并且每个列都有三列，每个季度使用销售数据。  下半行包含的文本包含两列，消息总数为：300000](././media/how-to-create-a-grid-element/how-to-create-a-grid-element.png)
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.Grid>
- [面板概述](panels-overview.md)
