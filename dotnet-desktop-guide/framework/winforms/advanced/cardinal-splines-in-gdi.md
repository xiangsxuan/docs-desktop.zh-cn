---
title: GDI+ 中的基数样条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], cardinal
- GDI+, cardinal splines
- cardinal splines
ms.assetid: 09b3797a-6294-422d-9adf-a5a0a7695c0c
ms.openlocfilehash: 4588f6f606f0f479aeae1d143f23175ec4be32a5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970689"
---
# <a name="cardinal-splines-in-gdi"></a>GDI+ 中的基数样条
基数样条是一系列连接起来形成更大曲线的单个曲线。 样条由点数组和张力参数指定。 基数样条平滑传递到数组中的每个点;曲线的 tightness 没有锐角，也没有任何突然改变。 下图显示了一组点和一个经过集内每个点的基数样条。  
  
 ![基数样条](./media/aboutgdip02-art09.gif "Aboutgdip02_art09")  
  
## <a name="physical-and-mathematical-splines"></a>物理和数学样条  
 物理样条是木材或其他灵活材料的一小部分。 在出现数学样条之前，设计器使用物理样条绘制曲线。 设计器会将样条放在一张纸上，并将其锚定到一组给定的点上。 然后，设计器可以通过用笔或铅笔绘制曲线来创建曲线。 一组给定的点可能产生各种曲线，具体取决于物理样条的属性。 例如，对弯曲产生高频的样条将产生与极具弹性的样条不同的曲线。  
  
 数学样条的公式基于挠性杆的属性，因此，数学样条产生的曲线类似于由物理样条生成的曲线。 正如不同张力的物理样条将通过一组给定的点生成不同的曲线，具有张力参数的不同值的数学样条将通过一组给定的点生成不同的曲线。 下图显示了通过同一组点传递的四个基数样条。 为每个样条显示张力。 0的张力对应于无限的物理张力，并强制曲线采用) 点之间 (直线的最短方式。 张力为1对应于无物理张力，这允许样条采用最小总折折的路径。 如果张力值大于1，则曲线的行为类似于压缩的弹簧，并经过较长的路径。  
  
 ![基数样条](./media/aboutgdip02-art10.gif "Aboutgdip02_art10")  
  
 上图中的四个样条在起始点共享相同的切线。 相切是从起点到曲线沿曲线绘制的直线。 同样，位于结束点的共享相切是从结束点绘制到曲线上点的直线。  
  
 若要绘制基数样条，需要类的实例、 <xref:System.Drawing.Graphics> <xref:System.Drawing.Pen> 和对象的数组。 <xref:System.Drawing.Point> 类的实例 <xref:System.Drawing.Graphics> 提供了 <xref:System.Drawing.Graphics.DrawCurve%2A> 方法，该方法用于绘制样条，并存储了样条的 <xref:System.Drawing.Pen> 属性，例如线条宽度和颜色。 <xref:System.Drawing.Point>对象数组存储曲线将通过的点。 下面的代码示例演示如何绘制经过中的点的基数样条 `myPointArray` 。 第三个参数为张力。  
  
 [!code-csharp[LinesCurvesAndShapes#31](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#31)]
 [!code-vb[LinesCurvesAndShapes#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>另请参阅

- [直线、曲线和图形](lines-curves-and-shapes.md)
- [构造并绘制曲线](constructing-and-drawing-curves.md)
