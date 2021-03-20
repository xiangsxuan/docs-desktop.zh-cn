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
# <a name="how-to-set-margins-of-elements-and-controls"></a><span data-ttu-id="4ae7a-102">如何：设置元素和控件的边距</span><span class="sxs-lookup"><span data-stu-id="4ae7a-102">How to: Set Margins of Elements and Controls</span></span>
<span data-ttu-id="4ae7a-103">此示例说明如何 <xref:System.Windows.FrameworkElement.Margin%2A> 通过在代码隐藏中更改边距的任何现有属性值来设置属性。</span><span class="sxs-lookup"><span data-stu-id="4ae7a-103">This example describes how to set the <xref:System.Windows.FrameworkElement.Margin%2A> property, by changing any existing property value for the margin in code-behind.</span></span> <span data-ttu-id="4ae7a-104"><xref:System.Windows.FrameworkElement.Margin%2A>属性是 <xref:System.Windows.FrameworkElement> 基本元素的属性，因此由各种控件和其他元素继承。</span><span class="sxs-lookup"><span data-stu-id="4ae7a-104">The <xref:System.Windows.FrameworkElement.Margin%2A> property is a property of the <xref:System.Windows.FrameworkElement> base element, and is thus inherited by a variety of controls and other elements.</span></span>  
  
 <span data-ttu-id="4ae7a-105">此示例是用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 引用的代码隐藏文件编写的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="4ae7a-105">This example is written in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], with a code-behind file that the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] refers to.</span></span> <span data-ttu-id="4ae7a-106">C # 和 Microsoft Visual Basic 版本中都显示了代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="4ae7a-106">The code-behind is shown in both a C# and a Microsoft Visual Basic version.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ae7a-107">示例</span><span class="sxs-lookup"><span data-stu-id="4ae7a-107">Example</span></span>  
 [!code-xaml[FEMarginProgrammatic#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
