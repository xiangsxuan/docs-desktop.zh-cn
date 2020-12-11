---
title: 如何：确保子表中的选定行保持在正确的位置
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- master-details view
- row position [Windows Forms]
- parent/child view [Windows Forms]
- resetting child position
- data binding [.NET Framework], row selection
- caching [.NET Framework], child position
- child position
- master/details view [Windows Forms]
- child tables row selection
- current child position
ms.assetid: c5fa2562-43a4-46fa-a604-52d8526a87bd
ms.openlocfilehash: 1047958a5600d8e6ee0ba461305e09395151ab14
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971729"
---
# <a name="how-to-ensure-the-selected-row-in-a-child-table-remains-at-the-correct-position"></a><span data-ttu-id="d6d6e-102">如何：确保子表中的选定行保持在正确的位置</span><span class="sxs-lookup"><span data-stu-id="d6d6e-102">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>
<span data-ttu-id="d6d6e-103">通常当在 Windows 窗体中使用数据绑定时，将显示称为父/子视图或母版/详细视图中的数据。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-103">Oftentimes when you work with data binding in Windows Forms, you will display data in what is called a parent/child or master/details view.</span></span> <span data-ttu-id="d6d6e-104">这是指一个数据绑定方案，其中来自同一源的数据将显示在两个控件中。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-104">This refers to a data-binding scenario where data from the same source is displayed in two controls.</span></span> <span data-ttu-id="d6d6e-105">更改一个控件中的选定内容会导致在第二个控件中显示的数据变动。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-105">Changing the selection in one control causes the data displayed in the second control to change.</span></span> <span data-ttu-id="d6d6e-106">例如，第一个控件可能会包含一个客户列表，而第二个控件则可能包含与第一个控件中选定客户相关的订单列表。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-106">For example, the first control might contain a list of customers and the second a list of orders related to the selected customer in the first control.</span></span>  
  
 <span data-ttu-id="d6d6e-107">开始使用.NET Framework 2.0 版本，当在父/子视图中显示数据时，可能需要采取额外步骤来确保子表中当前所选的行不会重置为表的第一行。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-107">Starting with the .NET Framework version 2.0, when you display data in a parent/child view you might have to take extra steps to make sure that the currently selected row in the child table is not reset to the first row of the table.</span></span> <span data-ttu-id="d6d6e-108">为了执行此操作，必须缓存子表位置并在父表发生更改后将其重置。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-108">In order to do this, you will have to cache the child table position and reset it after the parent table changes.</span></span> <span data-ttu-id="d6d6e-109">父表某一行中的字段第一次更改时通常会发生子表重置。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-109">Typically the child reset occurs the first time a field in a row of the parent table changes.</span></span>  
  
### <a name="to-cache-the-current-child-position"></a><span data-ttu-id="d6d6e-110">若要缓存当前子表位置</span><span class="sxs-lookup"><span data-stu-id="d6d6e-110">To Cache the Current Child Position</span></span>  
  
1. <span data-ttu-id="d6d6e-111">则声明一个整数变量，以存储子列表位置，并声明一个布尔变量，以存储是否缓存子表位置。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-111">Declare an integer variable to store the child list position and a Boolean variable to store whether to cache the child position.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#4)]  
  
2. <span data-ttu-id="d6d6e-112">为绑定的 <xref:System.Windows.Forms.CurrencyManager> 处理 <xref:System.Windows.Forms.CurrencyManager.ListChanged> 事件并检查 <xref:System.ComponentModel.ListChangedType.Reset> 的 <xref:System.ComponentModel.ListChangedType>。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-112">Handle the <xref:System.Windows.Forms.CurrencyManager.ListChanged> event for the binding's <xref:System.Windows.Forms.CurrencyManager> and check for a <xref:System.ComponentModel.ListChangedType> of <xref:System.ComponentModel.ListChangedType.Reset>.</span></span>  
  
3. <span data-ttu-id="d6d6e-113">检查 <xref:System.Windows.Forms.CurrencyManager> 的当前位置。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-113">Check the current position of the <xref:System.Windows.Forms.CurrencyManager>.</span></span> <span data-ttu-id="d6d6e-114">如果它大于列表中第一个条目（通常为 0），则将其保存到一个变量。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-114">If it is greater than first entry in the list (typically 0), save it to a variable.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#2)]  
  
4. <span data-ttu-id="d6d6e-115">为父货币管理器处理父列表的 <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> 事件。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-115">Handle the parent list's <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> event for the parent currency manager.</span></span> <span data-ttu-id="d6d6e-116">在处理程序中，设置布尔值，以指示其不是一个缓存方案。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-116">In the handler, set the Boolean value to indicate it is not a caching scenario.</span></span> <span data-ttu-id="d6d6e-117">如果发生了 <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged>，则对父对象的更改是列表位置的更改，而不是项目值的更改。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-117">If the <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> occurs, the change to the parent is a list position change and not an item value change.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#5)]  
  
