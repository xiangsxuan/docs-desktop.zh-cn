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
# <a name="how-to-override-metadata-for-a-dependency-property"></a>如何：重写依赖属性的元数据
此示例演示如何通过调用 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 方法并提供特定于类型的元数据，来重写来自继承类的默认依赖项属性元数据。  
  
## <a name="example"></a>示例  
 通过定义 <xref:System.Windows.PropertyMetadata> 类，类可以定义依赖属性的行为，例如其默认值和属性系统回调。 很多依赖属性类都已经将默认元数据创建为其注册过程的一部分。 这包括作为 API 一部分的依赖项属性 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 通过其类继承继承依赖属性的类可重写原始的元数据，以便可通过元数据更改的属性的特征与任何特定于子类的要求相匹配。  
  
 在依赖属性上重写元数据的操作必须在属性系统使用该属性之前进行，也就是说，在对注册属性的对象的特定实例进行实例化之前进行。 对的调用 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 必须在提供自身作为参数的类型的静态构造函数中进行 `forType` <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 。 所有者类型的实例存在之后尝试更改元数据不会引发异常，但会在属性系统中导致不一致的行为。 此外，每种类型只可以重写一次元数据。 以后在同一类型上重写元数据的尝试会引发异常。  
  
 在下面示例中，自定义类 `MyAdvancedStateControl` 重写了由带有新属性元数据的 `MyAdvancedStateControl` 为 `StateProperty` 提供的元数据。 例如，在新构造的 `MyAdvancedStateControl` 实例上查询 `StateProperty` 时，其默认值现在是 `true`。  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#MyAdvancedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#myadvancedstatecontrol)]
[!code-vb[PropertySystemEsoterics#MyAdvancedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#myadvancedstatecontrol)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.DependencyProperty>
- [依赖项属性概述](dependency-properties-overview.md)
- [自定义依赖项属性](custom-dependency-properties.md)
- [操作指南主题](properties-how-to-topics.md)
