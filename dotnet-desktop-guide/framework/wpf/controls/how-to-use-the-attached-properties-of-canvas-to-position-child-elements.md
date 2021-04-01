---
title: 如何：使用画布的附加属性来定位子元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
ms.openlocfilehash: 347c8502bd4c5fafcde7a142327f85bfb75b9954
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970487"
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a><span data-ttu-id="e5a7c-102">如何：使用画布的附加属性来定位子元素</span><span class="sxs-lookup"><span data-stu-id="e5a7c-102">How to: Use the Attached Properties of Canvas to Position Child Elements</span></span>
<span data-ttu-id="e5a7c-103">此示例演示如何使用的附加属性 <xref:System.Windows.Controls.Canvas> 来定位子元素。</span><span class="sxs-lookup"><span data-stu-id="e5a7c-103">This example shows how to use the attached properties of <xref:System.Windows.Controls.Canvas> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5a7c-104">示例</span><span class="sxs-lookup"><span data-stu-id="e5a7c-104">Example</span></span>  
 <span data-ttu-id="e5a7c-105">下面的示例将四个 <xref:System.Windows.Controls.Button> 元素添加为父级的子元素 <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="e5a7c-105">The following example adds four <xref:System.Windows.Controls.Button> elements as child elements of a parent <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="e5a7c-106">每个元素均由 <xref:System.Windows.Controls.Canvas.Bottom%2A> 、、 <xref:System.Windows.Controls.Canvas.Left%2A> 和表示 <xref:System.Windows.Controls.Canvas.Right%2A> <xref:System.Windows.Controls.Canvas.Top%2A> 。</span><span class="sxs-lookup"><span data-stu-id="e5a7c-106">Each element is represented by a <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, and <xref:System.Windows.Controls.Canvas.Top%2A>.</span></span>
<span data-ttu-id="e5a7c-107">每个 <xref:System.Windows.Controls.Button> 相对于父项定位 <xref:System.Windows.Controls.Canvas> ，根据其分配的属性值定位。</span><span class="sxs-lookup"><span data-stu-id="e5a7c-107">Each <xref:System.Windows.Controls.Button> is positioned relative to the parent <xref:System.Windows.Controls.Canvas> and according to its assigned property value.</span></span>  
  
 [!code-cpp[CanvasAttachedProperties#1](~/samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e5a7c-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5a7c-108">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.Canvas.Bottom%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- <xref:System.Windows.Controls.Canvas.Right%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="e5a7c-109">面板概述</span><span class="sxs-lookup"><span data-stu-id="e5a7c-109">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="e5a7c-110">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="e5a7c-110">How-to Topics</span></span>](canvas-how-to-topics.md)
- [<span data-ttu-id="e5a7c-111">附加属性概述</span><span class="sxs-lookup"><span data-stu-id="e5a7c-111">Attached Properties Overview</span></span>](../advanced/attached-properties-overview.md)
