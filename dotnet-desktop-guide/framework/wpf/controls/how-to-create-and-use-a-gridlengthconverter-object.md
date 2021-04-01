---
title: 如何：创建和使用 GridLengthConverter 对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
ms.openlocfilehash: 7cf6e12c1f3f9530d4616f0cfdecff1f07820615
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973556"
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a>如何：创建和使用 GridLengthConverter 对象
## <a name="example"></a>示例  
 下面的示例演示如何创建和使用的实例 <xref:System.Windows.GridLengthConverter> 。 该示例定义了一个名为的自定义方法，该方法将 `changeCol` 传递 <xref:System.Windows.Controls.ListBoxItem> 到 <xref:System.Windows.GridLengthConverter> ，后者将 <xref:System.Windows.Controls.ContentControl.Content%2A> 的转换为的 <xref:System.Windows.Controls.ListBoxItem> 实例 <xref:System.Windows.GridLength> 。 然后，将转换后的值作为元素的属性的值进行传递 <xref:System.Windows.Controls.ColumnDefinition.Width%2A> <xref:System.Windows.Controls.ColumnDefinition> 。  
  
 该示例还定义了一个名为的第二个自定义方法 `changeColVal` 。 此自定义方法将 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 的转换 <xref:System.Windows.Controls.Slider> 为 <xref:System.String> ，然后将该值作为元素的传递回的 <xref:System.Windows.Controls.ColumnDefinition> <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 。  
  
 请注意，单独的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 文件定义的内容 <xref:System.Windows.Controls.ListBoxItem> 。  
  
 [!code-csharp[gridlengthConverterGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.GridLengthConverter>
- <xref:System.Windows.GridLength>
