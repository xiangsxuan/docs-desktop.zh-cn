---
title: 将设计器用于 DataGridView 控件
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- DataGridView control [Windows Forms], designer support
- formatting [Windows Forms]
ms.assetid: b66057a6-5983-4864-b4e7-8cbc88a7010c
ms.openlocfilehash: 50e8bddb97c2dfb84cebdbb2ca4d42a6c5743304
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973111"
---
# <a name="using-the-designer-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="c6a00-102">将设计器与 Windows 窗体 DataGridView 控件结合使用</span><span class="sxs-lookup"><span data-stu-id="c6a00-102">Using the Designer with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c6a00-103">Visual Studio 为控件提供设计器支持 `DataGridView` ，使你能够在不编写代码的情况下执行多个安装任务。</span><span class="sxs-lookup"><span data-stu-id="c6a00-103">Visual Studio provides designer support for the `DataGridView` control that enables you to perform many setup tasks without writing code.</span></span> <span data-ttu-id="c6a00-104">这些任务包括将控件绑定到数据源、修改用于显示数据的列，以及调整控件的外观和基本行为。</span><span class="sxs-lookup"><span data-stu-id="c6a00-104">These tasks include binding the control to a data source, modifying the columns used to display data, and adjusting the appearance and basic behavior of the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c6a00-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="c6a00-105">In This Section</span></span>  
 [<span data-ttu-id="c6a00-106">如何：使用设计器添加和移除 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="c6a00-106">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c6a00-107">介绍如何使用 " **添加列** " 和 " **编辑列** " 对话框来填充和修改列集合。</span><span class="sxs-lookup"><span data-stu-id="c6a00-107">Describes how to use the **Add Columns** and **Edit Columns** dialog boxes to populate and modify the columns collection.</span></span>  
  
 [<span data-ttu-id="c6a00-108">如何：使用设计器将数据绑定到 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="c6a00-108">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>](bind-data-to-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c6a00-109">介绍如何使用控件的智能标记上的 " **选择数据源** " 选项来连接到数据。</span><span class="sxs-lookup"><span data-stu-id="c6a00-109">Describes how to use the **Choose Data Source** option on the control's smart tag to connect to data.</span></span>  
  
 [<span data-ttu-id="c6a00-110">如何：使用设计器更改 Windows 窗体 DataGridView 控件中列的顺序</span><span class="sxs-lookup"><span data-stu-id="c6a00-110">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c6a00-111">介绍如何使用 " **编辑列** " 对话框重新排列列。</span><span class="sxs-lookup"><span data-stu-id="c6a00-111">Describes how to use the **Edit Columns** dialog box to rearrange columns.</span></span>  
  
 [<span data-ttu-id="c6a00-112">如何：使用设计器更改 Windows 窗体 DataGridView 列类型</span><span class="sxs-lookup"><span data-stu-id="c6a00-112">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 <span data-ttu-id="c6a00-113">介绍如何使用 " **编辑列** " 对话框更改列类型。</span><span class="sxs-lookup"><span data-stu-id="c6a00-113">Describes how to use the **Edit Columns** dialog box to change column types.</span></span>  
  
 [<span data-ttu-id="c6a00-114">如何：使用设计器在 Windows 窗体 DataGridView 控件中启用列重新排序</span><span class="sxs-lookup"><span data-stu-id="c6a00-114">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c6a00-115">介绍如何使用控件的智能标记来使用户能够重新排列列。</span><span class="sxs-lookup"><span data-stu-id="c6a00-115">Describes how to use the control's smart tag to enable users to rearrange columns.</span></span>  
  
 [<span data-ttu-id="c6a00-116">如何：使用设计器冻结 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="c6a00-116">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c6a00-117">介绍如何使用 " **编辑列** " 对话框防止特定列滚动。</span><span class="sxs-lookup"><span data-stu-id="c6a00-117">Describes how to use the **Edit Columns** dialog box to prevent specific columns from scrolling.</span></span>  
  
 [<span data-ttu-id="c6a00-118">如何：使用设计器隐藏 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="c6a00-118">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](hide-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c6a00-119">介绍如何使用 " **编辑列** " 对话框隐藏特定列。</span><span class="sxs-lookup"><span data-stu-id="c6a00-119">Describes how to use the **Edit Columns** dialog box to hide specific columns.</span></span>  
  
 [<span data-ttu-id="c6a00-120">如何：使用设计器将 Windows 窗体 DataGridView 控件中的列设为只读</span><span class="sxs-lookup"><span data-stu-id="c6a00-120">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c6a00-121">介绍如何使用 " **编辑列** " 对话框防止用户编辑特定列中的值。</span><span class="sxs-lookup"><span data-stu-id="c6a00-121">Describes how to use the **Edit Columns** dialog box to prevent users from editing values in specific columns.</span></span>  
  
 [<span data-ttu-id="c6a00-122">如何：使用设计器防止在 Windows 窗体 DataGridView 控件中添加和删除行</span><span class="sxs-lookup"><span data-stu-id="c6a00-122">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c6a00-123">介绍如何使用控件的智能标记来阻止用户添加或删除行。</span><span class="sxs-lookup"><span data-stu-id="c6a00-123">Describes how to use the control's smart tag to prevent users from adding or deleting rows.</span></span>  
  
 [<span data-ttu-id="c6a00-124">如何：使用设计器设置 Windows 窗体 DataGridView 控件的交替行样式</span><span class="sxs-lookup"><span data-stu-id="c6a00-124">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c6a00-125">介绍如何使用 " **CellStyle 生成器** " 对话框在控件中创建类似于帐目的外观。</span><span class="sxs-lookup"><span data-stu-id="c6a00-125">Describes how to use the **CellStyle Builder** dialog box to create a ledger-like appearance in the control.</span></span>  
  
 [<span data-ttu-id="c6a00-126">如何：使用设计器设置 Windows 窗体 DataGridView 控件的默认单元格样式和数据格式</span><span class="sxs-lookup"><span data-stu-id="c6a00-126">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>](default-cell-styles-datagridview.md)  
 <span data-ttu-id="c6a00-127">介绍如何使用 " **CellStyle 生成器** " 对话框设置控件的基本外观和数据显示格式。</span><span class="sxs-lookup"><span data-stu-id="c6a00-127">Describes how to use the **CellStyle Builder** dialog box to set up the basic appearance and data-display formats for the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c6a00-128">参考</span><span class="sxs-lookup"><span data-stu-id="c6a00-128">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="c6a00-129">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="c6a00-129">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6a00-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6a00-130">See also</span></span>

- [<span data-ttu-id="c6a00-131">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="c6a00-131">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
