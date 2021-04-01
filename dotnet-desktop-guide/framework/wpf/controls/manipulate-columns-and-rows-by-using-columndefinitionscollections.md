---
title: 如何：使用 ColumnDefinitionsCollection 和 RowDefinitionsCollection 来操作列和行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Grid class
- Grid control [WPF], ColumnDefinitionCollection class
- Grid control [WPF], RowDefinitionCollection class
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
ms.openlocfilehash: 2f6d174fd54dca3744e5967f198c645e01a94fe5
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973195"
---
# <a name="how-to-manipulate-columns-and-rows-by-using-columndefinitionscollections-and-rowdefinitionscollections"></a>如何：使用 ColumnDefinitionsCollection 和 RowDefinitionsCollection 来操作列和行
此示例演示如何使用和类中的方法 <xref:System.Windows.Controls.ColumnDefinitionCollection> <xref:System.Windows.Controls.RowDefinitionCollection> 来执行诸如添加、清除或计算行或列内容的操作。 例如，您可以 <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A> 、 <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A> ，也可以 <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> 是或中包含的项 <xref:System.Windows.Controls.ColumnDefinition> <xref:System.Windows.Controls.RowDefinition> 。  
  
## <a name="example"></a>示例  
 下面的示例创建一个 <xref:System.Windows.Controls.Grid> 元素，该元素 <xref:System.Windows.FrameworkElement.Name%2A> 的为 `grid1` 。 <xref:System.Windows.Controls.Grid>包含一个 <xref:System.Windows.Controls.StackPanel> ，它保存 <xref:System.Windows.Controls.Button> 元素，每个元素由不同的集合方法控制。 单击时 <xref:System.Windows.Controls.Button> ，它会激活代码隐藏文件中的方法调用。  
  
 [!code-xaml[ColumnDefinitionsGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 此示例定义了一系列自定义方法，每个方法都对应于 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 文件中的一个事件 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。 您可以通过多种方式更改中的列和行的数目 <xref:System.Windows.Controls.Grid> ，包括添加或删除行和列，以及计算总行数和列数。 若要防止 <xref:System.ArgumentOutOfRangeException> 和 <xref:System.ArgumentException> 异常，可以使用方法提供的错误检查功能 <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A> 。  
  
 [!code-csharp[ColumnDefinitionsGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.ColumnDefinitionCollection>
- <xref:System.Windows.Controls.RowDefinitionCollection>
