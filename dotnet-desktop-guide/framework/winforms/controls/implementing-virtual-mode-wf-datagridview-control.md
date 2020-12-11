---
title: 演练：在 DataGridView 控件中实现虚拟模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 5db97b321238bc371c94e627a387bd83ca31b58a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972630"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="a2144-102">演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式</span><span class="sxs-lookup"><span data-stu-id="a2144-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a2144-103">如果要在控件中显示大量的表格数据 <xref:System.Windows.Forms.DataGridView> ，可以将 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 属性设置为， `true` 并显式管理控件与其数据存储区的交互。</span><span class="sxs-lookup"><span data-stu-id="a2144-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="a2144-104">这使您能够在这种情况下微调控件的性能。</span><span class="sxs-lookup"><span data-stu-id="a2144-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="a2144-105"><xref:System.Windows.Forms.DataGridView>控件提供若干事件，您可以处理这些事件以与自定义数据存储进行交互。</span><span class="sxs-lookup"><span data-stu-id="a2144-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="a2144-106">本演练将指导您完成实现这些事件处理程序的过程。</span><span class="sxs-lookup"><span data-stu-id="a2144-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="a2144-107">出于说明目的，本主题中的代码示例使用非常简单的数据源。</span><span class="sxs-lookup"><span data-stu-id="a2144-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="a2144-108">在生产设置中，通常只加载需要显示到缓存中的行，并处理 <xref:System.Windows.Forms.DataGridView> 事件以与缓存交互并更新缓存。</span><span class="sxs-lookup"><span data-stu-id="a2144-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="a2144-109">有关详细信息，请参阅 [在 Windows 窗体 DataGridView 控件中实现包含实时数据加载的虚拟模式](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span><span class="sxs-lookup"><span data-stu-id="a2144-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="a2144-110">若要将本主题中的代码复制为单个列表，请参阅 [如何：在 Windows 窗体 DataGridView 控件中实现虚拟模式](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="a2144-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="a2144-111">创建窗体</span><span class="sxs-lookup"><span data-stu-id="a2144-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="a2144-112">实现虚拟模式</span><span class="sxs-lookup"><span data-stu-id="a2144-112">To implement virtual mode</span></span>  
  
1. <span data-ttu-id="a2144-113">创建一个派生自的类 <xref:System.Windows.Forms.Form> ，并包含一个 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="a2144-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="a2144-114">下面的代码包含一些基本的初始化。</span><span class="sxs-lookup"><span data-stu-id="a2144-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="a2144-115">它声明将在后面的步骤中使用的一些变量，提供 `Main` 方法，并在类构造函数中提供简单的窗体布局。</span><span class="sxs-lookup"><span data-stu-id="a2144-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. <span data-ttu-id="a2144-116">实现窗体事件的处理程序 <xref:System.Windows.Forms.Form.Load> ，该处理程序初始化 <xref:System.Windows.Forms.DataGridView> 控件并使用示例值填充数据存储区。</span><span class="sxs-lookup"><span data-stu-id="a2144-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. <span data-ttu-id="a2144-117">实现事件的处理程序 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> ，该事件从数据存储区或当前正在编辑的对象中检索请求的单元格值 `Customer` 。</span><span class="sxs-lookup"><span data-stu-id="a2144-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="a2144-118">此事件在 <xref:System.Windows.Forms.DataGridView> 控件需要绘制单元格时发生。</span><span class="sxs-lookup"><span data-stu-id="a2144-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. <span data-ttu-id="a2144-119">实现事件的处理程序 <xref:System.Windows.Forms.DataGridView.CellValuePushed> ，该事件在 `Customer` 表示所编辑的行的对象中存储已编辑的单元值。</span><span class="sxs-lookup"><span data-stu-id="a2144-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="a2144-120">当用户提交单元值更改时，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="a2144-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. <span data-ttu-id="a2144-121">实现事件的处理程序 <xref:System.Windows.Forms.DataGridView.NewRowNeeded> ，该事件创建 `Customer` 表示新创建的行的新对象。</span><span class="sxs-lookup"><span data-stu-id="a2144-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="a2144-122">此事件在用户进入新记录行时出现。</span><span class="sxs-lookup"><span data-stu-id="a2144-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. <span data-ttu-id="a2144-123">实现事件的处理程序 <xref:System.Windows.Forms.DataGridView.RowValidated> ，该事件将新行或修改过的行保存到数据存储区。</span><span class="sxs-lookup"><span data-stu-id="a2144-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="a2144-124">当用户更改当前行时，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="a2144-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. <span data-ttu-id="a2144-125">实现事件的处理程序 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> ，该事件指示 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> 当用户通过在编辑模式中按 ESC 两次或在编辑模式之外时，是否会发出事件。</span><span class="sxs-lookup"><span data-stu-id="a2144-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="a2144-126">默认情况下， <xref:System.Windows.Forms.DataGridView.CancelRowEdit> 当修改了当前行中的任何单元格时，除非在 <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> `true` <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 事件处理程序中将属性设置为，否则将在行重新确定时出现。</span><span class="sxs-lookup"><span data-stu-id="a2144-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="a2144-127">在运行时确定提交范围时，此事件很有用。</span><span class="sxs-lookup"><span data-stu-id="a2144-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. <span data-ttu-id="a2144-128">实现事件的处理程序 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> ，该事件会丢弃 `Customer` 表示当前行的对象的值。</span><span class="sxs-lookup"><span data-stu-id="a2144-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="a2144-129">当用户通过在编辑模式中按 ESC 两次或在编辑模式之外时，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="a2144-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="a2144-130">如果当前行中没有单元格已修改，或者在 <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> `false` 事件处理程序中已将属性的值设置为，则不会发生此事件 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 。</span><span class="sxs-lookup"><span data-stu-id="a2144-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="a2144-131">实现事件的处理程序 <xref:System.Windows.Forms.DataGridView.UserDeletingRow> ，该事件 `Customer` 从数据存储区中删除现有的对象，或者放弃 `Customer` 表示新创建的行的未保存对象。</span><span class="sxs-lookup"><span data-stu-id="a2144-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="a2144-132">当用户通过单击行标题并按 DELETE 键删除行时，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="a2144-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="a2144-133">实现一个简单的 `Customers` 类，以表示此代码示例使用的数据项。</span><span class="sxs-lookup"><span data-stu-id="a2144-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="a2144-134">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="a2144-134">Testing the Application</span></span>  
 <span data-ttu-id="a2144-135">你现在可以对窗体进行测试，以确保它按预期方式运行。</span><span class="sxs-lookup"><span data-stu-id="a2144-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="a2144-136">测试窗体</span><span class="sxs-lookup"><span data-stu-id="a2144-136">To test the form</span></span>  
  
- <span data-ttu-id="a2144-137">编译并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a2144-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="a2144-138">你将看到一个 <xref:System.Windows.Forms.DataGridView> 控件填充了三个客户记录。</span><span class="sxs-lookup"><span data-stu-id="a2144-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="a2144-139">您可以修改某个行中多个单元格的值，并在编辑模式下按 ESC 两次，在编辑模式之外，将整行还原为其原始值。</span><span class="sxs-lookup"><span data-stu-id="a2144-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="a2144-140">在控件中修改、添加或删除行时， `Customer` 也会修改、添加或删除数据存储区中的对象。</span><span class="sxs-lookup"><span data-stu-id="a2144-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a2144-141">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a2144-141">Next Steps</span></span>  
 <span data-ttu-id="a2144-142">通过此应用程序，您可以对在控件中实现虚拟模式所必须处理的事件有一个基本的了解 <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="a2144-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a2144-143">可以通过多种方式改进此基本应用程序：</span><span class="sxs-lookup"><span data-stu-id="a2144-143">You can improve this basic application in a number of ways:</span></span>  
  
- <span data-ttu-id="a2144-144">实现用于缓存外部数据库中的值的数据存储区。</span><span class="sxs-lookup"><span data-stu-id="a2144-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="a2144-145">缓存应根据需要检索和丢弃值，以便它仅包含在使用客户端计算机上的少量内存时显示所需的内容。</span><span class="sxs-lookup"><span data-stu-id="a2144-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
- <span data-ttu-id="a2144-146">根据您的要求，微调数据存储区的性能。</span><span class="sxs-lookup"><span data-stu-id="a2144-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="a2144-147">例如，你可能想要使用较大的缓存大小来补偿慢速网络连接而不是客户端计算机内存限制，并将数据库查询的数量降至最低。</span><span class="sxs-lookup"><span data-stu-id="a2144-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="a2144-148">有关从外部数据库缓存值的详细信息，请参阅 [如何：使用 Windows 窗体 DataGridView 控件中的实时数据加载实现虚拟模式](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="a2144-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2144-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2144-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="a2144-150">Windows 窗体 DataGridView 控件中的性能优化</span><span class="sxs-lookup"><span data-stu-id="a2144-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a2144-151">缩放 Windows 窗体 DataGridView 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="a2144-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a2144-152">在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式</span><span class="sxs-lookup"><span data-stu-id="a2144-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="a2144-153">如何：在 Windows 窗体 DataGridView 控件中实现虚拟模式</span><span class="sxs-lookup"><span data-stu-id="a2144-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
