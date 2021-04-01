---
title: 如何：提高 TreeView 的性能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: de1b46da2a7c6c3db0c0c19cdbb654fcf2fbbd6c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973092"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>如何：提高 TreeView 的性能
如果 <xref:System.Windows.Controls.TreeView> 包含很多项，加载所需的时间可能会导致用户界面出现明显的延迟。 可以通过将 `VirtualizingStackPanel.IsVirtualizing` 附加属性设置为来缩短加载时间 `true` 。  当用户 <xref:System.Windows.Controls.TreeView> 使用鼠标轮滚动或拖动滚动条的滚动块时，UI 的响应速度也可能会很慢。 <xref:System.Windows.Controls.TreeView>通过将附加属性设置为，可以提高用户滚动时的性能 `VirtualizingStackPanel.VirtualizationMode` <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> 。  
  
## <a name="example"></a>示例  
  
## <a name="description"></a>描述  
下面的示例创建一个 <xref:System.Windows.Controls.TreeView> ，它将 `VirtualizingStackPanel.IsVirtualizing` 附加属性设置为 true，并将附加属性设置为以 `VirtualizingStackPanel.VirtualizationMode` <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> 优化其性能。  
  
## <a name="code"></a>代码  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 下面的示例显示了上一示例所使用的数据。  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>请参阅

- [控件](../advanced/optimizing-performance-controls.md)
