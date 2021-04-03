---
title: 如何：在数据对象中存储多种数据格式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], storing multiple formats
- DataFormats class [WPF], storing multiple formats
- drag-and-drop [WPF], storing multiple formats
ms.assetid: 941ace29-29c4-4c26-b75b-ea7d06aa0d69
ms.openlocfilehash: 3f8e7233e1d28fec1f7dac114b04287aa3aff49f
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970595"
---
# <a name="how-to-store-multiple-data-formats-in-a-data-object"></a><span data-ttu-id="c3b7d-102">如何：在数据对象中存储多种数据格式</span><span class="sxs-lookup"><span data-stu-id="c3b7d-102">How to: Store Multiple Data Formats in a Data Object</span></span>
<span data-ttu-id="c3b7d-103">下面的示例演示如何使用 <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> 方法将数据添加到采用多种格式的数据对象。</span><span class="sxs-lookup"><span data-stu-id="c3b7d-103">The following example shows how to use the <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> method to add data to a data object in multiple formats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3b7d-104">示例</span><span class="sxs-lookup"><span data-stu-id="c3b7d-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c3b7d-105">说明</span><span class="sxs-lookup"><span data-stu-id="c3b7d-105">Description</span></span>  
  
### <a name="code"></a><span data-ttu-id="c3b7d-106">代码</span><span class="sxs-lookup"><span data-stu-id="c3b7d-106">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
## <a name="see-also"></a><span data-ttu-id="c3b7d-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3b7d-107">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="c3b7d-108">拖放概述</span><span class="sxs-lookup"><span data-stu-id="c3b7d-108">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
