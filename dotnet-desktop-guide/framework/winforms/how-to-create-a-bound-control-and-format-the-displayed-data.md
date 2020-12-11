---
title: 如何：创建绑定控件并设置显示数据的格式
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: e1448e0dcb80a7ac7ab0199b14957bddec27c133
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970266"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="b3a30-102">如何：创建绑定控件并设置显示数据的格式</span><span class="sxs-lookup"><span data-stu-id="b3a30-102">How to: Create a Bound Control and Format the Displayed Data</span></span>

<span data-ttu-id="b3a30-103">使用 Windows 窗体数据绑定，可以通过使用 " **格式设置和高级绑定** " 对话框来设置数据绑定控件中显示的数据的格式。</span><span class="sxs-lookup"><span data-stu-id="b3a30-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>

## <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="b3a30-104">绑定控件并设置显示的数据的格式</span><span class="sxs-lookup"><span data-stu-id="b3a30-104">To bind a control and format the displayed data</span></span>

1. <span data-ttu-id="b3a30-105">连接到数据源。</span><span class="sxs-lookup"><span data-stu-id="b3a30-105">Connect to a data source.</span></span> <span data-ttu-id="b3a30-106">有关详细信息，请参阅 [连接到数据源](/dotnet/framework/data/adonet/connecting-to-a-data-source)。</span><span class="sxs-lookup"><span data-stu-id="b3a30-106">For more information, see [Connecting to a Data Source](/dotnet/framework/data/adonet/connecting-to-a-data-source).</span></span>

2. <span data-ttu-id="b3a30-107">在 Visual Studio 中，选择窗体上的控件，然后打开 " **属性** " 窗口。</span><span class="sxs-lookup"><span data-stu-id="b3a30-107">In Visual Studio, select the control on the form, and then open the **Properties** window.</span></span>

3. <span data-ttu-id="b3a30-108">展开 " **(** databinding") 属性，然后在 " **(高级)** " 框中，单击 "Visual Studio ( ( 中省略号按钮 ) 省略号按钮属性窗口"， ![ ](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png) 以显示 " **格式设置和高级绑定** " 对话框，该对话框具有该控件的完整属性列表。</span><span class="sxs-lookup"><span data-stu-id="b3a30-108">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>

4. <span data-ttu-id="b3a30-109">选择要绑定的属性，然后选择 " **绑定** " 箭头。</span><span class="sxs-lookup"><span data-stu-id="b3a30-109">Select the property you want to bind, and then select the **Binding** arrow.</span></span>

     <span data-ttu-id="b3a30-110">此时将显示可用数据源的列表。</span><span class="sxs-lookup"><span data-stu-id="b3a30-110">A list of available data sources is displayed.</span></span>

5. <span data-ttu-id="b3a30-111">展开要绑定到的数据源，直到找到所需的单个数据元素。</span><span class="sxs-lookup"><span data-stu-id="b3a30-111">Expand the data source you want to bind to until you find the single data element you want.</span></span>

     <span data-ttu-id="b3a30-112">例如，如果你正在绑定到数据集表中的列值，请展开该数据集的名称，然后展开表名以显示列名。</span><span class="sxs-lookup"><span data-stu-id="b3a30-112">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

6. <span data-ttu-id="b3a30-113">选择要绑定到的元素的名称。</span><span class="sxs-lookup"><span data-stu-id="b3a30-113">Select the name of an element to bind to.</span></span>

