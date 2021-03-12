---
title: 如何：使动画加速或减速
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: 04912e4bd51aba5ddcea7bb5f5a91bbb6501b6c3
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604285"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a>如何：加速或减速动画

此示例演示如何在一段时间内使动画加速和减速。 在下面的示例中，使用不同和设置的动画对几个矩形进行动画处理 <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> 。  
  
## <a name="example"></a>示例  
 [!code-xaml[timingbehaviors_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 此示例中省略了代码。 有关完整的代码，请参阅 [动画计时行为 (c # ) ](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) 或 [动画计时行为 (Visual Basic) ](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic)。
