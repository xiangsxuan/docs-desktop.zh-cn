---
title: 如何：使 Freezable 成为只读
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: b8dcbec18977d46bd47b82f528deb2eeccc4e441
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972783"
---
# <a name="how-to-make-a-freezable-read-only"></a>如何：使 Freezable 成为只读
此示例演示如何 <xref:System.Windows.Freezable> 通过调用方法来使其成为只读的 <xref:System.Windows.Freezable.Freeze%2A> 。  
  
 <xref:System.Windows.Freezable>如果以下任一情况涉及对象，则不能冻结对象 `true` ：  
  
- 它具有动画或数据绑定属性。  
  
- 它具有由动态资源设置的属性。 有关动态资源的详细信息，请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)。  
  
- 它包含 <xref:System.Windows.Freezable> 无法冻结的子对象。  
  
 如果这些条件 `false` 适用于你的 <xref:System.Windows.Freezable> 对象，并且你不打算修改它，请考虑将其冻结以获得性能优势。  
  
## <a name="example"></a>示例  
 下面的示例将冻结 <xref:System.Windows.Media.SolidColorBrush> ，这是一种 <xref:System.Windows.Freezable> 对象类型。  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 有关对象的详细信息 <xref:System.Windows.Freezable> ，请参阅 " [冻结对象概述](freezable-objects-overview.md)"。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [Freezable 对象概述](freezable-objects-overview.md)
- [操作指南主题](base-elements-how-to-topics.md)
