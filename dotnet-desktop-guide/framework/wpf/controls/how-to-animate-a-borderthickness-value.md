---
title: 如何：对 BorderThickness 值进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 4533ce6f2a1fe7243267ee8d638e2ad0a4f9cf3a
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973999"
---
# <a name="how-to-animate-a-borderthickness-value"></a>如何：对 BorderThickness 值进行动画处理
此示例演示如何使用类对边框的粗细进行动画处理 <xref:System.Windows.Media.Animation.ThicknessAnimation> 。  
  
## <a name="example"></a>示例  
 下面的示例使用对边框的粗细进行动画处理 <xref:System.Windows.Media.Animation.ThicknessAnimation> 。 该示例使用的 <xref:System.Windows.Controls.Border.BorderThickness%2A> 属性 <xref:System.Windows.Controls.Border> 。  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 有关完整示例，请参阅 [动画示例库](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [动画概述](../graphics-multimedia/animation-overview.md)
- [动画和计时帮助主题](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [使用关键帧对边框的粗细进行动画处理](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
