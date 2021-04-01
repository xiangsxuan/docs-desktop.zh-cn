---
title: 如何：向三维模型应用绘图
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3D models
- 3D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 794ca9a48bcec42c3eee4d8da143f3ae9d27fcf2
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973176"
---
# <a name="how-to-apply-a-drawing-to-a-3d-model"></a><span data-ttu-id="ef3e1-102">如何：向三维模型应用绘图</span><span class="sxs-lookup"><span data-stu-id="ef3e1-102">How to: Apply a Drawing to a 3D Model</span></span>

<span data-ttu-id="ef3e1-103">此示例演示如何使用 <xref:System.Windows.Media.DrawingBrush> 作为 <xref:System.Windows.Media.Media3D.Material> 应用于三维模型的。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3D model.</span></span>

<span data-ttu-id="ef3e1-104">下面的代码将定义 <xref:System.Windows.Media.DrawingGroup> 为的内容 <xref:System.Windows.Media.DrawingBrush> 。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="ef3e1-105"><xref:System.Windows.Media.DrawingBrush>设置为 <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> <xref:System.Windows.Media.Media3D.DiffuseMaterial> 应用于三维平面的的属性。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="ef3e1-106">通常需要将复杂对象和值（如下面的绘图）定义为可重复使用的资源，并简化你的代码。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="ef3e1-107">有关详细信息，请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define) 。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-107">See [XAML Resources](/dotnet/desktop-wpf/fundamentals/xaml-resources-define) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="ef3e1-108">示例</span><span class="sxs-lookup"><span data-stu-id="ef3e1-108">Example</span></span>

<span data-ttu-id="ef3e1-109">下面的代码显示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="ef3e1-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="ef3e1-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef3e1-110">See also</span></span>

- [<span data-ttu-id="ef3e1-111">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="ef3e1-111">XAML Resources</span></span>](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [<span data-ttu-id="ef3e1-112">创建三维场景</span><span class="sxs-lookup"><span data-stu-id="ef3e1-112">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="ef3e1-113">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="ef3e1-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="ef3e1-114">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="ef3e1-114">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
