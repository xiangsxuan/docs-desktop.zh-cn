---
title: 演练：在混合应用程序中绑定到数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: 4da9cd950564a5349cb7881c1f25d518e712fb1e
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667247"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a><span data-ttu-id="e1769-102">演练：在混合应用程序中绑定到数据</span><span class="sxs-lookup"><span data-stu-id="e1769-102">Walkthrough: Binding to Data in Hybrid Applications</span></span>

<span data-ttu-id="e1769-103">无论你使用 Windows 窗体还是，将数据源绑定到控件对于向用户提供对基础数据的访问至关重要。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1769-103">Binding a data source to a control is essential for providing users with access to underlying data, whether you are using Windows Forms or [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="e1769-104">本演练演示如何在包含 Windows 窗体和控件的混合应用程序中使用数据绑定 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="e1769-104">This walkthrough shows how you can use data binding in hybrid applications that include both Windows Forms and [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] controls.</span></span>

<span data-ttu-id="e1769-105">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="e1769-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="e1769-106">创建项目。</span><span class="sxs-lookup"><span data-stu-id="e1769-106">Creating the project.</span></span>

- <span data-ttu-id="e1769-107">定义数据模板。</span><span class="sxs-lookup"><span data-stu-id="e1769-107">Defining the data template.</span></span>

- <span data-ttu-id="e1769-108">指定窗体布局。</span><span class="sxs-lookup"><span data-stu-id="e1769-108">Specifying the form layout.</span></span>

- <span data-ttu-id="e1769-109">指定数据绑定。</span><span class="sxs-lookup"><span data-stu-id="e1769-109">Specifying data bindings.</span></span>

- <span data-ttu-id="e1769-110">使用互操作功能显示数据。</span><span class="sxs-lookup"><span data-stu-id="e1769-110">Displaying data by using interoperation.</span></span>

- <span data-ttu-id="e1769-111">向项目添加数据源。</span><span class="sxs-lookup"><span data-stu-id="e1769-111">Adding the data source to the project.</span></span>

- <span data-ttu-id="e1769-112">绑定到数据源。</span><span class="sxs-lookup"><span data-stu-id="e1769-112">Binding to the data source.</span></span>

<span data-ttu-id="e1769-113">有关本演练中所述任务的完整代码列表，请参阅 [混合应用程序中的数据绑定示例](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFWithWFAndDatabinding)。</span><span class="sxs-lookup"><span data-stu-id="e1769-113">For a complete code listing of the tasks illustrated in this walkthrough, see [Data Binding in Hybrid Applications Sample](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFWithWFAndDatabinding).</span></span>

<span data-ttu-id="e1769-114">完成本演练后，你将对混合应用程序中的数据绑定功能有所了解。</span><span class="sxs-lookup"><span data-stu-id="e1769-114">When you are finished, you will have an understanding of data binding features in hybrid applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e1769-115">先决条件</span><span class="sxs-lookup"><span data-stu-id="e1769-115">Prerequisites</span></span>

<span data-ttu-id="e1769-116">您需要满足以下条件才能完成本演练：</span><span class="sxs-lookup"><span data-stu-id="e1769-116">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="e1769-117">Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="e1769-117">Visual Studio.</span></span>

- <span data-ttu-id="e1769-118">访问 Microsoft SQL Server 上运行的 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="e1769-118">Access to the Northwind sample database running on Microsoft SQL Server.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="e1769-119">创建项目</span><span class="sxs-lookup"><span data-stu-id="e1769-119">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="e1769-120">创建并设置项目</span><span class="sxs-lookup"><span data-stu-id="e1769-120">To create and set up the project</span></span>

1. <span data-ttu-id="e1769-121">创建一个名为的 WPF 应用程序项目 `WPFWithWFAndDatabinding` 。</span><span class="sxs-lookup"><span data-stu-id="e1769-121">Create a WPF Application project named `WPFWithWFAndDatabinding`.</span></span>

2. <span data-ttu-id="e1769-122">在解决方案资源管理器中，添加对下列程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="e1769-122">In Solution Explorer, add references to the following assemblies.</span></span>

    - <span data-ttu-id="e1769-123">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="e1769-123">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="e1769-124">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="e1769-124">System.Windows.Forms</span></span>

