---
title: 如何：使用 FontSizeConverter 类
ms.date: 03/30/2017
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
ms.openlocfilehash: b4662ef60866150008d84f22de44852b65373282
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973741"
---
# <a name="how-to-use-the-fontsizeconverter-class"></a><span data-ttu-id="f1110-102">如何：使用 FontSizeConverter 类</span><span class="sxs-lookup"><span data-stu-id="f1110-102">How to: Use the FontSizeConverter Class</span></span>
## <a name="example"></a><span data-ttu-id="f1110-103">示例</span><span class="sxs-lookup"><span data-stu-id="f1110-103">Example</span></span>  
 <span data-ttu-id="f1110-104">此示例演示如何创建实例 <xref:System.Windows.FontSizeConverter> ，并使用它来更改字体大小。</span><span class="sxs-lookup"><span data-stu-id="f1110-104">This example shows how to create an instance of <xref:System.Windows.FontSizeConverter> and use it to change a font size.</span></span>  
  
 <span data-ttu-id="f1110-105">该示例定义了一个名为的自定义方法， `changeSize` 该方法将的内容 <xref:System.Windows.Controls.ListBoxItem> （如在单独的文件中定义）转换为的实例，稍后转换为 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] <xref:System.Double> <xref:System.String> 。</span><span class="sxs-lookup"><span data-stu-id="f1110-105">The example defines a custom method called `changeSize` that converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Double>, and later into a <xref:System.String>.</span></span> <span data-ttu-id="f1110-106">此方法将传递 <xref:System.Windows.Controls.ListBoxItem> 到一个 <xref:System.Windows.FontSizeConverter> 对象，该对象将 <xref:System.Windows.Controls.ContentControl.Content%2A> 的转换 <xref:System.Windows.Controls.ListBoxItem> 为的实例 <xref:System.Double> 。</span><span class="sxs-lookup"><span data-stu-id="f1110-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.FontSizeConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double>.</span></span> <span data-ttu-id="f1110-107">然后，将此值作为元素的属性的值传递回 <xref:System.Windows.Controls.TextBlock.FontSize%2A> <xref:System.Windows.Controls.TextBlock> 。</span><span class="sxs-lookup"><span data-stu-id="f1110-107">This value is then passed back as the value of the <xref:System.Windows.Controls.TextBlock.FontSize%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="f1110-108">此示例还定义了一个名为的第二个自定义方法 `changeFamily` 。</span><span class="sxs-lookup"><span data-stu-id="f1110-108">This example also defines a second custom method that is called `changeFamily`.</span></span> <span data-ttu-id="f1110-109">此方法将的转换 <xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.Windows.Controls.ListBoxItem> 为 <xref:System.String> ，然后将该值传递给该 <xref:System.Windows.Controls.TextBlock.FontFamily%2A> 元素的属性 <xref:System.Windows.Controls.TextBlock> 。</span><span class="sxs-lookup"><span data-stu-id="f1110-109">This method converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.String>, and then passes that value to the <xref:System.Windows.Controls.TextBlock.FontFamily%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="f1110-110">此示例不运行。</span><span class="sxs-lookup"><span data-stu-id="f1110-110">This example does not run.</span></span>  
  
 [!code-csharp[FontSizeConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f1110-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1110-111">See also</span></span>

- <xref:System.Windows.FontSizeConverter>
