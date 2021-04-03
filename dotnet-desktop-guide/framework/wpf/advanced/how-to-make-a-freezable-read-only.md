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
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="e668b-102">如何：使 Freezable 成为只读</span><span class="sxs-lookup"><span data-stu-id="e668b-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="e668b-103">此示例演示如何 <xref:System.Windows.Freezable> 通过调用方法来使其成为只读的 <xref:System.Windows.Freezable.Freeze%2A> 。</span><span class="sxs-lookup"><span data-stu-id="e668b-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="e668b-104"><xref:System.Windows.Freezable>如果以下任一情况涉及对象，则不能冻结对象 `true` ：</span><span class="sxs-lookup"><span data-stu-id="e668b-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
- <span data-ttu-id="e668b-105">它具有动画或数据绑定属性。</span><span class="sxs-lookup"><span data-stu-id="e668b-105">It has animated or data bound properties.</span></span>  
  
- <span data-ttu-id="e668b-106">它具有由动态资源设置的属性。</span><span class="sxs-lookup"><span data-stu-id="e668b-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="e668b-107">有关动态资源的详细信息，请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)。</span><span class="sxs-lookup"><span data-stu-id="e668b-107">For more information about dynamic resources, see the [XAML Resources](/dotnet/desktop-wpf/fundamentals/xaml-resources-define).</span></span>  
  
- <span data-ttu-id="e668b-108">它包含 <xref:System.Windows.Freezable> 无法冻结的子对象。</span><span class="sxs-lookup"><span data-stu-id="e668b-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="e668b-109">如果这些条件 `false` 适用于你的 <xref:System.Windows.Freezable> 对象，并且你不打算修改它，请考虑将其冻结以获得性能优势。</span><span class="sxs-lookup"><span data-stu-id="e668b-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e668b-110">示例</span><span class="sxs-lookup"><span data-stu-id="e668b-110">Example</span></span>  
 <span data-ttu-id="e668b-111">下面的示例将冻结 <xref:System.Windows.Media.SolidColorBrush> ，这是一种 <xref:System.Windows.Freezable> 对象类型。</span><span class="sxs-lookup"><span data-stu-id="e668b-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="e668b-112">有关对象的详细信息 <xref:System.Windows.Freezable> ，请参阅 " [冻结对象概述](freezable-objects-overview.md)"。</span><span class="sxs-lookup"><span data-stu-id="e668b-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e668b-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e668b-113">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="e668b-114">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="e668b-114">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="e668b-115">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="e668b-115">How-to Topics</span></span>](base-elements-how-to-topics.md)
