---
title: 如何：使用 SystemFonts
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: c81b37def3f1a7a95be2a855b773d00b502a37c1
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665765"
---
# <a name="how-to-use-systemfonts"></a>如何：使用 SystemFonts
此示例演示如何使用类的静态资源 <xref:System.Windows.SystemFonts> 来样式或自定义按钮。  
  
## <a name="example"></a>示例  
 系统资源将系统确定的许多值以资源和属性的形式公开，以帮助创建与系统设置一致的视觉效果。 <xref:System.Windows.SystemFonts> 是一个类，其中包含作为静态属性的系统字体值和引用资源键的属性，这些属性可用于在运行时动态访问这些值。 例如， <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> 是一个 <xref:System.Windows.SystemFonts> 值，并且 <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> 是对应的资源键。  
  
 在中 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，你可以将的成员 <xref:System.Windows.SystemFonts> 作为静态属性或动态资源引用 (，并将静态属性值用作键) 。 如果希望字体规格在应用程序运行时自动更新，请使用动态资源引用；否则，请使用静态值引用。  
  
> [!NOTE]
> 资源键属性名称后面附有“Key”后缀。  
  
 下面的示例演示如何访问并将的属性 <xref:System.Windows.SystemFonts> 用作静态值，以便样式或自定义按钮。 此标记示例 <xref:System.Windows.SystemFonts> 为按钮赋值。  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 若要 <xref:System.Windows.SystemFonts> 在代码中使用的值，则不必使用静态值或动态资源引用。 请改用类的非键属性 <xref:System.Windows.SystemFonts> 。 尽管非键属性已明确定义为静态属性，但是系统承载的的运行时行为 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 将会实时重新评估这些属性，并且将正确地考虑对系统值进行用户驱动的更改。 以下示例演示如何指定按钮的字体设置。  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.SystemFonts>
- [使用系统画笔绘制区域](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [使用 SystemParameters](how-to-use-systemparameters.md)
- [使用系统字体键](how-to-use-system-fonts-keys.md)
- [操作指南主题](resources-how-to-topics.md)
- [x:Static 标记扩展](/dotnet/desktop-wpf/xaml-services/xstatic-markup-extension)
- [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [DynamicResource 标记扩展](dynamicresource-markup-extension.md)
