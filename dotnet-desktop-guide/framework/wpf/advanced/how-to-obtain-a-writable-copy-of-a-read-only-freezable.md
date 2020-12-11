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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973656"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a><span data-ttu-id="cf9ce-102">如何：获取只读 Freezable 的可写副本</span><span class="sxs-lookup"><span data-stu-id="cf9ce-102">How to: Obtain a Writable Copy of a Read-Only Freezable</span></span>
<span data-ttu-id="cf9ce-103">此示例演示如何使用 <xref:System.Windows.Freezable.Clone%2A> 方法创建只读的可写副本 <xref:System.Windows.Freezable> 。</span><span class="sxs-lookup"><span data-stu-id="cf9ce-103">This example shows how to use the <xref:System.Windows.Freezable.Clone%2A> method to create a writable copy of a read-only <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="cf9ce-104">将 <xref:System.Windows.Freezable> 对象标记为只读后 ( "冻结" ) ，则无法对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="cf9ce-104">After a <xref:System.Windows.Freezable> object is marked as read-only ("frozen"), you cannot modify it.</span></span> <span data-ttu-id="cf9ce-105">但是，可以使用 <xref:System.Windows.Freezable.Clone%2A> 方法来创建冻结对象的可修改复本。</span><span class="sxs-lookup"><span data-stu-id="cf9ce-105">However, you can use the <xref:System.Windows.Freezable.Clone%2A> method to create a modifiable clone of the frozen object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf9ce-106">示例</span><span class="sxs-lookup"><span data-stu-id="cf9ce-106">Example</span></span>  
 <span data-ttu-id="cf9ce-107">下面的示例创建冻结对象的可修改复本 <xref:System.Windows.Media.SolidColorBrush> 。</span><span class="sxs-lookup"><span data-stu-id="cf9ce-107">The following example creates a modifiable clone of a frozen <xref:System.Windows.Media.SolidColorBrush> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 <span data-ttu-id="cf9ce-108">有关对象的详细信息 <xref:System.Windows.Freezable> ，请参阅 " [冻结对象概述](freezable-objects-overview.md)"。</span><span class="sxs-lookup"><span data-stu-id="cf9ce-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf9ce-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf9ce-109">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [<span data-ttu-id="cf9ce-110">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="cf9ce-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="cf9ce-111">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="cf9ce-111">How-to Topics</span></span>](base-elements-how-to-topics.md)