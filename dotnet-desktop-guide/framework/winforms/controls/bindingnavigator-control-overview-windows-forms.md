---
title: BindingNavigator 控件概述
ms.date: 03/30/2017
f1_keywords:
- DataNavigator
helpviewer_keywords:
- BindingNavigator control [Windows Forms], about BindingNavigator control
- records [Windows Forms], navigating on a form
- data [Windows Forms], navigating
- data navigation
ms.assetid: 4423eede-f8d1-4d02-822f-5bf8432680d0
ms.openlocfilehash: c2747a6801d4aa9cfde4227ffd5c29ca1de78d48
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971316"
---
# <a name="bindingnavigator-control-overview-windows-forms"></a><span data-ttu-id="aa1bc-102">BindingNavigator 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="aa1bc-102">BindingNavigator Control Overview (Windows Forms)</span></span>
<span data-ttu-id="aa1bc-103">你可以使用 <xref:System.Windows.Forms.BindingNavigator> 控件来创建标准化的方法，以便用户搜索和更改 Windows 窗体上的数据。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-103">You can use the <xref:System.Windows.Forms.BindingNavigator> control to create a standardized means for users to search and change data on a Windows Form.</span></span> <span data-ttu-id="aa1bc-104">频繁对 <xref:System.Windows.Forms.BindingSource> 组件使用 <xref:System.Windows.Forms.BindingNavigator>，以便用户能够在窗体上数据记录之间移动并与记录进行交互。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-104">You frequently use <xref:System.Windows.Forms.BindingNavigator> with the <xref:System.Windows.Forms.BindingSource> component to enable users to move through data records on a form and interact with the records.</span></span>  
  
## <a name="how-the-bindingnavigator-works"></a><span data-ttu-id="aa1bc-105">BindingNavigator 的工作原理</span><span class="sxs-lookup"><span data-stu-id="aa1bc-105">How the BindingNavigator Works</span></span>  

 <span data-ttu-id="aa1bc-106"><xref:System.Windows.Forms.BindingNavigator> 控件由包含一系列 <xref:System.Windows.Forms.ToolStripItem> 对象的 <xref:System.Windows.Forms.ToolStrip> 组成，以执行大部分常见的与数据相关的操作：添加数据、删除数据，以及在数据中导航。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-106">The <xref:System.Windows.Forms.BindingNavigator> control is composed of a <xref:System.Windows.Forms.ToolStrip> with a series of <xref:System.Windows.Forms.ToolStripItem> objects for most of the common data-related actions: adding data, deleting data, and navigating through data.</span></span> <span data-ttu-id="aa1bc-107">默认情况下，<xref:System.Windows.Forms.BindingNavigator> 控件包含这些标准按钮。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-107">By default, the <xref:System.Windows.Forms.BindingNavigator> control contains these standard buttons.</span></span> <span data-ttu-id="aa1bc-108">以下屏幕截图显示了 <xref:System.Windows.Forms.BindingNavigator> 窗体上的控件：</span><span class="sxs-lookup"><span data-stu-id="aa1bc-108">The following screenshot shows the <xref:System.Windows.Forms.BindingNavigator> control on a form:</span></span>
  
 ![显示 BindingNavigator 控件的屏幕截图。](./media/bindingnavigator-control-overview-windows-forms/bindingnavigator-control-form.gif)  
  
 <span data-ttu-id="aa1bc-110">下表列出了该控件并介绍了其功能。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-110">The following table lists the controls and describes their functions.</span></span>  
  
