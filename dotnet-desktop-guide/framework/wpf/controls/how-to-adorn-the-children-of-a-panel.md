---
title: 如何：装饰面板的子级
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 4c5ac537bfd68e9c43583758047b2ec378d0bb57
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972944"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a>如何：装饰面板的子级
此示例演示如何以编程方式将装饰器绑定到指定的子级 <xref:System.Windows.Controls.Panel> 。  
  
## <a name="example"></a>示例  
 若要将装饰器绑定到的子节点 <xref:System.Windows.Controls.Panel> ，请执行以下步骤：  
  
1. 声明一个新的 <xref:System.Windows.Documents.AdornerLayer> 对象，并调用 `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 方法，以便为其子元素将被装饰的元素查找装饰器层。  
  
2. 枚举父元素的子级并调用 <xref:System.Windows.Documents.AdornerLayer.Add%2A> 方法，将装饰器绑定到每个子元素。  
  
 下面的示例将上面所示) 的 SimpleCircleAdorner (绑定到 <xref:System.Windows.Controls.StackPanel> 名为 *myStackPanel* 的子项。  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
> 目前不支持使用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 将装饰器绑定到另一个元素。  
  
## <a name="see-also"></a>另请参阅

- [装饰器概述](adorners-overview.md)
