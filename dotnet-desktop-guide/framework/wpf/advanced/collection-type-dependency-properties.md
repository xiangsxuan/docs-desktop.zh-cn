---
title: 集合类型依赖项属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [WPF], dependency
- properties [WPF], collection-type
- dependency properties [WPF]
- collection-type properties [WPF]
ms.assetid: 99f96a42-3ab7-4f64-a16b-2e10d654e97c
ms.openlocfilehash: 8da798b3d7254d10d8da7ca6df335f63e4890763
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971957"
---
# <a name="collection-type-dependency-properties"></a><span data-ttu-id="6e760-102">集合类型依赖项属性</span><span class="sxs-lookup"><span data-stu-id="6e760-102">Collection-Type Dependency Properties</span></span>
<span data-ttu-id="6e760-103">本主题就如何实现属性类型为集合类型的依赖属性提供相应指导和建议模式。</span><span class="sxs-lookup"><span data-stu-id="6e760-103">This topic provides guidance and suggested patterns for how to implement a dependency property where the type of the property is a collection type.</span></span>  

<a name="implementing"></a>
## <a name="implementing-a-collection-type-dependency-property"></a><span data-ttu-id="6e760-104">实现集合类型依赖属性</span><span class="sxs-lookup"><span data-stu-id="6e760-104">Implementing a Collection-Type Dependency Property</span></span>  
 <span data-ttu-id="6e760-105">通常，对于依赖属性，你遵循的实现模式是定义 CLR 属性包装器，其中该属性是由 <xref:System.Windows.DependencyProperty> 标识符而不是字段或其他构造提供支持的。</span><span class="sxs-lookup"><span data-stu-id="6e760-105">For a dependency property in general, the implementation pattern that you follow is that you define a CLR property wrapper, where that property is backed by a <xref:System.Windows.DependencyProperty> identifier rather than a field or other construct.</span></span> <span data-ttu-id="6e760-106">实现集合类型属性时也应按照此相同模式。</span><span class="sxs-lookup"><span data-stu-id="6e760-106">You follow this same pattern when you implement a collection-type property.</span></span> <span data-ttu-id="6e760-107">但是，只要集合中包含的类型本身就是 <xref:System.Windows.DependencyObject> 或派生类，集合类型属性就会给模式带来一些复杂性 <xref:System.Windows.Freezable> 。</span><span class="sxs-lookup"><span data-stu-id="6e760-107">However, a collection-type property introduces some complexity to the pattern whenever the type that is contained within the collection is itself a <xref:System.Windows.DependencyObject> or <xref:System.Windows.Freezable> derived class.</span></span>  
  
