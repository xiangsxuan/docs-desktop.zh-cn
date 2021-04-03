---
title: 如何：清除自定义控件上的墨迹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
ms.openlocfilehash: 60e2af64cb0c5b313f4f1201cab70da6a88f61e7
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973480"
---
# <a name="how-to-erase-ink-on-a-custom-control"></a><span data-ttu-id="31955-102">如何：清除自定义控件上的墨迹</span><span class="sxs-lookup"><span data-stu-id="31955-102">How to: Erase Ink on a Custom Control</span></span>
<span data-ttu-id="31955-103"><xref:System.Windows.Ink.IncrementalStrokeHitTester>确定当前绘制的笔划是否与另一个笔画相交。</span><span class="sxs-lookup"><span data-stu-id="31955-103">The <xref:System.Windows.Ink.IncrementalStrokeHitTester> determines whether the currently drawn stroke intersects another stroke.</span></span>  <span data-ttu-id="31955-104">这适用于创建一个控件，该控件使用户能够擦除笔划的各个部分，即用户在 <xref:System.Windows.Controls.InkCanvas> 设置为时可以在上的方式 <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint> 。</span><span class="sxs-lookup"><span data-stu-id="31955-104">This is useful for creating a control that enables a user to erase parts of a stroke, the way a user can on an <xref:System.Windows.Controls.InkCanvas> when the <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> is set to <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31955-105">示例</span><span class="sxs-lookup"><span data-stu-id="31955-105">Example</span></span>  
 <span data-ttu-id="31955-106">下面的示例创建一个自定义控件，该控件允许用户擦除笔画的各个部分。</span><span class="sxs-lookup"><span data-stu-id="31955-106">The following example creates a custom control that enables the user to erase parts of strokes.</span></span>  <span data-ttu-id="31955-107">此示例创建一个控件，该控件在初始化时包含墨迹。</span><span class="sxs-lookup"><span data-stu-id="31955-107">This example creates a control that contains ink when it is initialized.</span></span>  <span data-ttu-id="31955-108">若要创建收集墨迹的控件，请参阅 [创建墨迹输入控件](creating-an-ink-input-control.md)。</span><span class="sxs-lookup"><span data-stu-id="31955-108">To create a control that collects ink, see [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  
  
 [!code-csharp[HowToEraseInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
