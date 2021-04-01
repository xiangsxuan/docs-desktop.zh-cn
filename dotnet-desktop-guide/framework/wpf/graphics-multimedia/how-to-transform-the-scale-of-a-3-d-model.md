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
# <a name="how-to-transform-the-scale-of-a-3d-model"></a><span data-ttu-id="d3d8e-102">如何：变换三维模型的比例</span><span class="sxs-lookup"><span data-stu-id="d3d8e-102">How to: Transform the Scale of a 3D Model</span></span>
<span data-ttu-id="d3d8e-103">此示例演示如何缩放三维对象。</span><span class="sxs-lookup"><span data-stu-id="d3d8e-103">This example shows how to scale a 3D object.</span></span> <span data-ttu-id="d3d8e-104">若要缩放三维对象，请使用 <xref:System.Windows.Media.Media3D.ScaleTransform3D> 。</span><span class="sxs-lookup"><span data-stu-id="d3d8e-104">To scale a 3D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="d3d8e-105"><xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>、 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> 和 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> 属性按指定的因子调整元素的大小。</span><span class="sxs-lookup"><span data-stu-id="d3d8e-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="d3d8e-106">例如，如果 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> 值为1.5，则将对象拉伸到其原始宽度的150%。</span><span class="sxs-lookup"><span data-stu-id="d3d8e-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="d3d8e-107"><xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>值0.5 将对象的高度缩减50%。</span><span class="sxs-lookup"><span data-stu-id="d3d8e-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="d3d8e-108">下面的代码演示如何使用 <xref:System.Windows.Media.Media3D.ScaleTransform3D> 作为的转换 <xref:System.Windows.Media.Media3D.GeometryModel3D> 。</span><span class="sxs-lookup"><span data-stu-id="d3d8e-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="d3d8e-109">示例</span><span class="sxs-lookup"><span data-stu-id="d3d8e-109">Example</span></span>  
 <span data-ttu-id="d3d8e-110">下面的代码显示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="d3d8e-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d3d8e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3d8e-111">See also</span></span>

- [<span data-ttu-id="d3d8e-112">对三维转换进行动画处理</span><span class="sxs-lookup"><span data-stu-id="d3d8e-112">Animate 3D Translations</span></span>](how-to-animate-3-d-translations.md)
- [<span data-ttu-id="d3d8e-113">创建三维场景</span><span class="sxs-lookup"><span data-stu-id="d3d8e-113">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="d3d8e-114">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="d3d8e-114">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
