---
title: 如何：根据绑定项列表生成值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: ab030fbf4335a5bfd12834cb7b19c280487dc2f7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970485"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a>如何：根据绑定项列表生成值
<xref:System.Windows.Data.MultiBinding> 允许您将绑定目标属性绑定到源属性列表，然后应用逻辑以生成具有给定输入的值。 此示例演示如何使用 <xref:System.Windows.Data.MultiBinding> 。  
  
## <a name="example"></a>示例  
 在下面的示例中，`NameListData` 引用包含 `firstName` 和 `lastName` 这两个属性的 `PersonName` 对象的集合。 下面的示例生成一个 <xref:System.Windows.Controls.TextBlock> ，它显示姓氏为姓的人员的名字和姓氏。  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 为了了解如何生成姓氏在前的格式，我们来了解一下 `NameConverter` 的实现：  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 `NameConverter` 实现 <xref:System.Windows.Data.IMultiValueConverter> 接口。 `NameConverter` 从个别绑定获取值并将其存储在值对象数组中。 元素 <xref:System.Windows.Data.Binding> 在元素下的显示顺序 <xref:System.Windows.Data.MultiBinding> 就是这些值在数组中的存储顺序。 特性的值 <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> 由方法的参数参数引用，该参数对 <xref:System.Windows.Data.MultiBinding.Converter%2A> 参数执行开关来确定如何设置名称的格式。  
  
## <a name="see-also"></a>另请参阅

- [转换绑定数据](how-to-convert-bound-data.md)
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [操作指南主题](data-binding-how-to-topics.md)
