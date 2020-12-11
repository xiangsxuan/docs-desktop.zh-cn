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
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的性能优化
处理大量数据时， `DataGridView` 控件可能会消耗大量内存，除非你小心使用。 在内存有限的客户端上，你可以通过避免使用具有较高内存成本的功能来避免一些开销。 你还可以使用虚拟模式自行管理部分或全部数据维护和检索任务，以便为你的方案自定义内存使用量。  
  
## <a name="in-this-section"></a>本节内容  
 [缩放 Windows 窗体 DataGridView 控件的最佳做法](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 介绍如何 `DataGridView` 在处理大量数据时，以避免不必要的内存使用情况和性能损失的方式使用控件。  
  
 [Windows 窗体 DataGridView 控件中的虚拟模式](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 介绍如何使用虚拟模式来补充或替换标准的数据绑定机制。  
  
 [演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-wf-datagridview-control.md)  
 描述如何为多个虚拟模式事件实现处理程序。 还演示如何实现行级回滚和提交以进行用户编辑。  
  
 [在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 描述如何按需加载数据，当要显示的数据多于可用客户端内存可以存储的数据时，这非常有用。  
  
## <a name="reference"></a>参考  
 <xref:System.Windows.Forms.DataGridView>  
 提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 提供属性的参考文档 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 。  
  
## <a name="see-also"></a>另请参阅

- [DataGridView 控件](datagridview-control-windows-forms.md)
- [Windows 窗体 DataGridView 控件中的数据显示模式](data-display-modes-in-the-windows-forms-datagridview-control.md)
