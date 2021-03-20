---
title: 如何：使数据可用于 XAML 中的绑定
description: 根据应用程序在 (WPF) Windows Presentation Foundation 的需求，发现可以使数据可用的各种方式。
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: aaff48ca90ffc72dc0a95e78485ceb26ae3e8079
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667910"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>如何：使数据可用于 XAML 中的绑定
本主题讨论可用于在中绑定数据的各种方法 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ，具体取决于应用程序的需求。  
  
## <a name="example"></a>示例  
 如果你有一个公共语言运行时 (要从其绑定到的 CLR) 对象 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，则可以使对象可用于绑定的一种方法是将其定义为资源，并为其提供 `x:Key` 。 在下面的示例中，具有一个 `Person` 名为的字符串属性的对象 `PersonName` 。 `Person`对象 (在突出显示的行中，其中包含 `<src>`) 在名为的命名空间中定义的元素 `SDKSample` 。  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 然后，可以将该 <xref:System.Windows.Controls.TextBlock> 控件绑定到中的对象 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，因为包含该元素的突出显示的行会 `<TextBlock>` 显示。
  
 或者，可以使用 <xref:System.Windows.Data.ObjectDataProvider> 类，如以下示例中所示：  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 可以采用相同的方式定义绑定，如包含元素的突出显示的行所 `<TextBlock>` 示。  
  
 在此特定示例中，结果是相同的：具有 <xref:System.Windows.Controls.TextBlock> 文本内容的 `Joe` 。 但是， <xref:System.Windows.Data.ObjectDataProvider> 类提供了一些功能，如可以绑定到方法的结果。 <xref:System.Windows.Data.ObjectDataProvider>如果需要它提供的功能，则可以选择使用类。  
  
 但是，如果要绑定到已创建的对象，则需要 `DataContext` 在代码中设置，如下面的示例中所示。  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 若要使用类访问用于绑定的 XML 数据 <xref:System.Windows.Data.XmlDataProvider> ，请参阅 [使用 XMLDataProvider 和 XPath 查询绑定到 xml 数据](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)。 若要使用类访问用于绑定的 XML 数据 <xref:System.Windows.Data.ObjectDataProvider> ，请参阅 binding [to XDocument、SYSTEM.XML.LINQ.XELEMENT> 或 LINQ For XML 查询结果](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)。  
  
 有关指定要绑定到的数据的多种方式的信息，请参阅 [指定绑定源](how-to-specify-the-binding-source.md)。 有关可以绑定到的数据类型或者如何实现您自己的公共语言运行时 (CLR) 对象进行绑定的信息，请参阅 [绑定源概述](binding-sources-overview.md)。  
  
## <a name="see-also"></a>请参阅

- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [操作指南主题](data-binding-how-to-topics.md)
