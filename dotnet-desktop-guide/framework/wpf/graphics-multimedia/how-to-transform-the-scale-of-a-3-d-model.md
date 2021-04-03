---
title: 如何：变换三维模型的比例
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3D objects
- 3D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: be41a0e10929912c1b54bf7140d743d9453199bf
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972763"
---
# <a name="how-to-transform-the-scale-of-a-3d-model"></a>如何：变换三维模型的比例
此示例演示如何缩放三维对象。 若要缩放三维对象，请使用 <xref:System.Windows.Media.Media3D.ScaleTransform3D> 。 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>、 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> 和 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> 属性按指定的因子调整元素的大小。 例如，如果 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> 值为1.5，则将对象拉伸到其原始宽度的150%。 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>值0.5 将对象的高度缩减50%。 下面的代码演示如何使用 <xref:System.Windows.Media.Media3D.ScaleTransform3D> 作为的转换 <xref:System.Windows.Media.Media3D.GeometryModel3D> 。  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a>示例  
 下面的代码显示了整个示例。  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- [对三维转换进行动画处理](how-to-animate-3-d-translations.md)
- [创建三维场景](how-to-create-a-3-d-scene.md)
- [三维图形概述](3-d-graphics-overview.md)
