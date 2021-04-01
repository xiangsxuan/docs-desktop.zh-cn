---
title: 如何：创建数据对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
ms.openlocfilehash: deae8751518d9322e8d924a1b1fcbc20e25b35ed
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973499"
---
# <a name="how-to-create-a-data-object"></a>如何：创建数据对象
下面的示例演示使用类提供的构造函数创建数据对象的各种方法 <xref:System.Windows.DataObject> 。  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 下面的代码示例创建一个新的数据对象，并使用 () 的重载构造函数之一 <xref:System.Windows.DataObject.%23ctor%28System.Object%29> 来使用字符串初始化该数据对象。  在这种情况下，将根据存储的数据的类型自动确定相应的数据格式，并在默认情况下允许自动转换存储的数据。  
  
### <a name="code"></a>代码  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a>说明  
 下面的示例代码是上面所示代码的精简版本。  
  
### <a name="code"></a>代码  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 下面的代码示例创建一个新的数据对象，并使用 () 的重载构造函数之一， <xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29> 以字符串和指定的数据格式初始化该数据对象。  在这种情况下，数据格式由字符串指定; <xref:System.Windows.DataFormats> 类提供一组预定义类型字符串。 默认情况下允许自动转换存储的数据。  
  
### <a name="code"></a>代码  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a>说明  
 下面的示例代码是上面所示代码的精简版本。  
  
### <a name="code"></a>代码  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 下面的代码示例创建一个新的数据对象，并使用 () 的重载构造函数之一， <xref:System.Windows.DataObject.%23ctor%2A> 以字符串和指定的数据格式初始化该数据对象。  在这种情况下，数据格式由 <xref:System.Type> 参数指定。  默认情况下允许自动转换存储的数据。  
  
### <a name="code"></a>代码  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a>说明  
 下面的示例代码是上面所示代码的精简版本。  
  
### <a name="code"></a>代码  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 下面的代码示例创建一个新的数据对象，并使用 () 的重载构造函数之一， <xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29> 以字符串和指定的数据格式初始化该数据对象。  在这种情况下，数据格式由字符串指定; <xref:System.Windows.DataFormats> 类提供一组预定义类型字符串。 此特定构造函数重载使调用方可以指定是否允许自动转换。  
  
### <a name="code"></a>代码  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a>说明  
 下面的示例代码是上面所示代码的精简版本。  
  
### <a name="code"></a>代码  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.IDataObject>
