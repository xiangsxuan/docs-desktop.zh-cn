---
title: 如何：使用 SystemParameters
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
ms.openlocfilehash: 1a198c9698a9cb2f56675bc953a4980cdecc3a0a
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665778"
---
# <a name="how-to-use-systemparameters"></a>如何：使用 SystemParameters
此示例演示如何访问和使用的属性，以便 <xref:System.Windows.SystemParameters> 样式或自定义按钮。  
  
## <a name="example"></a>示例  
 系统资源将多个基于系统的设置以资源的形式公开，以帮助创建与系统设置一致的视觉效果。 <xref:System.Windows.SystemParameters> 是包含系统参数值属性和绑定到值的资源键的类。 例如， <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> 是 <xref:System.Windows.SystemParameters> 属性值， <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> 是对应的资源键。  
  
 在中 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，你可以使用的成员 <xref:System.Windows.SystemParameters> 作为静态属性用法，或使用静态属性值 (作为键) 的动态资源引用。 如果希望基于系统的值在应用程序运行时自动更新，请使用动态资源引用；否则，请使用静态引用。 资源键将后缀 `Key` 追加到属性名称。  
  
 下面的示例演示如何访问和使用的静态值 <xref:System.Windows.SystemParameters> 来样式或自定义按钮。 此标记示例将值应用于按钮，从而调整按钮大小 <xref:System.Windows.SystemParameters> 。  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 若要 <xref:System.Windows.SystemParameters> 在代码中使用的值，则不必使用静态引用或动态资源引用。 请改用类的值 <xref:System.Windows.SystemParameters> 。 尽管非键属性已明确定义为静态属性，但是系统承载的的运行时行为 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 将会实时重新评估这些属性，并且会正确地考虑对系统值进行用户驱动的更改。 下面的示例演示如何使用值设置按钮的宽度和高度 <xref:System.Windows.SystemParameters> 。  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.SystemParameters>
- [使用系统画笔绘制区域](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [使用 SystemFonts](how-to-use-systemfonts.md)
- [使用系统参数键](how-to-use-system-parameters-keys.md)
- [操作指南主题](resources-how-to-topics.md)
