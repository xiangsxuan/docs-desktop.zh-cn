---
title: 如何：将装饰器绑定到元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: 951643602b09a522d23a6449aefa4be41e051a40
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972894"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a>如何：将装饰器绑定到元素
此示例演示如何以编程方式将装饰器绑定到指定的 <xref:System.Windows.UIElement> 。  
  
## <a name="example"></a>示例  
 若要将装饰器绑定到特定的 <xref:System.Windows.UIElement> ，请执行以下步骤：  
  
1. 调用 `static` 方法 <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 以获取 <xref:System.Windows.Documents.AdornerLayer> 要装饰的的对象 <xref:System.Windows.UIElement> 。 <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 遍历可视化树（从指定的 **UIElement** 开始），并返回它找到的第一个装饰器层。 （如果未发现装饰器层，该方法将返回 null。）  
  
2. 调用 <xref:System.Windows.Documents.AdornerLayer.Add%2A> 方法以将装饰器绑定到目标 **UIElement**。  
  
 下面的示例将如上所示) 的 (SimpleCircleAdorner 绑定到一个 <xref:System.Windows.Controls.TextBox> 命名的 *myTextBox*。  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
> 目前不支持使用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 将装饰器绑定到另一个元素。  
  
## <a name="see-also"></a>另请参阅

- [装饰器概述](adorners-overview.md)
