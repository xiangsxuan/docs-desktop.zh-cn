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
# <a name="how-to-define-a-pen"></a><span data-ttu-id="f2f1e-102">如何：定义钢笔</span><span class="sxs-lookup"><span data-stu-id="f2f1e-102">How to: Define a Pen</span></span>
<span data-ttu-id="f2f1e-103">此示例演示如何使用 <xref:System.Windows.Media.Pen> 来概述形状。</span><span class="sxs-lookup"><span data-stu-id="f2f1e-103">This example shows how use a <xref:System.Windows.Media.Pen> to outline a shape.</span></span> <span data-ttu-id="f2f1e-104">若要创建一个简单的 <xref:System.Windows.Media.Pen> ，只需指定其 <xref:System.Windows.Media.Pen.Thickness%2A> 和 <xref:System.Windows.Media.Pen.Brush%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f2f1e-104">To create a simple <xref:System.Windows.Media.Pen>, you need only specify its <xref:System.Windows.Media.Pen.Thickness%2A> and <xref:System.Windows.Media.Pen.Brush%2A>.</span></span> <span data-ttu-id="f2f1e-105">您可以通过指定、、、和来创建更复杂的笔 <xref:System.Windows.Media.Pen.DashStyle%2A> <xref:System.Windows.Media.Pen.DashCap%2A> <xref:System.Windows.Media.Pen.LineJoin%2A> <xref:System.Windows.Media.Pen.StartLineCap%2A> <xref:System.Windows.Media.Pen.EndLineCap%2A> 。</span><span class="sxs-lookup"><span data-stu-id="f2f1e-105">You can create more complex pen's by specifying a <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, and <xref:System.Windows.Media.Pen.EndLineCap%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2f1e-106">示例</span><span class="sxs-lookup"><span data-stu-id="f2f1e-106">Example</span></span>  
 <span data-ttu-id="f2f1e-107">下面的示例使用 <xref:System.Windows.Media.Pen> 来概述由定义的形状 <xref:System.Windows.Media.GeometryDrawing> 。</span><span class="sxs-lookup"><span data-stu-id="f2f1e-107">The following example uses a <xref:System.Windows.Media.Pen> to outline a shape defined by a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 <span data-ttu-id="f2f1e-108">![通过笔绘制的轮廓](./media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span><span class="sxs-lookup"><span data-stu-id="f2f1e-108">![Outlines produces by a Pen](./media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span></span>  
<span data-ttu-id="f2f1e-109">一个 GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="f2f1e-109">A GeometryDrawing</span></span>
