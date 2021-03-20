---
title: 依赖项属性元数据
ms.date: 03/30/2017
helpviewer_keywords:
- APIs [WPF], metadata
- dependency properties [WPF], metadata
- metadata [WPF], for dependency properties
- overriding metadata [WPF]
ms.assetid: d01ed009-b722-41bf-b82f-fe1a8cdc50dd
ms.openlocfilehash: 68724937df38372ea9b8221ee527368590cb6602
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666077"
---
# <a name="dependency-property-metadata"></a>依赖项属性元数据
[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]属性系统包含一个元数据报告系统，该系统超出了可通过反射或常规公共语言运行时 (CLR) 特征报告的属性。 依赖属性的元数据还可以由定义依赖属性的类来唯一地分配，可以在依赖属性添加到另一个类时进行更改，可以由所有从定义基类继承依赖属性的派生类来明确地重写。  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>必备条件  
 本主题假定你从 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 类的现有依赖属性的使用者角度了解依赖属性，并且已阅读[依赖属性概述](dependency-properties-overview.md)。 若要理解本主题中的示例，还应当了解 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 并知道如何编写 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序。  
  
<a name="dp_metadata_contents"></a>
## <a name="how-dependency-property-metadata-is-used"></a>依赖属性元数据的使用方式  
 依赖属性的元数据作为一个对象存在，可以通过查询该对象来检查依赖属性的特征。 当属性系统处理任何给定的依赖属性时，也会经常访问这些元数据。 依赖属性的元数据对象可以包含以下类型的信息：  
  
- 依赖项属性的默认值，如果无法按本地值、样式、继承等来确定依赖项属性的其他值，则为。有关为依赖属性赋值时默认值如何参与属性系统所使用的优先级的详细讨论，请参阅 [依赖属性值优先级](dependency-property-value-precedence.md)。  
  
- 对影响每个所有者类型的强制行为或更改通知行为的回叫实现的引用。 请注意，这些回叫通常是用非公共访问级别定义的，因此，除非实际引用位于允许的访问范围内，否则通常无法从元数据获得这些引用。 有关依赖属性回叫的详细信息，请参阅[依赖属性回调和验证](dependency-property-callbacks-and-validation.md)。  
  
- 如果所讨论的依赖属性被视为一个 WPF 框架级别的属性，则元数据中可能包含 WPF 框架级别的依赖属性特征，这些特征报告各种服务（如 WPF 框架级别的布局引擎和属性继承逻辑）的信息和状态。 有关依赖属性元数据的这一方面的详细信息，请参阅[框架属性元数据](framework-property-metadata.md)。  
  
<a name="APIs"></a>
## <a name="metadata-apis"></a>元数据 API  
 报告属性系统使用的大多数元数据信息的类型是 <xref:System.Windows.PropertyMetadata> 类。 在向属性系统注册依赖属性时，可以选择指定元数据实例，并且可以为以下附加类型再次指定这些实例：将自身作为所有者添加的类型，或者重写它们从基类依赖属性定义继承的元数据的类型。  (在属性注册未指定元数据的情况下，将 <xref:System.Windows.PropertyMetadata> 使用该类的默认值创建默认值。 <xref:System.Windows.PropertyMetadata> 当调用 <xref:System.Windows.DependencyProperty.GetMetadata%2A> 从实例的依赖项属性获取元数据的各种重载时，将返回注册的元数据 ) <xref:System.Windows.DependencyObject> 。  
  
 <xref:System.Windows.PropertyMetadata>然后从派生类，以便为体系结构分部（如 WPF 框架级类）提供更具体的元数据。 <xref:System.Windows.UIPropertyMetadata> 添加动画报告，并 <xref:System.Windows.FrameworkPropertyMetadata> 提供上一节中提到的 WPF 框架级属性。 当注册依赖属性时，可以将它们注册到这些 <xref:System.Windows.PropertyMetadata> 派生类。 检查元数据时， <xref:System.Windows.PropertyMetadata> 可以将基类型强制转换为派生类，以便可以检查更具体的属性。  
  
> [!NOTE]
> 在此文档中，可以指定的属性特征 <xref:System.Windows.FrameworkPropertyMetadata> 有时被称为 "标志"。 当你创建新的元数据实例以便在依赖属性注册或元数据重写中使用时，你可以使用 flagwise 枚举指定这些值， <xref:System.Windows.FrameworkPropertyMetadataOptions> 然后提供可能连接到 <xref:System.Windows.FrameworkPropertyMetadata> 构造函数的枚举值。 但是，一旦构造后，这些选项特征在中 <xref:System.Windows.FrameworkPropertyMetadata> 作为一系列布尔属性公开，而不是构造枚举值。 使用布尔属性，可以检查每个条件，而不必为了获得感兴趣的信息而向按标志枚举值应用掩码。 构造函数使用串联以便 <xref:System.Windows.FrameworkPropertyMetadataOptions> 保持构造函数签名的长度合理，而实际构造的元数据公开了离散属性，使查询元数据更加直观。  
  
