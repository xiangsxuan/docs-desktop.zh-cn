---
title: 如何：对三维场景中的材质属性进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3D scenes
- animation [WPF], Material properties in 3D scenes
- 3D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: db59debcd7558cde52d8604cb04c8c4e68921825
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970945"
---
# <a name="how-to-animate-material-properties-in-a-3d-scene"></a>如何：对三维场景中的材质属性进行动画处理
此示例演示如何对应用于 <xref:System.Windows.Media.Brush.Opacity%2A> 三维模型的的属性进行动画处理 <xref:System.Windows.Media.Media3D.Material> 。  
  
 下面的代码示例定义了 <xref:System.Windows.Media.LinearGradientBrush> 用于 <xref:System.Windows.Media.Media3D.Material> 3d 对象的。  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 <xref:System.Windows.Media.Brush.Opacity%2A> <xref:System.Windows.Media.LinearGradientBrush> 使用下面的代码示例对此的属性进行动画处理。  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a>示例  
 下面的代码显示了整个示例。  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [创建三维场景](how-to-create-a-3-d-scene.md)
- [三维图形概述](3-d-graphics-overview.md)
