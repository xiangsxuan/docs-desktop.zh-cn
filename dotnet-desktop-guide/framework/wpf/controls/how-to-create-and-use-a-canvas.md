---
title: 如何：创建和使用画布
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
ms.openlocfilehash: c9ee49327b6490df094e84b4227ea0fb2e757c4d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972901"
---
# <a name="how-to-create-and-use-a-canvas"></a>如何：创建和使用画布
此示例演示如何创建和使用的实例 <xref:System.Windows.Controls.Canvas> 。  
  
## <a name="example"></a>示例  
 下面的示例通过使用的和方法显式定位两个 <xref:System.Windows.Controls.TextBlock> 元素 <xref:System.Windows.Controls.Canvas.SetTop%2A> <xref:System.Windows.Controls.Canvas.SetLeft%2A> <xref:System.Windows.Controls.Canvas> 。 该示例还将 <xref:System.Windows.Controls.Control.Background%2A> 的颜色分配 `LightSteelBlue` 给 <xref:System.Windows.Controls.Canvas> 。  
  
> [!NOTE]
> 当你使用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 来放置 <xref:System.Windows.Controls.TextBlock> 元素时，请使用 <xref:System.Windows.Controls.Canvas.Top%2A> 和 <xref:System.Windows.Controls.Canvas.Left%2A> 属性。  
  
 [!code-csharp[CanvasCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [面板概述](panels-overview.md)
- [操作指南主题](canvas-how-to-topics.md)
