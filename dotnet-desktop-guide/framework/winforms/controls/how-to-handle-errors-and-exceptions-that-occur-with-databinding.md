---
title: 如何：处理因数据绑定而发生的错误和异常
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- error handling [Windows Forms], examples
- data binding [Windows Forms], examples
- examples [Windows Forms], error handling
- error handling [Windows Forms], data binding
- data binding [Windows Forms], error handling
- BindingSource component [Windows Forms], handling errors and exceptions
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
ms.openlocfilehash: 14326d793be3ee71022a7a1e7398b9af469aab10
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971172"
---
# <a name="how-to-handle-errors-and-exceptions-that-occur-with-databinding"></a>如何：处理因数据绑定而发生的错误和异常
将基础业务对象绑定到控件时，此类对象上时常发生异常和错误。 可以截获这些错误和异常，然后通过为特定的 <xref:System.Windows.Forms.Binding>、<xref:System.Windows.Forms.BindingSource> 或 <xref:System.Windows.Forms.CurrencyManager> 组件处理 <xref:System.Windows.Forms.Binding.BindingComplete> 事件恢复错误信息或将此信息传递至用户。  
  
## <a name="example"></a>示例  
 此代码示例演示了如何处理数据绑定操作过程中发生的错误和异常。 此示例演示了如何通过处理 <xref:System.Windows.Forms.Binding> 对象的 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> 事件截获错误。 为了通过处理此事件来截获错误和异常，必须启用绑定的格式化。 可在构造绑定或将其添加到绑定集合时，或通过将 <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> 属性设置为 `true`，来启用格式化。  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 当代码正在运行，且为部件名输入的字符串为空或为部件号输入的值小于 100 时，将显示一个消息框。 这是为这些文本框绑定处理 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> 事件产生的结果。  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=nameWithType>
- [BindingSource 组件](bindingsource-component.md)
