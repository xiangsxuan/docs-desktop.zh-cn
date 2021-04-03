---
title: 如何：以特定数据格式检索数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
ms.openlocfilehash: b3ec1b8fa873fd449956912e9e77e98b0362cb0e
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971500"
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a><span data-ttu-id="37621-102">如何：以特定数据格式检索数据</span><span class="sxs-lookup"><span data-stu-id="37621-102">How to: Retrieve Data in a Particular Data Format</span></span>
<span data-ttu-id="37621-103">下面的示例演示如何从具有指定格式的数据对象检索数据。</span><span class="sxs-lookup"><span data-stu-id="37621-103">The following examples show how to retrieve data from a data object in a specified format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37621-104">示例</span><span class="sxs-lookup"><span data-stu-id="37621-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="37621-105">说明</span><span class="sxs-lookup"><span data-stu-id="37621-105">Description</span></span>  
 <span data-ttu-id="37621-106">下面的示例代码先使用 <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> 重载来检查指定的数据格式是否 (本机或自动转换) 可用; 如果指定的格式可用，则该示例使用方法检索数据 <xref:System.Windows.DataObject.GetData%28System.String%29> 。</span><span class="sxs-lookup"><span data-stu-id="37621-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to first check if a specified data format is available (natively or by auto-convert); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="37621-107">代码</span><span class="sxs-lookup"><span data-stu-id="37621-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a><span data-ttu-id="37621-108">示例</span><span class="sxs-lookup"><span data-stu-id="37621-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="37621-109">说明</span><span class="sxs-lookup"><span data-stu-id="37621-109">Description</span></span>  
 <span data-ttu-id="37621-110">下面的示例代码先使用 <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> 重载来检查指定的数据格式是否在本机可用 (是否筛选了可自动转换的数据格式) ; 如果指定的格式可用，则该示例使用方法检索数据 <xref:System.Windows.DataObject.GetData%28System.String%29> 。</span><span class="sxs-lookup"><span data-stu-id="37621-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to first check if a specified data format is available natively (auto-convertible data formats are filtered); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="37621-111">代码</span><span class="sxs-lookup"><span data-stu-id="37621-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a><span data-ttu-id="37621-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37621-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="37621-113">拖放概述</span><span class="sxs-lookup"><span data-stu-id="37621-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
