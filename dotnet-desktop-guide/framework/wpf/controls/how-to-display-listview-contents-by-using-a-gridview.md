---
title: 如何：使用 GridView 显示 ListView 内容
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 9b467c95d541c326a41d1ed4bd9eb5c87e25bd5c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973707"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a>如何：使用 GridView 显示 ListView 内容
此示例演示如何为控件定义 <xref:System.Windows.Controls.GridView> 视图模式 <xref:System.Windows.Controls.ListView> 。  
  
## <a name="example"></a>示例  
 您可以 <xref:System.Windows.Controls.GridView> 通过指定对象来定义的查看模式 <xref:System.Windows.Controls.GridViewColumn> 。 下面的示例演示如何定义 <xref:System.Windows.Controls.GridViewColumn> 绑定到为控件指定的数据内容的对象 <xref:System.Windows.Controls.ListView> 。 此 <xref:System.Windows.Controls.GridView> 示例指定了三个 <xref:System.Windows.Controls.GridViewColumn> 对象，这些对象映射到 `FirstName` `LastName` `EmployeeNumber` `EmployeeInfoDataSource` 设置为控件的的的、和字段 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListView> 。  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 下图显示了此示例的显示方式。  
  
 ![显示带有 GridView 输出的 ListView 的屏幕截图。](./media/gridview-overview/listview-gridview-output.jpg)  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [ListView 概述](listview-overview.md)
- [GridView 概述](gridview-overview.md)
- [操作指南主题](listview-how-to-topics.md)
