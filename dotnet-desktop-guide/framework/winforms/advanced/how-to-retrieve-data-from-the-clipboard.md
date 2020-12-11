---
title: 如何：从剪贴板检索数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
ms.openlocfilehash: ca24615049abcc145698c033f31e6c98a38253bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971421"
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a><span data-ttu-id="bcc7c-102">如何：从剪贴板检索数据</span><span class="sxs-lookup"><span data-stu-id="bcc7c-102">How to: Retrieve Data from the Clipboard</span></span>

<span data-ttu-id="bcc7c-103"><xref:System.Windows.Forms.Clipboard>类提供可用于与 Windows 操作系统剪贴板功能进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="bcc7c-104">许多应用程序使用剪贴板作为数据的临时存储库。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="bcc7c-105">例如，在剪切和粘贴操作期间，word 处理器使用剪贴板。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="bcc7c-106">剪贴板还有助于将信息从一个应用程序传输到另一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-106">The Clipboard is also useful for transferring information from one application to another.</span></span>

<span data-ttu-id="bcc7c-107">某些应用程序以多种格式将数据存储在剪贴板上，以增加可能使用数据的其他应用程序的数目。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-107">Some applications store data on the Clipboard in multiple formats to increase the number of other applications that can potentially use the data.</span></span> <span data-ttu-id="bcc7c-108">剪贴板格式是标识格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-108">A Clipboard format is a string that identifies the format.</span></span> <span data-ttu-id="bcc7c-109">使用标识格式的应用程序可以检索剪贴板上关联的数据。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-109">An application that uses the identified format can retrieve the associated data on the Clipboard.</span></span> <span data-ttu-id="bcc7c-110"><xref:System.Windows.Forms.DataFormats>类提供预定义的格式名称供你使用。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="bcc7c-111">你还可以使用自己的格式名，或者使用对象的类型作为其格式。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-111">You can also use your own format names or use an object's type as its format.</span></span> <span data-ttu-id="bcc7c-112">有关将数据添加到剪贴板的信息，请参阅 [如何：将数据添加到剪贴板](how-to-add-data-to-the-clipboard.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-112">For information about adding data to the Clipboard, see [How to: Add Data to the Clipboard](how-to-add-data-to-the-clipboard.md).</span></span>

<span data-ttu-id="bcc7c-113">若要确定剪贴板是否包含特定格式的数据，请使用 `Contains` *格式* 方法或 <xref:System.Windows.Forms.Clipboard.GetData%2A> 方法之一。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-113">To determine whether the Clipboard contains data in a particular format, use one of the `Contains`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="bcc7c-114">若要从剪贴板检索数据，请使用 `Get` *格式* 方法或 <xref:System.Windows.Forms.Clipboard.GetData%2A> 方法之一。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-114">To retrieve data from the Clipboard, use one of the `Get`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="bcc7c-115">这些方法是 .NET Framework 2.0 中的新方法。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-115">These methods are new in .NET Framework 2.0.</span></span>

<span data-ttu-id="bcc7c-116">若要使用 .NET Framework 2.0 以前的版本访问剪贴板中的数据，请使用 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A?displayProperty=nameWithType> 方法并调用返回的的方法 <xref:System.Windows.Forms.IDataObject> 。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-116">To access data from the Clipboard by using versions earlier than .NET Framework 2.0, use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A?displayProperty=nameWithType> method and call the methods of the returned <xref:System.Windows.Forms.IDataObject>.</span></span> <span data-ttu-id="bcc7c-117">例如，若要确定特定格式在返回的对象中是否可用，请调用 <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-117">To determine whether a particular format is available in the returned object, for example, call the <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> method.</span></span>

> [!NOTE]
> <span data-ttu-id="bcc7c-118">所有基于 Windows 的应用程序共享系统剪贴板。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-118">All Windows-based applications share the system Clipboard.</span></span> <span data-ttu-id="bcc7c-119">因此，当你切换到另一个应用程序时，内容可能会更改。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-119">Therefore, the contents are subject to change when you switch to another application.</span></span>
>
> <span data-ttu-id="bcc7c-120"><xref:System.Windows.Forms.Clipboard>类只能在设置为单线程单元 (STA) 模式的线程中使用。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-120">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="bcc7c-121">若要使用此类，请确保使用 `Main` 特性标记方法 <xref:System.STAThreadAttribute> 。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-121">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>

### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="bcc7c-122">使用单个公共格式从剪贴板检索数据</span><span class="sxs-lookup"><span data-stu-id="bcc7c-122">To retrieve data from the Clipboard in a single, common format</span></span>

1. <span data-ttu-id="bcc7c-123">使用 <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A> 、 <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A> 、 <xref:System.Windows.Forms.Clipboard.GetImage%2A> 或 <xref:System.Windows.Forms.Clipboard.GetText%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-123">Use the <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, or <xref:System.Windows.Forms.Clipboard.GetText%2A> method.</span></span> <span data-ttu-id="bcc7c-124">（可选）首先使用相应的 `Contains` *格式* 方法来确定是否有特定格式的数据。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-124">Optionally, use the corresponding `Contains`*Format* methods first to determine whether data is available in a particular format.</span></span> <span data-ttu-id="bcc7c-125">这些方法仅在 .NET Framework 2.0 中提供。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-125">These methods are available only in .NET Framework 2.0.</span></span>

    [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
    [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]

### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a><span data-ttu-id="bcc7c-126">以自定义格式从剪贴板检索数据</span><span class="sxs-lookup"><span data-stu-id="bcc7c-126">To retrieve data from the Clipboard in a custom format</span></span>

1. <span data-ttu-id="bcc7c-127">使用 <xref:System.Windows.Forms.Clipboard.GetData%2A> 带有自定义格式名称的方法。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-127">Use the <xref:System.Windows.Forms.Clipboard.GetData%2A> method with a custom format name.</span></span> <span data-ttu-id="bcc7c-128">此方法仅在 .NET Framework 2.0 中提供。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-128">This method is available only in .NET Framework 2.0.</span></span>

    <span data-ttu-id="bcc7c-129">还可以通过方法使用预定义的格式名 <xref:System.Windows.Forms.Clipboard.SetData%2A> 。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-129">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="bcc7c-130">有关详细信息，请参阅 <xref:System.Windows.Forms.DataFormats>。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-130">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>

    [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
    [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a><span data-ttu-id="bcc7c-131">以多种格式从剪贴板检索数据</span><span class="sxs-lookup"><span data-stu-id="bcc7c-131">To retrieve data from the Clipboard in multiple formats</span></span>

1. <span data-ttu-id="bcc7c-132">使用 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-132">Use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> method.</span></span> <span data-ttu-id="bcc7c-133">必须使用此方法从剪贴板上检索早于 .NET Framework 2.0 的版本的数据。</span><span class="sxs-lookup"><span data-stu-id="bcc7c-133">You must use this method to retrieve data from the Clipboard on versions earlier than .NET Framework 2.0.</span></span>

    [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
    [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

## <a name="see-also"></a><span data-ttu-id="bcc7c-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcc7c-134">See also</span></span>

- [<span data-ttu-id="bcc7c-135">拖放操作和剪贴板支持</span><span class="sxs-lookup"><span data-stu-id="bcc7c-135">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
- [<span data-ttu-id="bcc7c-136">如何：将数据添加到剪贴板</span><span class="sxs-lookup"><span data-stu-id="bcc7c-136">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