<a name="initializing"></a>
## <a name="initializing-the-collection-beyond-the-default-value"></a><span data-ttu-id="6e760-108">不使用默认值初始化集合</span><span class="sxs-lookup"><span data-stu-id="6e760-108">Initializing the Collection Beyond the Default Value</span></span>  
 <span data-ttu-id="6e760-109">创建依赖属性时，不要将属性默认值指定为初始字段值。</span><span class="sxs-lookup"><span data-stu-id="6e760-109">When you create a dependency property, you do not specify the property default value as the initial field value.</span></span> <span data-ttu-id="6e760-110">相反，应通过依赖属性元数据指定默认值。</span><span class="sxs-lookup"><span data-stu-id="6e760-110">Instead, you specify the default value through the dependency property metadata.</span></span> <span data-ttu-id="6e760-111">如果属性为引用类型，则依赖属性元数据中指定的默认值不是每个实例分别的默认值，而是应用到类型的所有实例的默认值。</span><span class="sxs-lookup"><span data-stu-id="6e760-111">If your property is a reference type, the default value specified in dependency property metadata is not a default value per instance; instead it is a default value that applies to all instances of the type.</span></span> <span data-ttu-id="6e760-112">因此，对于类型的新创建实例，必须小心，不要将集合属性元数据定义的单个静态集合用作工作默认值。</span><span class="sxs-lookup"><span data-stu-id="6e760-112">Therefore you must be careful to not use the singular static collection defined by the collection property metadata as the working default value for newly created instances of your type.</span></span> <span data-ttu-id="6e760-113">相反，必须确保有意将集合值设置为唯一（实例）集合，作为类构造函数逻辑的一部分。</span><span class="sxs-lookup"><span data-stu-id="6e760-113">Instead, you must make sure that you deliberately set the collection value to a unique (instance) collection as part of your class constructor logic.</span></span> <span data-ttu-id="6e760-114">否则，你会创建一个不需要的单例类。</span><span class="sxs-lookup"><span data-stu-id="6e760-114">Otherwise you will have created an unintentional singleton class.</span></span>  
  
 <span data-ttu-id="6e760-115">请看下面的示例。</span><span class="sxs-lookup"><span data-stu-id="6e760-115">Consider the following example.</span></span> <span data-ttu-id="6e760-116">下面的示例部分演示了一个类的定义，该类 `Aquarium` 包含一个具有默认值的漏洞。</span><span class="sxs-lookup"><span data-stu-id="6e760-116">The following section of the example shows the definition for a class `Aquarium`, which contains a flaw with the default value.</span></span> <span data-ttu-id="6e760-117">类定义集合类型依赖项属性，该属性 `AquariumObjects` 使用 <xref:System.Collections.Generic.List%601> 具有类型约束的泛型类型 <xref:System.Windows.FrameworkElement> 。</span><span class="sxs-lookup"><span data-stu-id="6e760-117">The class defines the collection type dependency property `AquariumObjects`, which uses the generic <xref:System.Collections.Generic.List%601> type with a <xref:System.Windows.FrameworkElement> type constraint.</span></span> <span data-ttu-id="6e760-118">在对 <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29> 依赖项属性的调用中，元数据将默认值建立为新的泛型 <xref:System.Collections.Generic.List%601> 。</span><span class="sxs-lookup"><span data-stu-id="6e760-118">In the <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29> call for the dependency property, the metadata establishes the default value to be a new generic <xref:System.Collections.Generic.List%601>.</span></span>

