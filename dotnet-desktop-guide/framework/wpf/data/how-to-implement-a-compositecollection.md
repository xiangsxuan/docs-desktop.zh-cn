---
title: 如何：实现 CompositeCollection
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: fe3b7fb1020ac8022113246453d8247ca241449c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974044"
---
# <a name="how-to-implement-a-compositecollection"></a>如何：实现 CompositeCollection
## <a name="example"></a>示例  
 下面的示例演示如何使用类将多个集合和项显示为一个列表 <xref:System.Windows.Data.CompositeCollection> 。 在此示例中， `GreekGods` 是 <xref:System.Collections.ObjectModel.ObservableCollection%601> `GreekGod` 自定义对象的。 定义数据模板是为了使 `GreekGod` 对象和 `GreekHero` 对象分别以金色和青色前景颜色显示。  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [操作指南主题](data-binding-how-to-topics.md)