<a name="override_or_subclass"></a>
## <a name="when-to-override-metadata-when-to-derive-a-class"></a>何时重写元数据以及何时派生类  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 属性系统已经建立了如下功能：在不必完全重新实现依赖属性的情况下，更改依赖属性的某些特征。 这是通过为特定类型上所存在的依赖属性构造不同的属性元数据实例来完成的。 请注意，现有的大多数依赖属性都不是虚拟属性，因此，严格地说，只能通过隐藏现有成员来针对继承类“重新实现”依赖属性。  
  
 如果尝试对某个类型的依赖属性启用的方案不能通过修改现有依赖属性的特征来完成，则可能有必要创建一个派生类，然后为该派生类声明一个自定义依赖属性。 自定义依赖项属性的行为与 api 定义的依赖项属性的行为相同 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 有关自定义依赖属性的更多详细信息，请参阅[自定义依赖属性](custom-dependency-properties.md)。  
  
 不能重写的依赖属性的一个显著特征就是它的值类型。 如果要继承的依赖属性的行为与所需的行为大体相同，但是要求它具有另一种类型，则必须实现一个自定义依赖属性，可能还需要通过类型转换或其他实现机制在自定义类上链接这些属性。 此外，不能替换现有 <xref:System.Windows.ValidateValueCallback> 的，因为此回调存在于注册字段本身中，而不在其元数据中。  
  
<a name="scenarios"></a>
## <a name="scenarios-for-changing-existing-metadata"></a>更改现有元数据的方案  
 如果要处理现有依赖属性的元数据，则更改依赖属性元数据的一种常见方案是更改默认值。 更改或添加属性系统回叫是一种更高级的方案。 如果所实现的派生类的依赖属性之间具有不同的相互关系，则你可能希望这样做。 让编程模型既支持代码又支持声明性用法的条件之一就是，属性必须能够按任何顺序设置。 因此，需要在没有上下文的情况下实时设置任何依赖属性，而且可以不必知道设置顺序（例如，可能在构造函数中找到的顺序）。 有关属性系统这一方面的详细信息，请参阅[依赖属性回调和验证](dependency-property-callbacks-and-validation.md)。 请注意，验证回叫不是元数据的一部分，而是依赖属性标识符的一部分。 因此，不能通过重写元数据来更改验证回叫。  
  
 在某些情况下，可能还希望在现有的依赖属性上改变 WPF 框架级别的属性元数据选项。 这些选项将有关 WPF 框架级别属性的某些已知条件传递到其他 WPF 框架级别的进程，例如布局系统。  通常，仅当注册新的依赖属性时才会设置选项，但也可以将 WPF 框架级别的属性元数据作为或调用的一部分进行 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 更改 <xref:System.Windows.DependencyProperty.AddOwner%2A> 。 有关要使用的特定值以及详细信息，请参阅[框架属性元数据](framework-property-metadata.md)。 有关应当如何为新注册的依赖属性设置这些选项的详细信息，请参阅[自定义依赖属性](custom-dependency-properties.md)。  
  
