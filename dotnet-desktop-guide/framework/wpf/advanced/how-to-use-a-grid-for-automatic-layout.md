---
title: 如何：使用网格进行自动布局
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 5389d8d6130367d36a5c81b3bdc316c989474ce2
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971814"
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a>如何：使用网格进行自动布局
本示例介绍如何通过自动布局方法使用网格来创建可本地化的应用程序。  
  
 的本地化 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 可能是一个耗时的过程。 通常，本地化人员除翻译文本外，还需要重新调整元素大小并重新定位元素。 过去，每种语言都是 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 针对所需调整进行修改的。 现在， [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 您可以设计可减少调整需求的元素。 编写可以更轻松地调整大小和重新定位的应用程序的方法称为 `auto layout` 。  
  
 下面的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 示例演示如何使用网格来定位某些按钮和文本。 请注意，单元格的高度和宽度设置为 `Auto` ; 因此，包含带图像按钮的单元格会调整以适应图像。 由于 <xref:System.Windows.Controls.Grid> 元素可以调整到其内容，因此在采用自动布局方法设计可本地化的应用程序时，它可能非常有用。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用网格。  
  
 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 下图显示了代码示例的输出。  
  
 ![网格示例](./media/glob-grid.png "glob_grid")  
网格  
  
## <a name="see-also"></a>另请参阅

- [使用自动布局概述](use-automatic-layout-overview.md)
- [使用自动布局创建按钮](how-to-use-automatic-layout-to-create-a-button.md)
