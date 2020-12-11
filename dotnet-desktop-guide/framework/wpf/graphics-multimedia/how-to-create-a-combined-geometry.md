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
# <a name="how-to-create-a-combined-geometry"></a>如何：创建组合的几何图形
此示例演示如何组合几何图形。 若要合并两个几何图形，请使用 <xref:System.Windows.Media.CombinedGeometry> 对象。 将其 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 和 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 属性设置为要组合的两个几何图形，并设置 <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> 属性，该属性确定如何将几何图形组合在一起、 `Union` 、 `Intersect` `Exclude` 或 `Xor` 。  
  
 若要从两个或多个几何图形创建复合几何图形，请使用 <xref:System.Windows.Media.GeometryGroup> 。  
  
## <a name="example"></a>示例  
 在下面的示例中， <xref:System.Windows.Media.CombinedGeometry> 使用几何组合模式定义 `Exclude` 。  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和都 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 定义为相同半径的圆，但中心偏移量为50。  
  
 [!code-xaml[GeometrySample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 ![“排除”组合模式的结果](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")  
组合几何图形排除  
  
 在以下标记中， <xref:System.Windows.Media.CombinedGeometry> 使用的合并模式定义了 `Intersect` 。  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和都 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 定义为相同半径的圆，但中心偏移量为50。  
  
 [!code-xaml[GeometrySample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 ![“相交”组合模式的结果](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")  
组合几何交集  
  
 在以下标记中， <xref:System.Windows.Media.CombinedGeometry> 使用的合并模式定义了 `Union` 。  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和都 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 定义为相同半径的圆，但中心偏移量为50。  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![“联合”组合模式的结果](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
组合几何联合  
  
 在以下标记中， <xref:System.Windows.Media.CombinedGeometry> 使用的合并模式定义了 `Xor` 。  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>和都 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 定义为相同半径的圆，但中心偏移量为50。  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Xor 组合模式的结果](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
组合几何 Xor
