---
title: 如何：将数据添加到剪贴板
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
ms.openlocfilehash: 0d9b82f01080d18353ecb91578a8005260bbe739
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970338"
---
# <a name="how-to-add-data-to-the-clipboard"></a><span data-ttu-id="ea102-102">如何：将数据添加到剪贴板</span><span class="sxs-lookup"><span data-stu-id="ea102-102">How to: Add Data to the Clipboard</span></span>

<span data-ttu-id="ea102-103"><xref:System.Windows.Forms.Clipboard>类提供可用于与 Windows 操作系统剪贴板功能进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="ea102-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="ea102-104">许多应用程序使用剪贴板作为数据的临时存储库。</span><span class="sxs-lookup"><span data-stu-id="ea102-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="ea102-105">例如，在剪切和粘贴操作期间，word 处理器使用剪贴板。</span><span class="sxs-lookup"><span data-stu-id="ea102-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="ea102-106">剪贴板还适用于将数据从一个应用程序传输到另一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="ea102-106">The Clipboard is also useful for transferring data from one application to another.</span></span>

<span data-ttu-id="ea102-107">在将数据添加到剪贴板时，可以指示数据格式，以便其他应用程序能够使用该格式来识别数据。</span><span class="sxs-lookup"><span data-stu-id="ea102-107">When you add data to the Clipboard, you can indicate the data format so that other applications can recognize the data if they can use that format.</span></span> <span data-ttu-id="ea102-108">你还可以使用多种不同的格式将数据添加到剪贴板，以增加可能使用数据的其他应用程序的数目。</span><span class="sxs-lookup"><span data-stu-id="ea102-108">You can also add data to the Clipboard in multiple different formats to increase the number of other applications that can potentially use the data.</span></span>

<span data-ttu-id="ea102-109">剪贴板格式是标识格式的字符串，以便使用该格式的应用程序可以检索关联的数据。</span><span class="sxs-lookup"><span data-stu-id="ea102-109">A Clipboard format is a string that identifies the format so that an application that uses that format can retrieve the associated data.</span></span> <span data-ttu-id="ea102-110"><xref:System.Windows.Forms.DataFormats>类提供预定义的格式名称供你使用。</span><span class="sxs-lookup"><span data-stu-id="ea102-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="ea102-111">你还可以使用自己的格式名，或者使用对象的类型作为其格式。</span><span class="sxs-lookup"><span data-stu-id="ea102-111">You can also use your own format names or use the type of an object as its format.</span></span>

<span data-ttu-id="ea102-112">若要以一种或多种格式向剪贴板中添加数据，请使用 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="ea102-112">To add data to the Clipboard in one or multiple formats, use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> method.</span></span> <span data-ttu-id="ea102-113">可以将任何对象传递给此方法，但若要添加多种格式的数据，必须首先将数据添加到旨在使用多种格式的单独对象。</span><span class="sxs-lookup"><span data-stu-id="ea102-113">You can pass any object to this method, but to add data in multiple formats, you must first add the data to a separate object designed to work with multiple formats.</span></span> <span data-ttu-id="ea102-114">通常，您需要将数据添加到 <xref:System.Windows.Forms.DataObject> ，但您可以使用任何实现接口的类型 <xref:System.Windows.Forms.IDataObject> 。</span><span class="sxs-lookup"><span data-stu-id="ea102-114">Typically, you will add your data to a <xref:System.Windows.Forms.DataObject>, but you can use any type that implements the <xref:System.Windows.Forms.IDataObject> interface.</span></span>

<span data-ttu-id="ea102-115">在 .NET Framework 2.0 中，可以通过使用旨在使基本剪贴板任务更简单的新方法，将数据直接添加到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="ea102-115">In .NET Framework 2.0, you can add data directly to the Clipboard by using new methods designed to make basic Clipboard tasks easier.</span></span> <span data-ttu-id="ea102-116">当您使用单个公共格式（如文本）来处理数据时，请使用这些方法。</span><span class="sxs-lookup"><span data-stu-id="ea102-116">Use these methods when you work with data in a single, common format such as text.</span></span>

