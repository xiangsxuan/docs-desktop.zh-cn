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
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="892e6-102">如何：为 Windows 窗体 ComboBox 控件、ListBox 控件或 CheckedListBox 控件创建查找表</span><span class="sxs-lookup"><span data-stu-id="892e6-102">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>

<span data-ttu-id="892e6-103">有时，在 Windows 窗体上以用户友好格式显示数据，但存储数据时使用对程序而言更有意义的格式会很有帮助。</span><span class="sxs-lookup"><span data-stu-id="892e6-103">Sometimes it is useful to display data in a user-friendly format on a Windows Form, but store the data in a format that is more meaningful to your program.</span></span> <span data-ttu-id="892e6-104">例如，食品订单窗体可能按列表框中的名称显示菜单项。</span><span class="sxs-lookup"><span data-stu-id="892e6-104">For example, an order form for food might display the menu items by name in a list box.</span></span> <span data-ttu-id="892e6-105">但是，记录订单的数据表将包含代表该食品的唯一 ID 号。</span><span class="sxs-lookup"><span data-stu-id="892e6-105">However, the data table recording the order would contain the unique ID numbers representing the food.</span></span> <span data-ttu-id="892e6-106">下表显示如何存储和显示食品订单窗体数据的示例。</span><span class="sxs-lookup"><span data-stu-id="892e6-106">The following tables show an example of how to store and display order-form data for food.</span></span>  
  
### <a name="orderdetailstable"></a><span data-ttu-id="892e6-107">OrderDetailsTable</span><span class="sxs-lookup"><span data-stu-id="892e6-107">OrderDetailsTable</span></span>  
  
|<span data-ttu-id="892e6-108">OrderID</span><span class="sxs-lookup"><span data-stu-id="892e6-108">OrderID</span></span>|<span data-ttu-id="892e6-109">ItemID</span><span class="sxs-lookup"><span data-stu-id="892e6-109">ItemID</span></span>|<span data-ttu-id="892e6-110">数量</span><span class="sxs-lookup"><span data-stu-id="892e6-110">Quantity</span></span>|  
|-------------|------------|--------------|  
|<span data-ttu-id="892e6-111">4085</span><span class="sxs-lookup"><span data-stu-id="892e6-111">4085</span></span>|<span data-ttu-id="892e6-112">12</span><span class="sxs-lookup"><span data-stu-id="892e6-112">12</span></span>|<span data-ttu-id="892e6-113">1</span><span class="sxs-lookup"><span data-stu-id="892e6-113">1</span></span>|  
|<span data-ttu-id="892e6-114">4086</span><span class="sxs-lookup"><span data-stu-id="892e6-114">4086</span></span>|<span data-ttu-id="892e6-115">13</span><span class="sxs-lookup"><span data-stu-id="892e6-115">13</span></span>|<span data-ttu-id="892e6-116">3</span><span class="sxs-lookup"><span data-stu-id="892e6-116">3</span></span>|  
  
### <a name="itemtable"></a><span data-ttu-id="892e6-117">ItemTable</span><span class="sxs-lookup"><span data-stu-id="892e6-117">ItemTable</span></span>  
  
