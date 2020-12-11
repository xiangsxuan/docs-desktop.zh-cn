---
title: 如何：向绘图应用 GuidelineSet
ms.date: 03/30/2017
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
ms.openlocfilehash: 134236c5beca806b747d45f20764cc82ddd8a4e8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973669"
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a>如何：向绘图应用 GuidelineSet
此示例演示如何将应用 <xref:System.Windows.Media.GuidelineSet> 到 <xref:System.Windows.Media.DrawingGroup> 。  
  
 <xref:System.Windows.Media.DrawingGroup>类是具有属性的唯一类型 <xref:System.Windows.Media.Drawing> <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> 。 若要将应用于 <xref:System.Windows.Media.GuidelineSet> 另一种类型的 <xref:System.Windows.Media.Drawing> ，请将其添加到， <xref:System.Windows.Media.DrawingGroup> 然后将应用 <xref:System.Windows.Media.GuidelineSet> 到 <xref:System.Windows.Media.DrawingGroup> 。  
  
## <a name="example"></a>示例  
 下面的示例创建两个 <xref:System.Windows.Media.DrawingGroup> 几乎相同的对象; 唯一的区别是：第二个对象 <xref:System.Windows.Media.DrawingGroup> 具有 <xref:System.Windows.Media.GuidelineSet> ，第一个对象不是。  
  
 下图显示该示例的输出。 因为这两个对象之间的呈现差异 <xref:System.Windows.Media.DrawingGroup> 很微妙，所以部分绘图会放大。  
  
 ![具有和没有 GuidelineSet 的 DrawingGroup](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.GuidelineSet>
- [Drawing 对象概述](drawing-objects-overview.md)