7. <span data-ttu-id="b3a30-114">在 " **格式类型** " 框中，选择要应用于控件中显示的数据的格式。</span><span class="sxs-lookup"><span data-stu-id="b3a30-114">In the **Format type** box, select the format you want to apply to the data displayed in the control.</span></span>

     <span data-ttu-id="b3a30-115">在任何情况下，如果数据源包含 <xref:System.DBNull>，都可以指定控件中显示的值。</span><span class="sxs-lookup"><span data-stu-id="b3a30-115">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="b3a30-116">否则，选项会略有不同，具体取决于你选择的格式类型。</span><span class="sxs-lookup"><span data-stu-id="b3a30-116">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="b3a30-117">下表显示了格式类型和选项。</span><span class="sxs-lookup"><span data-stu-id="b3a30-117">The following table shows the format types and options.</span></span>

    |<span data-ttu-id="b3a30-118">格式类型</span><span class="sxs-lookup"><span data-stu-id="b3a30-118">Format type</span></span>|<span data-ttu-id="b3a30-119">格式选项</span><span class="sxs-lookup"><span data-stu-id="b3a30-119">Formatting option</span></span>|
    |-----------------|-----------------------|
    |<span data-ttu-id="b3a30-120">无格式</span><span class="sxs-lookup"><span data-stu-id="b3a30-120">No Formatting</span></span>|<span data-ttu-id="b3a30-121">无选项。</span><span class="sxs-lookup"><span data-stu-id="b3a30-121">No options.</span></span>|
    |<span data-ttu-id="b3a30-122">Numeric</span><span class="sxs-lookup"><span data-stu-id="b3a30-122">Numeric</span></span>|<span data-ttu-id="b3a30-123">使用 " **小数位数** " up-down 控件指定小数位数。</span><span class="sxs-lookup"><span data-stu-id="b3a30-123">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="b3a30-124">货币</span><span class="sxs-lookup"><span data-stu-id="b3a30-124">Currency</span></span>|<span data-ttu-id="b3a30-125">使用 " **小数位数** " up-down 控件指定小数位数。</span><span class="sxs-lookup"><span data-stu-id="b3a30-125">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="b3a30-126">DateTime</span><span class="sxs-lookup"><span data-stu-id="b3a30-126">Date Time</span></span>|<span data-ttu-id="b3a30-127">通过选择 " **类型** 选择" 框中的一个项来选择显示日期和时间的方式。</span><span class="sxs-lookup"><span data-stu-id="b3a30-127">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|
    |<span data-ttu-id="b3a30-128">科学记数</span><span class="sxs-lookup"><span data-stu-id="b3a30-128">Scientific</span></span>|<span data-ttu-id="b3a30-129">使用 " **小数位数** " up-down 控件指定小数位数。</span><span class="sxs-lookup"><span data-stu-id="b3a30-129">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="b3a30-130">自定义</span><span class="sxs-lookup"><span data-stu-id="b3a30-130">Custom</span></span>|<span data-ttu-id="b3a30-131">指定一个自定义格式字符串用法。</span><span class="sxs-lookup"><span data-stu-id="b3a30-131">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="b3a30-132">有关详细信息，请参阅[类型格式设置](/dotnet/standard/base-types/formatting-types)。</span><span class="sxs-lookup"><span data-stu-id="b3a30-132">For more information, see [Formatting Types](/dotnet/standard/base-types/formatting-types).</span></span> <span data-ttu-id="b3a30-133">**注意：**  不保证自定义格式字符串在数据源和绑定控件之间成功往返。</span><span class="sxs-lookup"><span data-stu-id="b3a30-133">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="b3a30-134">请改为处理该绑定的 <xref:System.Windows.Forms.Binding.Parse> 或 <xref:System.Windows.Forms.Binding.Format> 事件，并在事件处理代码中应用自定义格式设置。</span><span class="sxs-lookup"><span data-stu-id="b3a30-134">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|

8. <span data-ttu-id="b3a30-135">选择 **"确定"** 以关闭 " **格式设置和高级绑定** " 对话框并返回到属性窗口。</span><span class="sxs-lookup"><span data-stu-id="b3a30-135">Select **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3a30-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3a30-136">See also</span></span>

- [<span data-ttu-id="b3a30-137">如何：在 Windows 窗体上创建简单绑定控件</span><span class="sxs-lookup"><span data-stu-id="b3a30-137">How to: Create a Simple-Bound Control on a Windows Form</span></span>](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [<span data-ttu-id="b3a30-138">Windows 窗体中的用户输入验证</span><span class="sxs-lookup"><span data-stu-id="b3a30-138">User Input Validation in Windows Forms</span></span>](user-input-validation-in-windows-forms.md)
- [<span data-ttu-id="b3a30-139">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="b3a30-139">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
