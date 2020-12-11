---
title: 如何：确保绑定到同一数据源的多个控件保持同步
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
ms.openlocfilehash: 8a39c50bfc452c807a18a9bf0a65e56cb75d20aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970246"
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a>如何：确保绑定到同一数据源的多个控件保持同步
在 Windows 窗体中使用数据绑定时，经常会将多个控件绑定到同一个数据源。 在某些情况下，可能需要采取额外的措施来确保控件的绑定属性彼此保持同步和数据源。 在以下两种情况下，需要执行这些步骤：  
  
- 如果数据源未实现 <xref:System.ComponentModel.IBindingList> ，因此生成 <xref:System.ComponentModel.IBindingList.ListChanged> 类型为的事件 <xref:System.ComponentModel.ListChangedType.ItemChanged> 。  
  
- 如果数据源实现，则为 <xref:System.ComponentModel.IEditableObject> 。  
  
 在前一种情况下，可以使用将 <xref:System.Windows.Forms.BindingSource> 数据源绑定到控件。 在后一种情况下，将使用 <xref:System.Windows.Forms.BindingSource> 并处理 <xref:System.Windows.Forms.BindingSource.BindingComplete> 事件，并 <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> 在关联的上调用 <xref:System.Windows.Forms.BindingManagerBase> 。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何使用组件将三个控件（两个文本框控件和一个 <xref:System.Windows.Forms.DataGridView> 控件）绑定到中的同一列 <xref:System.Data.DataSet> <xref:System.Windows.Forms.BindingSource> 。 此示例演示如何处理事件， <xref:System.Windows.Forms.BindingSource.BindingComplete> 并确保在更改一个文本框的文本值时，将 <xref:System.Windows.Forms.DataGridView> 用正确的值更新其他文本框和控件。  
  
 该示例使用 <xref:System.Windows.Forms.BindingSource> 来绑定数据源和控件。 或者，可以将控件直接绑定到数据源，并 <xref:System.Windows.Forms.BindingManagerBase> 从窗体的中检索绑定的， <xref:System.Windows.Forms.Control.BindingContext%2A> 然后处理的 <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> 事件 <xref:System.Windows.Forms.BindingManagerBase> 。 有关如何执行此操作的示例，请参阅有关的事件的 "帮助" 页 <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> <xref:System.Windows.Forms.BindingManagerBase> 。  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
  
- 此代码示例需要  
  
- 对 <xref:System><xref:System.Windows.Forms> 和 <xref:System.Drawing> 程序集的引用。  
  
- 处理了事件的窗体 <xref:System.Windows.Forms.Form.Load> ，并 `InitializeControlsAndDataSource` 从窗体的 <xref:System.Windows.Forms.Form.Load> 事件处理程序调用了此示例中的方法。  
  
## <a name="see-also"></a>另请参阅

- [如何：使用 BindingSource 组件跨窗体共享绑定数据](./controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)
- [Windows 窗体数据绑定中的更改通知](change-notification-in-windows-forms-data-binding.md)
- [与数据绑定相关的接口](interfaces-related-to-data-binding.md)
- [Windows 窗体数据绑定](windows-forms-data-binding.md)
