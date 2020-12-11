---
title: 如何：列出数据对象中的数据格式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
ms.openlocfilehash: f8230eac33a18a0d99cc757d54c2b901c1afe977
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973591"
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a><span data-ttu-id="1a4a4-102">如何：列出数据对象中的数据格式</span><span class="sxs-lookup"><span data-stu-id="1a4a4-102">How to: List the Data Formats in a Data Object</span></span>
<span data-ttu-id="1a4a4-103">下面的示例演示如何使用 <xref:System.Windows.DataObject.GetFormats%2A> 方法重载获取一个字符串数组，用于表示数据对象中可用的每个数据格式。</span><span class="sxs-lookup"><span data-stu-id="1a4a4-103">The following examples show how to use the <xref:System.Windows.DataObject.GetFormats%2A> method overloads get an array of strings denoting each data format that is available in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a4a4-104">示例</span><span class="sxs-lookup"><span data-stu-id="1a4a4-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="1a4a4-105">描述</span><span class="sxs-lookup"><span data-stu-id="1a4a4-105">Description</span></span>  
 <span data-ttu-id="1a4a4-106">下面的示例代码使用 <xref:System.Windows.DataObject.GetFormats%2A> 重载获取一个字符串数组，该数组表示数据对象中所有可用的数据格式 (本机和自动可转换) 。</span><span class="sxs-lookup"><span data-stu-id="1a4a4-106">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and auto-convertible).</span></span>  
  
### <a name="code"></a><span data-ttu-id="1a4a4-107">代码</span><span class="sxs-lookup"><span data-stu-id="1a4a4-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a><span data-ttu-id="1a4a4-108">示例</span><span class="sxs-lookup"><span data-stu-id="1a4a4-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="1a4a4-109">描述</span><span class="sxs-lookup"><span data-stu-id="1a4a4-109">Description</span></span>  
 <span data-ttu-id="1a4a4-110">下面的示例代码使用 <xref:System.Windows.DataObject.GetFormats%2A> 重载获取一个字符串数组，该数组仅表示数据对象中可用的数据格式 (自动转换的数据格式) 进行筛选。</span><span class="sxs-lookup"><span data-stu-id="1a4a4-110">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting only data formats available in a data object (auto-convertible data formats are filtered).</span></span>  
  
### <a name="code"></a><span data-ttu-id="1a4a4-111">代码</span><span class="sxs-lookup"><span data-stu-id="1a4a4-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a><span data-ttu-id="1a4a4-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a4a4-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="1a4a4-113">拖放概述</span><span class="sxs-lookup"><span data-stu-id="1a4a4-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
