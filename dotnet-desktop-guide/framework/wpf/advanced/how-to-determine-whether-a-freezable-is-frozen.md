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
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a><span data-ttu-id="ee2d5-102">如何：确定 Freezable 是否处于冻结状态</span><span class="sxs-lookup"><span data-stu-id="ee2d5-102">How to: Determine Whether a Freezable Is Frozen</span></span>
<span data-ttu-id="ee2d5-103">此示例演示如何确定 <xref:System.Windows.Freezable> 对象是否已冻结。</span><span class="sxs-lookup"><span data-stu-id="ee2d5-103">This example shows how to determine whether a <xref:System.Windows.Freezable> object is frozen.</span></span> <span data-ttu-id="ee2d5-104">如果尝试修改冻结 <xref:System.Windows.Freezable> 对象，则会引发 <xref:System.InvalidOperationException> 。</span><span class="sxs-lookup"><span data-stu-id="ee2d5-104">If you try to modify a frozen <xref:System.Windows.Freezable> object, it throws an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="ee2d5-105">若要避免引发此异常，请使用 <xref:System.Windows.Freezable.IsFrozen%2A> 对象的属性 <xref:System.Windows.Freezable> 来确定它是否被冻结。</span><span class="sxs-lookup"><span data-stu-id="ee2d5-105">To avoid throwing this exception, use the <xref:System.Windows.Freezable.IsFrozen%2A> property of the <xref:System.Windows.Freezable> object to determine whether it is frozen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee2d5-106">示例</span><span class="sxs-lookup"><span data-stu-id="ee2d5-106">Example</span></span>  
 <span data-ttu-id="ee2d5-107">下面的示例将冻结 <xref:System.Windows.Media.SolidColorBrush> ，然后使用属性对其进行测试， <xref:System.Windows.Freezable.IsFrozen%2A> 以确定它是否已冻结。</span><span class="sxs-lookup"><span data-stu-id="ee2d5-107">The following example freezes a <xref:System.Windows.Media.SolidColorBrush> and then tests it by using the <xref:System.Windows.Freezable.IsFrozen%2A> property to determine whether it is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="ee2d5-108">有关对象的详细信息 <xref:System.Windows.Freezable> ，请参阅 " [冻结对象概述](freezable-objects-overview.md)"。</span><span class="sxs-lookup"><span data-stu-id="ee2d5-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee2d5-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee2d5-109">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [<span data-ttu-id="ee2d5-110">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="ee2d5-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="ee2d5-111">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="ee2d5-111">How-to Topics</span></span>](base-elements-how-to-topics.md)
