---
title: 如何：创建 GeometryDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: f5cdcfdb68ad8030bcbd6c689f45a8baddd000e1
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973511"
---
# <a name="how-to-create-a-geometrydrawing"></a><span data-ttu-id="20f06-102">如何：创建 GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="20f06-102">How to: Create a GeometryDrawing</span></span>
<span data-ttu-id="20f06-103">此示例演示如何创建和显示 <xref:System.Windows.Media.GeometryDrawing> 。</span><span class="sxs-lookup"><span data-stu-id="20f06-103">This example shows how to create and display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="20f06-104">利用， <xref:System.Windows.Media.GeometryDrawing> 你可以通过将和与关联来创建具有填充和轮廓的形状 <xref:System.Windows.Media.Pen> <xref:System.Windows.Media.Brush> <xref:System.Windows.Media.Geometry> 。</span><span class="sxs-lookup"><span data-stu-id="20f06-104">A <xref:System.Windows.Media.GeometryDrawing> enables you to create shape with a fill and an outline by associating a <xref:System.Windows.Media.Pen> and a <xref:System.Windows.Media.Brush> with a <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="20f06-105"><xref:System.Windows.Media.GeometryDrawing.Geometry%2A>描述形状的结构， <xref:System.Windows.Media.GeometryDrawing.Brush%2A> 描述形状的填充，并 <xref:System.Windows.Media.GeometryDrawing.Pen%2A> 描述形状的轮廓。</span><span class="sxs-lookup"><span data-stu-id="20f06-105">The <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describes the shape's structure, the <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describes the shape's fill, and the <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describes the shape's outline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20f06-106">示例</span><span class="sxs-lookup"><span data-stu-id="20f06-106">Example</span></span>  
 <span data-ttu-id="20f06-107">下面的示例使用 <xref:System.Windows.Media.GeometryDrawing> 来呈现形状。</span><span class="sxs-lookup"><span data-stu-id="20f06-107">The following example uses a <xref:System.Windows.Media.GeometryDrawing> to render a shape.</span></span> <span data-ttu-id="20f06-108">该形状由 <xref:System.Windows.Media.GeometryGroup> 和两个对象进行描述 <xref:System.Windows.Media.EllipseGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="20f06-108">The shape is described by a <xref:System.Windows.Media.GeometryGroup> and two <xref:System.Windows.Media.EllipseGeometry> objects.</span></span> <span data-ttu-id="20f06-109">形状的内部将使用绘制 <xref:System.Windows.Media.LinearGradientBrush> ，并使用绘制其轮廓 <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen> 。</span><span class="sxs-lookup"><span data-stu-id="20f06-109">The shape's interior is painted with a <xref:System.Windows.Media.LinearGradientBrush> and its outline is drawn with a <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span></span> <span data-ttu-id="20f06-110"><xref:System.Windows.Media.GeometryDrawing>使用 <xref:System.Windows.Media.ImageDrawing> 和 <xref:System.Windows.Controls.Image> 元素显示。</span><span class="sxs-lookup"><span data-stu-id="20f06-110">The <xref:System.Windows.Media.GeometryDrawing> is displayed using an <xref:System.Windows.Media.ImageDrawing> and an <xref:System.Windows.Controls.Image> element.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 <span data-ttu-id="20f06-111">下图显示了生成的 <xref:System.Windows.Media.GeometryDrawing> 。</span><span class="sxs-lookup"><span data-stu-id="20f06-111">The following illustration shows the resulting <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="20f06-112">![两个椭圆形的 GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="20f06-112">![A GeometryDrawing of two ellipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
  
 <span data-ttu-id="20f06-113">若要创建更复杂的绘图，可以使用将多个绘图对象组合成单个复合绘图 <xref:System.Windows.Media.DrawingGroup> 。</span><span class="sxs-lookup"><span data-stu-id="20f06-113">To create more complex drawings, you can combine multiple drawing objects into a single composite drawing using a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f06-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="20f06-114">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup>
- [<span data-ttu-id="20f06-115">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="20f06-115">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="20f06-116">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="20f06-116">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="20f06-117">创建复合绘图</span><span class="sxs-lookup"><span data-stu-id="20f06-117">Create a Composite Drawing</span></span>](how-to-create-a-composite-drawing.md)
