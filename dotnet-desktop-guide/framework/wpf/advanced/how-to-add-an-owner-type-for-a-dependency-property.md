---
title: 如何：为依赖项属性添加所有者类型
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
ms.openlocfilehash: 5866d8b57f7a1a5cce271c9e6529de66f3984065
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665973"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>如何：为依赖项属性添加所有者类型
此示例演示如何将类添加为为不同类型注册的依赖项属性的所有者。 通过执行此操作， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 读取器和属性系统都能将该类识别为属性的其他所有者。 添加为所有者可以选择允许添加类提供特定于类型的元数据。  
  
 在下面的示例中， `StateProperty` 是由类注册的属性 `MyStateControl` 。 类 `UnrelatedStateControl` 使用方法将自身添加为的所有者 `StateProperty` <xref:System.Windows.DependencyProperty.AddOwner%2A> ，特别是使用签名，该签名允许依赖项属性的新元数据，因为它存在于添加类型中。 请注意，应为属性提供公共语言运行时 (CLR) 访问器，此属性类似于 [实现依赖项属性](how-to-implement-a-dependency-property.md) 示例中所示的示例，并对作为所有者添加的类重新公开依赖属性标识符。  
  
 如果不使用包装，依赖属性仍将从使用或的编程访问角度来处理 <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> 。 但是，您通常需要将此属性系统行为与 CLR 属性包装器进行并行处理。 利用这些包装，可以以编程方式轻松设置依赖属性，并可以将属性设置为 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 属性。  
  
 若要了解如何重写默认元数据，请参阅 [重写依赖属性的元数据](how-to-override-metadata-for-a-dependency-property.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>请参阅

- [自定义依赖项属性](custom-dependency-properties.md)
- [依赖项属性概述](dependency-properties-overview.md)
