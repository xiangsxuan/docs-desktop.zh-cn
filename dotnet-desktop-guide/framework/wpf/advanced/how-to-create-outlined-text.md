---
title: 如何：创建空心文字
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: 12da12320a09fa825d9c75d4a6e5e3264724de77
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604345"
---
# <a name="how-to-create-outlined-text"></a>如何：创建空心文本

在大多数情况下，当你将装饰添加到应用程序中的文本字符串时， [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 将在离散字符或标志符号的集合中使用文本。 例如，可以创建线性渐变画笔，并将其应用于对象的 <xref:System.Windows.Controls.Control.Foreground%2A> 属性 <xref:System.Windows.Controls.TextBox> 。 显示或编辑文本框时，线性渐变画笔会自动应用于文本字符串中的当前字符集。  
  
 ![使用线性渐变画笔显示的文本](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 但是，您还可以将文本转换为 <xref:System.Windows.Media.Geometry> 对象，从而允许您创建其他类型的视觉对象。 例如，可以根据 <xref:System.Windows.Media.Geometry> 文本字符串的轮廓创建对象。  
  
 ![使用线性渐变画笔的文本轮廓](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 当文本转换为对象时 <xref:System.Windows.Media.Geometry> ，它不再是字符的集合，您不能修改文本字符串中的字符。 但是，可修改已转换文本的笔划和填充属性，以此来影响该文本的外观。 笔划是指已转换文本的轮廓；填充是指已转换文本的轮廓的内部区域。  
  
 下面的示例演示了通过修改已转换文本的笔划和填充来创建视觉效果的多种方法。  
  
 ![对填充和笔画使用不同颜色的文本](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![笔画应用了图像画笔的文本](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 还可以修改已转换文本的边界框矩形或突出显示的文本。 下面的示例演示了一种通过修改已转换文本的笔画和突出显示来创建视觉效果的方法。  
  
 ![将图像画笔应用于笔划和突出显示的文本](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a>示例  
 将文本转换为对象的关键 <xref:System.Windows.Media.Geometry> 是使用 <xref:System.Windows.Media.FormattedText> 对象。 创建此对象后，可以使用 <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> 和 <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> 方法将文本转换为 <xref:System.Windows.Media.Geometry> 对象。 第一种方法返回格式化文本的几何图形;第二个方法返回格式化文本的边界框的几何。 下面的代码示例演示如何创建 <xref:System.Windows.Media.FormattedText> 对象并检索带格式文本及其边界框的几何。  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 为了显示检索到的 <xref:System.Windows.Media.Geometry> 对象，需要访问 <xref:System.Windows.Media.DrawingContext> 显示已转换文本的对象的。 在以下代码示例中，通过创建一个自定义控件对象来实现此访问，该对象派生自支持用户定义的呈现的类。  
  
 若要显示 <xref:System.Windows.Media.Geometry> 自定义控件中的对象，请为方法提供重写 <xref:System.Windows.UIElement.OnRender%2A> 。 重写的方法应使用 <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> 方法来绘制 <xref:System.Windows.Media.Geometry> 对象。  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  有关示例自定义用户控件对象的源，请参阅 [OutlineTextControl.cs For c #](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) 和 [OutlineTextControl for Visual Basic](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb)。
  
## <a name="see-also"></a>另请参阅

- [绘制格式化文本](drawing-formatted-text.md)
