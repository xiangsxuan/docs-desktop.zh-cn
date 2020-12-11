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
# <a name="regions-in-gdi"></a><span data-ttu-id="f2ca5-102">GDI+ 中的区域</span><span class="sxs-lookup"><span data-stu-id="f2ca5-102">Regions in GDI+</span></span>
<span data-ttu-id="f2ca5-103">区域是输出设备的显示区域的一部分。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-103">A region is a portion of the display area of an output device.</span></span> <span data-ttu-id="f2ca5-104">区域可以简单 (单个矩形) 或复杂 (多边形和闭合曲线的组合) 。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-104">Regions can be simple (a single rectangle) or complex (a combination of polygons and closed curves).</span></span> <span data-ttu-id="f2ca5-105">下图显示了两个区域：一个从矩形构造，另一个从路径构造。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-105">The following illustration shows two regions: one constructed from a rectangle, and the other constructed from a path.</span></span>  
  
 <span data-ttu-id="f2ca5-106">![区域](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span><span class="sxs-lookup"><span data-stu-id="f2ca5-106">![Regions](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span></span>  
  
## <a name="using-regions"></a><span data-ttu-id="f2ca5-107">使用区域</span><span class="sxs-lookup"><span data-stu-id="f2ca5-107">Using Regions</span></span>  
 <span data-ttu-id="f2ca5-108">区域通常用于剪辑和命中测试。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-108">Regions are often used for clipping and hit testing.</span></span> <span data-ttu-id="f2ca5-109">剪辑涉及将绘图限制为显示区域的某个区域，通常是需要更新的部分。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-109">Clipping involves restricting drawing to a certain region of the display area, usually the portion that needs to be updated.</span></span> <span data-ttu-id="f2ca5-110">命中测试涉及到检查以确定在按下鼠标按钮时光标是否位于屏幕的某个区域。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-110">Hit testing involves checking to determine whether the cursor is in a certain region of the screen when a mouse button is pressed.</span></span>  
  
 <span data-ttu-id="f2ca5-111">可以从矩形或路径构造区域。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-111">You can construct a region from a rectangle or a path.</span></span> <span data-ttu-id="f2ca5-112">还可以通过组合现有区域来创建复杂区域。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-112">You can also create complex regions by combining existing regions.</span></span> <span data-ttu-id="f2ca5-113"><xref:System.Drawing.Region>类提供以下方法用于组合区域： <xref:System.Drawing.Region.Intersect%2A> 、 <xref:System.Drawing.Region.Union%2A> 、 <xref:System.Drawing.Region.Xor%2A> 、 <xref:System.Drawing.Region.Exclude%2A> 和 <xref:System.Drawing.Region.Complement%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-113">The <xref:System.Drawing.Region> class provides the following methods for combining regions: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, and <xref:System.Drawing.Region.Complement%2A>.</span></span>  
  
 <span data-ttu-id="f2ca5-114">两个区域的交集是属于这两个区域的所有点的集合。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-114">The intersection of two regions is the set of all points belonging to both regions.</span></span> <span data-ttu-id="f2ca5-115">联合是属于一个或两个区域的所有点的集合。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-115">The union is the set of all points belonging to one or the other or both regions.</span></span> <span data-ttu-id="f2ca5-116">区域的补码是不在区域中的所有点的集合。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-116">The complement of a region is the set of all points that are not in the region.</span></span> <span data-ttu-id="f2ca5-117">下图显示了上图中所示的两个区域的交集和并集。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-117">The following illustration shows the intersection and union of the two regions shown in the preceding illustration.</span></span>  
  
 <span data-ttu-id="f2ca5-118">![区域](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span><span class="sxs-lookup"><span data-stu-id="f2ca5-118">![Regions](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span></span>  
  
 <span data-ttu-id="f2ca5-119"><xref:System.Drawing.Region.Xor%2A>应用于一对区域的方法将生成一个区域，该区域包含属于一个或多个区域的所有点，但不能同时包含两者。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-119">The <xref:System.Drawing.Region.Xor%2A> method, applied to a pair of regions, produces a region that contains all points that belong to one region or the other, but not both.</span></span> <span data-ttu-id="f2ca5-120"><xref:System.Drawing.Region.Exclude%2A>应用于一对区域的方法将生成一个区域，其中包含第一个区域中不在第二个区域中的所有点。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-120">The <xref:System.Drawing.Region.Exclude%2A> method, applied to a pair of regions, produces a region that contains all points in the first region that are not in the second region.</span></span> <span data-ttu-id="f2ca5-121">下图显示了通过将 <xref:System.Drawing.Region.Xor%2A> 和 <xref:System.Drawing.Region.Exclude%2A> 方法应用于本主题开头所示的两个区域而产生的区域。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-121">The following illustration shows the regions that result from applying the <xref:System.Drawing.Region.Xor%2A> and <xref:System.Drawing.Region.Exclude%2A> methods to the two regions shown at the beginning of this topic.</span></span>  
  
 <span data-ttu-id="f2ca5-122">![区域](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span><span class="sxs-lookup"><span data-stu-id="f2ca5-122">![Regions](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span></span>  
  
 <span data-ttu-id="f2ca5-123">若要填充区域，需要 <xref:System.Drawing.Graphics> 对象、对象 <xref:System.Drawing.Brush> 和 <xref:System.Drawing.Region> 对象。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-123">To fill a region, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Brush> object, and a <xref:System.Drawing.Region> object.</span></span> <span data-ttu-id="f2ca5-124"><xref:System.Drawing.Graphics>对象提供 <xref:System.Drawing.Graphics.FillRegion%2A> 方法， <xref:System.Drawing.Brush> 对象存储填充的特性，如颜色或图案。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-124">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.FillRegion%2A> method, and the <xref:System.Drawing.Brush> object stores attributes of the fill, such as color or pattern.</span></span> <span data-ttu-id="f2ca5-125">下面的示例使用纯色填充区域。</span><span class="sxs-lookup"><span data-stu-id="f2ca5-125">The following example fills a region with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#61](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="f2ca5-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2ca5-126">See also</span></span>

- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [<span data-ttu-id="f2ca5-127">直线、曲线和图形</span><span class="sxs-lookup"><span data-stu-id="f2ca5-127">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="f2ca5-128">使用区域</span><span class="sxs-lookup"><span data-stu-id="f2ca5-128">Using Regions</span></span>](using-regions.md)
