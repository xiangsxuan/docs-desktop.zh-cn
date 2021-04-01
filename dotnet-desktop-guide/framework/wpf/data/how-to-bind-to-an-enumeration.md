---
title: 如何：绑定到枚举
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: c92f1f00aa3feb37b70aa9a3647265236a1625b2
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970392"
---
# <a name="how-to-bind-to-an-enumeration"></a>如何：绑定到枚举
此示例演示如何通过绑定到枚举的 GetValues 方法绑定到枚举。  
  
## <a name="example"></a>示例  
 在下面的示例中， <xref:System.Windows.Controls.ListBox> <xref:System.Windows.HorizontalAlignment> 通过数据绑定显示枚举值的列表。 <xref:System.Windows.Controls.ListBox>和将 <xref:System.Windows.Controls.Button> 绑定，以便您可以 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.Controls.Button> 通过在中选择一个值来更改的属性值 <xref:System.Windows.Controls.ListBox> 。  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>请参阅

- [绑定到方法](how-to-bind-to-a-method.md)
- [数据绑定概述](/dotnet/desktop-wpf/data/data-binding-overview)
- [操作指南主题](data-binding-how-to-topics.md)
