---
title: DataGridView 控件中的性能优化
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: 77ad86c4cd606bcf074473c97371ec27bcc5605b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971764"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2db5f-102">Windows 窗体 DataGridView 控件中的性能优化</span><span class="sxs-lookup"><span data-stu-id="2db5f-102">Performance Tuning in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2db5f-103">处理大量数据时， `DataGridView` 控件可能会消耗大量内存，除非你小心使用。</span><span class="sxs-lookup"><span data-stu-id="2db5f-103">When working with large amounts of data, the `DataGridView` control can consume a large amount of memory in overhead, unless you use it carefully.</span></span> <span data-ttu-id="2db5f-104">在内存有限的客户端上，你可以通过避免使用具有较高内存成本的功能来避免一些开销。</span><span class="sxs-lookup"><span data-stu-id="2db5f-104">On clients with limited memory, you can avoid some of this overhead by avoiding features that have a high memory cost.</span></span> <span data-ttu-id="2db5f-105">你还可以使用虚拟模式自行管理部分或全部数据维护和检索任务，以便为你的方案自定义内存使用量。</span><span class="sxs-lookup"><span data-stu-id="2db5f-105">You can also manage some or all of the data maintenance and retrieval tasks yourself using virtual mode in order to customize the memory usage for your scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2db5f-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="2db5f-106">In This Section</span></span>  
 [<span data-ttu-id="2db5f-107">缩放 Windows 窗体 DataGridView 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="2db5f-107">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2db5f-108">介绍如何 `DataGridView` 在处理大量数据时，以避免不必要的内存使用情况和性能损失的方式使用控件。</span><span class="sxs-lookup"><span data-stu-id="2db5f-108">Describes how to use the `DataGridView` control in a way that avoids unnecessary memory usage and performance penalties when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="2db5f-109">Windows 窗体 DataGridView 控件中的虚拟模式</span><span class="sxs-lookup"><span data-stu-id="2db5f-109">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2db5f-110">介绍如何使用虚拟模式来补充或替换标准的数据绑定机制。</span><span class="sxs-lookup"><span data-stu-id="2db5f-110">Describes how to use virtual mode to supplement or replace the standard data-binding mechanism.</span></span>  
  
 [<span data-ttu-id="2db5f-111">演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式</span><span class="sxs-lookup"><span data-stu-id="2db5f-111">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-wf-datagridview-control.md)  
 <span data-ttu-id="2db5f-112">描述如何为多个虚拟模式事件实现处理程序。</span><span class="sxs-lookup"><span data-stu-id="2db5f-112">Describes how to implement handlers for several virtual-mode events.</span></span> <span data-ttu-id="2db5f-113">还演示如何实现行级回滚和提交以进行用户编辑。</span><span class="sxs-lookup"><span data-stu-id="2db5f-113">Also demonstrates how to implement row-level rollback and commit for user edits.</span></span>  
  
 [<span data-ttu-id="2db5f-114">在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式</span><span class="sxs-lookup"><span data-stu-id="2db5f-114">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 <span data-ttu-id="2db5f-115">描述如何按需加载数据，当要显示的数据多于可用客户端内存可以存储的数据时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="2db5f-115">Describes how to load data on demand, which is useful when you have more data to display than the available client memory can store.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2db5f-116">参考</span><span class="sxs-lookup"><span data-stu-id="2db5f-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="2db5f-117">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="2db5f-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <span data-ttu-id="2db5f-118">提供属性的参考文档 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 。</span><span class="sxs-lookup"><span data-stu-id="2db5f-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2db5f-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2db5f-119">See also</span></span>

- [<span data-ttu-id="2db5f-120">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="2db5f-120">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="2db5f-121">Windows 窗体 DataGridView 控件中的数据显示模式</span><span class="sxs-lookup"><span data-stu-id="2db5f-121">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
