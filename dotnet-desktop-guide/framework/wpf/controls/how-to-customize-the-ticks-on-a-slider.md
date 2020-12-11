---
title: 如何：自定义滑块上的刻度
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 150a546a2c94c1bd552f1f7486652d2b4ad900e3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973724"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a><span data-ttu-id="2191d-102">如何：自定义滑块上的刻度</span><span class="sxs-lookup"><span data-stu-id="2191d-102">How to: Customize the Ticks on a Slider</span></span>

<span data-ttu-id="2191d-103">此示例演示如何创建 <xref:System.Windows.Controls.Slider> 包含刻度线的控件。</span><span class="sxs-lookup"><span data-stu-id="2191d-103">This example shows how to create a <xref:System.Windows.Controls.Slider> control that has tick marks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2191d-104">示例</span><span class="sxs-lookup"><span data-stu-id="2191d-104">Example</span></span>  

 <span data-ttu-id="2191d-105"><xref:System.Windows.Controls.Primitives.TickBar>如果将属性设置为以外的 <xref:System.Windows.Controls.Slider.TickPlacement%2A> 值，则将显示 <xref:System.Windows.Controls.Primitives.TickPlacement.None> 默认值。</span><span class="sxs-lookup"><span data-stu-id="2191d-105">The <xref:System.Windows.Controls.Primitives.TickBar> displays when you set the <xref:System.Windows.Controls.Slider.TickPlacement%2A> property to a value other than <xref:System.Windows.Controls.Primitives.TickPlacement.None>, which is the default value.</span></span>  
  
 <span data-ttu-id="2191d-106">下面的示例演示如何 <xref:System.Windows.Controls.Slider> 使用 <xref:System.Windows.Controls.Primitives.TickBar> 显示刻度线的来创建。</span><span class="sxs-lookup"><span data-stu-id="2191d-106">The following example shows how to create a <xref:System.Windows.Controls.Slider> with a <xref:System.Windows.Controls.Primitives.TickBar> that displays tick marks.</span></span> <span data-ttu-id="2191d-107"><xref:System.Windows.Controls.Slider.TickPlacement%2A>和 <xref:System.Windows.Controls.Slider.TickFrequency%2A> 属性定义刻度线的位置以及它们之间的间隔。</span><span class="sxs-lookup"><span data-stu-id="2191d-107">The <xref:System.Windows.Controls.Slider.TickPlacement%2A> and <xref:System.Windows.Controls.Slider.TickFrequency%2A> properties define the location of the tick marks and the interval between them.</span></span> <span data-ttu-id="2191d-108">在移动时 <xref:System.Windows.Controls.Primitives.Thumb> ，工具提示会显示的值 <xref:System.Windows.Controls.Slider> 。</span><span class="sxs-lookup"><span data-stu-id="2191d-108">When you move the <xref:System.Windows.Controls.Primitives.Thumb>, tooltips display the value of the <xref:System.Windows.Controls.Slider>.</span></span> <span data-ttu-id="2191d-109"><xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A>属性定义工具提示出现的位置。</span><span class="sxs-lookup"><span data-stu-id="2191d-109">The <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> property defines where the tooltips occur.</span></span> <span data-ttu-id="2191d-110"><xref:System.Windows.Controls.Primitives.Thumb>由于设置为，因此移动与刻度线的位置相对应 <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> `true` 。</span><span class="sxs-lookup"><span data-stu-id="2191d-110">The <xref:System.Windows.Controls.Primitives.Thumb> movements correspond to the location of the tick marks because <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> is set to `true`.</span></span>  
  
 <span data-ttu-id="2191d-111">下面的示例演示如何使用 <xref:System.Windows.Controls.Slider.Ticks%2A> 属性以 <xref:System.Windows.Controls.Slider> 不规则时间间隔创建刻度线。</span><span class="sxs-lookup"><span data-stu-id="2191d-111">The following example shows how to use the <xref:System.Windows.Controls.Slider.Ticks%2A> property to create tick marks along the <xref:System.Windows.Controls.Slider> at irregular intervals.</span></span>  
  
 [!code-xaml[Slider#4](~/samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="2191d-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2191d-112">See also</span></span>

- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- <span data-ttu-id="2191d-113">[如何：将滑块绑定到属性值](/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2191d-113">[How to: Bind a Slider to a Property Value](/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))</span></span>
