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
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a>如何：使用 StreamGeometry 创建形状
<xref:System.Windows.Media.StreamGeometry> 是 <xref:System.Windows.Media.PathGeometry> 用于创建几何形状的轻型替代项。 <xref:System.Windows.Media.StreamGeometry>当你需要描述复杂的几何图形但不需要支持数据绑定、动画或修改的开销时，请使用。 例如，由于此类的效率， <xref:System.Windows.Media.StreamGeometry> 该类是描述装饰器的不错选择。  
  
## <a name="example"></a>示例  
 下面的示例使用特性语法在中创建一个 <xref:System.Windows.Media.StreamGeometry> 三角形 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 有关属性语法的详细信息 <xref:System.Windows.Media.StreamGeometry> ，请参阅 [路径标记语法](path-markup-syntax.md) 页。  
  
## <a name="example"></a>示例  
 下一个示例使用在 <xref:System.Windows.Media.StreamGeometry> 代码中定义三角形。 首先，该示例创建一个 <xref:System.Windows.Media.StreamGeometry> ，然后获取 <xref:System.Windows.Media.StreamGeometryContext> 并使用它来描述三角形。  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a>示例  
 下一个示例创建一个方法，该方法使用 <xref:System.Windows.Media.StreamGeometry> 和 <xref:System.Windows.Media.StreamGeometryContext> 来基于指定的参数定义几何形状。  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.StreamGeometryContext>
- [使用 PathGeometry 创建形状](how-to-create-a-shape-by-using-a-pathgeometry.md)
- [Geometry 概述](geometry-overview.md)
