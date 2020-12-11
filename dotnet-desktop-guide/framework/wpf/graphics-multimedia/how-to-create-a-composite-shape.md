---
title: 如何：创建复合形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: c56053f2b07d6055deac5097a68fd7b80ad704ba
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973512"
---
# <a name="how-to-create-a-composite-shape"></a>如何：创建复合形状
此示例演示如何使用对象创建复合形状 <xref:System.Windows.Media.Geometry> 并使用元素显示它们 <xref:System.Windows.Shapes.Path> 。 在下面的示例中，将 <xref:System.Windows.Media.LineGeometry> 、 <xref:System.Windows.Media.EllipseGeometry> 和与 <xref:System.Windows.Media.RectangleGeometry> 结合使用 <xref:System.Windows.Media.GeometryGroup> 来创建复合形状。 然后使用元素绘制几何 <xref:System.Windows.Shapes.Path> 。  
  
## <a name="example"></a>示例  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 下图显示在上一个示例中创建的形状。  
  
 ![使用 GeometryGroup 创建的复合几何图形](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")  
复合几何图形  
  
 对于更复杂的形状（如多边形和带有曲线段的形状），可以使用创建 <xref:System.Windows.Media.PathGeometry> 。 有关演示如何使用创建形状的示例 <xref:System.Windows.Media.PathGeometry> ，请参阅 [使用 System.windows.media.pathgeometry> 创建形状](how-to-create-a-shape-by-using-a-pathgeometry.md)。  虽然此示例使用元素将形状呈现到屏幕 <xref:System.Windows.Shapes.Path> ，但 <xref:System.Windows.Media.Geometry> 对象也可用于描述或的内容 <xref:System.Windows.Media.GeometryDrawing> <xref:System.Windows.Media.DrawingContext> 。 它们还可用于剪辑和命中测试。  
  
 此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)。
