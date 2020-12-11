---
title: 如何：将文本绘制到 Visual 中
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: 654bfadb42f053b6dcf353d4423bddf281d69478
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973568"
---
# <a name="how-to-draw-text-to-a-visual"></a>如何：将文本绘制到 Visual 中
下面的示例演示如何使用对象将文本绘制到 <xref:System.Windows.Media.DrawingVisual> <xref:System.Windows.Media.DrawingContext> 。 通过调用对象的方法来返回一个绘图上下文 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> <xref:System.Windows.Media.DrawingVisual> 。 您可以在绘图上下文中绘制图形和文本。  
  
 若要在绘图上下文中绘制文本，请使用 <xref:System.Windows.Media.DrawingContext.DrawText%2A> 对象的方法 <xref:System.Windows.Media.DrawingContext> 。 完成将内容绘制到绘图上下文中后，调用 <xref:System.Windows.Media.DrawingContext.Close%2A> 方法关闭绘图上下文并保存内容。  
  
## <a name="example"></a>示例  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> 有关从中提取上述代码示例的完整代码示例，请参阅[使用 DrawingVisual 的命中测试示例](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual)。
