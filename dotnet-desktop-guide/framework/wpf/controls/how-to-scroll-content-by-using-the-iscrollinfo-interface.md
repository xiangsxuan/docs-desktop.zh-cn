---
title: 如何：使用 IScrollInfo 接口来滚动内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
ms.openlocfilehash: f45bb6dfd70084675ea9a9215ffa616de3e3753c
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668456"
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a>如何：使用 IScrollInfo 接口来滚动内容
此示例演示如何使用接口滚动内容 <xref:System.Windows.Controls.Primitives.IScrollInfo> 。  
  
## <a name="example"></a>示例  
 下面的示例演示接口的功能 <xref:System.Windows.Controls.Primitives.IScrollInfo> 。 此示例在 <xref:System.Windows.Controls.StackPanel> 中创建 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 嵌套在父级中的元素 <xref:System.Windows.Controls.ScrollViewer> 。 的子元素 <xref:System.Windows.Controls.StackPanel> 可以通过使用接口所定义的方法以逻辑方式滚动 <xref:System.Windows.Controls.Primitives.IScrollInfo> ，并强制转换为 <xref:System.Windows.Controls.StackPanel> 代码中的 (`sp1`) 的实例。  
  
 [!code-xaml[IScrollInfoMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 <xref:System.Windows.Controls.Button>文件中的每个都 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 触发一个关联的自定义方法，该方法控制中的滚动行为 <xref:System.Windows.Controls.StackPanel> 。 下面的示例演示如何使用 <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> 和 <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> 方法; 它还一般显示了如何使用类定义的所有定位方法 <xref:System.Windows.Controls.Primitives.IScrollInfo> 。  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- <xref:System.Windows.Controls.StackPanel>
- [ScrollViewer 概述](scrollviewer-overview.md)
- [操作指南主题](scrollviewer-how-to-topics.md)
- [面板概述](panels-overview.md)
