---
title: 如何：查找由 ControlTemplate 生成的元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ControlTemplates [WPF], finding elements
- finding ControlTemplate elements [WPF]
ms.assetid: d7b25447-ceff-4bb4-9be5-fd7c40ef00af
ms.openlocfilehash: 064f70835443accef83ca5f3d912ace861c2216a
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970698"
---
# <a name="how-to-find-controltemplate-generated-elements"></a>如何：查找由 ControlTemplate 生成的元素
此示例演示如何查找由生成的元素 <xref:System.Windows.Controls.ControlTemplate> 。  
  
## <a name="example"></a>示例  
 下面的示例演示为类创建简单的样式 <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Button> ：  
  
 [!code-xaml[FindGeneratedItems#CT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#ct)]  
  
 若要在应用模板后查找模板中的元素，可以调用的 <xref:System.Windows.FrameworkTemplate.FindName%2A> 方法 <xref:System.Windows.Controls.Control.Template%2A> 。 下面的示例创建一个消息框，该消息框显示控件模板内的实际宽度值 <xref:System.Windows.Controls.Grid> ：  
  
 [!code-csharp[FindGeneratedItems#CTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#ctfindelement)]
 [!code-vb[FindGeneratedItems#CTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#ctfindelement)]  
  
## <a name="see-also"></a>另请参阅

- [查找由 DataTemplate 生成的元素](../data/how-to-find-datatemplate-generated-elements.md)
- [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [WPF XAML 名称范围](../advanced/wpf-xaml-namescopes.md)
- [WPF 中的树](../advanced/trees-in-wpf.md)
