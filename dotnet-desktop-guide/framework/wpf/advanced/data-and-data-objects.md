---
title: 数据和数据对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data transfer [WPF], drag-and-drop
- DataFormats class [WPF]
- DataObject class [WPF]
ms.assetid: 5967d557-1867-420f-a524-ae3af78402da
ms.openlocfilehash: c0751c0f98406ac849075f347b4f812a5ee52a90
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666090"
---
# <a name="data-and-data-objects"></a>数据和数据对象
作为拖放操作的一部分传输的数据存储在数据对象中。  从概念上讲，数据对象由以下一个或多个对组成：  
  
- 一个 <xref:System.Object> 包含实际数据的。  
  
- 对应的数据格式标识符。  
  
 数据本身可以包含可表示为基础的任何内容 <xref:System.Object> 。  对应的数据格式是一个字符串或 <xref:System.Type> ，它提供有关数据所在格式的提示。  数据对象支持承载多个数据/数据格式对;这使得单个数据对象可以提供多种格式的数据。  
  
<a name="Data_and_Data_Objects"></a>
## <a name="data-objects"></a>数据对象  
 所有数据对象必须实现 <xref:System.Windows.IDataObject> 接口，该接口提供了以下标准方法集，可启用和简化数据传输。  
  
|方法|总结|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|检索指定数据格式的数据对象。|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|查看是否具有指定格式的数据，或者数据是否可以转换为指定格式。|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|返回一个格式列表，此数据对象中的数据以这些格式存储，或可以转换为这些格式。|  
|<xref:System.Windows.IDataObject.SetData%2A>|在此数据对象中存储指定的数据。|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 提供类中的的基本实现 <xref:System.Windows.IDataObject> <xref:System.Windows.DataObject> 。 Stock <xref:System.Windows.DataObject> 类足以满足许多常见数据传输方案的需求。  
  
 有几种预定义的格式，如位图、CSV、文件、HTML、RTF、字符串、文本和音频。 有关随一起提供的预定义数据格式的信息 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，请参见 <xref:System.Windows.DataFormats> 类参考主题。  
  
 数据对象通常包含用于在提取数据时自动将一种格式的数据转换为其他格式的功能;此功能称为自动转换。 查询数据对象中可用的数据格式时，可以通过调用 <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> 或 <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> 方法并将参数指定为，从本机数据格式筛选自动转换的数据格式 `autoConvert` `false` 。  使用方法向数据对象添加数据时 <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> ，可以通过将参数设置为来禁止自动转换数据 `autoConvert` `false` 。  
  
<a name="Working_with_Data_Objects"></a>
## <a name="working-with-data-objects"></a>使用数据对象  
 本部分介绍用于创建和使用数据对象的常用技术。  
  
### <a name="creating-new-data-objects"></a>创建新数据对象  
 <xref:System.Windows.DataObject>类提供多个重载构造函数，这些构造函数有助于 <xref:System.Windows.DataObject> 使用单个数据/数据格式对来填充新的实例。  
  
 下面的代码示例创建一个新的数据对象，并使用 () 的重载构造函数之一， <xref:System.Windows.DataObject.%23ctor%2A> <xref:System.Windows.DataObject.%23ctor(System.String,System.Object)> 以字符串和指定的数据格式初始化该数据对象。  在这种情况下，数据格式由字符串指定; <xref:System.Windows.DataFormats> 类提供一组预定义类型字符串。 默认情况下允许自动转换存储的数据。  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 有关创建数据对象的代码的更多示例，请参阅 [创建数据对象](how-to-create-a-data-object.md)。  
  
### <a name="storing-data-in-multiple-formats"></a>以多种格式存储数据  
 单个数据对象能够以多种格式存储数据。   在单个数据对象内使用多个数据格式时，可能会使数据对象被更多的拖放目标使用，而不是仅能表示一种数据格式。  请注意，通常情况下，拖动源对于可能的放置目标可以使用的数据格式是不可知的。  
  
 下面的示例演示如何使用 <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> 方法将数据添加到采用多种格式的数据对象。  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>查询数据对象的可用格式  
 由于单个数据对象可以包含任意数量的数据格式，因此数据对象包括用于检索可用数据格式列表的功能。  
  
 下面的示例代码使用 <xref:System.Windows.DataObject.GetFormats%2A> 重载获取一个字符串数组，该数组表示数据对象中所有可用的数据格式 (本机和自动转换) 。  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 有关查询数据对象以获取可用数据格式的更多代码示例，请参阅 [列出数据对象中的数据格式](how-to-list-the-data-formats-in-a-data-object.md)。  有关查询数据对象是否存在特定数据格式的示例，请参阅 [确定数据格式是否存在于数据对象中](how-to-determine-if-a-data-format-is-present-in-a-data-object.md)。  
  
### <a name="retrieving-data-from-a-data-object"></a>从数据对象检索数据  
 从数据对象中检索特定格式的数据只需调用其中一个 <xref:System.Windows.DataObject.GetData%2A> 方法并指定所需的数据格式即可。  其中一种 <xref:System.Windows.DataObject.GetDataPresent%2A> 方法可用于检查是否存在特定的数据格式。  <xref:System.Windows.DataObject.GetData%2A> 返回中的数据 <xref:System.Object> ; 根据数据格式，此对象可强制转换为特定于类型的容器。  
  
 下面的示例代码使用 <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> 重载来检查指定的数据格式 (本机还是自动转换) 可用。 如果指定的格式可用，则该示例使用方法检索数据 <xref:System.Windows.DataObject.GetData%28System.String%29> 。  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 有关从数据对象中检索数据的更多代码示例，请参阅 [以特定数据格式检索数据](how-to-retrieve-data-in-a-particular-data-format.md)。  
  
### <a name="removing-data-from-a-data-object"></a>从数据对象中删除数据  
 不能直接从数据对象中删除数据。  若要有效地从数据对象中删除数据，请执行以下步骤：  
  
1. 创建一个新的数据对象，该对象将只包含您要保留的数据。  
  
2. 将所需的数据从旧的数据对象复制到新的数据对象。  若要复制数据，请使用一种 <xref:System.Windows.DataObject.GetData%2A> 方法来检索 <xref:System.Object> 包含原始数据的，然后使用其中一种 <xref:System.Windows.DataObject.SetData%2A> 方法将数据添加到新的数据对象。  
  
3. 将旧数据对象替换为新对象。  
  
> [!NOTE]
> <xref:System.Windows.DataObject.SetData%2A>方法只将数据添加到数据对象; 不替换数据，即使数据和数据格式与上一个调用完全相同。 <xref:System.Windows.DataObject.SetData%2A>为相同的数据和数据格式调用两次会导致数据/数据格式在数据对象中出现两次。
