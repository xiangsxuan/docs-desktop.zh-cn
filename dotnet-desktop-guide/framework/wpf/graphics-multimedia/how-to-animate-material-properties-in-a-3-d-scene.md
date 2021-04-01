---
title: 如何：对三维场景中的材质属性进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3D scenes
- animation [WPF], Material properties in 3D scenes
- 3D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: db59debcd7558cde52d8604cb04c8c4e68921825
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970945"
---
# <a name="how-to-animate-material-properties-in-a-3d-scene"></a><span data-ttu-id="45f65-102">如何：对三维场景中的材质属性进行动画处理</span><span class="sxs-lookup"><span data-stu-id="45f65-102">How to: Animate Material Properties in a 3D Scene</span></span>
<span data-ttu-id="45f65-103">此示例演示如何对应用于 <xref:System.Windows.Media.Brush.Opacity%2A> 三维模型的的属性进行动画处理 <xref:System.Windows.Media.Media3D.Material> 。</span><span class="sxs-lookup"><span data-stu-id="45f65-103">This example shows how to animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Media3D.Material> applied to a 3D model.</span></span>  
  
 <span data-ttu-id="45f65-104">下面的代码示例定义了 <xref:System.Windows.Media.LinearGradientBrush> 用于 <xref:System.Windows.Media.Media3D.Material> 3d 对象的。</span><span class="sxs-lookup"><span data-stu-id="45f65-104">The following code example defines the <xref:System.Windows.Media.LinearGradientBrush> used as the <xref:System.Windows.Media.Media3D.Material> applied to the 3D object.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 <span data-ttu-id="45f65-105"><xref:System.Windows.Media.Brush.Opacity%2A> <xref:System.Windows.Media.LinearGradientBrush> 使用下面的代码示例对此的属性进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="45f65-105">The <xref:System.Windows.Media.Brush.Opacity%2A> property of this <xref:System.Windows.Media.LinearGradientBrush> is animated using the code example below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="45f65-106">示例</span><span class="sxs-lookup"><span data-stu-id="45f65-106">Example</span></span>  
 <span data-ttu-id="45f65-107">下面的代码显示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="45f65-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="45f65-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="45f65-108">See also</span></span>

- [<span data-ttu-id="45f65-109">创建三维场景</span><span class="sxs-lookup"><span data-stu-id="45f65-109">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="45f65-110">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="45f65-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
