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
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a>如何：访问 Windows 窗体 DataGridViewComboBoxCell 下拉列表中的对象
与 <xref:System.Windows.Forms.ComboBox> 控件一样， <xref:System.Windows.Forms.DataGridViewComboBoxColumn> 和 <xref:System.Windows.Forms.DataGridViewComboBoxCell> 类型使您能够向其下拉列表添加任意对象。 利用此功能，可以在下拉列表中表示复杂状态，而不必在单独的集合中存储相应的对象。  
  
 与 <xref:System.Windows.Forms.ComboBox> 控件不同， <xref:System.Windows.Forms.DataGridView> 类型没有 <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> 用于检索当前选定对象的属性。 相反，你必须将 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> 或 <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> 属性设置为业务对象上的属性的名称。 当用户进行选择时，业务对象的指定属性将设置该单元 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> 属性。  
  
 若要通过单元值检索业务对象， `ValueMember` 属性必须指示一个属性，该属性返回对业务对象本身的引用。 因此，如果业务对象的类型不在控件下，则必须通过继承扩展该类型来添加此类属性。  
  
 下面的过程演示如何使用业务对象填充下拉列表并通过 cell 属性检索对象 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> 。  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a>将业务对象添加到下拉列表中  
  
1. 创建一个新的 <xref:System.Windows.Forms.DataGridViewComboBoxColumn> 并填充其 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> 集合。 或者，您可以将 "列" <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> 属性设置为业务对象的集合。 但在这种情况下，不能将 "未分配" 添加到下拉列表中，也不会在集合中创建相应的业务对象。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. 设置 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> 和 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 属性。 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> 指示要在下拉列表中显示的业务对象的属性。 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 指示返回对业务对象的引用的属性。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. 请确保业务对象类型包含一个属性，该属性返回对当前实例的引用。 此属性的名称必须为 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 上一步中分配给的值。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a>检索当前选定的业务对象  
  
- 获取单元格 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> 属性，并将其转换为业务对象类型。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a>示例  
 完整的示例演示如何在下拉列表中使用业务对象。 在此示例中， <xref:System.Windows.Forms.DataGridView> 控件绑定到对象的集合 `Task` 。 每个 `Task` 对象都有一个 `AssignedTo` 属性，该属性指示 `Employee` 当前分配给该任务的对象。 `Assigned To`列显示 `Name` 每个已分配员工的属性值，如果属性值为，则为 "未分配" `Task.AssignedTo` `null` 。  
  
 若要查看此示例的行为，请执行以下步骤：  
  
1. `Assigned To`通过从下拉列表中选择不同的值或在组合框单元中按 CTRL + 0，更改列中的赋值。  
  
2. 单击 `Generate Report` 此可显示当前分配。 这说明列中的更改将 `Assigned To` 自动更新 `tasks` 集合。  
  
3. 单击某个 `Request Status` 按钮可以调用 `RequestStatus` 该行的当前对象的方法 `Employee` 。 这表明已成功检索到所选对象。  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

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
- [在 Windows 窗体 DataGridView 控件中显示数据](displaying-data-in-the-windows-forms-datagridview-control.md)
