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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973499"
---
# <a name="how-to-create-a-data-object"></a><span data-ttu-id="b6444-102">如何：创建数据对象</span><span class="sxs-lookup"><span data-stu-id="b6444-102">How to: Create a Data Object</span></span>
<span data-ttu-id="b6444-103">下面的示例演示使用类提供的构造函数创建数据对象的各种方法 <xref:System.Windows.DataObject> 。</span><span class="sxs-lookup"><span data-stu-id="b6444-103">The following examples show various ways to create a data object using the constructors provided by the <xref:System.Windows.DataObject> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6444-104">示例</span><span class="sxs-lookup"><span data-stu-id="b6444-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b6444-105">描述</span><span class="sxs-lookup"><span data-stu-id="b6444-105">Description</span></span>  
 <span data-ttu-id="b6444-106">下面的代码示例创建一个新的数据对象，并使用 () 的重载构造函数之一 <xref:System.Windows.DataObject.%23ctor%28System.Object%29> 来使用字符串初始化该数据对象。</span><span class="sxs-lookup"><span data-stu-id="b6444-106">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) to initialize the data object with a string.</span></span>  <span data-ttu-id="b6444-107">在这种情况下，将根据存储的数据的类型自动确定相应的数据格式，并在默认情况下允许自动转换存储的数据。</span><span class="sxs-lookup"><span data-stu-id="b6444-107">In this case, an appropriate data format is determined automatically according to the stored data's type, and auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b6444-108">代码</span><span class="sxs-lookup"><span data-stu-id="b6444-108">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a><span data-ttu-id="b6444-109">说明</span><span class="sxs-lookup"><span data-stu-id="b6444-109">Description</span></span>  
 <span data-ttu-id="b6444-110">下面的示例代码是上面所示代码的精简版本。</span><span class="sxs-lookup"><span data-stu-id="b6444-110">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b6444-111">代码</span><span class="sxs-lookup"><span data-stu-id="b6444-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a><span data-ttu-id="b6444-112">示例</span><span class="sxs-lookup"><span data-stu-id="b6444-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b6444-113">描述</span><span class="sxs-lookup"><span data-stu-id="b6444-113">Description</span></span>  
 <span data-ttu-id="b6444-114">下面的代码示例创建一个新的数据对象，并使用 () 的重载构造函数之一， <xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29> 以字符串和指定的数据格式初始化该数据对象。</span><span class="sxs-lookup"><span data-stu-id="b6444-114">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="b6444-115">在这种情况下，数据格式由字符串指定; <xref:System.Windows.DataFormats> 类提供一组预定义类型字符串。</span><span class="sxs-lookup"><span data-stu-id="b6444-115">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="b6444-116">默认情况下允许自动转换存储的数据。</span><span class="sxs-lookup"><span data-stu-id="b6444-116">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b6444-117">代码</span><span class="sxs-lookup"><span data-stu-id="b6444-117">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a><span data-ttu-id="b6444-118">说明</span><span class="sxs-lookup"><span data-stu-id="b6444-118">Description</span></span>  
 <span data-ttu-id="b6444-119">下面的示例代码是上面所示代码的精简版本。</span><span class="sxs-lookup"><span data-stu-id="b6444-119">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b6444-120">代码</span><span class="sxs-lookup"><span data-stu-id="b6444-120">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a><span data-ttu-id="b6444-121">示例</span><span class="sxs-lookup"><span data-stu-id="b6444-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b6444-122">描述</span><span class="sxs-lookup"><span data-stu-id="b6444-122">Description</span></span>  
 <span data-ttu-id="b6444-123">下面的代码示例创建一个新的数据对象，并使用 () 的重载构造函数之一， <xref:System.Windows.DataObject.%23ctor%2A> 以字符串和指定的数据格式初始化该数据对象。</span><span class="sxs-lookup"><span data-stu-id="b6444-123">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%2A>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="b6444-124">在这种情况下，数据格式由 <xref:System.Type> 参数指定。</span><span class="sxs-lookup"><span data-stu-id="b6444-124">In this case the data format is specified by a <xref:System.Type> parameter.</span></span>  <span data-ttu-id="b6444-125">默认情况下允许自动转换存储的数据。</span><span class="sxs-lookup"><span data-stu-id="b6444-125">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b6444-126">代码</span><span class="sxs-lookup"><span data-stu-id="b6444-126">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a><span data-ttu-id="b6444-127">说明</span><span class="sxs-lookup"><span data-stu-id="b6444-127">Description</span></span>  
 <span data-ttu-id="b6444-128">下面的示例代码是上面所示代码的精简版本。</span><span class="sxs-lookup"><span data-stu-id="b6444-128">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b6444-129">代码</span><span class="sxs-lookup"><span data-stu-id="b6444-129">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a><span data-ttu-id="b6444-130">示例</span><span class="sxs-lookup"><span data-stu-id="b6444-130">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b6444-131">描述</span><span class="sxs-lookup"><span data-stu-id="b6444-131">Description</span></span>  
 <span data-ttu-id="b6444-132">下面的代码示例创建一个新的数据对象，并使用 () 的重载构造函数之一， <xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29> 以字符串和指定的数据格式初始化该数据对象。</span><span class="sxs-lookup"><span data-stu-id="b6444-132">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="b6444-133">在这种情况下，数据格式由字符串指定; <xref:System.Windows.DataFormats> 类提供一组预定义类型字符串。</span><span class="sxs-lookup"><span data-stu-id="b6444-133">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="b6444-134">此特定构造函数重载使调用方可以指定是否允许自动转换。</span><span class="sxs-lookup"><span data-stu-id="b6444-134">This particular constructor overload enables the caller to specify whether auto-converting is allowed.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b6444-135">代码</span><span class="sxs-lookup"><span data-stu-id="b6444-135">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a><span data-ttu-id="b6444-136">说明</span><span class="sxs-lookup"><span data-stu-id="b6444-136">Description</span></span>  
 <span data-ttu-id="b6444-137">下面的示例代码是上面所示代码的精简版本。</span><span class="sxs-lookup"><span data-stu-id="b6444-137">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b6444-138">代码</span><span class="sxs-lookup"><span data-stu-id="b6444-138">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a><span data-ttu-id="b6444-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6444-139">See also</span></span>

- <xref:System.Windows.IDataObject>