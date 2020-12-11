---
title: 如何：使用纯色绘制区域
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972075"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="c08cc-102">如何：使用纯色绘制区域</span><span class="sxs-lookup"><span data-stu-id="c08cc-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="c08cc-103">若要使用纯色绘制区域，可以使用预定义的系统画笔（如 <xref:System.Windows.Media.Brushes.Red%2A> 或 <xref:System.Windows.Media.Brushes.Blue%2A> ），也可以创建新的 <xref:System.Windows.Media.SolidColorBrush> 并 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 使用 alpha、红色、绿色和蓝色值对其进行描述。</span><span class="sxs-lookup"><span data-stu-id="c08cc-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="c08cc-104">在 XAML 中，还可以使用十六进制表示法来利用纯色绘制区域。</span><span class="sxs-lookup"><span data-stu-id="c08cc-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="c08cc-105">下面的示例使用上述每种方法绘制 <xref:System.Windows.Shapes.Rectangle> 蓝色。</span><span class="sxs-lookup"><span data-stu-id="c08cc-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c08cc-106">示例</span><span class="sxs-lookup"><span data-stu-id="c08cc-106">Example</span></span>  
 <span data-ttu-id="c08cc-107">**使用预定义画笔**</span><span class="sxs-lookup"><span data-stu-id="c08cc-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="c08cc-108">在下面的示例中，使用预定义的画笔 <xref:System.Windows.Media.Brushes.Blue%2A> 绘制蓝色矩形。</span><span class="sxs-lookup"><span data-stu-id="c08cc-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="c08cc-109">**使用十六进制表示法**</span><span class="sxs-lookup"><span data-stu-id="c08cc-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="c08cc-110">下一个示例使用 8 位十六进制表示法绘制一个蓝色矩形。</span><span class="sxs-lookup"><span data-stu-id="c08cc-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="c08cc-111">**使用 ARGB 值**</span><span class="sxs-lookup"><span data-stu-id="c08cc-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="c08cc-112">下一个示例创建一个 <xref:System.Windows.Media.SolidColorBrush> ，并 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 使用蓝色的 ARGB 值对其进行描述。</span><span class="sxs-lookup"><span data-stu-id="c08cc-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="c08cc-113">有关描述颜色的其他方法，请参阅 <xref:System.Windows.Media.Color> 结构。</span><span class="sxs-lookup"><span data-stu-id="c08cc-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="c08cc-114">**相关主题**</span><span class="sxs-lookup"><span data-stu-id="c08cc-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="c08cc-115">有关 <xref:System.Windows.Media.SolidColorBrush> 和其他示例的详细信息，请参阅 [采用纯色和渐变的绘图概述](painting-with-solid-colors-and-gradients-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="c08cc-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="c08cc-116">此代码示例是为类提供的更大示例的一部分 <xref:System.Windows.Media.SolidColorBrush> 。</span><span class="sxs-lookup"><span data-stu-id="c08cc-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="c08cc-117">有关完整示例，请参阅[画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。</span><span class="sxs-lookup"><span data-stu-id="c08cc-117">For the complete sample, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c08cc-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c08cc-118">See also</span></span>

- <xref:System.Windows.Media.Brushes>
