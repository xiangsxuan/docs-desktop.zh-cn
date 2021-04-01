---
title: 如何：对三维平移进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations
- 3D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 7d4fff9c74663bd220ad5d15a983bcb639621afd
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970868"
---
# <a name="how-to-animate-3d-translations"></a><span data-ttu-id="96d05-102">如何：对三维平移进行动画处理</span><span class="sxs-lookup"><span data-stu-id="96d05-102">How to: Animate 3D Translations</span></span>
<span data-ttu-id="96d05-103">本主题演示如何对三维模型上设置的翻译转换进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="96d05-103">This topic demonstrates how to animate a translation transformation set on a 3D model.</span></span>  
  
 <span data-ttu-id="96d05-104">下面的代码演示了 <xref:System.Windows.Media.Media3D.TranslateTransform3D> 如何将对象应用到的 <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> 属性 <xref:System.Windows.Media.Media3D.GeometryModel3D> 。</span><span class="sxs-lookup"><span data-stu-id="96d05-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="96d05-105"><xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> <xref:System.Windows.Media.Media3D.TranslateTransform3D> 使用以下代码对此对象的属性进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="96d05-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="96d05-106">示例</span><span class="sxs-lookup"><span data-stu-id="96d05-106">Example</span></span>  
 <span data-ttu-id="96d05-107">下面的代码显示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="96d05-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="96d05-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="96d05-108">See also</span></span>

- [<span data-ttu-id="96d05-109">动画概述</span><span class="sxs-lookup"><span data-stu-id="96d05-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="96d05-110">创建三维场景</span><span class="sxs-lookup"><span data-stu-id="96d05-110">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="96d05-111">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="96d05-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="96d05-112">转换概述</span><span class="sxs-lookup"><span data-stu-id="96d05-112">Transforms Overview</span></span>](transforms-overview.md)
