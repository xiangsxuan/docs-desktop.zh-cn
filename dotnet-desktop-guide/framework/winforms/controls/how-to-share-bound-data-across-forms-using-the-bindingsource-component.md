---
title: 如何：使用 BindingSource 组件跨窗体共享绑定数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: aa497194fd4ac65f48773a45175333a1d862b453
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972653"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a>如何：使用 BindingSource 组件跨窗体共享绑定数据
使用 <xref:System.Windows.Forms.BindingSource> 组件可轻松跨窗体共享数据。 例如，你可能想要展示一个对数据源数据进行汇总的只读窗体和另一个包含有关数据源中当前所选项的详细信息的可编辑窗体。 此示例演示这种情况。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何跨窗体共享 <xref:System.Windows.Forms.BindingSource> 及其绑定数据。 在此示例中，共享的 <xref:System.Windows.Forms.BindingSource> 传递给子窗体的构造函数。 子窗体使用户可编辑主窗体中当前所选项的数据。  
  
> [!NOTE]
> 示例中处理了 <xref:System.Windows.Forms.BindingSource> 组件的 <xref:System.Windows.Forms.BindingSource.BindingComplete> 事件，以确保两个窗体保持同步。 若要深入了解进行此操作的原因，请参阅[如何：确保绑定到同一数据源的多个控件保持同步](../multiple-controls-bound-to-data-source-synchronized.md)。  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System、System.Windows.Forms、System.Drawing、System.Data 和 System.Xml 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- [BindingSource 组件](bindingsource-component.md)
- [Windows 窗体数据绑定](../windows-forms-data-binding.md)
- [如何：处理因数据绑定而发生的错误和异常](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
