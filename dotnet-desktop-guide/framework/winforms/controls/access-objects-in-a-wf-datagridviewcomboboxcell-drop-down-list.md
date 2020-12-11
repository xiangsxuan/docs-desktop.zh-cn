---
title: Drop-Down 列表访问 DataGridViewComboBoxCell 中的对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 7e76ab1ac9089778e4371f4ee65b06d5ebc570bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970756"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a><span data-ttu-id="23f15-102">如何：访问 Windows 窗体 DataGridViewComboBoxCell 下拉列表中的对象</span><span class="sxs-lookup"><span data-stu-id="23f15-102">How to: Access Objects in a Windows Forms DataGridViewComboBoxCell Drop-Down List</span></span>
<span data-ttu-id="23f15-103">与 <xref:System.Windows.Forms.ComboBox> 控件一样， <xref:System.Windows.Forms.DataGridViewComboBoxColumn> 和 <xref:System.Windows.Forms.DataGridViewComboBoxCell> 类型使您能够向其下拉列表添加任意对象。</span><span class="sxs-lookup"><span data-stu-id="23f15-103">Like the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and <xref:System.Windows.Forms.DataGridViewComboBoxCell> types enable you to add arbitrary objects to their drop-down lists.</span></span> <span data-ttu-id="23f15-104">利用此功能，可以在下拉列表中表示复杂状态，而不必在单独的集合中存储相应的对象。</span><span class="sxs-lookup"><span data-stu-id="23f15-104">With this feature, you can represent complex states in a drop-down list without having to store corresponding objects in a separate collection.</span></span>  
  
 <span data-ttu-id="23f15-105">与 <xref:System.Windows.Forms.ComboBox> 控件不同， <xref:System.Windows.Forms.DataGridView> 类型没有 <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> 用于检索当前选定对象的属性。</span><span class="sxs-lookup"><span data-stu-id="23f15-105">Unlike the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridView> types do not have a <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> property for retrieving the currently selected object.</span></span> <span data-ttu-id="23f15-106">相反，你必须将 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> 或 <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> 属性设置为业务对象上的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="23f15-106">Instead, you must set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> property to the name of a property on your business object.</span></span> <span data-ttu-id="23f15-107">当用户进行选择时，业务对象的指定属性将设置该单元 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="23f15-107">When the user makes a selection, the indicated property of the business object sets the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
 <span data-ttu-id="23f15-108">若要通过单元值检索业务对象， `ValueMember` 属性必须指示一个属性，该属性返回对业务对象本身的引用。</span><span class="sxs-lookup"><span data-stu-id="23f15-108">To retrieve the business object through the cell value, the `ValueMember` property must indicate a property that returns a reference to the business object itself.</span></span> <span data-ttu-id="23f15-109">因此，如果业务对象的类型不在控件下，则必须通过继承扩展该类型来添加此类属性。</span><span class="sxs-lookup"><span data-stu-id="23f15-109">Therefore, if the type of the business object is not under your control, you must add such a property by extending the type through inheritance.</span></span>  
  
 <span data-ttu-id="23f15-110">下面的过程演示如何使用业务对象填充下拉列表并通过 cell 属性检索对象 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> 。</span><span class="sxs-lookup"><span data-stu-id="23f15-110">The following procedures demonstrate how to populate a drop-down list with business objects and retrieve the objects through the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a><span data-ttu-id="23f15-111">将业务对象添加到下拉列表中</span><span class="sxs-lookup"><span data-stu-id="23f15-111">To add business objects to the drop-down list</span></span>  
  
1. <span data-ttu-id="23f15-112">创建一个新的 <xref:System.Windows.Forms.DataGridViewComboBoxColumn> 并填充其 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> 集合。</span><span class="sxs-lookup"><span data-stu-id="23f15-112">Create a new <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and populate its <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> collection.</span></span> <span data-ttu-id="23f15-113">或者，您可以将 "列" <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> 属性设置为业务对象的集合。</span><span class="sxs-lookup"><span data-stu-id="23f15-113">Alternatively, you can set the column <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property to the collection of business objects.</span></span> <span data-ttu-id="23f15-114">但在这种情况下，不能将 "未分配" 添加到下拉列表中，也不会在集合中创建相应的业务对象。</span><span class="sxs-lookup"><span data-stu-id="23f15-114">In that case, however, you cannot add "unassigned" to the drop-down list without creating a corresponding business object in your collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. <span data-ttu-id="23f15-115">设置 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> 和 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="23f15-115">Set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> and <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> properties.</span></span> <span data-ttu-id="23f15-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> 指示要在下拉列表中显示的业务对象的属性。</span><span class="sxs-lookup"><span data-stu-id="23f15-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indicates the property of the business object to display in the drop-down list.</span></span> <span data-ttu-id="23f15-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 指示返回对业务对象的引用的属性。</span><span class="sxs-lookup"><span data-stu-id="23f15-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indicates the property that returns a reference to the business object.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. <span data-ttu-id="23f15-118">请确保业务对象类型包含一个属性，该属性返回对当前实例的引用。</span><span class="sxs-lookup"><span data-stu-id="23f15-118">Make sure that your business object type contains a property that returns a reference to the current instance.</span></span> <span data-ttu-id="23f15-119">此属性的名称必须为 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 上一步中分配给的值。</span><span class="sxs-lookup"><span data-stu-id="23f15-119">This property must be named with the value assigned to <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> in the previous step.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a><span data-ttu-id="23f15-120">检索当前选定的业务对象</span><span class="sxs-lookup"><span data-stu-id="23f15-120">To retrieve the currently selected business object</span></span>  
  
