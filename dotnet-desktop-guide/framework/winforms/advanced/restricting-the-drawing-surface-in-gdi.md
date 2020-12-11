---
title: 在 GDI+ 中限制绘制图面
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: d0508166f905b45789ce638b03d0747dd6fa904e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971601"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a>在 GDI+ 中限制绘制图面
剪辑涉及将绘图限制为某个矩形或区域。 下图显示了剪辑到心形区域的字符串 "Hello"。  
  
 ![受限绘制图面](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")  
  
## <a name="clipping-with-regions"></a>用区域进行剪辑  
 可以从路径构造区域，路径可以包含字符串的轮廓，因此可以使用轮廓文本进行剪辑。 下图显示了一组同心圆省略号，它们被剪裁到文本字符串的内部。  
  
 ![受限绘制图面](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")  
  
 若要使用剪辑进行绘制，请创建 <xref:System.Drawing.Graphics> 对象，设置其 <xref:System.Drawing.Graphics.Clip%2A> 属性，然后调用相同对象的绘图方法 <xref:System.Drawing.Graphics> ：  
  
 [!code-csharp[LinesCurvesAndShapes#91](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [直线、曲线和图形](lines-curves-and-shapes.md)
- [使用区域](using-regions.md)
