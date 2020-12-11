---
title: 将控件绑定到 DBNull 数据库值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingSource component [Windows Forms], binding to DBNull values
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to DBNull values
ms.assetid: 96494e6f-5f40-4f83-af97-bbd7192c2af8
ms.openlocfilehash: 175d7f5aee2540916480e2c55a485af1f9d16653
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972061"
---
# <a name="how-to-bind-windows-forms-controls-to-dbnull-database-values"></a>如何：将 Windows 窗体控件绑定到 DBNull 数据库值
将 Windows 窗体绑定到数据源且该数据源返回 <xref:System.DBNull> 值时，可以直接替换相应的值，而不用处理、格式化或解析事件。 在格式化或解析数据源的值时，<xref:System.Windows.Forms.Binding.NullValue%2A> 属性将 <xref:System.DBNull> 转换为指定的对象。  
  
## <a name="example"></a>示例  
 以下示例演示在两种不同情况下如何绑定 <xref:System.DBNull> 值。 前者演示如何为字符串属性设置 <xref:System.Windows.Forms.Binding.NullValue%2A>，后者演示如何为图像属性设置 <xref:System.Windows.Forms.Binding.NullValue%2A>。  
  
 [!code-csharp[System.Windows.Forms.BindingDBNull#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingDBNull#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/VB/form1.vb#1)]  
  
 绑定属性和 <xref:System.Windows.Forms.Binding.NullValue%2A> 属性的类型必需相同，否则会引发错误，并且不会继续处理 <xref:System.Windows.Forms.Binding.NullValue%2A> 值。 在这种情况下，将不会引发异常。  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- [BindingSource 组件](bindingsource-component.md)
- [如何：处理因数据绑定而发生的错误和异常](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
- [如何：将 Windows 窗体控件绑定到类型](how-to-bind-a-windows-forms-control-to-a-type.md)
