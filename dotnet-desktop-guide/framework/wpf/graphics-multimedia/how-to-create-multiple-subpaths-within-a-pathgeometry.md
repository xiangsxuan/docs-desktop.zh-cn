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
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a>如何：在 PathGeometry 内部创建多个子路径
此示例演示如何在中创建多个子路径 <xref:System.Windows.Media.PathGeometry> 。 若要创建多个子路径，请 <xref:System.Windows.Media.PathFigure> 为每个子路径创建一个。  
  
## <a name="example"></a>示例  
 下面的示例创建两个子路径，每个都有一个三角形。  
  
 [!code-xaml[GeometrySample#38](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 下面的示例演示如何使用 <xref:System.Windows.Shapes.Path> 和特性语法创建多个子路径 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。 每个 `M` 创建一个新的子路径，以使该示例创建两个分别绘制三角形的子路径。  
  
 [!code-xaml[GeometrySample#58](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
  (请注意，此特性语法实际上会创建一个 <xref:System.Windows.Media.StreamGeometry> 较轻量版本的 <xref:System.Windows.Media.PathGeometry> 。 有关详细信息，请参阅[路径标记语法](path-markup-syntax.md)页。）  
  
## <a name="see-also"></a>请参阅

- [Geometry 概述](geometry-overview.md)
