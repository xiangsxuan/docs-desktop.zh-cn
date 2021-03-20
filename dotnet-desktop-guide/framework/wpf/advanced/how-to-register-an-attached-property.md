---
title: 如何：注册附加属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF], registering
- registering attached properties [WPF]
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
ms.openlocfilehash: 4793111e5aca841f63aa479924a3c8c6d020423f
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665856"
---
# <a name="how-to-register-an-attached-property"></a><span data-ttu-id="1b5b9-102">如何：注册附加属性</span><span class="sxs-lookup"><span data-stu-id="1b5b9-102">How to: Register an Attached Property</span></span>
<span data-ttu-id="1b5b9-103">此示例演示如何注册附加属性和提供公共访问器，以便可以在 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 和代码中使用该属性。</span><span class="sxs-lookup"><span data-stu-id="1b5b9-103">This example shows how to register an attached property and provide public accessors so that you can use the property in both [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] and code.</span></span> <span data-ttu-id="1b5b9-104">附加属性是由 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 定义的语法概念。</span><span class="sxs-lookup"><span data-stu-id="1b5b9-104">Attached properties are a syntax concept defined by [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="1b5b9-105">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 类型的大多数附加属性还作为依赖属性实现。</span><span class="sxs-lookup"><span data-stu-id="1b5b9-105">Most attached properties for [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] types are also implemented as dependency properties.</span></span> <span data-ttu-id="1b5b9-106">可以对任何类型使用依赖属性 <xref:System.Windows.DependencyObject> 。</span><span class="sxs-lookup"><span data-stu-id="1b5b9-106">You can use dependency properties on any <xref:System.Windows.DependencyObject> types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b5b9-107">示例</span><span class="sxs-lookup"><span data-stu-id="1b5b9-107">Example</span></span>  
 <span data-ttu-id="1b5b9-108">下面的示例演示如何使用方法将附加属性注册为依赖属性 <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 。</span><span class="sxs-lookup"><span data-stu-id="1b5b9-108">The following example shows how to register an attached property as a dependency property, by using the <xref:System.Windows.DependencyProperty.RegisterAttached%2A> method.</span></span> <span data-ttu-id="1b5b9-109">在其他类上使用属性时，提供程序类可以选择为适用的属性提供默认元数据，除非该类会重写元数据。</span><span class="sxs-lookup"><span data-stu-id="1b5b9-109">The provider class has the option of providing default metadata for the property that is applicable when the property is used on another class, unless that class overrides the metadata.</span></span> <span data-ttu-id="1b5b9-110">在此示例中，`IsBubbleSource` 属性的默认值设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="1b5b9-110">In this example, the default value of the `IsBubbleSource` property is set to `false`.</span></span>  
  
 <span data-ttu-id="1b5b9-111">附加属性（即使未注册为依赖属性）的提供程序类必须提供遵循 `Set`*[附加属性名称]* 和 `Get`*[附加属性名称]* 命名约定的静态 get 和 set 访问器。</span><span class="sxs-lookup"><span data-stu-id="1b5b9-111">The provider class for an attached property (even if it is not registered as a dependency property) must provide static get and set accessors that follow the naming convention `Set`*[AttachedPropertyName]* and `Get`*[AttachedPropertyName]*.</span></span> <span data-ttu-id="1b5b9-112">需要这些访问器目的是生效的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 读取器可以在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中将属性识别为特性，并解析相应的类型。</span><span class="sxs-lookup"><span data-stu-id="1b5b9-112">These accessors are required so that the acting [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] reader can recognize the property as an attribute in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] and resolve the appropriate types.</span></span>  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## <a name="see-also"></a><span data-ttu-id="1b5b9-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b5b9-113">See also</span></span>

- <xref:System.Windows.DependencyProperty>
- [<span data-ttu-id="1b5b9-114">依赖项属性概述</span><span class="sxs-lookup"><span data-stu-id="1b5b9-114">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="1b5b9-115">自定义依赖项属性</span><span class="sxs-lookup"><span data-stu-id="1b5b9-115">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="1b5b9-116">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="1b5b9-116">How-to Topics</span></span>](properties-how-to-topics.md)
