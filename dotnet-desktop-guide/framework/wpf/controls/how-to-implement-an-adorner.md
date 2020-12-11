---
title: 如何：实现装饰器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: da318fee42b4628351217774de2a2225cfb21ee1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972812"
---
# <a name="how-to-implement-an-adorner"></a><span data-ttu-id="0a94f-102">如何：实现装饰器</span><span class="sxs-lookup"><span data-stu-id="0a94f-102">How to: Implement an Adorner</span></span>
<span data-ttu-id="0a94f-103">此示例演示了一个最小装饰器实现。</span><span class="sxs-lookup"><span data-stu-id="0a94f-103">This example shows a minimal adorner implementation.</span></span>  
  
## <a name="notes-for-implementers"></a><span data-ttu-id="0a94f-104">实施者注意事项</span><span class="sxs-lookup"><span data-stu-id="0a94f-104">Notes for Implementers</span></span>  
 <span data-ttu-id="0a94f-105">请务必注意，装饰器不包括任何继承呈现行为，确保装饰器呈现是装饰器实施者的责任。</span><span class="sxs-lookup"><span data-stu-id="0a94f-105">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="0a94f-106">实现呈现行为的常见方法是重写 <xref:System.Windows.UIElement.OnRender%2A> 方法，并使用一个或多个 <xref:System.Windows.Media.DrawingContext> 对象根据需要呈现装饰器的视觉对象 (如此示例) 中所示。</span><span class="sxs-lookup"><span data-stu-id="0a94f-106">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in this example).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a94f-107">示例</span><span class="sxs-lookup"><span data-stu-id="0a94f-107">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="0a94f-108">描述</span><span class="sxs-lookup"><span data-stu-id="0a94f-108">Description</span></span>  
 <span data-ttu-id="0a94f-109">通过实现继承自抽象类的类来创建自定义装饰器 <xref:System.Windows.Documents.Adorner> 。</span><span class="sxs-lookup"><span data-stu-id="0a94f-109">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  <span data-ttu-id="0a94f-110">示例装饰器 <xref:System.Windows.UIElement> 通过重写方法，只是装饰的角 <xref:System.Windows.UIElement.OnRender%2A> 。</span><span class="sxs-lookup"><span data-stu-id="0a94f-110">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles by overriding the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0a94f-111">代码</span><span class="sxs-lookup"><span data-stu-id="0a94f-111">Code</span></span>  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="0a94f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a94f-112">See also</span></span>

- [<span data-ttu-id="0a94f-113">装饰器概述</span><span class="sxs-lookup"><span data-stu-id="0a94f-113">Adorners Overview</span></span>](adorners-overview.md)
