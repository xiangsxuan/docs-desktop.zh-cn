---
title: 如何：自定义滑块上的刻度
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 150a546a2c94c1bd552f1f7486652d2b4ad900e3
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973724"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a>如何：自定义滑块上的刻度

此示例演示如何创建 <xref:System.Windows.Controls.Slider> 包含刻度线的控件。  
  
## <a name="example"></a>示例  

 <xref:System.Windows.Controls.Primitives.TickBar>如果将属性设置为以外的 <xref:System.Windows.Controls.Slider.TickPlacement%2A> 值，则将显示 <xref:System.Windows.Controls.Primitives.TickPlacement.None> 默认值。  
  
 下面的示例演示如何 <xref:System.Windows.Controls.Slider> 使用 <xref:System.Windows.Controls.Primitives.TickBar> 显示刻度线的来创建。 <xref:System.Windows.Controls.Slider.TickPlacement%2A>和 <xref:System.Windows.Controls.Slider.TickFrequency%2A> 属性定义刻度线的位置以及它们之间的间隔。 在移动时 <xref:System.Windows.Controls.Primitives.Thumb> ，工具提示会显示的值 <xref:System.Windows.Controls.Slider> 。 <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A>属性定义工具提示出现的位置。 <xref:System.Windows.Controls.Primitives.Thumb>由于设置为，因此移动与刻度线的位置相对应 <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> `true` 。  
  
 下面的示例演示如何使用 <xref:System.Windows.Controls.Slider.Ticks%2A> 属性以 <xref:System.Windows.Controls.Slider> 不规则时间间隔创建刻度线。  
  
 [!code-xaml[Slider#4](~/samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- [如何：将滑块绑定到属性值](/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))
