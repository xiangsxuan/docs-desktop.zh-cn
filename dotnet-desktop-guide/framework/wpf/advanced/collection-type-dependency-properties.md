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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971957"
---
# <a name="collection-type-dependency-properties"></a>集合类型依赖项属性
本主题就如何实现属性类型为集合类型的依赖属性提供相应指导和建议模式。  

<a name="implementing"></a>
## <a name="implementing-a-collection-type-dependency-property"></a>实现集合类型依赖属性  
 通常，对于依赖属性，你遵循的实现模式是定义 CLR 属性包装器，其中该属性是由 <xref:System.Windows.DependencyProperty> 标识符而不是字段或其他构造提供支持的。 实现集合类型属性时也应按照此相同模式。 但是，只要集合中包含的类型本身就是 <xref:System.Windows.DependencyObject> 或派生类，集合类型属性就会给模式带来一些复杂性 <xref:System.Windows.Freezable> 。  
  
<a name="initializing"></a>
## <a name="initializing-the-collection-beyond-the-default-value"></a>不使用默认值初始化集合  
 创建依赖属性时，不要将属性默认值指定为初始字段值。 相反，应通过依赖属性元数据指定默认值。 如果属性为引用类型，则依赖属性元数据中指定的默认值不是每个实例分别的默认值，而是应用到类型的所有实例的默认值。 因此，对于类型的新创建实例，必须小心，不要将集合属性元数据定义的单个静态集合用作工作默认值。 相反，必须确保有意将集合值设置为唯一（实例）集合，作为类构造函数逻辑的一部分。 否则，你会创建一个不需要的单例类。  
  
 请考虑以下示例。 下面的示例部分演示了一个类的定义，该类 `Aquarium` 包含一个具有默认值的漏洞。 类定义集合类型依赖项属性，该属性 `AquariumObjects` 使用 <xref:System.Collections.Generic.List%601> 具有类型约束的泛型类型 <xref:System.Windows.FrameworkElement> 。 在对 <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29> 依赖项属性的调用中，元数据将默认值建立为新的泛型 <xref:System.Collections.Generic.List%601> 。

> [!WARNING]
> 以下代码的行为不正确。

 [!code-csharp[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport2/CSharp/page.xaml.cs#collectionproblemdefinition)]
 [!code-vb[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport2/visualbasic/page.xaml.vb#collectionproblemdefinition)]  
  
 但是，如果仅如上所示保留代码，该单一列表默认值会对 `Aquarium` 的所有实例共享。 如果运行以下测试代码（用于演示如何实例化两个单独的 `Aquarium` 实例并向二者皆添加一个不同的 `Fish`），则其结果可能出乎意料：  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 每个集合具有两个计数，而不是一个！ 这是因为，每个 `Aquarium` 将其 `Fish` 添加到默认值集合，此默认值集合因元数据中单个构造函数调用而产生，因此会在所有实例之间共享。 而你全然不希望出现这种情况。  
  
 为纠正此问题，必须将集合依赖属性值重置为唯一实例，作为类构造函数调用的一部分。 由于属性是只读依赖属性，因此可以使用 <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> 方法对其进行设置，方法是使用只能在 <xref:System.Windows.DependencyPropertyKey> 类中访问的。  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 现在，如果再次运行此相同测试代码，则每个 `Aquarium` 会仅支持自己的唯一集合，这样的结果更符合预期。  
  
 如果选择集合属性为读写，则此模式会稍有变化。 在这种情况下，你可以从构造函数调用公共集访问器来执行初始化，这仍将 <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> 使用公共标识符在你的集包装内调用的非键签名 <xref:System.Windows.DependencyProperty> 。  
  
## <a name="reporting-binding-value-changes-from-collection-properties"></a>报告集合属性中的绑定值更改  
 本身为依赖属性的集合属性不会自动将更改报告给其子属性。 如果将绑定创建到集合，这可阻止绑定报告更改，从而使某些数据绑定方案无效。 但是，如果使用集合类型 <xref:System.Windows.FreezableCollection%601> 作为集合类型，则会正确报告集合中包含的元素的子属性更改，并且绑定将按预期方式工作。  
  
 若要启用依赖项对象集合中的子属性绑定，请创建类型为的集合属性 <xref:System.Windows.FreezableCollection%601> ，并将该集合的类型约束为任何 <xref:System.Windows.DependencyObject> 派生类。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.FreezableCollection%601>
- [XAML 及 WPF 的自定义类](xaml-and-custom-classes-for-wpf.md)
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [依赖项属性概述](dependency-properties-overview.md)
- [自定义依赖项属性](custom-dependency-properties.md)
- [依赖项属性元数据](dependency-property-metadata.md)
