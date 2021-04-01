---
title: 如何：获取只读 Freezable 的可写副本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 910c5dada6ca82f68992722e4df6b35f9f7497c7
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973656"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a>如何：获取只读 Freezable 的可写副本
此示例演示如何使用 <xref:System.Windows.Freezable.Clone%2A> 方法创建只读的可写副本 <xref:System.Windows.Freezable> 。  
  
 将 <xref:System.Windows.Freezable> 对象标记为只读后 ( "冻结" ) ，则无法对其进行修改。 但是，可以使用 <xref:System.Windows.Freezable.Clone%2A> 方法来创建冻结对象的可修改复本。  
  
## <a name="example"></a>示例  
 下面的示例创建冻结对象的可修改复本 <xref:System.Windows.Media.SolidColorBrush> 。  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 有关对象的详细信息 <xref:System.Windows.Freezable> ，请参阅 " [冻结对象概述](freezable-objects-overview.md)"。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [Freezable 对象概述](freezable-objects-overview.md)
- [操作指南主题](base-elements-how-to-topics.md)