3. <span data-ttu-id="e1769-125">在 WPF 设计器中打开 Mainwindow.xaml。</span><span class="sxs-lookup"><span data-stu-id="e1769-125">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="e1769-126">在 <xref:System.Windows.Window> 元素中，添加以下 Windows 窗体命名空间映射。</span><span class="sxs-lookup"><span data-stu-id="e1769-126">In the <xref:System.Windows.Window> element, add the following Windows Forms namespaces mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="e1769-127"><xref:System.Windows.Controls.Grid> `mainGrid` 通过分配属性来命名默认元素 <xref:System.Windows.FrameworkElement.Name%2A> 。</span><span class="sxs-lookup"><span data-stu-id="e1769-127">Name the default <xref:System.Windows.Controls.Grid> element `mainGrid` by assigning the <xref:System.Windows.FrameworkElement.Name%2A> property.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]

## <a name="defining-the-data-template"></a><span data-ttu-id="e1769-128">定义数据模板</span><span class="sxs-lookup"><span data-stu-id="e1769-128">Defining the Data Template</span></span>

<span data-ttu-id="e1769-129">客户的主列表显示在 <xref:System.Windows.Controls.ListBox> 控件中。</span><span class="sxs-lookup"><span data-stu-id="e1769-129">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="e1769-130">下面的代码示例定义一个 <xref:System.Windows.DataTemplate> 名为 `ListItemsTemplate` 的对象，该对象控制控件的可视化树 <xref:System.Windows.Controls.ListBox> 。</span><span class="sxs-lookup"><span data-stu-id="e1769-130">The following code example defines a <xref:System.Windows.DataTemplate> object named `ListItemsTemplate` that controls the visual tree of the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="e1769-131">这 <xref:System.Windows.DataTemplate> 会分配给 <xref:System.Windows.Controls.ListBox> 控件的 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="e1769-131">This <xref:System.Windows.DataTemplate> is assigned to the <xref:System.Windows.Controls.ListBox> control's <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> property.</span></span>

### <a name="to-define-the-data-template"></a><span data-ttu-id="e1769-132">定义数据模板</span><span class="sxs-lookup"><span data-stu-id="e1769-132">To define the data template</span></span>

- <span data-ttu-id="e1769-133">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素的声明中。</span><span class="sxs-lookup"><span data-stu-id="e1769-133">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]

## <a name="specifying-the-form-layout"></a><span data-ttu-id="e1769-134">指定窗体布局</span><span class="sxs-lookup"><span data-stu-id="e1769-134">Specifying the Form Layout</span></span>

<span data-ttu-id="e1769-135">窗体的布局由一个三行三列的网格来定义。</span><span class="sxs-lookup"><span data-stu-id="e1769-135">The layout of the form is defined by a grid with three rows and three columns.</span></span> <span data-ttu-id="e1769-136"><xref:System.Windows.Controls.Label> 提供了用于标识 Customers 表中每一列的控件。</span><span class="sxs-lookup"><span data-stu-id="e1769-136"><xref:System.Windows.Controls.Label> controls are provided to identify each column in the Customers table.</span></span>

### <a name="to-set-up-the-grid-layout"></a><span data-ttu-id="e1769-137">设置网格布局</span><span class="sxs-lookup"><span data-stu-id="e1769-137">To set up the Grid layout</span></span>

- <span data-ttu-id="e1769-138">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素的声明中。</span><span class="sxs-lookup"><span data-stu-id="e1769-138">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]

### <a name="to-set-up-the-label-controls"></a><span data-ttu-id="e1769-139">设置 Label 控件</span><span class="sxs-lookup"><span data-stu-id="e1769-139">To set up the Label controls</span></span>

- <span data-ttu-id="e1769-140">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素的声明中。</span><span class="sxs-lookup"><span data-stu-id="e1769-140">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]

## <a name="specifying-data-bindings"></a><span data-ttu-id="e1769-141">指定数据绑定</span><span class="sxs-lookup"><span data-stu-id="e1769-141">Specifying Data Bindings</span></span>

<span data-ttu-id="e1769-142">客户的主列表显示在 <xref:System.Windows.Controls.ListBox> 控件中。</span><span class="sxs-lookup"><span data-stu-id="e1769-142">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="e1769-143">附加的将 `ListItemsTemplate` <xref:System.Windows.Controls.TextBlock> 控件绑定到 `ContactName` 数据库中的字段。</span><span class="sxs-lookup"><span data-stu-id="e1769-143">The attached `ListItemsTemplate` binds a <xref:System.Windows.Controls.TextBlock> control to the `ContactName` field from the database.</span></span>

<span data-ttu-id="e1769-144">每个客户记录的详细信息显示在多个 <xref:System.Windows.Controls.TextBox> 控件中。</span><span class="sxs-lookup"><span data-stu-id="e1769-144">The details of each customer record are displayed in several <xref:System.Windows.Controls.TextBox> controls.</span></span>

