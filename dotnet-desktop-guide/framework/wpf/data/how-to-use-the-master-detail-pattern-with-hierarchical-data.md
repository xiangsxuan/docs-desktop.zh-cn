---
title: 如何：对分层数据使用主-从模式
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: dd3ecff2593c88505a1d301f14fe3456e8e4dc85
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972084"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>如何：对分层数据使用主-从模式
此示例演示如何实现主-从方案。  
  
## <a name="example"></a>示例  
 在此示例中， `LeagueList` 是的集合 `Leagues` 。 每个 `League` 都有一个 `Name` 和集合 `Divisions` ，每个都 `Division` 有一个名称和集合 `Teams` 。 每个 `Team` 都有一个团队名称。  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 下面是该示例的一个屏幕快照。 `Divisions` <xref:System.Windows.Controls.ListBox> 会自动跟踪中的选定内容 `Leagues` <xref:System.Windows.Controls.ListBox> ，并显示相应的数据。 `Teams` <xref:System.Windows.Controls.ListBox> 跟踪在其他两个控件中所做的选择 <xref:System.Windows.Controls.ListBox> 。  
  
 ![显示主&#45;详细方案示例的屏幕截图。](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 在此示例中，需要注意以下两个事项：  
  
1. 这三个 <xref:System.Windows.Controls.ListBox> 控件绑定到同一个源。 将绑定的 <xref:System.Windows.Data.Binding.Path%2A> 属性设置为指定要显示的数据级别 <xref:System.Windows.Controls.ListBox> 。  
  
2. 您必须在要 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> `true` 跟踪的选择的控件上将属性设置为 <xref:System.Windows.Controls.ListBox> 。 设置此属性可确保所选项始终设置为 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> 。 或者，如果 <xref:System.Windows.Controls.ListBox> 从获取数据 <xref:System.Windows.Data.CollectionViewSource> ，则会自动同步选定内容和货币。  
  
 使用 XML 数据时，技术略有不同。 有关示例，请参阅 [将 Master-Detail 模式用于分层 XML 数据](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.HierarchicalDataTemplate>
- [绑定到集合并基于选择显示信息](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [数据模板化概述](data-templating-overview.md)
- [操作指南主题](data-binding-how-to-topics.md)
