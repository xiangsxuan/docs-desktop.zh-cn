---
title: 如何：使用 ImageDrawing 绘制图像
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: f9459185bf81160b45222e7d6821e0f945ada381
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970214"
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a><span data-ttu-id="f9fed-102">如何：使用 ImageDrawing 绘制图像</span><span class="sxs-lookup"><span data-stu-id="f9fed-102">How to: Draw an Image Using ImageDrawing</span></span>
<span data-ttu-id="f9fed-103">此示例演示如何使用 <xref:System.Windows.Media.ImageDrawing> 绘制图像。</span><span class="sxs-lookup"><span data-stu-id="f9fed-103">This example shows how to use an <xref:System.Windows.Media.ImageDrawing> to draw an image.</span></span> <span data-ttu-id="f9fed-104"><xref:System.Windows.Media.ImageDrawing>使您能够显示 <xref:System.Windows.Media.ImageSource> 带有 <xref:System.Windows.Media.DrawingBrush> 、或的 <xref:System.Windows.Media.DrawingImage> <xref:System.Windows.Media.Visual> 。</span><span class="sxs-lookup"><span data-stu-id="f9fed-104">An <xref:System.Windows.Media.ImageDrawing> enables you display an <xref:System.Windows.Media.ImageSource> with a <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, or <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="f9fed-105">若要绘制图像，请创建 <xref:System.Windows.Media.ImageDrawing> 并设置其 <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="f9fed-105">To draw an image, you create an <xref:System.Windows.Media.ImageDrawing> and set its <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> and <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="f9fed-106"><xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType>属性指定要绘制的图像，而 <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> 属性指定每个图像的位置和大小。</span><span class="sxs-lookup"><span data-stu-id="f9fed-106">The <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> property specifies the image to draw, and the <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> property specifies the position and size of each image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9fed-107">示例</span><span class="sxs-lookup"><span data-stu-id="f9fed-107">Example</span></span>  
 <span data-ttu-id="f9fed-108">下面的示例使用四个对象创建复合绘图 <xref:System.Windows.Media.ImageDrawing> 。</span><span class="sxs-lookup"><span data-stu-id="f9fed-108">The following example creates a composite drawing using four <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="f9fed-109">此示例生成以下图像：</span><span class="sxs-lookup"><span data-stu-id="f9fed-109">This example produces the following image:</span></span>  
  
 <span data-ttu-id="f9fed-110">![几个 DrawingImage 对象](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span><span class="sxs-lookup"><span data-stu-id="f9fed-110">![Several DrawingImage objects](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span></span>  
<span data-ttu-id="f9fed-111">四个 ImageDrawing 对象</span><span class="sxs-lookup"><span data-stu-id="f9fed-111">Four ImageDrawing objects</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 <span data-ttu-id="f9fed-112">有关演示如何在不使用的情况下显示图像的简单方法 <xref:System.Windows.Media.ImageDrawing> ，请参阅 [使用 image 元素](../controls/how-to-use-the-image-element.md)。</span><span class="sxs-lookup"><span data-stu-id="f9fed-112">For an example showing a simple way to display an image without using <xref:System.Windows.Media.ImageDrawing>, see [Use the Image Element](../controls/how-to-use-the-image-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9fed-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9fed-113">See also</span></span>

- <xref:System.Windows.Freezable.Freeze%2A>
- <xref:System.Windows.Controls.Image>
- [<span data-ttu-id="f9fed-114">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="f9fed-114">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="f9fed-115">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="f9fed-115">Freezable Objects Overview</span></span>](../advanced/freezable-objects-overview.md)
- [<span data-ttu-id="f9fed-116">PresentationOptions:Freeze 特性</span><span class="sxs-lookup"><span data-stu-id="f9fed-116">PresentationOptions:Freeze Attribute</span></span>](../advanced/presentationoptions-freeze-attribute.md)
