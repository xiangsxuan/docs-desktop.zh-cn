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
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="6fb0e-102">如何：在形状中平铺图像</span><span class="sxs-lookup"><span data-stu-id="6fb0e-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="6fb0e-103">正如可以将磁贴置于彼此旁边以涵盖楼层一样，可以将矩形图像放在相邻位置，以填充形状)  (图块。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="6fb0e-104">若要平铺形状的内部，请使用纹理画笔。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="6fb0e-105">构造 <xref:System.Drawing.TextureBrush> 对象时，传递给构造函数的参数之一是 <xref:System.Drawing.Image> 对象。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="6fb0e-106">使用纹理画笔绘制形状的内部时，会使用此图像的重复副本填充形状。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="6fb0e-107">对象的 "环绕模式" 属性可 <xref:System.Drawing.TextureBrush> 确定图像的定向方式，因为它在矩形网格中是重复的。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="6fb0e-108">您可以使网格中的所有磁贴具有相同的方向，也可以使图像从一个网格位置翻转到下一个网格位置。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="6fb0e-109">翻转可以是水平、垂直或同时为两者。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="6fb0e-110">下面的示例演示了不同类型的翻转的平铺。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="6fb0e-111">平铺图像</span><span class="sxs-lookup"><span data-stu-id="6fb0e-111">To tile an image</span></span>  
  
- <span data-ttu-id="6fb0e-112">此示例使用以下75×75图像平铺200×200矩形。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 ![显示红色房屋和树的图块图像。](./media/how-to-tile-a-shape-with-an-image/rectangle-tile-200x200.gif)  
  
- <span data-ttu-id="6fb0e-114">下图显示了如何用图像平铺矩形。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="6fb0e-115">请注意，所有图块都具有相同的方向;没有翻转。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 ![用图像平铺的矩形，对所有图块使用相同的方向。](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-no-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="6fb0e-117">平铺时水平翻转图像</span><span class="sxs-lookup"><span data-stu-id="6fb0e-117">To flip an image horizontally while tiling</span></span>  
  
- <span data-ttu-id="6fb0e-118">此示例使用同一75×75图像来填充200×200矩形。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="6fb0e-119">环绕模式设置为水平翻转图像。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="6fb0e-120">下图显示了如何用图像平铺矩形。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="6fb0e-121">请注意，当你从一个磁贴移动到给定行中的下一个磁贴时，该图像将水平翻转。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 ![用水平翻转的图像平铺的矩形。](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="6fb0e-123">平铺时垂直翻转图像</span><span class="sxs-lookup"><span data-stu-id="6fb0e-123">To flip an image vertically while tiling</span></span>  
  
- <span data-ttu-id="6fb0e-124">此示例使用同一75×75图像来填充200×200矩形。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="6fb0e-125">环绕模式设置为垂直翻转图像。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="6fb0e-126">平铺时水平和垂直翻转图像</span><span class="sxs-lookup"><span data-stu-id="6fb0e-126">To flip an image horizontally and vertically while tiling</span></span>  
  
- <span data-ttu-id="6fb0e-127">此示例使用同一75×75图像平铺200×200矩形。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="6fb0e-128">环绕模式设置为在水平和垂直方向上翻转图像。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="6fb0e-129">下图显示了矩形如何按图像平铺。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="6fb0e-130">请注意，当你从一个磁贴移动到给定行中的下一个磁贴时，该图像将水平翻转，当你从一个磁贴移到给定列中的下一个磁贴时，图像会垂直翻转。</span><span class="sxs-lookup"><span data-stu-id="6fb0e-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 ![以水平和垂直翻转的图像平铺的矩形。](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-vertical-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="6fb0e-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6fb0e-132">See also</span></span>

- [<span data-ttu-id="6fb0e-133">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="6fb0e-133">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
