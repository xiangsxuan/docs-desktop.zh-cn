---
title: 将控件绑定到工厂对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], binding
- factory objects [Windows Forms], binding to
- BindingSource component [Windows Forms], binding to a factory object
- BindingSource component [Windows Forms], examples
ms.assetid: 7d59af89-ff82-41d8-a48a-f1fbae788b0d
ms.openlocfilehash: 2b4d9aca3345a0cb1e7e995f66a8982dee983ca8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971897"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-factory-object"></a>如何：将 Windows 窗体控件绑定到 Factory 对象
生成与数据交互的控件时，有时需要将控件绑定到生成其他对象的对象或方法。 此类对象或方法被称为 Factory。 例如，数据源可能是方法调用的返回值，而不是内存中的对象或类型。 只要源返回集合，即可将控件绑定到此类数据源。  
  
 借助 <xref:System.Windows.Forms.BindingSource> 控件可轻松将控件绑定到工厂对象。  
  
## <a name="example"></a>示例  
 下面的示例演示了如何使用 <xref:System.Windows.Forms.BindingSource> 控件将 <xref:System.Windows.Forms.DataGridView> 控件绑定到工厂方法。 Factory 方法命名为 `GetOrdersByCustomerId`，并返回 Northwind 数据库中给定客户的所有订单。  
  
 [!code-cpp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [BindingSource 组件](bindingsource-component.md)
- [如何：将 Windows 窗体控件绑定到类型](how-to-bind-a-windows-forms-control-to-a-type.md)
