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
# <a name="antialiasing-with-lines-and-curves"></a><span data-ttu-id="294ab-102">用直线和曲线抗锯齿</span><span class="sxs-lookup"><span data-stu-id="294ab-102">Antialiasing with Lines and Curves</span></span>
<span data-ttu-id="294ab-103">使用 GDI + 绘制线条时，需要提供直线的起点和终点，但不需要提供有关线条上的单个像素的任何信息。</span><span class="sxs-lookup"><span data-stu-id="294ab-103">When you use GDI+ to draw a line, you provide the starting point and ending point of the line, but you do not have to provide any information about the individual pixels on the line.</span></span> <span data-ttu-id="294ab-104">GDI + 与显示器驱动程序软件结合使用，以确定哪些像素会打开，以在特定显示设备上显示线条。</span><span class="sxs-lookup"><span data-stu-id="294ab-104">GDI+ works in conjunction with the display driver software to determine which pixels will be turned on to show the line on a particular display device.</span></span>  
  
## <a name="aliasing"></a><span data-ttu-id="294ab-105">别名</span><span class="sxs-lookup"><span data-stu-id="294ab-105">Aliasing</span></span>  
 <span data-ttu-id="294ab-106">请考虑从点 (4，2) 点到 (16，10) 点的红线。</span><span class="sxs-lookup"><span data-stu-id="294ab-106">Consider the straight red line that goes from the point (4, 2) to the point (16, 10).</span></span> <span data-ttu-id="294ab-107">假设坐标系统的原点位于左上角，且度量单位是像素。</span><span class="sxs-lookup"><span data-stu-id="294ab-107">Assume the coordinate system has its origin in the upper-left corner and that the unit of measure is the pixel.</span></span> <span data-ttu-id="294ab-108">还假定 x 轴向右，y 轴向下指。</span><span class="sxs-lookup"><span data-stu-id="294ab-108">Also assume that the x-axis points to the right and the y-axis points down.</span></span> <span data-ttu-id="294ab-109">下图显示了在多色背景上绘制的红线的放大视图。</span><span class="sxs-lookup"><span data-stu-id="294ab-109">The following illustration shows an enlarged view of the red line drawn on a multicolored background.</span></span>  
  
 <span data-ttu-id="294ab-110">![未抗锯齿的直线](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span><span class="sxs-lookup"><span data-stu-id="294ab-110">![Line, no antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span></span>  
  
 <span data-ttu-id="294ab-111">用于呈现线条的红色像素是不透明的。</span><span class="sxs-lookup"><span data-stu-id="294ab-111">The red pixels used to render the line are opaque.</span></span> <span data-ttu-id="294ab-112">行中没有半透明的像素。</span><span class="sxs-lookup"><span data-stu-id="294ab-112">There are no partially transparent pixels in the line.</span></span> <span data-ttu-id="294ab-113">这种类型的线条呈现使线条具有锯齿状外观，线条看起来有点像一只是一种楼梯。</span><span class="sxs-lookup"><span data-stu-id="294ab-113">This type of line rendering gives the line a jagged appearance, and the line looks somewhat like a staircase.</span></span> <span data-ttu-id="294ab-114">这种表示带有楼梯的线条的方法称为别名;楼梯是理论行的别名。</span><span class="sxs-lookup"><span data-stu-id="294ab-114">This technique of representing a line with a staircase is called aliasing; the staircase is an alias for the theoretical line.</span></span>  
  
## <a name="antialiasing"></a><span data-ttu-id="294ab-115">抗</span><span class="sxs-lookup"><span data-stu-id="294ab-115">Antialiasing</span></span>  
 <span data-ttu-id="294ab-116">用于绘制线条的一种更为复杂的方法涉及使用部分透明像素以及不透明像素。</span><span class="sxs-lookup"><span data-stu-id="294ab-116">A more sophisticated technique for rendering a line involves using partially transparent pixels along with opaque pixels.</span></span> <span data-ttu-id="294ab-117">将像素设置为纯红色，或将其设置为红色和背景色的某种混合，具体取决于它们对线条的接近程度。</span><span class="sxs-lookup"><span data-stu-id="294ab-117">Pixels are set to pure red, or to some blend of red and the background color, depending on how close they are to the line.</span></span> <span data-ttu-id="294ab-118">这种类型的渲染称为抗锯齿，并产生一条线条，人们眼就会感觉更平滑。</span><span class="sxs-lookup"><span data-stu-id="294ab-118">This type of rendering is called antialiasing and results in a line that the human eye perceives as more smooth.</span></span> <span data-ttu-id="294ab-119">下图显示了如何混合特定像素与背景，以生成抗锯齿线。</span><span class="sxs-lookup"><span data-stu-id="294ab-119">The following illustration shows how certain pixels are blended with the background to produce an antialiased line.</span></span>  
  
 <span data-ttu-id="294ab-120">![消除直线的锯齿](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span><span class="sxs-lookup"><span data-stu-id="294ab-120">![Antialiasing a Line](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span></span>  
  
 <span data-ttu-id="294ab-121">抗锯齿（也称为平滑）也可以应用于曲线。</span><span class="sxs-lookup"><span data-stu-id="294ab-121">Antialiasing, also called smoothing, can also be applied to curves.</span></span> <span data-ttu-id="294ab-122">下图显示了平滑椭圆的放大视图。</span><span class="sxs-lookup"><span data-stu-id="294ab-122">The following illustration shows an enlarged view of a smoothed ellipse.</span></span>  
  
 <span data-ttu-id="294ab-123">![消除曲线的锯齿](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span><span class="sxs-lookup"><span data-stu-id="294ab-123">![Antialiasing Curves](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span></span>  
  
 <span data-ttu-id="294ab-124">下图显示了其实际大小的同一椭圆，一次不进行抗锯齿，一次是消除锯齿。</span><span class="sxs-lookup"><span data-stu-id="294ab-124">The following illustration shows the same ellipse in its actual size, once without antialiasing and once with antialiasing.</span></span>  
  
 <span data-ttu-id="294ab-125">![抗锯齿示例](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span><span class="sxs-lookup"><span data-stu-id="294ab-125">![Antialiasing example](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span></span>  
  
 <span data-ttu-id="294ab-126">若要绘制使用抗锯齿的线条和曲线，请创建类的实例 <xref:System.Drawing.Graphics> 并将其 <xref:System.Drawing.Graphics.SmoothingMode%2A> 属性设置为 <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> 或 <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality> 。</span><span class="sxs-lookup"><span data-stu-id="294ab-126">To draw lines and curves that use antialiasing, create an instance of the <xref:System.Drawing.Graphics> class and set its <xref:System.Drawing.Graphics.SmoothingMode%2A> property to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> or <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span></span> <span data-ttu-id="294ab-127">然后调用同一类的一个绘图方法 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="294ab-127">Then call one of the drawing methods of that same <xref:System.Drawing.Graphics> class.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#81](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a><span data-ttu-id="294ab-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="294ab-128">See also</span></span>

- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [<span data-ttu-id="294ab-129">直线、曲线和图形</span><span class="sxs-lookup"><span data-stu-id="294ab-129">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="294ab-130">如何：对文本使用抗锯齿效果</span><span class="sxs-lookup"><span data-stu-id="294ab-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)
