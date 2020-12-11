---
title: 如何：获取字体规格
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 7d7ad92199bb8a8f01290066f8ae023a14c2f9ce
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971680"
---
# <a name="how-to-obtain-font-metrics"></a>如何：获取字体规格
<xref:System.Drawing.FontFamily>类提供以下方法，这些方法检索特定系列/样式组合的各种度量值：  
  
- <xref:System.Drawing.FontFamily.GetEmHeight%2A> (FontStyle)   
  
- <xref:System.Drawing.FontFamily.GetCellAscent%2A> (FontStyle)   
  
- <xref:System.Drawing.FontFamily.GetCellDescent%2A> (FontStyle)   
  
- <xref:System.Drawing.FontFamily.GetLineSpacing%2A> (FontStyle)   
  
 这些方法返回的值位于字体设计单元中，因此它们与特定对象的大小和单位无关 <xref:System.Drawing.Font> 。  
  
 下图显示了各种度量值：
  
 ![字体规格的插图：上升、下降和行距。](./media/how-to-obtain-font-metrics/various-font-metrics.png)  
  
## <a name="example"></a>示例  
 下面的示例显示 Arial 字体系列的常规样式的指标。 此代码还会根据 <xref:System.Drawing.Font> Arial 系列) （大小为16像素）创建对象 (，并显示该特定对象的度量值 () （以像素为单位） <xref:System.Drawing.Font> 。  
  
 下图显示了该示例代码的输出：
  
 ![Arial 字体指标的示例代码输出。](./media/how-to-obtain-font-metrics/example-output-code-arial-font.png)  
  
 请注意上图中输出的前两行。 <xref:System.Drawing.Font>对象返回的大小为16，而 <xref:System.Drawing.FontFamily> 对象返回的全身高度为2048。 这两个数字 (16 和 2048) 是在这种情况下，在字体设计单位与 (的单位之间进行转换的关键，这种情况下，对象的) 像素 <xref:System.Drawing.Font> 。  
  
 例如，您可以按如下所示将设计单位中的升高转换为像素：  
  
 ![显示从设计单位到像素的转换的公式](./media/how-to-obtain-font-metrics/convert-font-units-example.png)  
  
 以下代码通过设置对象的数据成员，使文本垂直放置 <xref:System.Drawing.PointF.Y%2A> <xref:System.Drawing.PointF> 。 `font.Height`对于每个新的文本行，y 坐标都将增加。 <xref:System.Drawing.Font.Height%2A>对象的属性 <xref:System.Drawing.Font> 返回该特定对象) 的行距 (以像素为单位 <xref:System.Drawing.Font> 。 在此示例中，返回的数量 <xref:System.Drawing.Font.Height%2A> 为19。 请注意，这与 (向上舍入到) 通过将行距度量值转换为像素获得的整数。  
  
 请注意，全身高度 (也称为大小或全身大小) 不是上升和下降之和。 升高和下降的总和称为单元高度。 单元高度减去内部前导，等于全身高度。 单元格高度加上外部前导与行距相等。  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [使用字体和文本](using-fonts-and-text.md)
