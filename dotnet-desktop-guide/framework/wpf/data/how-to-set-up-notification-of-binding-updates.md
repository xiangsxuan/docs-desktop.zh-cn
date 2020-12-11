---
title: 如何：设置绑定更新的通知
ms.date: 03/30/2017
helpviewer_keywords:
- notifications [WPF], binding updates
- data binding [WPF], notification of binding updates
- binding [WPF], updates [WPF], notifications of
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
ms.openlocfilehash: d6a27d0226abe1b67a92f76219be3a563fc26216
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973673"
---
# <a name="how-to-set-up-notification-of-binding-updates"></a>如何：设置绑定更新的通知
本示例演示如何设置在绑定的绑定目标（目标）或绑定源（源）属性更新时收到通知。  
  
## <a name="example"></a>示例  
 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 在每次更新绑定源或目标时都会引发数据更新事件。 在内部，此事件用于通知 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)]：它应该更新，因为绑定数据已更改。 请注意，若要使这些事件正常工作，并且若要使单向或双向绑定正常工作，需要使用接口实现数据类 <xref:System.ComponentModel.INotifyPropertyChanged> 。 有关详细信息，请参阅[实现属性更改通知](how-to-implement-property-change-notification.md)。  
  
 <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>在绑定中，将或 <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> 两个)  (设置为或。 `true` 用户提供的用于侦听此事件的处理程序必须直接附加到希望收到更改通知的元素，或者如果希望在上下文中的任何内容发生变化时得到通知，则附加到整个数据上下文。  
  
 下面的示例演示如何设置当目标属性更新时收到通知。  
  
 [!code-xaml[DirectionalBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 然后，可以根据 EventHandler \<T> 委托（在本示例中为 *OnTargetUpdated* ）分配处理程序来处理事件：  
  
 [!code-csharp[DirectionalBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 事件的参数可用于确定已更改属性的详细信息（例如，如果同一处理程序附加到多个元素，则可确定类型或特定元素信息），如果在单个元素上有多个绑定属性，则这些详细信息将很有用。  
  
## <a name="see-also"></a>另请参阅

- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [操作指南主题](data-binding-how-to-topics.md)
