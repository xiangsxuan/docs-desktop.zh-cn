---
title: 如何：从已绑定的目标属性获取绑定对象
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: c528515124898c7deb6114e620ce21766123ab3c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974047"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a><span data-ttu-id="520d8-102">如何：从已绑定的目标属性获取绑定对象</span><span class="sxs-lookup"><span data-stu-id="520d8-102">How to: Get the Binding Object from a Bound Target Property</span></span>
<span data-ttu-id="520d8-103">本示例演示如何从数据绑定的目标属性获取绑定对象。</span><span class="sxs-lookup"><span data-stu-id="520d8-103">This example shows how to obtain the binding object from a data-bound target property.</span></span>

## <a name="example"></a><span data-ttu-id="520d8-104">示例</span><span class="sxs-lookup"><span data-stu-id="520d8-104">Example</span></span>
 <span data-ttu-id="520d8-105">可以执行以下操作来获取 <xref:System.Windows.Data.Binding> 对象：</span><span class="sxs-lookup"><span data-stu-id="520d8-105">You can do the following to get the <xref:System.Windows.Data.Binding> object:</span></span>

 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]

> [!NOTE]
> <span data-ttu-id="520d8-106">必须为所需的绑定指定依赖属性，因为目标对象的多个属性可能正在使用数据绑定。</span><span class="sxs-lookup"><span data-stu-id="520d8-106">You must specify the dependency property for the binding you want because it is possible that more than one property of the target object is using data binding.</span></span>

 <span data-ttu-id="520d8-107">或者，你可以获取， <xref:System.Windows.Data.BindingExpression> 然后获取属性的值 <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> 。</span><span class="sxs-lookup"><span data-stu-id="520d8-107">Alternatively, you can get the <xref:System.Windows.Data.BindingExpression> and then get the value of the <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> property.</span></span>

 <span data-ttu-id="520d8-108">有关完整示例，请参阅[绑定验证示例](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation)。</span><span class="sxs-lookup"><span data-stu-id="520d8-108">For the complete example see [Binding Validation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span></span>

> [!NOTE]
> <span data-ttu-id="520d8-109">如果绑定为 <xref:System.Windows.Data.MultiBinding> ，请使用 <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="520d8-109">If your binding is a <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="520d8-110">如果是 <xref:System.Windows.Data.PriorityBinding> ，请使用 <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="520d8-110">If it is a <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="520d8-111">如果不确定是否使用、或来绑定目标属性， <xref:System.Windows.Data.Binding> <xref:System.Windows.Data.MultiBinding> <xref:System.Windows.Data.PriorityBinding> 可以使用 <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="520d8-111">If you are uncertain whether the target property is bound using a <xref:System.Windows.Data.Binding>, a <xref:System.Windows.Data.MultiBinding>, or a <xref:System.Windows.Data.PriorityBinding>, you can use <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>.</span></span>

## <a name="see-also"></a><span data-ttu-id="520d8-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="520d8-112">See also</span></span>

- [<span data-ttu-id="520d8-113">在代码中创建绑定</span><span class="sxs-lookup"><span data-stu-id="520d8-113">Create a Binding in Code</span></span>](how-to-create-a-binding-in-code.md)
- [<span data-ttu-id="520d8-114">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="520d8-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
