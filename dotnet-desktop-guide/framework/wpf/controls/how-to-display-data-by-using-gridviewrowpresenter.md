---
title: 如何：使用 GridViewRowPresenter 来显示数据
ms.date: 03/30/2017
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
ms.openlocfilehash: 0e471df3ab6fd10417fc58ece4cdb8ff1c457c95
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973715"
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a>如何：使用 GridViewRowPresenter 来显示数据
此示例演示如何使用 <xref:System.Windows.Controls.GridViewRowPresenter> 和 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> 对象在列中显示数据。  
  
## <a name="example"></a>示例  
 下面的示例演示如何 <xref:System.Windows.Controls.GridViewColumnCollection> <xref:System.DateTime.DayOfWeek%2A> <xref:System.DateTime.Year%2A> <xref:System.DateTime> 使用 <xref:System.Windows.Controls.GridViewRowPresenter> 和 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> 对象来指定显示对象的和的。 该示例还 <xref:System.Windows.Style> 为的定义了 <xref:System.Windows.Controls.GridViewColumn.Header%2A> <xref:System.Windows.Controls.GridViewColumn> 。  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewColumnCollection>
- [GridView 概述](gridview-overview.md)
