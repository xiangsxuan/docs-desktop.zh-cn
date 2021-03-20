---
title: 如何：重写依赖属性的元数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [WPF], overriding for dependency properties
- dependency properties [WPF], overriding metadata for
- overriding metadata for dependency properties [WPF]
ms.assetid: f90f026e-60d8-428a-933d-edf0dba4441f
ms.openlocfilehash: 754ecee603e44356a362161b489eb3c962988f7f
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665869"
---
# <a name="how-to-override-metadata-for-a-dependency-property"></a><span data-ttu-id="24335-102">如何：重写依赖属性的元数据</span><span class="sxs-lookup"><span data-stu-id="24335-102">How to: Override Metadata for a Dependency Property</span></span>
<span data-ttu-id="24335-103">此示例演示如何通过调用 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 方法并提供特定于类型的元数据，来重写来自继承类的默认依赖项属性元数据。</span><span class="sxs-lookup"><span data-stu-id="24335-103">This example shows how to override default dependency property metadata that comes from an inherited class, by calling the <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> method and providing type-specific metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24335-104">示例</span><span class="sxs-lookup"><span data-stu-id="24335-104">Example</span></span>  
 <span data-ttu-id="24335-105">通过定义 <xref:System.Windows.PropertyMetadata> 类，类可以定义依赖属性的行为，例如其默认值和属性系统回调。</span><span class="sxs-lookup"><span data-stu-id="24335-105">By defining its <xref:System.Windows.PropertyMetadata>, a class can define the dependency property's behaviors, such as its default value and property system callbacks.</span></span> <span data-ttu-id="24335-106">很多依赖属性类都已经将默认元数据创建为其注册过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="24335-106">Many dependency property classes already have default metadata established as part of their registration process.</span></span> <span data-ttu-id="24335-107">这包括作为 API 一部分的依赖项属性 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="24335-107">This includes the dependency properties that are part of the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] API.</span></span> <span data-ttu-id="24335-108">通过其类继承继承依赖属性的类可重写原始的元数据，以便可通过元数据更改的属性的特征与任何特定于子类的要求相匹配。</span><span class="sxs-lookup"><span data-stu-id="24335-108">A class that inherits the dependency property through its class inheritance can override the original metadata so that the characteristics of the property that can be altered through metadata will match any subclass-specific requirements.</span></span>  
  
 <span data-ttu-id="24335-109">在依赖属性上重写元数据的操作必须在属性系统使用该属性之前进行，也就是说，在对注册属性的对象的特定实例进行实例化之前进行。</span><span class="sxs-lookup"><span data-stu-id="24335-109">Overriding metadata on a dependency property must be done prior to that property being placed in use by the property system (this equates to the time that specific instances of objects that register the property are instantiated).</span></span> <span data-ttu-id="24335-110">对的调用 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 必须在提供自身作为参数的类型的静态构造函数中进行 `forType` <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 。</span><span class="sxs-lookup"><span data-stu-id="24335-110">Calls to <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> must be performed within the static constructors of the type that provides itself as the `forType` parameter of <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>.</span></span> <span data-ttu-id="24335-111">所有者类型的实例存在之后尝试更改元数据不会引发异常，但会在属性系统中导致不一致的行为。</span><span class="sxs-lookup"><span data-stu-id="24335-111">If you attempt to change metadata once instances of the owner type exist, this will not raise exceptions, but will result in inconsistent behaviors in the property system.</span></span> <span data-ttu-id="24335-112">此外，每种类型只可以重写一次元数据。</span><span class="sxs-lookup"><span data-stu-id="24335-112">Also, metadata can only be overridden once per type.</span></span> <span data-ttu-id="24335-113">以后在同一类型上重写元数据的尝试会引发异常。</span><span class="sxs-lookup"><span data-stu-id="24335-113">Subsequent attempts to override metadata on the same type will raise an exception.</span></span>  
  
 <span data-ttu-id="24335-114">在下面示例中，自定义类 `MyAdvancedStateControl` 重写了由带有新属性元数据的 `MyAdvancedStateControl` 为 `StateProperty` 提供的元数据。</span><span class="sxs-lookup"><span data-stu-id="24335-114">In the following example, the custom class `MyAdvancedStateControl` overrides the metadata provided for `StateProperty` by `MyAdvancedStateControl` with new property metadata.</span></span> <span data-ttu-id="24335-115">例如，在新构造的 `MyAdvancedStateControl` 实例上查询 `StateProperty` 时，其默认值现在是 `true`。</span><span class="sxs-lookup"><span data-stu-id="24335-115">For instance, the default value of the `StateProperty` is now `true` when the property is queried on a newly constructed `MyAdvancedStateControl` instance.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#MyAdvancedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#myadvancedstatecontrol)]
[!code-vb[PropertySystemEsoterics#MyAdvancedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#myadvancedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="24335-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="24335-116">See also</span></span>

- <xref:System.Windows.DependencyProperty>
- [<span data-ttu-id="24335-117">依赖项属性概述</span><span class="sxs-lookup"><span data-stu-id="24335-117">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="24335-118">自定义依赖项属性</span><span class="sxs-lookup"><span data-stu-id="24335-118">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="24335-119">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="24335-119">How-to Topics</span></span>](properties-how-to-topics.md)
