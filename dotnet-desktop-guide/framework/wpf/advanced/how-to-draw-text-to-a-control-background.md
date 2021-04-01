---
title: 如何：将文本绘制到控件的背景上
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 14300f763b67c6ac67ee408de2009c328d499c13
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970090"
---
# <a name="how-to-draw-text-to-a-controls-background"></a>如何：将文本绘制到控件的背景上
您可以通过将文本字符串转换为 <xref:System.Windows.Media.FormattedText> 对象，然后将该对象绘制到控件的，来直接将文本绘制到控件的背景中 <xref:System.Windows.Media.DrawingContext> 。 你还可以使用此方法来绘制到派生自的对象的背景 <xref:System.Windows.Controls.Panel> ，例如 <xref:System.Windows.Controls.Canvas> 和 <xref:System.Windows.Controls.StackPanel> 。  
  
 ![以背景形式显示文本的控件的屏幕截图。](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")  
具有自定义文本背景的控件的示例  
  
## <a name="example"></a>示例  
 若要在控件的背景上绘制，请创建新的 <xref:System.Windows.Media.DrawingBrush> 对象，并将转换后的文本绘制到对象的 <xref:System.Windows.Media.DrawingContext> 。 然后，将新的分配 <xref:System.Windows.Media.DrawingBrush> 给控件的背景属性。  
  
 下面的代码示例演示如何创建 <xref:System.Windows.Media.FormattedText> 对象并将其绘制到和对象的背景 <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.Button> 。  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.FormattedText>
- [绘制格式化文本](drawing-formatted-text.md)
