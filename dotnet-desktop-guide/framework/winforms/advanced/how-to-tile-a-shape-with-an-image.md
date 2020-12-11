---
title: 如何：在形状中平铺图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: a906db44a548361df2822efa24d1dd1849cb5a24
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971401"
---
# <a name="how-to-tile-a-shape-with-an-image"></a>如何：在形状中平铺图像
正如可以将磁贴置于彼此旁边以涵盖楼层一样，可以将矩形图像放在相邻位置，以填充形状)  (图块。 若要平铺形状的内部，请使用纹理画笔。 构造 <xref:System.Drawing.TextureBrush> 对象时，传递给构造函数的参数之一是 <xref:System.Drawing.Image> 对象。 使用纹理画笔绘制形状的内部时，会使用此图像的重复副本填充形状。  
  
 对象的 "环绕模式" 属性可 <xref:System.Drawing.TextureBrush> 确定图像的定向方式，因为它在矩形网格中是重复的。 您可以使网格中的所有磁贴具有相同的方向，也可以使图像从一个网格位置翻转到下一个网格位置。 翻转可以是水平、垂直或同时为两者。 下面的示例演示了不同类型的翻转的平铺。  
  
### <a name="to-tile-an-image"></a>平铺图像  
  
- 此示例使用以下75×75图像平铺200×200矩形。  
  
 ![显示红色房屋和树的图块图像。](./media/how-to-tile-a-shape-with-an-image/rectangle-tile-200x200.gif)  
  
- 下图显示了如何用图像平铺矩形。 请注意，所有图块都具有相同的方向;没有翻转。  
  
 ![用图像平铺的矩形，对所有图块使用相同的方向。](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-no-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a>平铺时水平翻转图像  
  
- 此示例使用同一75×75图像来填充200×200矩形。 环绕模式设置为水平翻转图像。 下图显示了如何用图像平铺矩形。 请注意，当你从一个磁贴移动到给定行中的下一个磁贴时，该图像将水平翻转。  
  
 ![用水平翻转的图像平铺的矩形。](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a>平铺时垂直翻转图像  
  
- 此示例使用同一75×75图像来填充200×200矩形。 环绕模式设置为垂直翻转图像。  
  
     [!code-csharp[System.Drawing.UsingABrush#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a>平铺时水平和垂直翻转图像  
  
- 此示例使用同一75×75图像平铺200×200矩形。 环绕模式设置为在水平和垂直方向上翻转图像。 下图显示了矩形如何按图像平铺。 请注意，当你从一个磁贴移动到给定行中的下一个磁贴时，该图像将水平翻转，当你从一个磁贴移到给定列中的下一个磁贴时，图像会垂直翻转。  
  
 ![以水平和垂直翻转的图像平铺的矩形。](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-vertical-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>另请参阅

- [使用画笔填充形状](using-a-brush-to-fill-shapes.md)