### <a name="to-specify-data-bindings"></a><span data-ttu-id="e1769-145">指定数据绑定</span><span class="sxs-lookup"><span data-stu-id="e1769-145">To specify data bindings</span></span>

- <span data-ttu-id="e1769-146">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素的声明中。</span><span class="sxs-lookup"><span data-stu-id="e1769-146">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     <span data-ttu-id="e1769-147"><xref:System.Windows.Data.Binding>类将这些 <xref:System.Windows.Controls.TextBox> 控件绑定到数据库中的相应字段。</span><span class="sxs-lookup"><span data-stu-id="e1769-147">The <xref:System.Windows.Data.Binding> class binds the <xref:System.Windows.Controls.TextBox> controls to the appropriate fields in the database.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]

## <a name="displaying-data-by-using-interoperation"></a><span data-ttu-id="e1769-148">使用互操作功能显示数据</span><span class="sxs-lookup"><span data-stu-id="e1769-148">Displaying Data by Using Interoperation</span></span>

<span data-ttu-id="e1769-149">对应于所选客户的订单将显示在一个 <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> 名为的控件中 `dataGridView1` 。</span><span class="sxs-lookup"><span data-stu-id="e1769-149">The orders corresponding to the selected customer are displayed in a <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> control named `dataGridView1`.</span></span> <span data-ttu-id="e1769-150">`dataGridView1`控件绑定到代码隐藏文件中的数据源。</span><span class="sxs-lookup"><span data-stu-id="e1769-150">The `dataGridView1` control is bound to the data source in the code-behind file.</span></span> <span data-ttu-id="e1769-151"><xref:System.Windows.Forms.Integration.WindowsFormsHost>控件是此 Windows 窗体控件的父级。</span><span class="sxs-lookup"><span data-stu-id="e1769-151">A <xref:System.Windows.Forms.Integration.WindowsFormsHost> control is the parent of this Windows Forms control.</span></span>

### <a name="to-display-data-in-the-datagridview-control"></a><span data-ttu-id="e1769-152">在 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="e1769-152">To display data in the DataGridView control</span></span>

- <span data-ttu-id="e1769-153">将以下 XAML 复制到 <xref:System.Windows.Controls.Grid> 元素的声明中。</span><span class="sxs-lookup"><span data-stu-id="e1769-153">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]

## <a name="adding-the-data-source-to-the-project"></a><span data-ttu-id="e1769-154">向项目添加数据源</span><span class="sxs-lookup"><span data-stu-id="e1769-154">Adding the Data Source to the Project</span></span>

<span data-ttu-id="e1769-155">使用 Visual Studio，可以轻松地将数据源添加到项目。</span><span class="sxs-lookup"><span data-stu-id="e1769-155">With Visual Studio, you can easily add a data source to your project.</span></span> <span data-ttu-id="e1769-156">此过程将向项目添加强类型数据集。</span><span class="sxs-lookup"><span data-stu-id="e1769-156">This procedure adds a strongly typed data set to your project.</span></span> <span data-ttu-id="e1769-157">还添加了其他支持类，例如每个所选表适用的表适配器。</span><span class="sxs-lookup"><span data-stu-id="e1769-157">Several other support classes, such as table adapters for each of the chosen tables, are also added.</span></span>

### <a name="to-add-the-data-source"></a><span data-ttu-id="e1769-158">添加数据源</span><span class="sxs-lookup"><span data-stu-id="e1769-158">To add the data source</span></span>

1. <span data-ttu-id="e1769-159">从 " **数据** " 菜单中，选择 " **添加新数据源**"。</span><span class="sxs-lookup"><span data-stu-id="e1769-159">From the **Data** menu, select **Add New Data Source**.</span></span>

