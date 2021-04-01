---
title: 如何：确定 Freezable 是否处于冻结状态
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 6a63862d35f2c40289ea6445eb3dab8a2abe4a61
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972586"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a>如何：确定 Freezable 是否处于冻结状态
此示例演示如何确定 <xref:System.Windows.Freezable> 对象是否已冻结。 如果尝试修改冻结 <xref:System.Windows.Freezable> 对象，则会引发 <xref:System.InvalidOperationException> 。 若要避免引发此异常，请使用 <xref:System.Windows.Freezable.IsFrozen%2A> 对象的属性 <xref:System.Windows.Freezable> 来确定它是否被冻结。  
  
## <a name="example"></a>示例  
 下面的示例将冻结 <xref:System.Windows.Media.SolidColorBrush> ，然后使用属性对其进行测试， <xref:System.Windows.Freezable.IsFrozen%2A> 以确定它是否已冻结。  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 有关对象的详细信息 <xref:System.Windows.Freezable> ，请参阅 " [冻结对象概述](freezable-objects-overview.md)"。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [Freezable 对象概述](freezable-objects-overview.md)
- [操作指南主题](base-elements-how-to-topics.md)
