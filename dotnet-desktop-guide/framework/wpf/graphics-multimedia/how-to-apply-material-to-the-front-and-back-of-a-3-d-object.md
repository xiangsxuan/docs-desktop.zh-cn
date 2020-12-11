---
title: 如何：向三维对象的正面和背面应用材料
ms.date: 03/30/2017
helpviewer_keywords:
- 3D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 5c24879d97e7857fb07fcef4a9ba8efa901e4a39
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970851"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3d-object"></a><span data-ttu-id="9f9d1-102">如何：向三维对象的正面和背面应用材料</span><span class="sxs-lookup"><span data-stu-id="9f9d1-102">How to: Apply Material to the Front and Back of a 3D Object</span></span>
<span data-ttu-id="9f9d1-103">下面的示例演示如何将应用于 <xref:System.Windows.Media.Media3D.Material> 三维对象的正面和背面，并对对象进行动画处理，以显示对象的两侧。</span><span class="sxs-lookup"><span data-stu-id="9f9d1-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="9f9d1-104">的 <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> 属性 <xref:System.Windows.Media.Media3D.GeometryModel3D> 用于将红色应用于 <xref:System.Windows.Media.Brush> 对象的正面，并 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> 使用的属性将 <xref:System.Windows.Media.Media3D.GeometryModel3D> 蓝色应用于 <xref:System.Windows.Media.Brush> 对象的后一方。</span><span class="sxs-lookup"><span data-stu-id="9f9d1-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="9f9d1-105">下面的代码演示了如何将材料应用到对象：</span><span class="sxs-lookup"><span data-stu-id="9f9d1-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="9f9d1-106">示例</span><span class="sxs-lookup"><span data-stu-id="9f9d1-106">Example</span></span>  
 <span data-ttu-id="9f9d1-107">下面的代码显示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="9f9d1-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="9f9d1-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f9d1-108">See also</span></span>

- [<span data-ttu-id="9f9d1-109">创建三维场景</span><span class="sxs-lookup"><span data-stu-id="9f9d1-109">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="9f9d1-110">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="9f9d1-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="9f9d1-111">对三维场景中的材料属性进行动画处理</span><span class="sxs-lookup"><span data-stu-id="9f9d1-111">Animate Material Properties in a 3D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="9f9d1-112">向三维对象应用放射材料</span><span class="sxs-lookup"><span data-stu-id="9f9d1-112">Apply Emissive Material to a 3D Object</span></span>](how-to-apply-emissive-material-to-a-3-d-object.md)
