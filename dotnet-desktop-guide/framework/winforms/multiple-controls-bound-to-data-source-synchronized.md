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
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a><span data-ttu-id="7c24c-102">如何：确保绑定到同一数据源的多个控件保持同步</span><span class="sxs-lookup"><span data-stu-id="7c24c-102">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>
<span data-ttu-id="7c24c-103">在 Windows 窗体中使用数据绑定时，经常会将多个控件绑定到同一个数据源。</span><span class="sxs-lookup"><span data-stu-id="7c24c-103">Oftentimes when working with data binding in Windows Forms, multiple controls are bound to the same data source.</span></span> <span data-ttu-id="7c24c-104">在某些情况下，可能需要采取额外的措施来确保控件的绑定属性彼此保持同步和数据源。</span><span class="sxs-lookup"><span data-stu-id="7c24c-104">In some cases, it may be necessary to take extra steps to ensure that the bound properties of the controls remain synchronized with each other and the data source.</span></span> <span data-ttu-id="7c24c-105">在以下两种情况下，需要执行这些步骤：</span><span class="sxs-lookup"><span data-stu-id="7c24c-105">These steps are necessary in two situations:</span></span>  
  
- <span data-ttu-id="7c24c-106">如果数据源未实现 <xref:System.ComponentModel.IBindingList> ，因此生成 <xref:System.ComponentModel.IBindingList.ListChanged> 类型为的事件 <xref:System.ComponentModel.ListChangedType.ItemChanged> 。</span><span class="sxs-lookup"><span data-stu-id="7c24c-106">If the data source does not implement <xref:System.ComponentModel.IBindingList>, and therefore generate <xref:System.ComponentModel.IBindingList.ListChanged> events of type <xref:System.ComponentModel.ListChangedType.ItemChanged>.</span></span>  
  
- <span data-ttu-id="7c24c-107">如果数据源实现，则为 <xref:System.ComponentModel.IEditableObject> 。</span><span class="sxs-lookup"><span data-stu-id="7c24c-107">If the data source implements <xref:System.ComponentModel.IEditableObject>.</span></span>  
  
 <span data-ttu-id="7c24c-108">在前一种情况下，可以使用将 <xref:System.Windows.Forms.BindingSource> 数据源绑定到控件。</span><span class="sxs-lookup"><span data-stu-id="7c24c-108">In the former case, you can use a <xref:System.Windows.Forms.BindingSource> to bind the data source to the controls.</span></span> <span data-ttu-id="7c24c-109">在后一种情况下，将使用 <xref:System.Windows.Forms.BindingSource> 并处理 <xref:System.Windows.Forms.BindingSource.BindingComplete> 事件，并 <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> 在关联的上调用 <xref:System.Windows.Forms.BindingManagerBase> 。</span><span class="sxs-lookup"><span data-stu-id="7c24c-109">In the latter case, you use a <xref:System.Windows.Forms.BindingSource> and handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and call <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> on the associated <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c24c-110">示例</span><span class="sxs-lookup"><span data-stu-id="7c24c-110">Example</span></span>  
 <span data-ttu-id="7c24c-111">下面的代码示例演示如何使用组件将三个控件（两个文本框控件和一个 <xref:System.Windows.Forms.DataGridView> 控件）绑定到中的同一列 <xref:System.Data.DataSet> <xref:System.Windows.Forms.BindingSource> 。</span><span class="sxs-lookup"><span data-stu-id="7c24c-111">The following code example demonstrates how to bind three controls—two text-box controls and a <xref:System.Windows.Forms.DataGridView> control—to the same column in a <xref:System.Data.DataSet> using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="7c24c-112">此示例演示如何处理事件， <xref:System.Windows.Forms.BindingSource.BindingComplete> 并确保在更改一个文本框的文本值时，将 <xref:System.Windows.Forms.DataGridView> 用正确的值更新其他文本框和控件。</span><span class="sxs-lookup"><span data-stu-id="7c24c-112">This example demonstrates how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and ensure that when the text value of one text box is changed, the additional text box and the <xref:System.Windows.Forms.DataGridView> control are updated with the correct value.</span></span>  
  
 <span data-ttu-id="7c24c-113">该示例使用 <xref:System.Windows.Forms.BindingSource> 来绑定数据源和控件。</span><span class="sxs-lookup"><span data-stu-id="7c24c-113">The example uses a <xref:System.Windows.Forms.BindingSource> to bind the data source and the controls.</span></span> <span data-ttu-id="7c24c-114">或者，可以将控件直接绑定到数据源，并 <xref:System.Windows.Forms.BindingManagerBase> 从窗体的中检索绑定的， <xref:System.Windows.Forms.Control.BindingContext%2A> 然后处理的 <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> 事件 <xref:System.Windows.Forms.BindingManagerBase> 。</span><span class="sxs-lookup"><span data-stu-id="7c24c-114">Alternatively, you can bind the controls directly to the data source and retrieve the <xref:System.Windows.Forms.BindingManagerBase> for the binding from the form's <xref:System.Windows.Forms.Control.BindingContext%2A> and then handle the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event for the <xref:System.Windows.Forms.BindingManagerBase>.</span></span> <span data-ttu-id="7c24c-115">有关如何执行此操作的示例，请参阅有关的事件的 "帮助" 页 <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> <xref:System.Windows.Forms.BindingManagerBase> 。</span><span class="sxs-lookup"><span data-stu-id="7c24c-115">For an example of how to do this, see the Help page about the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event of <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7c24c-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="7c24c-116">Compiling the Code</span></span>  
  
- <span data-ttu-id="7c24c-117">此代码示例需要</span><span class="sxs-lookup"><span data-stu-id="7c24c-117">This code example requires</span></span>  
  
- <span data-ttu-id="7c24c-118">对 <xref:System><xref:System.Windows.Forms> 和 <xref:System.Drawing> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="7c24c-118">References to the <xref:System>, <xref:System.Windows.Forms>, and <xref:System.Drawing> assemblies.</span></span>  
  
- <span data-ttu-id="7c24c-119">处理了事件的窗体 <xref:System.Windows.Forms.Form.Load> ，并 `InitializeControlsAndDataSource` 从窗体的 <xref:System.Windows.Forms.Form.Load> 事件处理程序调用了此示例中的方法。</span><span class="sxs-lookup"><span data-stu-id="7c24c-119">A form with the <xref:System.Windows.Forms.Form.Load> event handled and a call to the `InitializeControlsAndDataSource` method in the example from the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c24c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c24c-120">See also</span></span>

- [<span data-ttu-id="7c24c-121">如何：使用 BindingSource 组件跨窗体共享绑定数据</span><span class="sxs-lookup"><span data-stu-id="7c24c-121">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](./controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)
- [<span data-ttu-id="7c24c-122">Windows 窗体数据绑定中的更改通知</span><span class="sxs-lookup"><span data-stu-id="7c24c-122">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="7c24c-123">与数据绑定相关的接口</span><span class="sxs-lookup"><span data-stu-id="7c24c-123">Interfaces Related to Data Binding</span></span>](interfaces-related-to-data-binding.md)
- [<span data-ttu-id="7c24c-124">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="7c24c-124">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
