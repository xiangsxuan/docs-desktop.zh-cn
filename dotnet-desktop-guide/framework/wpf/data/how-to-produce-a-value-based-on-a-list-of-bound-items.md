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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970485"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="4f00d-102">如何：根据绑定项列表生成值</span><span class="sxs-lookup"><span data-stu-id="4f00d-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<span data-ttu-id="4f00d-103"><xref:System.Windows.Data.MultiBinding> 允许您将绑定目标属性绑定到源属性列表，然后应用逻辑以生成具有给定输入的值。</span><span class="sxs-lookup"><span data-stu-id="4f00d-103"><xref:System.Windows.Data.MultiBinding> allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="4f00d-104">此示例演示如何使用 <xref:System.Windows.Data.MultiBinding> 。</span><span class="sxs-lookup"><span data-stu-id="4f00d-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f00d-105">示例</span><span class="sxs-lookup"><span data-stu-id="4f00d-105">Example</span></span>  
 <span data-ttu-id="4f00d-106">在下面的示例中，`NameListData` 引用包含 `firstName` 和 `lastName` 这两个属性的 `PersonName` 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="4f00d-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="4f00d-107">下面的示例生成一个 <xref:System.Windows.Controls.TextBlock> ，它显示姓氏为姓的人员的名字和姓氏。</span><span class="sxs-lookup"><span data-stu-id="4f00d-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="4f00d-108">为了了解如何生成姓氏在前的格式，我们来了解一下 `NameConverter` 的实现：</span><span class="sxs-lookup"><span data-stu-id="4f00d-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 <span data-ttu-id="4f00d-109">`NameConverter` 实现 <xref:System.Windows.Data.IMultiValueConverter> 接口。</span><span class="sxs-lookup"><span data-stu-id="4f00d-109">`NameConverter` implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> <span data-ttu-id="4f00d-110">`NameConverter` 从个别绑定获取值并将其存储在值对象数组中。</span><span class="sxs-lookup"><span data-stu-id="4f00d-110">`NameConverter` takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="4f00d-111">元素 <xref:System.Windows.Data.Binding> 在元素下的显示顺序 <xref:System.Windows.Data.MultiBinding> 就是这些值在数组中的存储顺序。</span><span class="sxs-lookup"><span data-stu-id="4f00d-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="4f00d-112">特性的值 <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> 由方法的参数参数引用，该参数对 <xref:System.Windows.Data.MultiBinding.Converter%2A> 参数执行开关来确定如何设置名称的格式。</span><span class="sxs-lookup"><span data-stu-id="4f00d-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f00d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f00d-113">See also</span></span>

- [<span data-ttu-id="4f00d-114">转换绑定数据</span><span class="sxs-lookup"><span data-stu-id="4f00d-114">Convert Bound Data</span></span>](how-to-convert-bound-data.md)
- [<span data-ttu-id="4f00d-115">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="4f00d-115">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="4f00d-116">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="4f00d-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
