---
title: 如何：创建网格元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
ms.openlocfilehash: c87ca1d6642bd18fa85806c92caab049d259d45e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973974"
---
# <a name="how-to-create-a-grid-element"></a><span data-ttu-id="feca2-102">如何：创建网格元素</span><span class="sxs-lookup"><span data-stu-id="feca2-102">How to: Create a Grid Element</span></span>
## <a name="example"></a><span data-ttu-id="feca2-103">示例</span><span class="sxs-lookup"><span data-stu-id="feca2-103">Example</span></span>  
 <span data-ttu-id="feca2-104">下面的示例演示如何 <xref:System.Windows.Controls.Grid> 使用或代码创建和使用的实例 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="feca2-104">The following example shows how to create and use an instance of <xref:System.Windows.Controls.Grid> by using either [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] or code.</span></span> <span data-ttu-id="feca2-105">此示例使用三个 <xref:System.Windows.Controls.ColumnDefinition> 对象和三个 <xref:System.Windows.Controls.RowDefinition> 对象创建一个具有九个单元的网格，如在工作表中。</span><span class="sxs-lookup"><span data-stu-id="feca2-105">This example uses three <xref:System.Windows.Controls.ColumnDefinition> objects and three <xref:System.Windows.Controls.RowDefinition> objects to create a grid that has nine cells, such as in a worksheet.</span></span> <span data-ttu-id="feca2-106">每个单元格 <xref:System.Windows.Controls.TextBlock> 都包含一个表示数据的元素，第一行包含一个 <xref:System.Windows.Controls.TextBlock> 应用了属性的 <xref:System.Windows.Controls.Grid.ColumnSpan%2A> 。</span><span class="sxs-lookup"><span data-stu-id="feca2-106">Each cell contains a <xref:System.Windows.Controls.TextBlock> element that represents data, and the top row contains a <xref:System.Windows.Controls.TextBlock> with the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> property applied.</span></span> <span data-ttu-id="feca2-107">若要显示每个单元格的边界，请 <xref:System.Windows.Controls.Grid.ShowGridLines%2A> 启用属性。</span><span class="sxs-lookup"><span data-stu-id="feca2-107">To show the boundaries of each cell, the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property is enabled.</span></span>  
  
 [!code-csharp[Grid#3](~/samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](~/samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
  <span data-ttu-id="feca2-108">这两种方法都将生成一个与下面类似的用户界面。</span><span class="sxs-lookup"><span data-stu-id="feca2-108">Either approach will generate a user interface that looks much the same, like the one below.</span></span>

  ![屏幕截图描述了一个 WPF 用户界面，其中包含一个分为三列的网格。](././media/how-to-create-a-grid-element/how-to-create-a-grid-element.png)
## <a name="see-also"></a><span data-ttu-id="feca2-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="feca2-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="feca2-113">面板概述</span><span class="sxs-lookup"><span data-stu-id="feca2-113">Panels Overview</span></span>](panels-overview.md)
