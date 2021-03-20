---
title: 如何：使用系统字体键
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: 20df7037b439d798bdafa782811ebd46d76b4589
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665817"
---
# <a name="how-to-use-system-fonts-keys"></a>如何：使用系统字体键
系统资源将多个系统规格以资源的形式公开，以帮助开发人员创建与系统设置一致的视觉效果。 <xref:System.Windows.SystemFonts> 是包含系统字体值和绑定到值的系统字体资源（例如和）的类 <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> 。  
  
 系统字体规格可用作静态或动态资源。 如果希望字体规格在应用程序运行时自动更新，请使用动态资源；否则，请使用静态资源。  
  
> [!NOTE]
> 动态资源将关键字关键字 *追加到* 属性名称上。  
  
 以下示例演示如何访问和使用系统字体动态资源来设计按钮样式或自定义按钮。 此 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 示例创建一个按钮样式，该样式 <xref:System.Windows.SystemFonts> 为按钮赋值。  
  
## <a name="example"></a>示例  
 [!code-xaml[SystemRes_snip#FontDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a>请参阅

- [使用系统画笔绘制区域](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [使用 SystemParameters](how-to-use-systemparameters.md)
- [使用 SystemFonts](how-to-use-systemfonts.md)
