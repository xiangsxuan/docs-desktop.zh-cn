---
title: 如何：创建简单绑定
description: 通过此操作方法示例，为应用程序创建一个简单的绑定 Windows Presentation Foundation (WPF) 。
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 9649116427c7da805323270fe3a23e6b23d330a5
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973085"
---
# <a name="how-to-create-a-simple-binding"></a>如何：创建简单绑定
此示例演示如何创建一个简单的 <xref:System.Windows.Data.Binding> 。  
  
## <a name="example"></a>示例  
 在此示例中，具有一个 `Person` 名为的字符串属性的对象 `PersonName` 。 `Person`对象是在名为的命名空间中定义的 `SDKSample` 。  
  
 在下面的示例中，包含元素的突出显示的行将 `<src>` 实例化 `Person` 对象，其 `PersonName` 属性值为 `Joe` 。 此操作在节中完成 `Resources` ，并分配了 `x:Key` 。  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 包含元素的突出显示行将 `<TextBlock>` <xref:System.Windows.Controls.TextBlock> 控件绑定到 `PersonName` 属性。 因此，将 <xref:System.Windows.Controls.TextBlock> 显示值 "Joe"。  
  
## <a name="see-also"></a>请参阅

- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [操作指南主题](data-binding-how-to-topics.md)
