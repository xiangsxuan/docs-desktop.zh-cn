---
title: 如何：创建三维场景
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3D
- 3D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 36453894e06e7b59f339c21713449140c17f6851
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973526"
---
# <a name="how-to-create-a-3d-scene"></a>如何：创建三维场景
此示例演示如何创建一个三维对象，使其看起来像一张旋转的纸张。 <xref:System.Windows.Controls.Viewport3D>和以下组件一起用于创建这个简单的三维场景：  
  
- 照相机是使用创建的 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 。 照相机指定三维场景的哪部分是可查看的。  
  
- 将创建一个网格，以使用的属性指定 (纸) 的3D 对象的形状 <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> <xref:System.Windows.Media.Media3D.GeometryModel3D> 。  
  
- 在此示例中使用的属性指定要在对象的表面上显示的材料 (线性渐变) <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> <xref:System.Windows.Media.Media3D.GeometryModel3D> 。  
  
- 将创建一个用来照射对象的光源 <xref:System.Windows.Media.Media3D.DirectionalLight> 。  
  
## <a name="example"></a>示例  
 下面的代码演示如何在 XAML 中创建三维场景。  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a>示例  
 下面的代码演示如何在程序代码中创建相同的三维场景。  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [三维图形概述](3-d-graphics-overview.md)
