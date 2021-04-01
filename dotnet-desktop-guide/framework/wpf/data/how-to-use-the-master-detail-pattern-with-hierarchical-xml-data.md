---
title: 如何：对分层 XML 数据使用主-从模式
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 0fe42d57fcaf4acee09340fdb3f5df73d7291566
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972085"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a>如何：对分层 XML 数据使用主-从模式
此示例演示如何用 XML 数据实现主-从方案。  
  
## <a name="example"></a>示例  
 此示例是 [将 Master-Detail 模式与分层数据结合使用](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)中所述的示例的 XML 数据版本。 在此示例中，数据来自该文件 `League.xml` 。 请注意第三个 <xref:System.Windows.Controls.ListBox> 控件如何 <xref:System.Windows.Controls.ListBox> 通过绑定到其属性来跟踪第二个选定内容的更改 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 。  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.HierarchicalDataTemplate>
- [操作指南主题](data-binding-how-to-topics.md)
