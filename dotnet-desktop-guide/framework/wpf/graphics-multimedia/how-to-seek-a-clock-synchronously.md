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
# <a name="how-to-seek-a-clock-synchronously"></a>如何：同步定位时钟
使用 <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> 方法可同步地将时钟定位到特定点。 下面的示例演示了的 <xref:System.Windows.Media.Animation.ClockController.Seek%2A> 和 <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> 方法 <xref:System.Windows.Media.Animation.ClockController> 。  
  
 此示例演示如何查找 <xref:System.Windows.Media.Animation.Clock> ; 有关演示如何查找情节提要的示例，请参阅以 [同步方式查找情节提要](how-to-seek-a-storyboard-synchronously.md) 。  
  
## <a name="example"></a>示例  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
