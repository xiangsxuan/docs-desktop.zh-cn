---
title: 如何：向三维对象的正面和背面应用材料
ms.date: 03/30/2017
helpviewer_keywords:
- 3D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 5c24879d97e7857fb07fcef4a9ba8efa901e4a39
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970851"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3d-object"></a>如何：向三维对象的正面和背面应用材料
下面的示例演示如何将应用于 <xref:System.Windows.Media.Media3D.Material> 三维对象的正面和背面，并对对象进行动画处理，以显示对象的两侧。 的 <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> 属性 <xref:System.Windows.Media.Media3D.GeometryModel3D> 用于将红色应用于 <xref:System.Windows.Media.Brush> 对象的正面，并 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> 使用的属性将 <xref:System.Windows.Media.Media3D.GeometryModel3D> 蓝色应用于 <xref:System.Windows.Media.Brush> 对象的后一方。 下面的代码演示了如何将材料应用到对象：  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a>示例  
 下面的代码显示了整个示例。  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a>请参阅

- [创建三维场景](how-to-create-a-3-d-scene.md)
- [三维图形概述](3-d-graphics-overview.md)
- [对三维场景中的材料属性进行动画处理](how-to-animate-material-properties-in-a-3-d-scene.md)
- [向三维对象应用放射材料](how-to-apply-emissive-material-to-a-3-d-object.md)
