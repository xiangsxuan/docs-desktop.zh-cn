---
title: 如何：使用系统参数键
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: dda2d174421818005bcc3d4493f08918cb49b9e1
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665804"
---
# <a name="how-to-use-system-parameters-keys"></a>如何：使用系统参数键
系统资源将多个系统规格以资源的形式公开，以帮助开发人员创建与系统设置一致的视觉效果。 <xref:System.Windows.SystemParameters> 是包含系统参数值和绑定到值的资源键（例如和）的类 <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> 。 系统参数规格可用作静态或动态资源。 如果希望参数规格在应用程序运行时自动更新，请使用动态资源；否则，请使用静态资源。  
  
> [!NOTE]
> 动态资源将关键字关键字 *追加到* 属性名称上。  
  
 以下示例演示如何访问和使用系统参数动态资源来设计按钮样式或自定义按钮。 此 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 示例通过将 <xref:System.Windows.SystemParameters> 值分配给按钮的宽度和高度来调整按钮的大小。  
  
## <a name="example"></a>示例  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a>请参阅

- [使用系统画笔绘制区域](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [使用 SystemFonts](how-to-use-systemfonts.md)
- [使用 SystemParameters](how-to-use-systemparameters.md)
