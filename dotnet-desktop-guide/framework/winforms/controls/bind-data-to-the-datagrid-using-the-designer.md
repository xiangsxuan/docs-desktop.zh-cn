---
title: 使用设计器将数据绑定到 DataGridView 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
ms.openlocfilehash: 6a8ffdbf950eb0fcda7b4752e6e9dd73a6df3f6f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970719"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="7e6a8-102">如何：使用设计器将数据绑定到 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="7e6a8-102">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="7e6a8-103">您可以使用设计器将控件连接 <xref:System.Windows.Forms.DataGridView> 到多种不同种类（包括数据库、业务对象或 Web 服务）的数据源。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-103">You can use the designer to connect a <xref:System.Windows.Forms.DataGridView> control to data sources of several different varieties, including databases, business objects, or Web services.</span></span> <span data-ttu-id="7e6a8-104">使用设计器将控件绑定到数据源时，控件将自动绑定到 <xref:System.Windows.Forms.BindingSource> 表示数据源的组件。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-104">When you bind the control to a data source using the designer, the control is automatically bound to a <xref:System.Windows.Forms.BindingSource> component that represents the data source.</span></span> <span data-ttu-id="7e6a8-105">此外，会在控件中自动生成列以匹配数据源提供的架构信息。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-105">Additionally, columns are automatically generated in the control to match the schema information provided by the data source.</span></span>

 <span data-ttu-id="7e6a8-106">生成列后，可根据需要对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-106">After columns have been generated, you can modify them to meet your needs.</span></span> <span data-ttu-id="7e6a8-107">例如，可删除或隐藏不不想显示的列、重新排列各列或修改列的类型。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-107">For example, you can remove or hide columns you are not interested in displaying, you can rearrange the columns, or you can modify the column types.</span></span> <span data-ttu-id="7e6a8-108">有关修改列的详细信息，请参阅“另请参阅”部分中列出的主题。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-108">For more information about modifying columns, see the topics listed in the See Also section.</span></span>

 <span data-ttu-id="7e6a8-109">您还可以将多个 <xref:System.Windows.Forms.DataGridView> 控件绑定到相关表，以创建主/从关系。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-109">You can also bind multiple <xref:System.Windows.Forms.DataGridView> controls to related tables to create master/detail relationships.</span></span> <span data-ttu-id="7e6a8-110">在此配置中，一个控件显示父表，另一个控件只显示子表中与父表中的当前行相关的行。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-110">In this configuration, one control displays a parent table and another control displays only those rows from a child table that are related to the current row in the parent table.</span></span> <span data-ttu-id="7e6a8-111">有关详细信息，请参阅[如何：在 Windows 窗体应用程序中显示相关数据](/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-111">For more information, see [How to: Display Related Data in a Windows Forms Application](/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120)).</span></span>

 <span data-ttu-id="7e6a8-112">下面的过程需要一个 **Windows 应用程序** 项目，该项目具有一个窗体，其中包含一个 <xref:System.Windows.Forms.DataGridView> 用于主/从关系的控件或两个控件。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-112">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.DataGridView> control or two controls for a master/detail relationship.</span></span> <span data-ttu-id="7e6a8-113">有关启动此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-113">For information about starting such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-bind-the-control-to-a-data-source"></a><span data-ttu-id="7e6a8-114">将控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="7e6a8-114">To bind the control to a data source</span></span>

1. <span data-ttu-id="7e6a8-115">单击 ![ ](./media/designer-actions-glyph.gif) 控件右上角) 的 "设计器操作" 标志符号 (小黑色箭头 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-115">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control.</span></span>

2. <span data-ttu-id="7e6a8-116">单击“选择数据源”选项的下拉箭头。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-116">Click the drop-down arrow for the **Choose Data Source** option.</span></span>

3. <span data-ttu-id="7e6a8-117">如果项目尚没有数据源，请单击“添加项目数据源”，按照向导指示的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-117">If your project does not already have a data source, click **Add Project Data Source** and follow the steps indicated by the wizard.</span></span>

     <span data-ttu-id="7e6a8-118">有关详细信息，请参阅[数据源配置向导](/previous-versions/visualstudio/visual-studio-2013/w4dd7z6t(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-118">For more information, see [Data Source Configuration Wizard](/previous-versions/visualstudio/visual-studio-2013/w4dd7z6t(v=vs.120)).</span></span> <span data-ttu-id="7e6a8-119">新数据源将显示在“选择数据源”下拉窗口中。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-119">Your new data source will appear in the **Choose Data Source** drop-down window.</span></span> <span data-ttu-id="7e6a8-120">如果新数据源只包含一个成员（例如单个数据库表），控件将自动绑定到该成员。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-120">If your new data source contains only one member, such as a single database table, the control will automatically bind to that member.</span></span> <span data-ttu-id="7e6a8-121">否则，继续执行下一步。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-121">Otherwise, continue to the next step.</span></span>

4. <span data-ttu-id="7e6a8-122">如果尚未展开，则展开“其他数据源”和“项目数据源”节点，然后选择绑定控件的数据源。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-122">Expand the **Other Data Sources** and **Project Data Sources** nodes if they are not already expanded, and then select the data source to bind the control to.</span></span>

5. <span data-ttu-id="7e6a8-123">如果您的数据源包含多个成员（例如，如果您创建了一个 <xref:System.Data.DataSet?displayProperty=nameWithType> 包含多个表的），则展开该数据源，然后选择要绑定到的特定成员。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-123">If your data source contains more than one member, such as if you have created a <xref:System.Data.DataSet?displayProperty=nameWithType> that contains multiple tables, expand the data source, and then select the specific member to bind to.</span></span>

6. <span data-ttu-id="7e6a8-124">若要创建主/从关系，请在另一个控件的 " **选择数据源** " 下拉窗口中 <xref:System.Windows.Forms.DataGridView> ，展开 <xref:System.Windows.Forms.BindingSource> 为父表创建的，然后从显示的列表中选择相关的子表。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-124">To create a master/detail relationship, in the **Choose Data Source** drop-down window for a second <xref:System.Windows.Forms.DataGridView> control, expand the <xref:System.Windows.Forms.BindingSource> created for the parent table, and then select the related child table from the list shown.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7e6a8-125">如果项目已有数据源，还可以使用“数据源”窗口创建数据窗体。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-125">If your project already has a data source, you can also use the **Data Sources** window to create a data form.</span></span> <span data-ttu-id="7e6a8-126">有关详细信息，请参阅[数据源窗口](/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="7e6a8-126">For more information, see [Data Sources Window](/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120)).</span></span>

## <a name="see-also"></a><span data-ttu-id="7e6a8-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e6a8-127">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <span data-ttu-id="7e6a8-128">[如何：连接到数据库中的数据](/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="7e6a8-128">[How to: Connect to Data in a Database](/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))</span></span>
- [<span data-ttu-id="7e6a8-129">如何：使用设计器添加和移除 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="7e6a8-129">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="7e6a8-130">如何：使用设计器更改 Windows 窗体 DataGridView 控件中列的顺序</span><span class="sxs-lookup"><span data-stu-id="7e6a8-130">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="7e6a8-131">如何：使用设计器更改 Windows 窗体 DataGridView 列类型</span><span class="sxs-lookup"><span data-stu-id="7e6a8-131">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)
- [<span data-ttu-id="7e6a8-132">如何：使用设计器冻结 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="7e6a8-132">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="7e6a8-133">如何：使用设计器隐藏 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="7e6a8-133">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](hide-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="7e6a8-134">如何：使用设计器将 Windows 窗体 DataGridView 控件中的列设为只读</span><span class="sxs-lookup"><span data-stu-id="7e6a8-134">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](make-columns-read-only-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="7e6a8-135">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="7e6a8-135">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="7e6a8-136">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="7e6a8-136">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- <span data-ttu-id="7e6a8-137">[“数据源”窗口](/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="7e6a8-137">[Data Sources Window](/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span></span>
- <span data-ttu-id="7e6a8-138">[如何：在 Windows 窗体应用程序中显示相关数据](/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="7e6a8-138">[How to: Display Related Data in a Windows Forms Application](/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))</span></span>
