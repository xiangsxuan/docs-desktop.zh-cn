---
title: 如何：使用系统画笔绘制区域
ms.date: 03/30/2017
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
ms.openlocfilehash: 26511c577bf06b016dfc69cedc7fce2bafb35f32
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972775"
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a>如何：使用系统画笔绘制区域
<xref:System.Windows.SystemColors>类提供对系统画笔和颜色（如、和）的访问 <xref:System.Windows.SystemColors.ControlBrush%2A> <xref:System.Windows.SystemColors.ControlBrushKey%2A> <xref:System.Windows.SystemColors.DesktopBrush%2A> 。 系统画笔是一个 <xref:System.Windows.Media.SolidColorBrush> 对象，它使用指定的系统颜色绘制区域。 系统画笔总是生成纯色填充，它不能用于创建渐变。  
  
 可以将系统画笔用作静态资源，也可以用作动态资源。 如果希望在应用程序运行期间画笔自动进行更新（当用户更改系统画笔时），请使用动态资源；否则请使用静态资源。 SystemColors 类包含大量静态属性，这些属性严格遵循命名约定：  
  
- *\<SystemColor>* 画笔  
  
     获取对 <xref:System.Windows.Media.SolidColorBrush> 指定系统颜色的的静态引用。  
  
- *\<SystemColor>* BrushKey  
  
     获取对指定系统颜色的的动态引用 <xref:System.Windows.Media.SolidColorBrush> 。  
  
- *\<SystemColor>* 颜色  
  
     获取对 <xref:System.Windows.Media.Color> 指定系统颜色的结构的静态引用。  
  
- *\<SystemColor>* ColorKey  
  
     获取对 <xref:System.Windows.Media.Color> 指定系统颜色的结构的动态引用。  
  
 系统颜色是 <xref:System.Windows.Media.Color> 可用于配置画笔的结构。 例如，您可以通过使用系统颜色设置 <xref:System.Windows.Media.GradientStop.Color%2A> <xref:System.Windows.Media.LinearGradientBrush> 对象的渐变停止点的属性来创建使用系统颜色的渐变。 有关示例，请参阅 [在渐变中使用系统颜色](how-to-use-system-colors-in-a-gradient.md)。  
  
## <a name="example"></a>示例  
 以下示例使用动态系统画笔引用来设置按钮的背景。  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 下一个示例使用静态系统画笔引用来设置按钮的背景。  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 有关演示如何在渐变中使用系统颜色的示例，请参阅 [在渐变中使用系统颜色](how-to-use-system-colors-in-a-gradient.md)。  
  
## <a name="see-also"></a>另请参阅

- [在渐变中使用系统颜色](how-to-use-system-colors-in-a-gradient.md)
- [使用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)
