---
title: GDI+ 中的画笔和实心形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [Windows Forms], GDI+
- filled shapes [Windows Forms], GDI+
- shapes [Windows Forms], GDI+
- GDI+, brushes
- GDI+, filled shapes
- gradient brushes
- brushes [Windows Forms], gradient
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
ms.openlocfilehash: 45ef0b5920e43300e047d363149ea10a7833477b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970361"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a><span data-ttu-id="a72a5-102">GDI+ 中的画笔和实心形状</span><span class="sxs-lookup"><span data-stu-id="a72a5-102">Brushes and Filled Shapes in GDI+</span></span>
<span data-ttu-id="a72a5-103">闭合形状（如矩形或椭圆）由轮廓和内部组成。</span><span class="sxs-lookup"><span data-stu-id="a72a5-103">A closed shape, such as a rectangle or an ellipse, consists of an outline and an interior.</span></span> <span data-ttu-id="a72a5-104">使用笔绘制轮廓，并使用画笔填充内部。</span><span class="sxs-lookup"><span data-stu-id="a72a5-104">The outline is drawn with a pen and the interior is filled with a brush.</span></span> <span data-ttu-id="a72a5-105">Gdi + 提供了多个用于填充闭合形状的内部的画笔类： <xref:System.Drawing.SolidBrush> 、 <xref:System.Drawing.Drawing2D.HatchBrush> 、、 <xref:System.Drawing.TextureBrush> <xref:System.Drawing.Drawing2D.LinearGradientBrush> 和 <xref:System.Drawing.Drawing2D.PathGradientBrush> 。</span><span class="sxs-lookup"><span data-stu-id="a72a5-105">GDI+ provides several brush classes for filling the interiors of closed shapes: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, and <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span></span> <span data-ttu-id="a72a5-106">所有这些类都继承自 <xref:System.Drawing.Brush> 类。</span><span class="sxs-lookup"><span data-stu-id="a72a5-106">All of these classes inherit from the <xref:System.Drawing.Brush> class.</span></span> <span data-ttu-id="a72a5-107">下图显示了使用纯色画笔填充的矩形以及用阴影画笔填充的椭圆。</span><span class="sxs-lookup"><span data-stu-id="a72a5-107">The following illustration shows a rectangle filled with a solid brush and an ellipse filled with a hatch brush.</span></span>  
  
 <span data-ttu-id="a72a5-108">![实心形状](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span><span class="sxs-lookup"><span data-stu-id="a72a5-108">![Filled Shapes](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span></span>  
  
## <a name="solid-brushes"></a><span data-ttu-id="a72a5-109">纯色画笔</span><span class="sxs-lookup"><span data-stu-id="a72a5-109">Solid Brushes</span></span>  
 <span data-ttu-id="a72a5-110">若要填充闭合的形状，需要 <xref:System.Drawing.Graphics> 类和的实例 <xref:System.Drawing.Brush> 。</span><span class="sxs-lookup"><span data-stu-id="a72a5-110">To fill a closed shape, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Brush>.</span></span> <span data-ttu-id="a72a5-111">类的实例 <xref:System.Drawing.Graphics> 提供了方法（如 <xref:System.Drawing.Graphics.FillRectangle%2A> 和）， <xref:System.Drawing.Graphics.FillEllipse%2A> 以及 <xref:System.Drawing.Brush> 存储填充的特性，如颜色和模式。</span><span class="sxs-lookup"><span data-stu-id="a72a5-111">The instance of the <xref:System.Drawing.Graphics> class provides methods, such as <xref:System.Drawing.Graphics.FillRectangle%2A> and <xref:System.Drawing.Graphics.FillEllipse%2A>, and the <xref:System.Drawing.Brush> stores attributes of the fill, such as color and pattern.</span></span> <span data-ttu-id="a72a5-112"><xref:System.Drawing.Brush>作为一个自变量传递给 fill 方法。</span><span class="sxs-lookup"><span data-stu-id="a72a5-112">The <xref:System.Drawing.Brush> is passed as one of the arguments to the fill method.</span></span> <span data-ttu-id="a72a5-113">下面的代码示例演示如何使用纯红色填充椭圆。</span><span class="sxs-lookup"><span data-stu-id="a72a5-113">The following code example shows how to fill an ellipse with a solid red color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#121](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
> <span data-ttu-id="a72a5-114">在前面的示例中，画笔的类型为 <xref:System.Drawing.SolidBrush> ，它继承自 <xref:System.Drawing.Brush> 。</span><span class="sxs-lookup"><span data-stu-id="a72a5-114">In the preceding example, the brush is of type <xref:System.Drawing.SolidBrush>, which inherits from <xref:System.Drawing.Brush>.</span></span>  
  
## <a name="hatch-brushes"></a><span data-ttu-id="a72a5-115">阴影画笔</span><span class="sxs-lookup"><span data-stu-id="a72a5-115">Hatch Brushes</span></span>  
 <span data-ttu-id="a72a5-116">使用阴影画笔填充形状时，需要指定前景色、背景色和阴影样式。</span><span class="sxs-lookup"><span data-stu-id="a72a5-116">When you fill a shape with a hatch brush, you specify a foreground color, a background color, and a hatch style.</span></span> <span data-ttu-id="a72a5-117">前景色是阴影的颜色。</span><span class="sxs-lookup"><span data-stu-id="a72a5-117">The foreground color is the color of the hatching.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#122](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 <span data-ttu-id="a72a5-118">GDI + 提供的阴影样式超过50个;下图中显示的三个样式为 <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal> 、 <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal> 和 <xref:System.Drawing.Drawing2D.HatchStyle.Cross> 。</span><span class="sxs-lookup"><span data-stu-id="a72a5-118">GDI+ provides more than 50 hatch styles; the three styles shown in the following illustration are <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, and <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span></span>  
  
 <span data-ttu-id="a72a5-119">![实心形状](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span><span class="sxs-lookup"><span data-stu-id="a72a5-119">![Filled Shapes](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span></span>  
  
## <a name="texture-brushes"></a><span data-ttu-id="a72a5-120">纹理画笔</span><span class="sxs-lookup"><span data-stu-id="a72a5-120">Texture Brushes</span></span>  
 <span data-ttu-id="a72a5-121">使用纹理画笔，可以使用位图中存储的模式来填充形状。</span><span class="sxs-lookup"><span data-stu-id="a72a5-121">With a texture brush, you can fill a shape with a pattern stored in a bitmap.</span></span> <span data-ttu-id="a72a5-122">例如，假设下面的图片存储在名为的磁盘文件中 `MyTexture.bmp` 。</span><span class="sxs-lookup"><span data-stu-id="a72a5-122">For example, suppose the following picture is stored in a disk file named `MyTexture.bmp`.</span></span>  
  
 <span data-ttu-id="a72a5-123">![实心形状](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span><span class="sxs-lookup"><span data-stu-id="a72a5-123">![Filled Shape](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span></span>  
  
 <span data-ttu-id="a72a5-124">下面的代码示例演示如何通过重复存储在中的图片来填充椭圆 `MyTexture.bmp` 。</span><span class="sxs-lookup"><span data-stu-id="a72a5-124">The following code example shows how to fill an ellipse by repeating the picture stored in `MyTexture.bmp`.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#123](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 <span data-ttu-id="a72a5-125">下图显示了实心椭圆。</span><span class="sxs-lookup"><span data-stu-id="a72a5-125">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="a72a5-126">![实心形状](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span><span class="sxs-lookup"><span data-stu-id="a72a5-126">![Filled Shape](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span></span>  
  
## <a name="gradient-brushes"></a><span data-ttu-id="a72a5-127">渐变画笔</span><span class="sxs-lookup"><span data-stu-id="a72a5-127">Gradient Brushes</span></span>  
 <span data-ttu-id="a72a5-128">GDI + 提供了两种类型的渐变画笔：线性和路径。</span><span class="sxs-lookup"><span data-stu-id="a72a5-128">GDI+ provides two kinds of gradient brushes: linear and path.</span></span> <span data-ttu-id="a72a5-129">您可以使用线性渐变画笔来填充形状，颜色在水平、垂直或对角移动时逐渐变化。</span><span class="sxs-lookup"><span data-stu-id="a72a5-129">You can use a linear gradient brush to fill a shape with color that changes gradually as you move across the shape horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="a72a5-130">下面的代码示例演示如何使用水平渐变画笔（当您从椭圆的左边缘向右边缘移动时，使用从蓝色到绿色的更改）填充椭圆。</span><span class="sxs-lookup"><span data-stu-id="a72a5-130">The following code example shows how to fill an ellipse with a horizontal gradient brush that changes from blue to green as you move from the left edge of the ellipse to the right edge.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#124](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 <span data-ttu-id="a72a5-131">下图显示了实心椭圆。</span><span class="sxs-lookup"><span data-stu-id="a72a5-131">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="a72a5-132">![实心形状](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span><span class="sxs-lookup"><span data-stu-id="a72a5-132">![Filled Shape](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span></span>  
  
 <span data-ttu-id="a72a5-133">可以将路径渐变画笔配置为在从形状的中心向边缘移动时更改颜色。</span><span class="sxs-lookup"><span data-stu-id="a72a5-133">A path gradient brush can be configured to change color as you move from the center of a shape toward the edge.</span></span>  
  
 <span data-ttu-id="a72a5-134">![实心形状](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span><span class="sxs-lookup"><span data-stu-id="a72a5-134">![Filled Shape](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span></span>  
  
 <span data-ttu-id="a72a5-135">路径渐变画笔非常灵活。</span><span class="sxs-lookup"><span data-stu-id="a72a5-135">Path gradient brushes are quite flexible.</span></span> <span data-ttu-id="a72a5-136">在下图中，用于填充三角形的渐变画笔在顶点处逐步变化为三种不同颜色中的每一种颜色。</span><span class="sxs-lookup"><span data-stu-id="a72a5-136">The gradient brush used to fill the triangle in the following illustration changes gradually from red at the center to each of three different colors at the vertices.</span></span>  
  
 <span data-ttu-id="a72a5-137">![实心形状](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span><span class="sxs-lookup"><span data-stu-id="a72a5-137">![Filled Shape](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a72a5-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a72a5-138">See also</span></span>

- <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>
- <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="a72a5-139">直线、曲线和图形</span><span class="sxs-lookup"><span data-stu-id="a72a5-139">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="a72a5-140">如何：在 Windows 窗体上绘制实心矩形</span><span class="sxs-lookup"><span data-stu-id="a72a5-140">How to: Draw a Filled Rectangle on a Windows Form</span></span>](how-to-draw-a-filled-rectangle-on-a-windows-form.md)
- [<span data-ttu-id="a72a5-141">如何：在 Windows 窗体上绘制实心椭圆</span><span class="sxs-lookup"><span data-stu-id="a72a5-141">How to: Draw a Filled Ellipse on a Windows Form</span></span>](how-to-draw-a-filled-ellipse-on-a-windows-form.md)
