---
title: 如何：使用 StreamGeometry 创建形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
ms.openlocfilehash: aa1270265ff79469c9f325ffe637bbede73374c7
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666870"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a><span data-ttu-id="2f795-102">如何：使用 StreamGeometry 创建形状</span><span class="sxs-lookup"><span data-stu-id="2f795-102">How to: Create a Shape Using a StreamGeometry</span></span>
<span data-ttu-id="2f795-103"><xref:System.Windows.Media.StreamGeometry> 是 <xref:System.Windows.Media.PathGeometry> 用于创建几何形状的轻型替代项。</span><span class="sxs-lookup"><span data-stu-id="2f795-103"><xref:System.Windows.Media.StreamGeometry> is lightweight alternative to <xref:System.Windows.Media.PathGeometry> for creating geometric shapes.</span></span> <span data-ttu-id="2f795-104"><xref:System.Windows.Media.StreamGeometry>当你需要描述复杂的几何图形但不需要支持数据绑定、动画或修改的开销时，请使用。</span><span class="sxs-lookup"><span data-stu-id="2f795-104">Use a <xref:System.Windows.Media.StreamGeometry> when you need to describe a complex geometry but do not want the overhead of supporting data binding, animation, or modification.</span></span> <span data-ttu-id="2f795-105">例如，由于此类的效率， <xref:System.Windows.Media.StreamGeometry> 该类是描述装饰器的不错选择。</span><span class="sxs-lookup"><span data-stu-id="2f795-105">For example, because of its efficiency, the <xref:System.Windows.Media.StreamGeometry> class is a good choice for describing adorners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f795-106">示例</span><span class="sxs-lookup"><span data-stu-id="2f795-106">Example</span></span>  
 <span data-ttu-id="2f795-107">下面的示例使用特性语法在中创建一个 <xref:System.Windows.Media.StreamGeometry> 三角形 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="2f795-107">The following example uses attribute syntax to create a triangular <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 <span data-ttu-id="2f795-108">有关属性语法的详细信息 <xref:System.Windows.Media.StreamGeometry> ，请参阅 [路径标记语法](path-markup-syntax.md) 页。</span><span class="sxs-lookup"><span data-stu-id="2f795-108">For more information about <xref:System.Windows.Media.StreamGeometry> attribute syntax, see the [Path Markup Syntax](path-markup-syntax.md) page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f795-109">示例</span><span class="sxs-lookup"><span data-stu-id="2f795-109">Example</span></span>  
 <span data-ttu-id="2f795-110">下一个示例使用在 <xref:System.Windows.Media.StreamGeometry> 代码中定义三角形。</span><span class="sxs-lookup"><span data-stu-id="2f795-110">The next example uses a <xref:System.Windows.Media.StreamGeometry> to define a triangle in code.</span></span> <span data-ttu-id="2f795-111">首先，该示例创建一个 <xref:System.Windows.Media.StreamGeometry> ，然后获取 <xref:System.Windows.Media.StreamGeometryContext> 并使用它来描述三角形。</span><span class="sxs-lookup"><span data-stu-id="2f795-111">First, the example creates a <xref:System.Windows.Media.StreamGeometry>, then obtains a <xref:System.Windows.Media.StreamGeometryContext> and uses it to describe the triangle.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="2f795-112">示例</span><span class="sxs-lookup"><span data-stu-id="2f795-112">Example</span></span>  
 <span data-ttu-id="2f795-113">下一个示例创建一个方法，该方法使用 <xref:System.Windows.Media.StreamGeometry> 和 <xref:System.Windows.Media.StreamGeometryContext> 来基于指定的参数定义几何形状。</span><span class="sxs-lookup"><span data-stu-id="2f795-113">The next example creates a method that uses a <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.StreamGeometryContext> to define a geometric shape based on specified parameters.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2f795-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f795-114">See also</span></span>

- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.StreamGeometryContext>
- [<span data-ttu-id="2f795-115">使用 PathGeometry 创建形状</span><span class="sxs-lookup"><span data-stu-id="2f795-115">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
- [<span data-ttu-id="2f795-116">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="2f795-116">Geometry Overview</span></span>](geometry-overview.md)
