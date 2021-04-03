---
title: 如何：实现装饰器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: da318fee42b4628351217774de2a2225cfb21ee1
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972812"
---
# <a name="how-to-implement-an-adorner"></a>如何：实现装饰器
此示例演示了一个最小装饰器实现。  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 请务必注意，装饰器不包括任何继承呈现行为，确保装饰器呈现是装饰器实施者的责任。   实现呈现行为的常见方法是重写 <xref:System.Windows.UIElement.OnRender%2A> 方法，并使用一个或多个 <xref:System.Windows.Media.DrawingContext> 对象根据需要呈现装饰器的视觉对象 (如此示例) 中所示。  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>说明  
 通过实现继承自抽象类的类来创建自定义装饰器 <xref:System.Windows.Documents.Adorner> 。  示例装饰器 <xref:System.Windows.UIElement> 通过重写方法，只是装饰的角 <xref:System.Windows.UIElement.OnRender%2A> 。  
  
### <a name="code"></a>代码  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a>另请参阅

- [装饰器概述](adorners-overview.md)
