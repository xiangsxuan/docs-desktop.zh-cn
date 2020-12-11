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
# <a name="how-to-use-the-fontsizeconverter-class"></a>如何：使用 FontSizeConverter 类
## <a name="example"></a>示例  
 此示例演示如何创建实例 <xref:System.Windows.FontSizeConverter> ，并使用它来更改字体大小。  
  
 该示例定义了一个名为的自定义方法， `changeSize` 该方法将的内容 <xref:System.Windows.Controls.ListBoxItem> （如在单独的文件中定义）转换为的实例，稍后转换为 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] <xref:System.Double> <xref:System.String> 。 此方法将传递 <xref:System.Windows.Controls.ListBoxItem> 到一个 <xref:System.Windows.FontSizeConverter> 对象，该对象将 <xref:System.Windows.Controls.ContentControl.Content%2A> 的转换 <xref:System.Windows.Controls.ListBoxItem> 为的实例 <xref:System.Double> 。 然后，将此值作为元素的属性的值传递回 <xref:System.Windows.Controls.TextBlock.FontSize%2A> <xref:System.Windows.Controls.TextBlock> 。  
  
 此示例还定义了一个名为的第二个自定义方法 `changeFamily` 。 此方法将的转换 <xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.Windows.Controls.ListBoxItem> 为 <xref:System.String> ，然后将该值传递给该 <xref:System.Windows.Controls.TextBlock.FontFamily%2A> 元素的属性 <xref:System.Windows.Controls.TextBlock> 。  
  
 此示例不运行。  
  
 [!code-csharp[FontSizeConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.FontSizeConverter>
