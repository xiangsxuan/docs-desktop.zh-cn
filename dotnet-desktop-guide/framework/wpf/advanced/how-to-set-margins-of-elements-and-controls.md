---
title: 如何：设置元素和控件的边距
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting [WPF], Margin property
- properties [WPF], Margin property
- Margin property [WPF], setting
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
ms.openlocfilehash: dc0a2a2625fa83ffffabd2ec64983602b6f1e6c7
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665843"
---
# <a name="how-to-set-margins-of-elements-and-controls"></a>如何：设置元素和控件的边距
此示例说明如何 <xref:System.Windows.FrameworkElement.Margin%2A> 通过在代码隐藏中更改边距的任何现有属性值来设置属性。 <xref:System.Windows.FrameworkElement.Margin%2A>属性是 <xref:System.Windows.FrameworkElement> 基本元素的属性，因此由各种控件和其他元素继承。  
  
 此示例是用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 引用的代码隐藏文件编写的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。 C # 和 Microsoft Visual Basic 版本中都显示了代码隐藏。  
  
## <a name="example"></a>示例  
 [!code-xaml[FEMarginProgrammatic#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