|<span data-ttu-id="aa1bc-111">控制</span><span class="sxs-lookup"><span data-stu-id="aa1bc-111">Control</span></span>|<span data-ttu-id="aa1bc-112">函数</span><span class="sxs-lookup"><span data-stu-id="aa1bc-112">Function</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="aa1bc-113"><xref:System.Windows.Forms.BindingNavigator.AddNewItem%2A> 按钮</span><span class="sxs-lookup"><span data-stu-id="aa1bc-113"><xref:System.Windows.Forms.BindingNavigator.AddNewItem%2A> button</span></span>|<span data-ttu-id="aa1bc-114">将新行插入到基础数据源。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-114">Inserts a new row into the underlying data source.</span></span>|  
|<span data-ttu-id="aa1bc-115"><xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> 按钮</span><span class="sxs-lookup"><span data-stu-id="aa1bc-115"><xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button</span></span>|<span data-ttu-id="aa1bc-116">从基础数据源中删除当前行。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-116">Deletes the current row from the underlying data source.</span></span>|  
|<span data-ttu-id="aa1bc-117"><xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> 按钮</span><span class="sxs-lookup"><span data-stu-id="aa1bc-117"><xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button</span></span>|<span data-ttu-id="aa1bc-118">移动到基础数据源中的第一项。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-118">Moves to the first item in the underlying data source.</span></span>|  
|<span data-ttu-id="aa1bc-119"><xref:System.Windows.Forms.BindingNavigator.MoveLastItem%2A> 按钮</span><span class="sxs-lookup"><span data-stu-id="aa1bc-119"><xref:System.Windows.Forms.BindingNavigator.MoveLastItem%2A> button</span></span>|<span data-ttu-id="aa1bc-120">移动到基础数据源中的最后一项。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-120">Moves to the last item in the underlying data source.</span></span>|  
|<span data-ttu-id="aa1bc-121"><xref:System.Windows.Forms.BindingNavigator.MoveNextItem%2A> 按钮</span><span class="sxs-lookup"><span data-stu-id="aa1bc-121"><xref:System.Windows.Forms.BindingNavigator.MoveNextItem%2A> button</span></span>|<span data-ttu-id="aa1bc-122">移动到基础数据源中的下一项。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-122">Moves to the next item in the underlying data source.</span></span>|  
|<span data-ttu-id="aa1bc-123"><xref:System.Windows.Forms.BindingNavigator.MovePreviousItem%2A> 按钮</span><span class="sxs-lookup"><span data-stu-id="aa1bc-123"><xref:System.Windows.Forms.BindingNavigator.MovePreviousItem%2A> button</span></span>|<span data-ttu-id="aa1bc-124">移动到基础数据源中的上一项。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-124">Moves to the previous item in the underlying data source.</span></span>|  
|<span data-ttu-id="aa1bc-125"><xref:System.Windows.Forms.BindingNavigator.PositionItem%2A> 文本框</span><span class="sxs-lookup"><span data-stu-id="aa1bc-125"><xref:System.Windows.Forms.BindingNavigator.PositionItem%2A> text box</span></span>|<span data-ttu-id="aa1bc-126">返回基础数据源中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-126">Returns the current position within the underlying data source.</span></span>|  
|<span data-ttu-id="aa1bc-127"><xref:System.Windows.Forms.BindingNavigator.CountItem%2A> 文本框</span><span class="sxs-lookup"><span data-stu-id="aa1bc-127"><xref:System.Windows.Forms.BindingNavigator.CountItem%2A> text box</span></span>|<span data-ttu-id="aa1bc-128">返回基础数据源中的总项数。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-128">Returns the total number of items in the underlying data source.</span></span>|  
  
 <span data-ttu-id="aa1bc-129">对于此集合中每个控件，都有相应的以编程方式提供相同功能的 <xref:System.Windows.Forms.BindingSource> 组件成员。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-129">For each control in this collection, there is a corresponding member of the <xref:System.Windows.Forms.BindingSource> component that programmatically provides the same functionality.</span></span> <span data-ttu-id="aa1bc-130">例如，<xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> 按钮对应 <xref:System.Windows.Forms.BindingSource> 组件的 <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> 方法，<xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> 按钮对应 <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> 方法，依次类推。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-130">For example, the <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> method of the <xref:System.Windows.Forms.BindingSource> component, the <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> method, and so on.</span></span>  
  
 <span data-ttu-id="aa1bc-131">如果默认按钮不适合你的应用程序，或者如果你需要其他按钮来支持其他类型的功能，则可以提供你自己的 <xref:System.Windows.Forms.ToolStrip> 按钮。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-131">If the default buttons are not suited to your application, or if you require additional buttons to support other types of functionality, you can supply your own <xref:System.Windows.Forms.ToolStrip> buttons.</span></span> <span data-ttu-id="aa1bc-132">另请参阅[如何：向 Windows 窗体 BindingNavigator 控件添加“加载”、“保存”和“取消”按钮](load-save-and-cancel-bindingnavigator.md)。</span><span class="sxs-lookup"><span data-stu-id="aa1bc-132">Also see [How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control](load-save-and-cancel-bindingnavigator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa1bc-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa1bc-133">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="aa1bc-134">BindingNavigator 控件</span><span class="sxs-lookup"><span data-stu-id="aa1bc-134">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
