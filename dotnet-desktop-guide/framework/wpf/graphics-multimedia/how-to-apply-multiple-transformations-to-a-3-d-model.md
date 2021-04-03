---
title: 如何：向三维模型应用多个转换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D models [WPF], applying multiple transformations to
ms.assetid: cb72245a-5560-4c96-9f58-593c66296992
ms.openlocfilehash: 6400d224fb51b93c76c5e9798b4bcc68ff3b9de6
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973670"
---
# <a name="how-to-apply-multiple-transformations-to-a-3d-model"></a><span data-ttu-id="76039-102">如何：向三维模型应用多个转换</span><span class="sxs-lookup"><span data-stu-id="76039-102">How to: Apply Multiple Transformations to a 3D Model</span></span>
<span data-ttu-id="76039-103">此示例演示如何使用 <xref:System.Windows.Media.Media3D.RotateTransform3D> 和 <xref:System.Windows.Media.Media3D.ScaleTransform3D> 来旋转和更改三维模型的刻度。</span><span class="sxs-lookup"><span data-stu-id="76039-103">This sample shows how to use a <xref:System.Windows.Media.Media3D.RotateTransform3D> and a <xref:System.Windows.Media.Media3D.ScaleTransform3D> to rotate and change the scale of a 3D model.</span></span> <span data-ttu-id="76039-104">下面的代码演示如何在 XAML 中将这些转换应用到 <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> 的属性 <xref:System.Windows.Media.Media3D.GeometryModel3D> 。</span><span class="sxs-lookup"><span data-stu-id="76039-104">The code below shows how to apply these transforms to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexampleinline1)]  
  
 <span data-ttu-id="76039-105">在代码中：</span><span class="sxs-lookup"><span data-stu-id="76039-105">In code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="76039-106">示例</span><span class="sxs-lookup"><span data-stu-id="76039-106">Example</span></span>  
 <span data-ttu-id="76039-107">下面的代码演示了 XAML 中的整个示例。</span><span class="sxs-lookup"><span data-stu-id="76039-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="76039-108">示例</span><span class="sxs-lookup"><span data-stu-id="76039-108">Example</span></span>  
 <span data-ttu-id="76039-109">下面是代码中的整个示例。</span><span class="sxs-lookup"><span data-stu-id="76039-109">Below is the entire sample in code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="76039-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76039-110">See also</span></span>

- [<span data-ttu-id="76039-111">转换三维模型的比例</span><span class="sxs-lookup"><span data-stu-id="76039-111">Transform the Scale of a 3D Model</span></span>](how-to-transform-the-scale-of-a-3-d-model.md)
