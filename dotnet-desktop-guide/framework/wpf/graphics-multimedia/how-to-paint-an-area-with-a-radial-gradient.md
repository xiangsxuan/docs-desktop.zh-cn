---
title: 如何：使用径向渐变绘制区域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 8a53d5d7247f82905816265f7c92b22f287591c5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972076"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="ac558-102">如何：使用径向渐变绘制区域</span><span class="sxs-lookup"><span data-stu-id="ac558-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="ac558-103">此示例演示如何使用 <xref:System.Windows.Media.RadialGradientBrush> 类绘制带有径向渐变的区域。</span><span class="sxs-lookup"><span data-stu-id="ac558-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac558-104">示例</span><span class="sxs-lookup"><span data-stu-id="ac558-104">Example</span></span>  
 <span data-ttu-id="ac558-105">下面的示例使用 <xref:System.Windows.Media.RadialGradientBrush> 绘制一个矩形，该矩形具有从黄色转换为红色到浅绿色的径向渐变。</span><span class="sxs-lookup"><span data-stu-id="ac558-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="ac558-106">下图显示了前面示例的渐变。</span><span class="sxs-lookup"><span data-stu-id="ac558-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="ac558-107">渐变的停止点已突出显示。</span><span class="sxs-lookup"><span data-stu-id="ac558-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="ac558-108">![径向渐变中的渐变停止点](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="ac558-108">![Gradient stops in a radial gradient](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ac558-109">本主题中的示例使用默认坐标系统来设置控制点。</span><span class="sxs-lookup"><span data-stu-id="ac558-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="ac558-110">默认坐标系与边界框相关：0指示边界框的0%，1指示边界框的100%。</span><span class="sxs-lookup"><span data-stu-id="ac558-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="ac558-111">您可以通过将属性设置为值来更改此坐标系统 <xref:System.Windows.Media.GradientBrush.MappingMode%2A> <xref:System.Windows.Media.BrushMappingMode.Absolute> 。</span><span class="sxs-lookup"><span data-stu-id="ac558-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="ac558-112">绝对坐标系与范围框无关。</span><span class="sxs-lookup"><span data-stu-id="ac558-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="ac558-113">值直接在本地空间中解释。</span><span class="sxs-lookup"><span data-stu-id="ac558-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="ac558-114">有关其他 <xref:System.Windows.Media.RadialGradientBrush> 示例，请参阅 [画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。</span><span class="sxs-lookup"><span data-stu-id="ac558-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="ac558-115">有关渐变和其他类型画笔的详细信息，请参阅 [采用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="ac558-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