> [!WARNING]
> <span data-ttu-id="6e760-119">以下代码的行为不正确。</span><span class="sxs-lookup"><span data-stu-id="6e760-119">The following code does not behave correctly.</span></span>

 [!code-csharp[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport2/CSharp/page.xaml.cs#collectionproblemdefinition)]
 [!code-vb[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport2/visualbasic/page.xaml.vb#collectionproblemdefinition)]  
  
 <span data-ttu-id="6e760-120">但是，如果仅如上所示保留代码，该单一列表默认值会对 `Aquarium` 的所有实例共享。</span><span class="sxs-lookup"><span data-stu-id="6e760-120">However, if you just left the code as shown, that single list default value is shared for all instances of `Aquarium`.</span></span> <span data-ttu-id="6e760-121">如果运行以下测试代码（用于演示如何实例化两个单独的 `Aquarium` 实例并向二者皆添加一个不同的 `Fish`），则其结果可能出乎意料：</span><span class="sxs-lookup"><span data-stu-id="6e760-121">If you ran the following test code, which is intended to show how you would instantiate two separate `Aquarium` instances and add a single different `Fish` to each of them, you would see a surprising result:</span></span>  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 <span data-ttu-id="6e760-122">每个集合具有两个计数，而不是一个！</span><span class="sxs-lookup"><span data-stu-id="6e760-122">Instead of each collection having a count of one, each collection has a count of two!</span></span> <span data-ttu-id="6e760-123">这是因为，每个 `Aquarium` 将其 `Fish` 添加到默认值集合，此默认值集合因元数据中单个构造函数调用而产生，因此会在所有实例之间共享。</span><span class="sxs-lookup"><span data-stu-id="6e760-123">This is because each `Aquarium` added its `Fish` to the default value collection, which resulted from a single constructor call in the metadata and is therefore shared between all instances.</span></span> <span data-ttu-id="6e760-124">而你全然不希望出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="6e760-124">This situation is almost never what you want.</span></span>  
  
 <span data-ttu-id="6e760-125">为纠正此问题，必须将集合依赖属性值重置为唯一实例，作为类构造函数调用的一部分。</span><span class="sxs-lookup"><span data-stu-id="6e760-125">To correct this problem, you must reset the collection dependency property value to a unique instance, as part of the class constructor call.</span></span> <span data-ttu-id="6e760-126">由于属性是只读依赖属性，因此可以使用 <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> 方法对其进行设置，方法是使用只能在 <xref:System.Windows.DependencyPropertyKey> 类中访问的。</span><span class="sxs-lookup"><span data-stu-id="6e760-126">Because the property is a read-only dependency property, you use the <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> method to set it, using the <xref:System.Windows.DependencyPropertyKey> that is only accessible within the class.</span></span>  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 <span data-ttu-id="6e760-127">现在，如果再次运行此相同测试代码，则每个 `Aquarium` 会仅支持自己的唯一集合，这样的结果更符合预期。</span><span class="sxs-lookup"><span data-stu-id="6e760-127">Now, if you ran that same test code again, you could see more expected results, where each `Aquarium` supported its own unique collection.</span></span>  
  
 <span data-ttu-id="6e760-128">如果选择集合属性为读写，则此模式会稍有变化。</span><span class="sxs-lookup"><span data-stu-id="6e760-128">There would be a slight variation on this pattern if you chose to have your collection property be read-write.</span></span> <span data-ttu-id="6e760-129">在这种情况下，你可以从构造函数调用公共集访问器来执行初始化，这仍将 <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> 使用公共标识符在你的集包装内调用的非键签名 <xref:System.Windows.DependencyProperty> 。</span><span class="sxs-lookup"><span data-stu-id="6e760-129">In that case, you could call the public set accessor from the constructor to do the initialization, which would still be calling the nonkey signature of <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> within your set wrapper, using a public <xref:System.Windows.DependencyProperty> identifier.</span></span>  
  
## <a name="reporting-binding-value-changes-from-collection-properties"></a><span data-ttu-id="6e760-130">报告集合属性中的绑定值更改</span><span class="sxs-lookup"><span data-stu-id="6e760-130">Reporting Binding Value Changes from Collection Properties</span></span>  
 <span data-ttu-id="6e760-131">本身为依赖属性的集合属性不会自动将更改报告给其子属性。</span><span class="sxs-lookup"><span data-stu-id="6e760-131">A collection property that is itself a dependency property does not automatically report changes to its subproperties.</span></span> <span data-ttu-id="6e760-132">如果将绑定创建到集合，这可阻止绑定报告更改，从而使某些数据绑定方案无效。</span><span class="sxs-lookup"><span data-stu-id="6e760-132">If you are creating bindings into a collection, this can prevent the binding from reporting changes, thus invalidating some data binding scenarios.</span></span> <span data-ttu-id="6e760-133">但是，如果使用集合类型 <xref:System.Windows.FreezableCollection%601> 作为集合类型，则会正确报告集合中包含的元素的子属性更改，并且绑定将按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="6e760-133">However, if you use the collection type <xref:System.Windows.FreezableCollection%601> as your collection type, then subproperty changes to contained elements in the collection are properly reported, and binding works as expected.</span></span>  
  
 <span data-ttu-id="6e760-134">若要启用依赖项对象集合中的子属性绑定，请创建类型为的集合属性 <xref:System.Windows.FreezableCollection%601> ，并将该集合的类型约束为任何 <xref:System.Windows.DependencyObject> 派生类。</span><span class="sxs-lookup"><span data-stu-id="6e760-134">To enable subproperty binding in a dependency object collection, create the collection property as type <xref:System.Windows.FreezableCollection%601>, with a type constraint for that collection to any <xref:System.Windows.DependencyObject> derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e760-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e760-135">See also</span></span>

- <xref:System.Windows.FreezableCollection%601>
- [<span data-ttu-id="6e760-136">XAML 及 WPF 的自定义类</span><span class="sxs-lookup"><span data-stu-id="6e760-136">XAML and Custom Classes for WPF</span></span>](xaml-and-custom-classes-for-wpf.md)
- [<span data-ttu-id="6e760-137">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="6e760-137">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="6e760-138">依赖项属性概述</span><span class="sxs-lookup"><span data-stu-id="6e760-138">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="6e760-139">自定义依赖项属性</span><span class="sxs-lookup"><span data-stu-id="6e760-139">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="6e760-140">依赖项属性元数据</span><span class="sxs-lookup"><span data-stu-id="6e760-140">Dependency Property Metadata</span></span>](dependency-property-metadata.md)
