---
title: 如何：创建复合绘图
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
ms.openlocfilehash: 0af7fbca593627ebe8cd102a02617a27eac50aa5
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974128"
---
# <a name="how-to-create-a-composite-drawing"></a><span data-ttu-id="a37a8-102">如何：创建复合绘图</span><span class="sxs-lookup"><span data-stu-id="a37a8-102">How to: Create a Composite Drawing</span></span>
<span data-ttu-id="a37a8-103">此示例演示如何 <xref:System.Windows.Media.DrawingGroup> 通过将多个 <xref:System.Windows.Media.Drawing> 对象组合成单个复合绘图来使用来创建复杂的绘图。</span><span class="sxs-lookup"><span data-stu-id="a37a8-103">This example shows how to use a <xref:System.Windows.Media.DrawingGroup> to create complex drawings by combining multiple <xref:System.Windows.Media.Drawing> objects into a single composite drawing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a37a8-104">示例</span><span class="sxs-lookup"><span data-stu-id="a37a8-104">Example</span></span>  
 <span data-ttu-id="a37a8-105">下面的示例使用 <xref:System.Windows.Media.DrawingGroup> 从和对象创建复合绘图 <xref:System.Windows.Media.GeometryDrawing> <xref:System.Windows.Media.ImageDrawing> 。</span><span class="sxs-lookup"><span data-stu-id="a37a8-105">The following example uses a <xref:System.Windows.Media.DrawingGroup> to create a composite drawing from the <xref:System.Windows.Media.GeometryDrawing> and <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="a37a8-106">下图显示了此示例生成的输出。</span><span class="sxs-lookup"><span data-stu-id="a37a8-106">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="a37a8-107">![具有多个绘图的 DrawingGroup](./media/graphicsmm-simple.jpg "graphicsmm_simple")</span><span class="sxs-lookup"><span data-stu-id="a37a8-107">![A DrawingGroup with multiple drawings](./media/graphicsmm-simple.jpg "graphicsmm_simple")</span></span>  
<span data-ttu-id="a37a8-108">使用 DrawingGroup 创建的复合绘图</span><span class="sxs-lookup"><span data-stu-id="a37a8-108">A composite drawing that is created by using DrawingGroup</span></span>  
  
 <span data-ttu-id="a37a8-109">请注意显示绘图边界的灰色边框。</span><span class="sxs-lookup"><span data-stu-id="a37a8-109">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <span data-ttu-id="a37a8-110">你可以使用将 <xref:System.Windows.Media.DrawingGroup> <xref:System.Windows.Media.DrawingGroup.Transform%2A> 、 <xref:System.Windows.Media.DrawingGroup.Opacity%2A> 设置、、或应用 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A> 于 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A> <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A> <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> 它包含的绘图。</span><span class="sxs-lookup"><span data-stu-id="a37a8-110">You can use a <xref:System.Windows.Media.DrawingGroup> to apply a <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> setting, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, or <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> to the drawings it contains.</span></span> <span data-ttu-id="a37a8-111">因为 <xref:System.Windows.Media.DrawingGroup> 也是 <xref:System.Windows.Media.Drawing> ，所以它可以包含其他 <xref:System.Windows.Media.DrawingGroup> 对象。</span><span class="sxs-lookup"><span data-stu-id="a37a8-111">Because a <xref:System.Windows.Media.DrawingGroup> is also a <xref:System.Windows.Media.Drawing>, it can contain other <xref:System.Windows.Media.DrawingGroup> objects.</span></span>  
  
 <span data-ttu-id="a37a8-112">下面的示例与前面的示例类似，不同之处在于它使用其他 <xref:System.Windows.Media.DrawingGroup> 对象将位图效果和不透明蒙板应用于其部分绘图。</span><span class="sxs-lookup"><span data-stu-id="a37a8-112">The following example is similar to the preceding example, except that it uses additional <xref:System.Windows.Media.DrawingGroup> objects to apply bitmap effects and an opacity mask to some of its drawings.</span></span> <span data-ttu-id="a37a8-113">下图显示了此示例生成的输出。</span><span class="sxs-lookup"><span data-stu-id="a37a8-113">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="a37a8-114">![具有多个绘图的 DrawingGroup](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span><span class="sxs-lookup"><span data-stu-id="a37a8-114">![A DrawingGroup with multiple drawings](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span></span>  
<span data-ttu-id="a37a8-115">具有多个 DrawingGroup 对象的复合绘图</span><span class="sxs-lookup"><span data-stu-id="a37a8-115">Composite drawing that has multiple DrawingGroup objects</span></span>  
  
 <span data-ttu-id="a37a8-116">请注意显示绘图边界的灰色边框。</span><span class="sxs-lookup"><span data-stu-id="a37a8-116">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 <span data-ttu-id="a37a8-117">有关对象的详细信息 <xref:System.Windows.Media.Drawing> ，请参阅 [绘图对象概述](drawing-objects-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a37a8-117">For more information about <xref:System.Windows.Media.Drawing> objects, see [Drawing Objects Overview](drawing-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a37a8-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a37a8-118">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>
- <xref:System.Windows.Media.DrawingGroup.Transform%2A>
- <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>
- <xref:System.Windows.Media.DrawingGroup.Opacity%2A>
- <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>
- <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>
- [<span data-ttu-id="a37a8-119">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="a37a8-119">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