|<span data-ttu-id="892e6-118">ID</span><span class="sxs-lookup"><span data-stu-id="892e6-118">ID</span></span>|<span data-ttu-id="892e6-119">名称</span><span class="sxs-lookup"><span data-stu-id="892e6-119">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="892e6-120">12</span><span class="sxs-lookup"><span data-stu-id="892e6-120">12</span></span>|<span data-ttu-id="892e6-121">Potato</span><span class="sxs-lookup"><span data-stu-id="892e6-121">Potato</span></span>|  
|<span data-ttu-id="892e6-122">13</span><span class="sxs-lookup"><span data-stu-id="892e6-122">13</span></span>|<span data-ttu-id="892e6-123">Chicken</span><span class="sxs-lookup"><span data-stu-id="892e6-123">Chicken</span></span>|  
  
 <span data-ttu-id="892e6-124">在这种情况下，一个表 **OrderDetailsTable** 将存储你所关心的有关显示和保存的实际信息。</span><span class="sxs-lookup"><span data-stu-id="892e6-124">In this scenario, one table, **OrderDetailsTable**, stores the actual information you are concerned with displaying and saving.</span></span> <span data-ttu-id="892e6-125">但为了节省空间，它采用一种很隐秘的方式。</span><span class="sxs-lookup"><span data-stu-id="892e6-125">But to save space, it does so in a fairly cryptic fashion.</span></span> <span data-ttu-id="892e6-126">另一个表 **ItemTable** 仅包含与外观相关的信息，该信息有关哪个 ID 号等效于哪个食物名称，以及与实际食物订单无关的信息。</span><span class="sxs-lookup"><span data-stu-id="892e6-126">The other table, **ItemTable**, contains only appearance-related information about which ID number is equivalent to which food name, and nothing about the actual food orders.</span></span>  
  
 <span data-ttu-id="892e6-127">**ItemTable** <xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.ListBox> 通过三个属性连接到、或 <xref:System.Windows.Forms.CheckedListBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="892e6-127">The **ItemTable** is connected to the <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control through three properties.</span></span> <span data-ttu-id="892e6-128">`DataSource`属性包含此表的名称。</span><span class="sxs-lookup"><span data-stu-id="892e6-128">The `DataSource` property contains the name of this table.</span></span> <span data-ttu-id="892e6-129">`DisplayMember`属性包含要显示在控件中的表的数据列 (食物名称) 。</span><span class="sxs-lookup"><span data-stu-id="892e6-129">The `DisplayMember` property contains the data column of that table that you want to display in the control (the food name).</span></span> <span data-ttu-id="892e6-130">`ValueMember`属性包含该表中的数据列，其中存储的信息 (ID 号) 。</span><span class="sxs-lookup"><span data-stu-id="892e6-130">The `ValueMember` property contains the data column of that table with the stored information (the ID number).</span></span>  
  
 <span data-ttu-id="892e6-131">**OrderDetailsTable** 由其绑定集合连接到控件，并通过属性进行访问 <xref:System.Windows.Forms.Control.DataBindings%2A> 。</span><span class="sxs-lookup"><span data-stu-id="892e6-131">The **OrderDetailsTable** is connected to the control by its bindings collection, accessed through the <xref:System.Windows.Forms.Control.DataBindings%2A> property.</span></span> <span data-ttu-id="892e6-132">向集合中添加绑定对象时，会将控件属性连接到特定的数据成员， ( (**OrderDetailsTable**) 的数据源中) 的 ID 号列。</span><span class="sxs-lookup"><span data-stu-id="892e6-132">When you add a binding object to the collection, you connect a control property to a specific data member (the column of ID numbers) in a data source (the **OrderDetailsTable**).</span></span> <span data-ttu-id="892e6-133">在控件中进行选择时，窗体输入将保存到此表。</span><span class="sxs-lookup"><span data-stu-id="892e6-133">When a selection is made in the control, this table is where the form input is saved.</span></span>  
  
### <a name="to-create-a-lookup-table"></a><span data-ttu-id="892e6-134">创建查找表的步骤</span><span class="sxs-lookup"><span data-stu-id="892e6-134">To create a lookup table</span></span>  
  
1. <span data-ttu-id="892e6-135">向窗体添加 <xref:System.Windows.Forms.ComboBox><xref:System.Windows.Forms.ListBox> 或 <xref:System.Windows.Forms.CheckedListBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="892e6-135">Add a <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control to the form.</span></span>  
  
2. <span data-ttu-id="892e6-136">连接到数据源。</span><span class="sxs-lookup"><span data-stu-id="892e6-136">Connect to your data source.</span></span>  
  
