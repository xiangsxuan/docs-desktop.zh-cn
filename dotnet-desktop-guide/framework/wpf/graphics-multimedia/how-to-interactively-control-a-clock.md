---
title: 如何：以交互方式控制时钟
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 2d18f395974750a6b85458f636a27f6101e7978f
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973506"
---
# <a name="how-to-interactively-control-a-clock"></a>如何：以交互方式控制时钟
<xref:System.Windows.Media.Animation.Clock>对象的 <xref:System.Windows.Media.Animation.ClockController> 属性使你能够以交互方式启动、暂停、恢复、查找、将时钟推进到其填充期并停止时钟。 只能以交互方式控制计时树的根时钟。  
  
> [!NOTE]
> 还可以通过其他方式以交互方式控制不需要直接使用时钟的动画：你也可以使用情节提要。 标记和代码都支持情节提要。 有关示例，请参阅使用情节提要或[动画概述](animation-overview.md)对[属性进行动画处理](how-to-animate-a-property-by-using-a-storyboard.md)。  
  
 在下面的示例中，使用了多个按钮以交互方式控制动画时钟。  
  
## <a name="example"></a>示例  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>另请参阅

- [使用情节提要对属性进行动画处理](how-to-animate-a-property-by-using-a-storyboard.md)
- [动画概述](animation-overview.md)
