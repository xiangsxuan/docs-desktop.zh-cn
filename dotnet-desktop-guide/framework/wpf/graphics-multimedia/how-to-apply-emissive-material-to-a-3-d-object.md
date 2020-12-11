---
title: 如何：向三维对象应用放射材料
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3D objects
- 3D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: bf32b41ec2410c01ad137ec0ca9311f7c2b70061
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973672"
---
# <a name="how-to-apply-emissive-material-to-a-3d-object"></a><span data-ttu-id="75117-102">如何：向三维对象应用放射材料</span><span class="sxs-lookup"><span data-stu-id="75117-102">How to: Apply Emissive Material to a 3D Object</span></span>
<span data-ttu-id="75117-103">下面的示例演示如何使用 <xref:System.Windows.Media.Media3D.EmissiveMaterial> 向与 EmissiveMaterial 画笔的颜色相等的现有材料添加颜色。</span><span class="sxs-lookup"><span data-stu-id="75117-103">The following example shows how to use <xref:System.Windows.Media.Media3D.EmissiveMaterial> to add color to an existing Material equal to the color of the EmissiveMaterial's brush.</span></span> <span data-ttu-id="75117-104">下面的代码以 <xref:System.Windows.Media.Media3D.DiffuseMaterial> 组合显示和 <xref:System.Windows.Media.Media3D.EmissiveMaterial> 应用，以将蓝色添加到 DiffuseMaterial 的外观。</span><span class="sxs-lookup"><span data-stu-id="75117-104">The code below shows <xref:System.Windows.Media.Media3D.DiffuseMaterial> and <xref:System.Windows.Media.Media3D.EmissiveMaterial> applied in combination to add blue to the DiffuseMaterial's appearance.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 <span data-ttu-id="75117-105">在程序代码中：</span><span class="sxs-lookup"><span data-stu-id="75117-105">In procedural code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="75117-106">示例</span><span class="sxs-lookup"><span data-stu-id="75117-106">Example</span></span>  
 <span data-ttu-id="75117-107">下面的代码演示了 XAML 中的整个示例。</span><span class="sxs-lookup"><span data-stu-id="75117-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="75117-108">示例</span><span class="sxs-lookup"><span data-stu-id="75117-108">Example</span></span>  
 <span data-ttu-id="75117-109">下面是过程代码中的整个示例。</span><span class="sxs-lookup"><span data-stu-id="75117-109">Below is the entire sample in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="75117-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75117-110">See also</span></span>

- [<span data-ttu-id="75117-111">创建三维场景</span><span class="sxs-lookup"><span data-stu-id="75117-111">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="75117-112">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="75117-112">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="75117-113">对三维场景中的材料属性进行动画处理</span><span class="sxs-lookup"><span data-stu-id="75117-113">Animate Material Properties in a 3D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="75117-114">向三维对象的正面和背面应用材料</span><span class="sxs-lookup"><span data-stu-id="75117-114">Apply Material to the Front and Back of a 3D Object</span></span>](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
