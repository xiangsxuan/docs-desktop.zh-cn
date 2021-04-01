---
title: 如何：同步定位时钟
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
ms.openlocfilehash: 9b6b1f5523effc56ccd9ddaa4f478e1d3a20ada8
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971721"
---
# <a name="how-to-seek-a-clock-synchronously"></a><span data-ttu-id="3cb39-102">如何：同步定位时钟</span><span class="sxs-lookup"><span data-stu-id="3cb39-102">How to: Seek a Clock Synchronously</span></span>
<span data-ttu-id="3cb39-103">使用 <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> 方法可同步地将时钟定位到特定点。</span><span class="sxs-lookup"><span data-stu-id="3cb39-103">Use the <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> method to seek a clock to a specific point synchronously.</span></span> <span data-ttu-id="3cb39-104">下面的示例演示了的 <xref:System.Windows.Media.Animation.ClockController.Seek%2A> 和 <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> 方法 <xref:System.Windows.Media.Animation.ClockController> 。</span><span class="sxs-lookup"><span data-stu-id="3cb39-104">The following example demonstrates both the <xref:System.Windows.Media.Animation.ClockController.Seek%2A> and <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> methods of a <xref:System.Windows.Media.Animation.ClockController>.</span></span>  
  
 <span data-ttu-id="3cb39-105">此示例演示如何查找 <xref:System.Windows.Media.Animation.Clock> ; 有关演示如何查找情节提要的示例，请参阅以 [同步方式查找情节提要](how-to-seek-a-storyboard-synchronously.md) 。</span><span class="sxs-lookup"><span data-stu-id="3cb39-105">This example shows how to seek a <xref:System.Windows.Media.Animation.Clock>; for an example showing how to seek a storyboard, see [Seek a Storyboard Synchronously](how-to-seek-a-storyboard-synchronously.md) .</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cb39-106">示例</span><span class="sxs-lookup"><span data-stu-id="3cb39-106">Example</span></span>  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
