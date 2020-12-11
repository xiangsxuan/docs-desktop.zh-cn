---
title: 用直线和曲线抗锯齿
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
ms.openlocfilehash: 871c5cb3cd9356f677633acb04fe82021a9787c5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970608"
---
# <a name="antialiasing-with-lines-and-curves"></a>用直线和曲线抗锯齿
使用 GDI + 绘制线条时，需要提供直线的起点和终点，但不需要提供有关线条上的单个像素的任何信息。 GDI + 与显示器驱动程序软件结合使用，以确定哪些像素会打开，以在特定显示设备上显示线条。  
  
## <a name="aliasing"></a>别名  
 请考虑从点 (4，2) 点到 (16，10) 点的红线。 假设坐标系统的原点位于左上角，且度量单位是像素。 还假定 x 轴向右，y 轴向下指。 下图显示了在多色背景上绘制的红线的放大视图。  
  
 ![未抗锯齿的直线](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")  
  
 用于呈现线条的红色像素是不透明的。 行中没有半透明的像素。 这种类型的线条呈现使线条具有锯齿状外观，线条看起来有点像一只是一种楼梯。 这种表示带有楼梯的线条的方法称为别名;楼梯是理论行的别名。  
  
## <a name="antialiasing"></a>抗  
 用于绘制线条的一种更为复杂的方法涉及使用部分透明像素以及不透明像素。 将像素设置为纯红色，或将其设置为红色和背景色的某种混合，具体取决于它们对线条的接近程度。 这种类型的渲染称为抗锯齿，并产生一条线条，人们眼就会感觉更平滑。 下图显示了如何混合特定像素与背景，以生成抗锯齿线。  
  
 ![消除直线的锯齿](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")  
  
 抗锯齿（也称为平滑）也可以应用于曲线。 下图显示了平滑椭圆的放大视图。  
  
 ![消除曲线的锯齿](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")  
  
 下图显示了其实际大小的同一椭圆，一次不进行抗锯齿，一次是消除锯齿。  
  
 ![抗锯齿示例](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")  
  
 若要绘制使用抗锯齿的线条和曲线，请创建类的实例 <xref:System.Drawing.Graphics> 并将其 <xref:System.Drawing.Graphics.SmoothingMode%2A> 属性设置为 <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> 或 <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality> 。 然后调用同一类的一个绘图方法 <xref:System.Drawing.Graphics> 。  
  
 [!code-csharp[LinesCurvesAndShapes#81](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [直线、曲线和图形](lines-curves-and-shapes.md)
- [如何：对文本使用抗锯齿效果](how-to-use-antialiasing-with-text.md)
