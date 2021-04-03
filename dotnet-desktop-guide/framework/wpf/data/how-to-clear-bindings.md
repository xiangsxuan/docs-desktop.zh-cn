---
title: 如何：清除绑定
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
ms.openlocfilehash: ab89c185d1b45ab49e680135ca4c1d54395fe0f4
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973091"
---
# <a name="how-to-clear-bindings"></a><span data-ttu-id="49e0a-102">如何：清除绑定</span><span class="sxs-lookup"><span data-stu-id="49e0a-102">How to: Clear Bindings</span></span>
<span data-ttu-id="49e0a-103">此示例演示如何从对象中清除绑定。</span><span class="sxs-lookup"><span data-stu-id="49e0a-103">This example shows how to clear bindings from an object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49e0a-104">示例</span><span class="sxs-lookup"><span data-stu-id="49e0a-104">Example</span></span>  
 <span data-ttu-id="49e0a-105">若要从对象的单个属性中清除绑定，请调用， <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> 如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="49e0a-105">To clear a binding from an individual property on an object, call <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> as shown in the following example.</span></span> <span data-ttu-id="49e0a-106">下面的示例从 mytext 的中删除 <xref:System.Windows.Controls.TextBlock.TextProperty> 了一个对象的绑定 <xref:System.Windows.Controls.TextBlock> 。</span><span class="sxs-lookup"><span data-stu-id="49e0a-106">The following example removes the binding from the <xref:System.Windows.Controls.TextBlock.TextProperty> of *mytext*, a <xref:System.Windows.Controls.TextBlock> object.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 <span data-ttu-id="49e0a-107">清除绑定会移除绑定，这样依赖属性的值会更改为过去尚未绑定时的值。</span><span class="sxs-lookup"><span data-stu-id="49e0a-107">Clearing the binding removes the binding so that the value of the dependency property is changed to whatever it would have been without the binding.</span></span> <span data-ttu-id="49e0a-108">此值可以是默认值、继承值或来自数据模板绑定的值。</span><span class="sxs-lookup"><span data-stu-id="49e0a-108">This value could be a default value, an inherited value, or a value from a data template binding.</span></span>  
  
 <span data-ttu-id="49e0a-109">若要清除对象的所有可能属性的绑定，请使用 <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A> 。</span><span class="sxs-lookup"><span data-stu-id="49e0a-109">To clear bindings from all possible properties on an object, use <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49e0a-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49e0a-110">See also</span></span>

- <xref:System.Windows.Data.BindingOperations>
- [<span data-ttu-id="49e0a-111">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="49e0a-111">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="49e0a-112">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="49e0a-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
