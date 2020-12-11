---
title: 如何：使用 ScrollViewer 创建 Expander
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: ef0bc5d344f7d465de9209708430d3e61d40d4f7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973558"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a>如何：使用 ScrollViewer 创建 Expander
此示例演示如何创建 <xref:System.Windows.Controls.Expander> 包含复杂内容（如图像和文本）的控件。 该示例还 <xref:System.Windows.Controls.Expander> 在控件中包含的内容 <xref:System.Windows.Controls.ScrollViewer> 。  
  
## <a name="example"></a>示例  
 下面的示例演示如何创建 <xref:System.Windows.Controls.Expander> 。 该示例使用 <xref:System.Windows.Controls.Primitives.BulletDecorator> 包含图像和文本的控件来定义 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 。 <xref:System.Windows.Controls.ScrollViewer>控件提供用于滚动展开内容的方法。  
  
 请注意，该示例在上设置 <xref:System.Windows.FrameworkElement.Height%2A> 属性， <xref:System.Windows.Controls.ScrollViewer> 而不是在内容上设置。 如果对 <xref:System.Windows.FrameworkElement.Height%2A> 内容设置了，则不 <xref:System.Windows.Controls.ScrollViewer> 允许用户滚动内容。 在 <xref:System.Windows.FrameworkElement.Width%2A> 控件上设置属性 <xref:System.Windows.Controls.Expander> ，此设置应用于 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 和扩展的内容。  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Expander>
- [Expander 概述](expander-overview.md)
- [操作指南主题](expander-how-to-topics.md)