### <a name="to-reset-the-child-position"></a><span data-ttu-id="d6d6e-118">若要重置子表位置</span><span class="sxs-lookup"><span data-stu-id="d6d6e-118">To Reset the Child Position</span></span>  
  
1. <span data-ttu-id="d6d6e-119">为子绑定的 <xref:System.Windows.Forms.CurrencyManager>处理 <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> 事件。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-119">Handle the <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> event for the child binding's <xref:System.Windows.Forms.CurrencyManager>.</span></span>  
  
2. <span data-ttu-id="d6d6e-120">将子表位置重置到前述过程中保存的缓存位置。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-120">Reset the child table position to the cached position saved in the previous procedure.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="d6d6e-121">示例</span><span class="sxs-lookup"><span data-stu-id="d6d6e-121">Example</span></span>  
 <span data-ttu-id="d6d6e-122">以下示例演示了如何在子表的 <xref:System.Windows.Forms.CurrencyManager> 上保存当前位置，并在父表上的编辑完成后重置该位置。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-122">The following example demonstrates how to save the current position on the <xref:System.Windows.Forms.CurrencyManager>.for a child table and reset the position after an edit is completed on the parent table.</span></span> <span data-ttu-id="d6d6e-123">此示例包含通过使用 <xref:System.Windows.Forms.BindingSource> 组件绑定到 <xref:System.Data.DataSet> 中的两个表的两个 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-123">This example contains two <xref:System.Windows.Forms.DataGridView> controls bound to two tables in a <xref:System.Data.DataSet> using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="d6d6e-124">两个表之间建立了关系并将此关系添加到了 <xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-124">A relation is established between the two tables and the relation is added to the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="d6d6e-125">出于演示目的，子表中的位置最初设置为第三行。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-125">The position in the child table is initially set to the third row for demonstration purposes.</span></span>  
  
 [!code-csharp[System.Windows.Forms.CurrencyManagerReset#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CurrencyManagerReset#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#1)]  
  
 <span data-ttu-id="d6d6e-126">若要测试代码示例，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d6d6e-126">To test the code example, perform the following steps:</span></span>  
  
1. <span data-ttu-id="d6d6e-127">运行示例。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-127">Run the example.</span></span>  
  
2. <span data-ttu-id="d6d6e-128">请确保“缓存并重置位置”复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-128">Make sure the **Cache and reset position** check box is selected.</span></span>  
  
3. <span data-ttu-id="d6d6e-129">单击“清除父字段”按钮会导致父表的某个字段发生更改。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-129">Click the **Clear parent field** button to cause a change in a field of the parent table.</span></span> <span data-ttu-id="d6d6e-130">请注意，子表中的所选行将不会更改。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-130">Notice that the selected row in the child table does not change.</span></span>  
  
4. <span data-ttu-id="d6d6e-131">关闭，然后再次运行该示例。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-131">Close and run the example again.</span></span> <span data-ttu-id="d6d6e-132">需要这样做的原因是重置行为仅在父行中第一次更改时发生。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-132">You need to do this because the reset behavior occurs only on the first change in the parent row.</span></span>  
  
5. <span data-ttu-id="d6d6e-133">清除“缓存并重置位置”复选框。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-133">Clear the **Cache and reset position** check box.</span></span>  
  
6. <span data-ttu-id="d6d6e-134">单击“清除父字段”按钮。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-134">Click the **Clear parent field** button.</span></span> <span data-ttu-id="d6d6e-135">请注意，子表中的选定的行将更改为第一行。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-135">Notice that the selected row in the child table changes to the first row.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d6d6e-136">编译代码</span><span class="sxs-lookup"><span data-stu-id="d6d6e-136">Compiling the Code</span></span>  
 <span data-ttu-id="d6d6e-137">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="d6d6e-137">This example requires:</span></span>  
  
- <span data-ttu-id="d6d6e-138">对 System、System.Data、System.Drawing、System.Windows.Forms 和 System.Xml 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d6d6e-138">References to the System, System.Data, System.Drawing, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6d6e-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6d6e-139">See also</span></span>

- [<span data-ttu-id="d6d6e-140">如何：确保绑定到同一数据源的多个控件保持同步</span><span class="sxs-lookup"><span data-stu-id="d6d6e-140">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](multiple-controls-bound-to-data-source-synchronized.md)
- [<span data-ttu-id="d6d6e-141">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="d6d6e-141">BindingSource Component</span></span>](./controls/bindingsource-component.md)
- [<span data-ttu-id="d6d6e-142">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="d6d6e-142">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
