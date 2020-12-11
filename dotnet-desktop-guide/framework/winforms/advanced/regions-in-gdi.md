---
title: GDI+ 中的区域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
ms.openlocfilehash: 33d4f4ecca7b9d777fa4eab5b6d031de10f03ccc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970784"
---
# <a name="regions-in-gdi"></a>GDI+ 中的区域
区域是输出设备的显示区域的一部分。 区域可以简单 (单个矩形) 或复杂 (多边形和闭合曲线的组合) 。 下图显示了两个区域：一个从矩形构造，另一个从路径构造。  
  
 ![区域](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")  
  
## <a name="using-regions"></a>使用区域  
 区域通常用于剪辑和命中测试。 剪辑涉及将绘图限制为显示区域的某个区域，通常是需要更新的部分。 命中测试涉及到检查以确定在按下鼠标按钮时光标是否位于屏幕的某个区域。  
  
 可以从矩形或路径构造区域。 还可以通过组合现有区域来创建复杂区域。 <xref:System.Drawing.Region>类提供以下方法用于组合区域： <xref:System.Drawing.Region.Intersect%2A> 、 <xref:System.Drawing.Region.Union%2A> 、 <xref:System.Drawing.Region.Xor%2A> 、 <xref:System.Drawing.Region.Exclude%2A> 和 <xref:System.Drawing.Region.Complement%2A> 。  
  
 两个区域的交集是属于这两个区域的所有点的集合。 联合是属于一个或两个区域的所有点的集合。 区域的补码是不在区域中的所有点的集合。 下图显示了上图中所示的两个区域的交集和并集。  
  
 ![区域](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")  
  
 <xref:System.Drawing.Region.Xor%2A>应用于一对区域的方法将生成一个区域，该区域包含属于一个或多个区域的所有点，但不能同时包含两者。 <xref:System.Drawing.Region.Exclude%2A>应用于一对区域的方法将生成一个区域，其中包含第一个区域中不在第二个区域中的所有点。 下图显示了通过将 <xref:System.Drawing.Region.Xor%2A> 和 <xref:System.Drawing.Region.Exclude%2A> 方法应用于本主题开头所示的两个区域而产生的区域。  
  
 ![区域](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")  
  
 若要填充区域，需要 <xref:System.Drawing.Graphics> 对象、对象 <xref:System.Drawing.Brush> 和 <xref:System.Drawing.Region> 对象。 <xref:System.Drawing.Graphics>对象提供 <xref:System.Drawing.Graphics.FillRegion%2A> 方法， <xref:System.Drawing.Brush> 对象存储填充的特性，如颜色或图案。 下面的示例使用纯色填充区域。  
  
 [!code-csharp[LinesCurvesAndShapes#61](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [直线、曲线和图形](lines-curves-and-shapes.md)
- [使用区域](using-regions.md)
