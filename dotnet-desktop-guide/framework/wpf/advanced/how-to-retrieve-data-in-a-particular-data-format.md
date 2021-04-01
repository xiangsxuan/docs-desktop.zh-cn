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
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a>如何：以特定数据格式检索数据
下面的示例演示如何从具有指定格式的数据对象检索数据。  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>说明  
 下面的示例代码先使用 <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> 重载来检查指定的数据格式是否 (本机或自动转换) 可用; 如果指定的格式可用，则该示例使用方法检索数据 <xref:System.Windows.DataObject.GetData%28System.String%29> 。  
  
### <a name="code"></a>代码  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>说明  
 下面的示例代码先使用 <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> 重载来检查指定的数据格式是否在本机可用 (是否筛选了可自动转换的数据格式) ; 如果指定的格式可用，则该示例使用方法检索数据 <xref:System.Windows.DataObject.GetData%28System.String%29> 。  
  
### <a name="code"></a>代码  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.IDataObject>
- [拖放概述](drag-and-drop-overview.md)
