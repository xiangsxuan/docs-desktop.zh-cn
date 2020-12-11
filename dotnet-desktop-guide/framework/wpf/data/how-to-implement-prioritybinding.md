---
title: 如何：实现 PriorityBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: 694679183f92c9737bbdb511b4ebd5a4bf2185f1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974040"
---
# <a name="how-to-implement-prioritybinding"></a>如何：实现 PriorityBinding

<xref:System.Windows.Data.PriorityBinding> 在 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 工作中，指定绑定的列表。 绑定列表按从最高优先级到最低优先级的顺序排列。 如果最高优先级绑定在处理时成功返回值，则永远不需要处理列表中的其他绑定。 这种情况可能是最高优先级的绑定需要很长的时间来计算，因此，在更高优先级的绑定成功返回值之前，将使用下一个最高优先级来成功返回值。  
  
## <a name="example"></a>示例  

 为了演示 <xref:System.Windows.Data.PriorityBinding> 工作方式， `AsyncDataSource` 已使用以下三个属性创建了对象： `FastDP` 、 `SlowerDP` 和 `SlowestDP` 。  
  
 的 get 访问器 `FastDP` 返回数据成员的值 `_fastDP` 。  
  
 的 get 访问器在 `SlowerDP` 返回数据成员的值之前等待3秒 `_slowerDP` 。  
  
 的 get 访问器在 `SlowestDP` 返回数据成员的值之前等待5秒 `_slowestDP` 。  
  
> [!NOTE]
> 此示例只为了方便演示。 .NET 指导原则建议不要定义比字段集慢的数量级顺序的属性。 有关详细信息，请参阅 [在属性和方法之间进行选择](/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100))。  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <xref:System.Windows.Controls.TextBlock.Text%2A>属性使用绑定到上面的 `AsyncDS` <xref:System.Windows.Data.PriorityBinding> ：  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 当绑定引擎处理对象时 <xref:System.Windows.Data.Binding> ，它将从 <xref:System.Windows.Data.Binding> 绑定到属性的第一个中开始 `SlowestDP` 。 当 <xref:System.Windows.Data.Binding> 处理此操作时，它不会成功返回值，因为它处于休眠状态5秒，因此会 <xref:System.Windows.Data.Binding> 处理下一个元素。 下一步不 <xref:System.Windows.Data.Binding> 会成功返回值，因为它处于休眠状态3秒。 然后，绑定引擎会移动到 <xref:System.Windows.Data.Binding> 绑定到属性的下一个元素 `FastDP` 。 这会 <xref:System.Windows.Data.Binding> 返回值 "Fast value"。 <xref:System.Windows.Controls.TextBlock>现在会显示 "快速值" 值。  
  
 3秒后， `SlowerDP` 属性返回值 "慢速值"。 然后，将 <xref:System.Windows.Controls.TextBlock> 显示值 "慢速值"。  
  
 超过5秒钟后， `SlowestDP` 属性将返回值 "最慢的值"。 由于此绑定首先列出，因此具有最高优先级。 <xref:System.Windows.Controls.TextBlock>现在会显示值 "最慢的值"。  
  
 有关 <xref:System.Windows.Data.PriorityBinding> 从绑定中被视为成功返回值的信息，请参阅。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [操作指南主题](data-binding-how-to-topics.md)
