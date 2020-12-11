---
title: 如何：定义钢笔
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [WPF], defining
- creating [WPF], pens
ms.assetid: 7a4f2900-cdf9-49de-84e0-ba5d0ded4d33
ms.openlocfilehash: 1d69a40604dbf2f7a73c17279ae946faeb6c634a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971724"
---
# <a name="how-to-define-a-pen"></a>如何：定义钢笔
此示例演示如何使用 <xref:System.Windows.Media.Pen> 来概述形状。 若要创建一个简单的 <xref:System.Windows.Media.Pen> ，只需指定其 <xref:System.Windows.Media.Pen.Thickness%2A> 和 <xref:System.Windows.Media.Pen.Brush%2A> 。 您可以通过指定、、、和来创建更复杂的笔 <xref:System.Windows.Media.Pen.DashStyle%2A> <xref:System.Windows.Media.Pen.DashCap%2A> <xref:System.Windows.Media.Pen.LineJoin%2A> <xref:System.Windows.Media.Pen.StartLineCap%2A> <xref:System.Windows.Media.Pen.EndLineCap%2A> 。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.Pen> 来概述由定义的形状 <xref:System.Windows.Media.GeometryDrawing> 。  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 ![通过笔绘制的轮廓](./media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")  
一个 GeometryDrawing
