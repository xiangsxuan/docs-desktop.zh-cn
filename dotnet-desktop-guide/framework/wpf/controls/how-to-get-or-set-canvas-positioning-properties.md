---
title: 如何：获取或设置画布定位属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 06508e1198736ccb1cbda41641dff4bc634ef82b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971034"
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a><span data-ttu-id="c7db9-102">如何：获取或设置画布定位属性</span><span class="sxs-lookup"><span data-stu-id="c7db9-102">How to: Get or Set Canvas Positioning Properties</span></span>
<span data-ttu-id="c7db9-103">此示例演示如何使用元素的定位方法 <xref:System.Windows.Controls.Canvas> 来定位子内容。</span><span class="sxs-lookup"><span data-stu-id="c7db9-103">This example shows how to use the positioning methods of the <xref:System.Windows.Controls.Canvas> element to position child content.</span></span> <span data-ttu-id="c7db9-104">此示例使用中的内容 <xref:System.Windows.Controls.ListBoxItem> 来表示定位值，并将值转换为的实例 <xref:System.Double> ，这是定位的必需参数。</span><span class="sxs-lookup"><span data-stu-id="c7db9-104">This example uses content in a <xref:System.Windows.Controls.ListBoxItem> to represent positioning values and converts the values into instances of <xref:System.Double>, which is a required argument for positioning.</span></span> <span data-ttu-id="c7db9-105">然后，使用方法将这些值转换回字符串并在元素中显示为文本 <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.Canvas.GetLeft%2A> 。</span><span class="sxs-lookup"><span data-stu-id="c7db9-105">The values are then converted back into strings and displayed as text in a <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.Canvas.GetLeft%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7db9-106">示例</span><span class="sxs-lookup"><span data-stu-id="c7db9-106">Example</span></span>  
 <span data-ttu-id="c7db9-107">下面的示例创建一个 <xref:System.Windows.Controls.ListBox> 具有十一个可选择 <xref:System.Windows.Controls.ListBoxItem> 元素的元素。</span><span class="sxs-lookup"><span data-stu-id="c7db9-107">The following example creates a <xref:System.Windows.Controls.ListBox> element that has eleven selectable <xref:System.Windows.Controls.ListBoxItem> elements.</span></span> <span data-ttu-id="c7db9-108">此 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 事件触发 `ChangeLeft` 自定义方法，后面的代码块将定义该方法。</span><span class="sxs-lookup"><span data-stu-id="c7db9-108">The <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event triggers the `ChangeLeft` custom method, which the subsequent code block defines.</span></span>  
  
 <span data-ttu-id="c7db9-109">每个都 <xref:System.Windows.Controls.ListBoxItem> 表示一个 <xref:System.Double> 值，该值是接受的方法的参数之一 <xref:System.Windows.Controls.Canvas.SetLeft%2A> <xref:System.Windows.Controls.Canvas> 。</span><span class="sxs-lookup"><span data-stu-id="c7db9-109">Each <xref:System.Windows.Controls.ListBoxItem> represents a <xref:System.Double> value, which is one of the arguments that the <xref:System.Windows.Controls.Canvas.SetLeft%2A> method of <xref:System.Windows.Controls.Canvas> accepts.</span></span> <span data-ttu-id="c7db9-110">为了使用 <xref:System.Windows.Controls.ListBoxItem> 来表示的实例 <xref:System.Double> ，必须先将转换 <xref:System.Windows.Controls.ListBoxItem> 为正确的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c7db9-110">In order to use a <xref:System.Windows.Controls.ListBoxItem> to represent an instance of <xref:System.Double>, you must first convert the <xref:System.Windows.Controls.ListBoxItem> to the correct data type.</span></span>  
  
 [!code-xaml[CanvasPositioningProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="c7db9-111">当用户更改 <xref:System.Windows.Controls.ListBox> 所选内容时，它会调用 `ChangeLeft` 自定义方法。</span><span class="sxs-lookup"><span data-stu-id="c7db9-111">When a user changes the <xref:System.Windows.Controls.ListBox> selection, it invokes the `ChangeLeft` custom method.</span></span> <span data-ttu-id="c7db9-112">此方法将传递 <xref:System.Windows.Controls.ListBoxItem> 到一个 <xref:System.Windows.LengthConverter> 对象，该对象将 <xref:System.Windows.Controls.ContentControl.Content%2A> 的转换 <xref:System.Windows.Controls.ListBoxItem> 为 <xref:System.Double> (注意，此值已 <xref:System.String> 通过使用 <xref:System.Windows.Controls.Control.ToString%2A> 方法) 转换为。</span><span class="sxs-lookup"><span data-stu-id="c7db9-112">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.LengthConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double> (notice that this value has already been converted to a <xref:System.String> by using the <xref:System.Windows.Controls.Control.ToString%2A> method).</span></span> <span data-ttu-id="c7db9-113">然后，将此值传递回的 <xref:System.Windows.Controls.Canvas.SetLeft%2A> 和 <xref:System.Windows.Controls.Canvas.GetLeft%2A> 方法，以 <xref:System.Windows.Controls.Canvas> 更改对象的位置 `text1` 。</span><span class="sxs-lookup"><span data-stu-id="c7db9-113">This value is then passed back to the <xref:System.Windows.Controls.Canvas.SetLeft%2A> and <xref:System.Windows.Controls.Canvas.GetLeft%2A> methods of <xref:System.Windows.Controls.Canvas> in order to change the position of the `text1` object.</span></span>  
  
 [!code-csharp[CanvasPositioningProperties#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c7db9-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7db9-114">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.ListBoxItem>
- <xref:System.Windows.LengthConverter>
- [<span data-ttu-id="c7db9-115">面板概述</span><span class="sxs-lookup"><span data-stu-id="c7db9-115">Panels Overview</span></span>](panels-overview.md)
