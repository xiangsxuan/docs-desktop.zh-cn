---
title: 如何：查找由 DataTemplate 生成的元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
ms.openlocfilehash: a0cb3c6f4431e16425d8aae305a917d87a3d7f96
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974049"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>如何：查找由 DataTemplate 生成的元素
此示例演示如何查找由生成的元素 <xref:System.Windows.DataTemplate> 。  
  
## <a name="example"></a>示例  
 在此示例中，有一个 <xref:System.Windows.Controls.ListBox> 绑定到一些 XML 数据的：  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 <xref:System.Windows.Controls.ListBox>使用以下 <xref:System.Windows.DataTemplate> 内容：  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 如果要检索 <xref:System.Windows.Controls.TextBlock> 由特定的生成的元素 <xref:System.Windows.DataTemplate> <xref:System.Windows.Controls.ListBoxItem> ，则需要获取 <xref:System.Windows.Controls.ListBoxItem> ，找到其中的， <xref:System.Windows.Controls.ContentPresenter> 然后对 <xref:System.Windows.Controls.ListBoxItem> <xref:System.Windows.FrameworkTemplate.FindName%2A> <xref:System.Windows.DataTemplate> 上设置的设置 <xref:System.Windows.Controls.ContentPresenter> 。 下面的示例演示如何执行这些步骤。 出于演示目的，此示例将创建一个消息框，其中显示生成的文本块的文本内容 <xref:System.Windows.DataTemplate> 。  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 下面是的实现 `FindVisualChild` ，它使用 <xref:System.Windows.Media.VisualTreeHelper> 方法：  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>另请参阅

- [如何：查找由 ControlTemplate 生成的元素](../controls/how-to-find-controltemplate-generated-elements.md)
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [操作指南主题](data-binding-how-to-topics.md)
- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [WPF XAML 名称范围](../advanced/wpf-xaml-namescopes.md)
- [WPF 中的树](../advanced/trees-in-wpf.md)
