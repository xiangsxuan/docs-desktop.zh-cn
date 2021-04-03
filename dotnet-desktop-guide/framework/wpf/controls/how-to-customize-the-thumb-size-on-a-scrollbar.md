---
title: 如何：自定义滚动条上的滚动块大小
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 60ae7c4e95801036c5deb0c485645297509b830c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973719"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a>如何：自定义滚动条上的滚动块大小
本主题说明如何将的设置 <xref:System.Windows.Controls.Primitives.Thumb> <xref:System.Windows.Controls.Primitives.ScrollBar> 为固定大小，以及如何为指定的最小大小 <xref:System.Windows.Controls.Primitives.Thumb> <xref:System.Windows.Controls.Primitives.ScrollBar> 。  
  
## <a name="example"></a>示例  
  
## <a name="description"></a>说明  
 下面的示例创建一个 <xref:System.Windows.Controls.Primitives.ScrollBar> 具有 <xref:System.Windows.Controls.Primitives.Thumb> 固定大小的。 该示例将 <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> 的属性设置 <xref:System.Windows.Controls.Primitives.Thumb> 为 <xref:System.Double.NaN> ，并设置的高度 <xref:System.Windows.Controls.Primitives.Thumb> 。  若要创建具有 <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.Primitives.Thumb> 固定宽度的水平，请设置的宽度 <xref:System.Windows.Controls.Primitives.Thumb> 。  
  
## <a name="code"></a>代码  
 [!code-xaml[ScrollBarCustomThumbSize#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a>说明  
 下面的示例创建一个 <xref:System.Windows.Controls.Primitives.ScrollBar> 具有 <xref:System.Windows.Controls.Primitives.Thumb> 最小大小的。 该示例设置的值 <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A> 。 若要创建具有 <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.Primitives.Thumb> 最小宽度的水平，请设置 <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A> 。  
  
## <a name="code"></a>代码  
 [!code-xaml[ScrollBarCustomThumbSize#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a>另请参阅

- [ScrollBar 样式和模板](scrollbar-styles-and-templates.md)