3. <span data-ttu-id="892e6-137">在两张表之间建立数据关系。</span><span class="sxs-lookup"><span data-stu-id="892e6-137">Establish a data relation between the two tables.</span></span> <span data-ttu-id="892e6-138">请参阅 [DataRelation 对象简介](/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="892e6-138">See [Introduction to DataRelation Objects](/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).</span></span>  
  
4. <span data-ttu-id="892e6-139">设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="892e6-139">Set the following properties.</span></span> <span data-ttu-id="892e6-140">以下属性可在代码或设计器中设置。</span><span class="sxs-lookup"><span data-stu-id="892e6-140">They can be set in code or in the designer.</span></span>  
  
    |<span data-ttu-id="892e6-141">Property</span><span class="sxs-lookup"><span data-stu-id="892e6-141">Property</span></span>|<span data-ttu-id="892e6-142">设置</span><span class="sxs-lookup"><span data-stu-id="892e6-142">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|<span data-ttu-id="892e6-143">包含有关哪个 ID 号等同于哪一项的信息的表。</span><span class="sxs-lookup"><span data-stu-id="892e6-143">The table that contains information about which ID number is equivalent to which item.</span></span> <span data-ttu-id="892e6-144">在前面的方案中，这是 `ItemTable` 。</span><span class="sxs-lookup"><span data-stu-id="892e6-144">In the previous scenario, this is `ItemTable`.</span></span>|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|<span data-ttu-id="892e6-145">你想要在控件中显示的源数据表的列。</span><span class="sxs-lookup"><span data-stu-id="892e6-145">The column of the data source table that you want to display in the control.</span></span> <span data-ttu-id="892e6-146">在前面的方案中，这是 `"Name"` (在代码中设置的，使用引号) 。</span><span class="sxs-lookup"><span data-stu-id="892e6-146">In the previous scenario, this is `"Name"` (to set in code, use quotation marks).</span></span>|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|<span data-ttu-id="892e6-147">包含所存储信息的源数据表的列。</span><span class="sxs-lookup"><span data-stu-id="892e6-147">The column of the data source table that contains the stored information.</span></span> <span data-ttu-id="892e6-148">在前面的方案中，这是 `"ID"` (在代码中设置的，使用引号) 。</span><span class="sxs-lookup"><span data-stu-id="892e6-148">In the previous scenario, this is `"ID"` (to set in code, use quotation marks).</span></span>|  
  
5. <span data-ttu-id="892e6-149">在过程中，调用 <xref:System.Windows.Forms.ControlBindingsCollection> 类的 <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> 方法，以将控件的 <xref:System.Windows.Forms.ListControl.SelectedValue%2A> 属性绑定到记录窗体输入的表。</span><span class="sxs-lookup"><span data-stu-id="892e6-149">In a procedure, call the <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> method of the <xref:System.Windows.Forms.ControlBindingsCollection> class to bind the control's <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property to the table recording the form input.</span></span> <span data-ttu-id="892e6-150">您也可以在设计器而不是代码中执行此操作，方法是在 <xref:System.Windows.Forms.Control.DataBindings%2A> " **属性** " 窗口中访问控件的属性。</span><span class="sxs-lookup"><span data-stu-id="892e6-150">You can also do this in the Designer instead of in code, by accessing the control's <xref:System.Windows.Forms.Control.DataBindings%2A> property in the **Properties** window.</span></span> <span data-ttu-id="892e6-151">在前面的方案中，此为 `OrderDetailsTable` ，列为 `"ItemID"` 。</span><span class="sxs-lookup"><span data-stu-id="892e6-151">In the previous scenario, this is `OrderDetailsTable`, and the column is `"ItemID"`.</span></span>  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="892e6-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="892e6-152">See also</span></span>

- [<span data-ttu-id="892e6-153">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="892e6-153">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="892e6-154">ListBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="892e6-154">ListBox Control Overview</span></span>](listbox-control-overview-windows-forms.md)
- [<span data-ttu-id="892e6-155">ComboBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="892e6-155">ComboBox Control Overview</span></span>](combobox-control-overview-windows-forms.md)
- [<span data-ttu-id="892e6-156">CheckedListBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="892e6-156">CheckedListBox Control Overview</span></span>](checkedlistbox-control-overview-windows-forms.md)
- [<span data-ttu-id="892e6-157">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="892e6-157">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
