---
title: 如何：使用 ThicknessConverter 对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: 7420824ad939012d12f61ecbb72f2d00ce483e8b
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971810"
---
# <a name="how-to-use-a-thicknessconverter-object"></a>如何：使用 ThicknessConverter 对象

## <a name="example"></a>示例  

 此示例演示如何创建实例 <xref:System.Windows.ThicknessConverter> ，并使用它来更改边框的粗细。  
  
 该示例定义了一个名为的自定义方法 `changeThickness` ; 此方法首先将中定义的的内容转换为的 <xref:System.Windows.Controls.ListBoxItem> 实例，然后将 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Thickness> 内容转换为 <xref:System.String> 。 此方法将传递 <xref:System.Windows.Controls.ListBoxItem> 到一个 <xref:System.Windows.ThicknessConverter> 对象，该对象将 <xref:System.Windows.Controls.ContentControl.Content%2A> 的转换 <xref:System.Windows.Controls.ListBoxItem> 为的实例 <xref:System.Windows.Thickness> 。 然后，将此值作为的属性的值传递回 <xref:System.Windows.Controls.Border.BorderThickness%2A> <xref:System.Windows.Controls.Border> 。  
  
 此示例不运行。  
  
 [!code-csharp[ThicknessConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- [如何：更改 Margin 属性](/previous-versions/dotnet/netframework-3.5/ms750561(v=vs.90))
- [如何：将 ListBoxItem 转换为新数据类型](/previous-versions/dotnet/netframework-3.5/ms749147(v=vs.90))
- [面板概述](../controls/panels-overview.md)
