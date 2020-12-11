---
title: 为 ComboBox、ListBox 或 CheckedListBox 控件创建查找表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
ms.openlocfilehash: 57dc95fc16d77ee1492f53bf57eac001a343ca8f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970170"
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>如何：为 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件创建查找表

有时，在 Windows 窗体上以用户友好格式显示数据，但存储数据时使用对程序而言更有意义的格式会很有帮助。 例如，食品订单窗体可能按列表框中的名称显示菜单项。 但是，记录订单的数据表将包含代表该食品的唯一 ID 号。 下表显示如何存储和显示食品订单窗体数据的示例。  
  
### <a name="orderdetailstable"></a>OrderDetailsTable  
  
|OrderID|ItemID|数量|  
|-------------|------------|--------------|  
|4085|12|1|  
|4086|13|3|  
  
### <a name="itemtable"></a>ItemTable  
  
|ID|名称|  
|--------|----------|  
|12|Potato|  
|13|Chicken|  
  
 在这种情况下，一个表 **OrderDetailsTable** 将存储你所关心的有关显示和保存的实际信息。 但为了节省空间，它采用一种很隐秘的方式。 另一个表 **ItemTable** 仅包含与外观相关的信息，该信息有关哪个 ID 号等效于哪个食物名称，以及与实际食物订单无关的信息。  
  
 **ItemTable** <xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.ListBox> 通过三个属性连接到、或 <xref:System.Windows.Forms.CheckedListBox> 控件。 `DataSource`属性包含此表的名称。 `DisplayMember`属性包含要显示在控件中的表的数据列 (食物名称) 。 `ValueMember`属性包含该表中的数据列，其中存储的信息 (ID 号) 。  
  
 **OrderDetailsTable** 由其绑定集合连接到控件，并通过属性进行访问 <xref:System.Windows.Forms.Control.DataBindings%2A> 。 向集合中添加绑定对象时，会将控件属性连接到特定的数据成员， ( (**OrderDetailsTable**) 的数据源中) 的 ID 号列。 在控件中进行选择时，窗体输入将保存到此表。  
  
### <a name="to-create-a-lookup-table"></a>创建查找表的步骤  
  
1. 向窗体添加 <xref:System.Windows.Forms.ComboBox><xref:System.Windows.Forms.ListBox> 或 <xref:System.Windows.Forms.CheckedListBox> 控件。  
  
2. 连接到数据源。  
  
3. 在两张表之间建立数据关系。 请参阅 [DataRelation 对象简介](/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120))。  
  
4. 设置以下属性： 以下属性可在代码或设计器中设置。  
  
    |Property|设置|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|包含有关哪个 ID 号等同于哪一项的信息的表。 在前面的方案中，这是 `ItemTable` 。|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|你想要在控件中显示的源数据表的列。 在前面的方案中，这是 `"Name"` (在代码中设置的，使用引号) 。|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|包含所存储信息的源数据表的列。 在前面的方案中，这是 `"ID"` (在代码中设置的，使用引号) 。|  
  
5. 在过程中，调用 <xref:System.Windows.Forms.ControlBindingsCollection> 类的 <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> 方法，以将控件的 <xref:System.Windows.Forms.ListControl.SelectedValue%2A> 属性绑定到记录窗体输入的表。 您也可以在设计器而不是代码中执行此操作，方法是在 <xref:System.Windows.Forms.Control.DataBindings%2A> " **属性** " 窗口中访问控件的属性。 在前面的方案中，此为 `OrderDetailsTable` ，列为 `"ItemID"` 。  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a>另请参阅

- [数据绑定和 Windows 窗体](../data-binding-and-windows-forms.md)
- [ListBox 控件概述](listbox-control-overview-windows-forms.md)
- [ComboBox 控件概述](combobox-control-overview-windows-forms.md)
- [CheckedListBox 控件概述](checkedlistbox-control-overview-windows-forms.md)
- [用于列出选项的 Windows 窗体控件](windows-forms-controls-used-to-list-options.md)