> [!NOTE]
> <span data-ttu-id="ea102-117">所有基于 Windows 的应用程序共享剪贴板。</span><span class="sxs-lookup"><span data-stu-id="ea102-117">All Windows-based applications share the Clipboard.</span></span> <span data-ttu-id="ea102-118">因此，当你切换到另一个应用程序时，内容可能会更改。</span><span class="sxs-lookup"><span data-stu-id="ea102-118">Therefore, the contents are subject to change when you switch to another application.</span></span>
>
> <span data-ttu-id="ea102-119"><xref:System.Windows.Forms.Clipboard>类只能在设置为单线程单元 (STA) 模式的线程中使用。</span><span class="sxs-lookup"><span data-stu-id="ea102-119">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="ea102-120">若要使用此类，请确保使用 `Main` 特性标记方法 <xref:System.STAThreadAttribute> 。</span><span class="sxs-lookup"><span data-stu-id="ea102-120">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>
>
> <span data-ttu-id="ea102-121">对象必须是可序列化的，才能将其放在剪贴板上。</span><span class="sxs-lookup"><span data-stu-id="ea102-121">An object must be serializable for it to be put on the Clipboard.</span></span> <span data-ttu-id="ea102-122">若要使类型可序列化，请使用属性对其进行标记 <xref:System.SerializableAttribute> 。</span><span class="sxs-lookup"><span data-stu-id="ea102-122">To make a type serializable, mark it with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="ea102-123">如果将非序列化对象传递到剪贴板方法，则该方法将失败，且不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="ea102-123">If you pass a non-serializable object to a Clipboard method, the method will fail without throwing an exception.</span></span> <span data-ttu-id="ea102-124">有关序列化的详细信息，请参阅<xref:System.Runtime.Serialization>。</span><span class="sxs-lookup"><span data-stu-id="ea102-124">For more information about serialization, see <xref:System.Runtime.Serialization>.</span></span>

### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="ea102-125">使用单个公共格式将数据添加到剪贴板</span><span class="sxs-lookup"><span data-stu-id="ea102-125">To add data to the Clipboard in a single, common format</span></span>

1. <span data-ttu-id="ea102-126">使用 <xref:System.Windows.Forms.Clipboard.SetAudio%2A> 、 <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A> 、 <xref:System.Windows.Forms.Clipboard.SetImage%2A> 或 <xref:System.Windows.Forms.Clipboard.SetText%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="ea102-126">Use the <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, or <xref:System.Windows.Forms.Clipboard.SetText%2A> method.</span></span> <span data-ttu-id="ea102-127">这些方法仅在 .NET Framework 2.0 中提供。</span><span class="sxs-lookup"><span data-stu-id="ea102-127">These methods are available only in .NET Framework 2.0.</span></span>

    [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
    [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]

### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a><span data-ttu-id="ea102-128">以自定义格式将数据添加到剪贴板</span><span class="sxs-lookup"><span data-stu-id="ea102-128">To add data to the Clipboard in a custom format</span></span>

1. <span data-ttu-id="ea102-129">使用 <xref:System.Windows.Forms.Clipboard.SetData%2A> 带有自定义格式名称的方法。</span><span class="sxs-lookup"><span data-stu-id="ea102-129">Use the <xref:System.Windows.Forms.Clipboard.SetData%2A> method with a custom format name.</span></span> <span data-ttu-id="ea102-130">此方法仅在 .NET Framework 2.0 中提供。</span><span class="sxs-lookup"><span data-stu-id="ea102-130">This method is available only in .NET Framework 2.0.</span></span>

    <span data-ttu-id="ea102-131">还可以通过方法使用预定义的格式名 <xref:System.Windows.Forms.Clipboard.SetData%2A> 。</span><span class="sxs-lookup"><span data-stu-id="ea102-131">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="ea102-132">有关详细信息，请参阅 <xref:System.Windows.Forms.DataFormats>。</span><span class="sxs-lookup"><span data-stu-id="ea102-132">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>

    [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
    [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a><span data-ttu-id="ea102-133">以多种格式将数据添加到剪贴板</span><span class="sxs-lookup"><span data-stu-id="ea102-133">To add data to the Clipboard in multiple formats</span></span>

1. <span data-ttu-id="ea102-134">使用 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A?displayProperty=nameWithType> 方法并传入 <xref:System.Windows.Forms.DataObject> 包含你的数据的。</span><span class="sxs-lookup"><span data-stu-id="ea102-134">Use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A?displayProperty=nameWithType> method and pass in a <xref:System.Windows.Forms.DataObject> that contains your data.</span></span> <span data-ttu-id="ea102-135">必须使用此方法将数据添加到 .NET Framework 2.0 之前版本的剪贴板上。</span><span class="sxs-lookup"><span data-stu-id="ea102-135">You must use this method to add data to the Clipboard on versions earlier than .NET Framework 2.0.</span></span>

    [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
    [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

## <a name="see-also"></a><span data-ttu-id="ea102-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea102-136">See also</span></span>

- [<span data-ttu-id="ea102-137">拖放操作和剪贴板支持</span><span class="sxs-lookup"><span data-stu-id="ea102-137">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
- [<span data-ttu-id="ea102-138">如何：从剪贴板检索数据</span><span class="sxs-lookup"><span data-stu-id="ea102-138">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