<a name="dp_override_metadata"></a>
### <a name="overriding-metadata"></a>重写元数据  
 重写元数据的主要目的在于，使你有机会更改各种派生自元数据的行为，这些行为应用于类型上存在的依赖属性。 [元数据](#dp_metadata_contents)一节中更详细地介绍了重写元数据的原因。 有关详细信息（包括一些代码示例），请参阅[重写依赖属性的元数据](how-to-override-metadata-for-a-dependency-property.md)。  
  
 可以在注册调用期间为依赖属性提供属性元数据， (<xref:System.Windows.DependencyProperty.Register%2A>) 。 但是，在许多情况下，当类继承该依赖属性时，你可能希望为该类提供特定于类型的元数据。 可以通过调用方法来执行此操作 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 。  对于来自 api 的示例 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ， <xref:System.Windows.FrameworkElement> 类是第一次注册依赖属性的类型 <xref:System.Windows.UIElement.Focusable%2A> 。 但是， <xref:System.Windows.Controls.Control> 类会重写依赖属性的元数据，以提供其自己的初始默认值，将其从更改 `false` 为 `true` ，否则会重新使用原始 <xref:System.Windows.UIElement.Focusable%2A> 实现。  
  
 当你重写元数据时，系统会合并或替换不同的元数据特征。  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 合并。 如果添加新 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 的，则该回调将存储在元数据中。 如果未 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 在重写中指定，则的值 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 将从在元数据中指定的最接近的上级中升级为引用。  
  
- 的实际属性系统行为 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 是：在层次结构中的所有元数据所有者的实现将被保留并添加到表中，属性系统执行顺序是首先调用派生程度最高的派生类的回调。  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A> 被替换。 如果未 <xref:System.Windows.PropertyMetadata.DefaultValue%2A> 在重写中指定，则的值来自在 <xref:System.Windows.PropertyMetadata.DefaultValue%2A> 元数据中指定它的最近上级。  
  
- <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 替换实现。 如果添加新 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 的，则该回调将存储在元数据中。 如果未 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 在重写中指定，则的值 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 将从在元数据中指定的最接近的上级中升级为引用。  
  
- 属性系统行为是只 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 调用直接元数据中的。 不 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 会保留对层次结构中的其他实现的引用。  
  
 此行为由实现 <xref:System.Windows.PropertyMetadata.Merge%2A> ，并且可在派生的元数据类上重写。  
  
#### <a name="overriding-attached-property-metadata"></a>重写附加属性元数据  
 在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 中，附加属性作为依赖属性来实现。 这意味着它们还具有能够由个别类重写的属性元数据。 中附加属性的作用域注意事项 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 通常是在 <xref:System.Windows.DependencyObject> 其上设置附加属性。 因此，任何 <xref:System.Windows.DependencyObject> 派生类都可以重写任何附加属性的元数据，因为它可能是在类的实例上设置的。 可以重写默认值、回叫或 WPF 框架级别的特征报告属性。 如果针对类的实例设置了附加属性，则这些重写属性元数据特征将适用。 例如，可以重写默认值，这样，只要未以其他方式设置附加属性，重写值就会报告为类实例的附加属性的值。  
  
> [!NOTE]
> <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>属性与附加属性无关。  
  
<a name="dp_add_owner"></a>
### <a name="adding-a-class-as-an-owner-of-an-existing-dependency-property"></a>将类作为现有依赖属性的所有者来添加  
 类可以使用方法将自身添加为已注册的依赖属性的所有者 <xref:System.Windows.DependencyProperty.AddOwner%2A> 。 这使得该类可以使用最初针对另一个类型注册的依赖属性。 添加类通常不是首先将该依赖属性注册为所有者的类型的派生类。 实际上，这使类及其派生类可以“继承”依赖属性实现，而不需要最初的所有者类，而且添加类也不必位于同一个实际的类层次结构中。 另外，添加类（以及所有派生类）随后可以为最初的依赖属性提供特定于类型的元数据。  
  
 添加类除了通过属性系统的实用工具方法将自身添加为所有者以外，还应当在自身声明其他公共成员，以使依赖属性向代码和标记公开，从而完全参与属性系统。 就为依赖属性公开对象模型而言，添加现有依赖属性的类与定义新的自定义依赖属性的类具有相同的职责。 要公开的第一个此类成员是依赖属性标识符字段。 此字段应为 `public static readonly` 类型为的字段 <xref:System.Windows.DependencyProperty> ，该字段将分配给调用的返回值 <xref:System.Windows.DependencyProperty.AddOwner%2A> 。 要定义的第二个成员是公共语言运行时 (CLR) "包装器" 属性。 包装使你可以更方便地在代码中操作依赖属性 (避免 <xref:System.Windows.DependencyObject.SetValue%2A> 每次调用，并可以在包装器自身) 只调用一次。 包装器的实现方式与在注册自定义依赖属性时的实现方式完全相同。 有关实现依赖属性的详细信息，请参阅[自定义依赖属性](custom-dependency-properties.md)和[为依赖属性添加所有者类型](how-to-add-an-owner-type-for-a-dependency-property.md)。  
  
#### <a name="addowner-and-attached-properties"></a>AddOwner 和附加属性  
 可以调用 <xref:System.Windows.DependencyProperty.AddOwner%2A> 由所有者类定义为附加属性的依赖属性。 这样做的目的通常是为了将以前附加的属性作为非附加依赖属性来公开。 然后，你会将 <xref:System.Windows.DependencyProperty.AddOwner%2A> 返回值公开为用作 `public static readonly` 依赖项属性标识符的字段，并将定义适当的 "包装器" 属性，以便属性显示在成员表中并支持类中的非附加属性用法。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.PropertyMetadata>
- <xref:System.Windows.DependencyObject>
- <xref:System.Windows.DependencyProperty>
- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [依赖项属性概述](dependency-properties-overview.md)
- [框架属性元数据](framework-property-metadata.md)