2. <span data-ttu-id="e1769-160">在 " **数据源配置向导**" 中，使用数据集创建到 Northwind 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="e1769-160">In the **Data Source Configuration Wizard**, create a connection to the Northwind database by using a dataset.</span></span> <span data-ttu-id="e1769-161">有关详细信息，请参阅 [How to: Connect to Data in a Database](/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="e1769-161">For more information, see [How to: Connect to Data in a Database](/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).</span></span>

3. <span data-ttu-id="e1769-162">当您通过 " **数据源配置向导**" 提示您时，请将连接字符串保存为 `NorthwindConnectionString` 。</span><span class="sxs-lookup"><span data-stu-id="e1769-162">When you are prompted by the **Data Source Configuration Wizard**, save the connection string as `NorthwindConnectionString`.</span></span>

4. <span data-ttu-id="e1769-163">当系统提示您选择数据库对象时，选择 `Customers` 和 `Orders` 表，并将生成的数据集命名为 `NorthwindDataSet` 。</span><span class="sxs-lookup"><span data-stu-id="e1769-163">When you are prompted to choose your database objects, select the `Customers` and `Orders` tables, and name the generated data set `NorthwindDataSet`.</span></span>

## <a name="binding-to-the-data-source"></a><span data-ttu-id="e1769-164">绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="e1769-164">Binding to the Data Source</span></span>

<span data-ttu-id="e1769-165"><xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>组件提供应用程序数据源的统一接口。</span><span class="sxs-lookup"><span data-stu-id="e1769-165">The <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> component provides a uniform interface for the application's data source.</span></span> <span data-ttu-id="e1769-166">绑定到数据源是在代码隐藏文件中实现的。</span><span class="sxs-lookup"><span data-stu-id="e1769-166">Binding to the data source is implemented in the code-behind file.</span></span>

### <a name="to-bind-to-the-data-source"></a><span data-ttu-id="e1769-167">绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="e1769-167">To bind to the data source</span></span>

1. <span data-ttu-id="e1769-168">打开名为 MainWindow.xaml.vb 或 MainWindow.xaml.cs 的代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="e1769-168">Open the code-behind file, which is named MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span>

2. <span data-ttu-id="e1769-169">将以下代码复制到 `MainWindow` 类定义中。</span><span class="sxs-lookup"><span data-stu-id="e1769-169">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="e1769-170">此代码声明 <xref:System.Windows.Forms.BindingSource> 连接到数据库的组件和关联的帮助器类。</span><span class="sxs-lookup"><span data-stu-id="e1769-170">This code declares the <xref:System.Windows.Forms.BindingSource> component and associated helper classes that connect to the database.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. <span data-ttu-id="e1769-171">将以下代码复制到构造函数中。</span><span class="sxs-lookup"><span data-stu-id="e1769-171">Copy the following code into the constructor.</span></span>

     <span data-ttu-id="e1769-172">此代码将创建并初始化该 <xref:System.Windows.Forms.BindingSource> 组件。</span><span class="sxs-lookup"><span data-stu-id="e1769-172">This code creates and initializes the <xref:System.Windows.Forms.BindingSource> component.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. <span data-ttu-id="e1769-173">打开 MainWindow.xaml。</span><span class="sxs-lookup"><span data-stu-id="e1769-173">Open MainWindow.xaml.</span></span>

5. <span data-ttu-id="e1769-174">在设计视图或 XAML 视图中，选择 <xref:System.Windows.Window> 元素。</span><span class="sxs-lookup"><span data-stu-id="e1769-174">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="e1769-175">在属性窗口中，单击 " **事件** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e1769-175">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="e1769-176">双击该 <xref:System.Windows.FrameworkElement.Loaded> 事件。</span><span class="sxs-lookup"><span data-stu-id="e1769-176">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="e1769-177">将以下代码复制到 <xref:System.Windows.FrameworkElement.Loaded> 事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="e1769-177">Copy the following code into the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

     <span data-ttu-id="e1769-178">此代码会将 <xref:System.Windows.Forms.BindingSource> 组件分配为数据上下文，并填充 `Customers` 和 `Orders` 适配器对象。</span><span class="sxs-lookup"><span data-stu-id="e1769-178">This code assigns the <xref:System.Windows.Forms.BindingSource> component as the data context and populates the `Customers` and `Orders` adapter objects.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. <span data-ttu-id="e1769-179">将以下代码复制到 `MainWindow` 类定义中。</span><span class="sxs-lookup"><span data-stu-id="e1769-179">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="e1769-180">此方法处理 <xref:System.Windows.Data.CollectionView.CurrentChanged> 事件并更新数据绑定的当前项。</span><span class="sxs-lookup"><span data-stu-id="e1769-180">This method handles the <xref:System.Windows.Data.CollectionView.CurrentChanged> event and updates the current item of the data binding.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]

10. <span data-ttu-id="e1769-181">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="e1769-181">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1769-182">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1769-182">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="e1769-183">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="e1769-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="e1769-184">混合应用程序中的数据绑定示例</span><span class="sxs-lookup"><span data-stu-id="e1769-184">Data Binding in Hybrid Applications Sample</span></span>](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFWithWFAndDatabinding)
- [<span data-ttu-id="e1769-185">演练：在 WPF 中托管 Windows 窗体复合控件</span><span class="sxs-lookup"><span data-stu-id="e1769-185">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="e1769-186">演练：在 Windows 窗体中承载 WPF 复合控件</span><span class="sxs-lookup"><span data-stu-id="e1769-186">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
