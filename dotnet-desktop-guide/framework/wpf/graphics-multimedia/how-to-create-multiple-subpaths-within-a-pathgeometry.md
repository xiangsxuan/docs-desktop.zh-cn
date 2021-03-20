---
title: 如何：在 PathGeometry 内部创建多个子路径
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: 8b88e47c329041ada4cb7d82c876ac98f0e23d05
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667157"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a><span data-ttu-id="4d991-102">如何：在 PathGeometry 内部创建多个子路径</span><span class="sxs-lookup"><span data-stu-id="4d991-102">How to: Create Multiple Subpaths Within a PathGeometry</span></span>
<span data-ttu-id="4d991-103">此示例演示如何在中创建多个子路径 <xref:System.Windows.Media.PathGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="4d991-103">This example shows how to create multiple subpaths in a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="4d991-104">若要创建多个子路径，请 <xref:System.Windows.Media.PathFigure> 为每个子路径创建一个。</span><span class="sxs-lookup"><span data-stu-id="4d991-104">To create multiple subpaths, you create a <xref:System.Windows.Media.PathFigure> for each subpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d991-105">示例</span><span class="sxs-lookup"><span data-stu-id="4d991-105">Example</span></span>  
 <span data-ttu-id="4d991-106">下面的示例创建两个子路径，每个都有一个三角形。</span><span class="sxs-lookup"><span data-stu-id="4d991-106">The following example creates two subpaths, each one a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#38](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 <span data-ttu-id="4d991-107">下面的示例演示如何使用 <xref:System.Windows.Shapes.Path> 和特性语法创建多个子路径 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="4d991-107">The following example shows how to create multiple subpaths by using a <xref:System.Windows.Shapes.Path> and [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] attribute syntax.</span></span> <span data-ttu-id="4d991-108">每个 `M` 创建一个新的子路径，以使该示例创建两个分别绘制三角形的子路径。</span><span class="sxs-lookup"><span data-stu-id="4d991-108">Each `M` creates a new subpath so that the example creates two subpaths that each draw a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#58](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 <span data-ttu-id="4d991-109"> (请注意，此特性语法实际上会创建一个 <xref:System.Windows.Media.StreamGeometry> 较轻量版本的 <xref:System.Windows.Media.PathGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="4d991-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="4d991-110">有关详细信息，请参阅[路径标记语法](path-markup-syntax.md)页。）</span><span class="sxs-lookup"><span data-stu-id="4d991-110">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d991-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d991-111">See also</span></span>

- [<span data-ttu-id="4d991-112">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="4d991-112">Geometry Overview</span></span>](geometry-overview.md)