- <span data-ttu-id="23f15-121">获取单元格 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> 属性，并将其转换为业务对象类型。</span><span class="sxs-lookup"><span data-stu-id="23f15-121">Get the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property and cast it to the business object type.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a><span data-ttu-id="23f15-122">示例</span><span class="sxs-lookup"><span data-stu-id="23f15-122">Example</span></span>  
 <span data-ttu-id="23f15-123">完整的示例演示如何在下拉列表中使用业务对象。</span><span class="sxs-lookup"><span data-stu-id="23f15-123">The complete example demonstrates the use of business objects in a drop-down list.</span></span> <span data-ttu-id="23f15-124">在此示例中， <xref:System.Windows.Forms.DataGridView> 控件绑定到对象的集合 `Task` 。</span><span class="sxs-lookup"><span data-stu-id="23f15-124">In the example, a <xref:System.Windows.Forms.DataGridView> control is bound to a collection of `Task` objects.</span></span> <span data-ttu-id="23f15-125">每个 `Task` 对象都有一个 `AssignedTo` 属性，该属性指示 `Employee` 当前分配给该任务的对象。</span><span class="sxs-lookup"><span data-stu-id="23f15-125">Each `Task` object has an `AssignedTo` property that indicates the `Employee` object currently assigned to that task.</span></span> <span data-ttu-id="23f15-126">`Assigned To`列显示 `Name` 每个已分配员工的属性值，如果属性值为，则为 "未分配" `Task.AssignedTo` `null` 。</span><span class="sxs-lookup"><span data-stu-id="23f15-126">The `Assigned To` column displays the `Name` property value for each assigned employee, or "unassigned" if the `Task.AssignedTo` property value is `null`.</span></span>  
  
 <span data-ttu-id="23f15-127">若要查看此示例的行为，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="23f15-127">To view the behavior of this example, perform the following steps:</span></span>  
  
1. <span data-ttu-id="23f15-128">`Assigned To`通过从下拉列表中选择不同的值或在组合框单元中按 CTRL + 0，更改列中的赋值。</span><span class="sxs-lookup"><span data-stu-id="23f15-128">Change assignments in the `Assigned To` column by selecting different values from the drop-down lists or pressing CTRL+0 in a combo-box cell.</span></span>  
  
2. <span data-ttu-id="23f15-129">单击 `Generate Report` 此可显示当前分配。</span><span class="sxs-lookup"><span data-stu-id="23f15-129">Click `Generate Report` to display the current assignments.</span></span> <span data-ttu-id="23f15-130">这说明列中的更改将 `Assigned To` 自动更新 `tasks` 集合。</span><span class="sxs-lookup"><span data-stu-id="23f15-130">This demonstrates that a change in the `Assigned To` column automatically updates the `tasks` collection.</span></span>  
  
3. <span data-ttu-id="23f15-131">单击某个 `Request Status` 按钮可以调用 `RequestStatus` 该行的当前对象的方法 `Employee` 。</span><span class="sxs-lookup"><span data-stu-id="23f15-131">Click a `Request Status` button to call the `RequestStatus` method of the current `Employee` object for that row.</span></span> <span data-ttu-id="23f15-132">这表明已成功检索到所选对象。</span><span class="sxs-lookup"><span data-stu-id="23f15-132">This demonstrates that the selected object has been successfully retrieved.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="23f15-133">编译代码</span><span class="sxs-lookup"><span data-stu-id="23f15-133">Compiling the Code</span></span>  
 <span data-ttu-id="23f15-134">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="23f15-134">This example requires:</span></span>  
  
- <span data-ttu-id="23f15-135">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="23f15-135">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f15-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23f15-136">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ComboBox>
- [<span data-ttu-id="23f15-137">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="23f15-137">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
