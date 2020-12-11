---
title: 如何：创建组合的几何图形
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: c5ebe87abd4c2cf70f8fa17f1fcc773293f3ad27
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973518"
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="86b98-102">如何：创建组合的几何图形</span><span class="sxs-lookup"><span data-stu-id="86b98-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="86b98-103">此示例演示如何组合几何图形。</span><span class="sxs-lookup"><span data-stu-id="86b98-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="86b98-104">若要合并两个几何图形，请使用 <xref:System.Windows.Media.CombinedGeometry> 对象。</span><span class="sxs-lookup"><span data-stu-id="86b98-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="86b98-105">将其 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 和 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 属性设置为要组合的两个几何图形，并设置 <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> 属性，该属性确定如何将几何图形组合在一起、 `Union` 、 `Intersect` `Exclude` 或 `Xor` 。</span><span class="sxs-lookup"><span data-stu-id="86b98-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="86b98-106">若要从两个或多个几何图形创建复合几何图形，请使用 <xref:System.Windows.Media.GeometryGroup> 。</span><span class="sxs-lookup"><span data-stu-id="86b98-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86b98-107">示例</span><span class="sxs-lookup"><span data-stu-id="86b98-107">Example</span></span>  
 <span data-ttu-id="86b98-108">在下面的示例中， <xref:System.Windows.Media.CombinedGeometry> 使用几何组合模式定义 `Exclude` 。</span><span class="sxs-lookup"><span data-stu-id="86b98-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="86b98-109"><xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和都 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 定义为相同半径的圆，但中心偏移量为50。</span><span class="sxs-lookup"><span data-stu-id="86b98-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="86b98-110">![“排除”组合模式的结果](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="86b98-110">![Results of the Exclude combine mode](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="86b98-111">组合几何图形排除</span><span class="sxs-lookup"><span data-stu-id="86b98-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="86b98-112">在以下标记中， <xref:System.Windows.Media.CombinedGeometry> 使用的合并模式定义了 `Intersect` 。</span><span class="sxs-lookup"><span data-stu-id="86b98-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="86b98-113"><xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和都 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 定义为相同半径的圆，但中心偏移量为50。</span><span class="sxs-lookup"><span data-stu-id="86b98-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="86b98-114">![“相交”组合模式的结果](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="86b98-114">![Results of the Intersect combine mode](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="86b98-115">组合几何交集</span><span class="sxs-lookup"><span data-stu-id="86b98-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="86b98-116">在以下标记中， <xref:System.Windows.Media.CombinedGeometry> 使用的合并模式定义了 `Union` 。</span><span class="sxs-lookup"><span data-stu-id="86b98-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="86b98-117"><xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和都 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 定义为相同半径的圆，但中心偏移量为50。</span><span class="sxs-lookup"><span data-stu-id="86b98-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="86b98-118">![“联合”组合模式的结果](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="86b98-118">![Results of the Union combine mode](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="86b98-119">组合几何联合</span><span class="sxs-lookup"><span data-stu-id="86b98-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="86b98-120">在以下标记中， <xref:System.Windows.Media.CombinedGeometry> 使用的合并模式定义了 `Xor` 。</span><span class="sxs-lookup"><span data-stu-id="86b98-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="86b98-121"><xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和都 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 定义为相同半径的圆，但中心偏移量为50。</span><span class="sxs-lookup"><span data-stu-id="86b98-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="86b98-122">![Xor 组合模式的结果](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span><span class="sxs-lookup"><span data-stu-id="86b98-122">![Results of the Xor combine mode](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="86b98-123">组合几何 Xor</span><span class="sxs-lookup"><span data-stu-id="86b98-123">Combined Geometry Xor</span></span>
