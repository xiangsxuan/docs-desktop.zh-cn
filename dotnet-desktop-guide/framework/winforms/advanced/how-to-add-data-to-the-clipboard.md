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
# <a name="how-to-add-data-to-the-clipboard"></a>如何：将数据添加到剪贴板

<xref:System.Windows.Forms.Clipboard>类提供可用于与 Windows 操作系统剪贴板功能进行交互的方法。 许多应用程序使用剪贴板作为数据的临时存储库。 例如，在剪切和粘贴操作期间，word 处理器使用剪贴板。 剪贴板还适用于将数据从一个应用程序传输到另一个应用程序。

在将数据添加到剪贴板时，可以指示数据格式，以便其他应用程序能够使用该格式来识别数据。 你还可以使用多种不同的格式将数据添加到剪贴板，以增加可能使用数据的其他应用程序的数目。

剪贴板格式是标识格式的字符串，以便使用该格式的应用程序可以检索关联的数据。 <xref:System.Windows.Forms.DataFormats>类提供预定义的格式名称供你使用。 你还可以使用自己的格式名，或者使用对象的类型作为其格式。

若要以一种或多种格式向剪贴板中添加数据，请使用 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> 方法。 可以将任何对象传递给此方法，但若要添加多种格式的数据，必须首先将数据添加到旨在使用多种格式的单独对象。 通常，您需要将数据添加到 <xref:System.Windows.Forms.DataObject> ，但您可以使用任何实现接口的类型 <xref:System.Windows.Forms.IDataObject> 。

在 .NET Framework 2.0 中，可以通过使用旨在使基本剪贴板任务更简单的新方法，将数据直接添加到剪贴板。 当您使用单个公共格式（如文本）来处理数据时，请使用这些方法。

> [!NOTE]
> 所有基于 Windows 的应用程序共享剪贴板。 因此，当你切换到另一个应用程序时，内容可能会更改。
>
> <xref:System.Windows.Forms.Clipboard>类只能在设置为单线程单元 (STA) 模式的线程中使用。 若要使用此类，请确保使用 `Main` 特性标记方法 <xref:System.STAThreadAttribute> 。
>
> 对象必须是可序列化的，才能将其放在剪贴板上。 若要使类型可序列化，请使用属性对其进行标记 <xref:System.SerializableAttribute> 。 如果将非序列化对象传递到剪贴板方法，则该方法将失败，且不会引发异常。 有关序列化的详细信息，请参阅<xref:System.Runtime.Serialization>。

### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a>使用单个公共格式将数据添加到剪贴板

1. 使用 <xref:System.Windows.Forms.Clipboard.SetAudio%2A> 、 <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A> 、 <xref:System.Windows.Forms.Clipboard.SetImage%2A> 或 <xref:System.Windows.Forms.Clipboard.SetText%2A> 方法。 这些方法仅在 .NET Framework 2.0 中提供。

    [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
    [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]

### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a>以自定义格式将数据添加到剪贴板

1. 使用 <xref:System.Windows.Forms.Clipboard.SetData%2A> 带有自定义格式名称的方法。 此方法仅在 .NET Framework 2.0 中提供。

    还可以通过方法使用预定义的格式名 <xref:System.Windows.Forms.Clipboard.SetData%2A> 。 有关详细信息，请参阅 <xref:System.Windows.Forms.DataFormats>。

    [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
    [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a>以多种格式将数据添加到剪贴板

1. 使用 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A?displayProperty=nameWithType> 方法并传入 <xref:System.Windows.Forms.DataObject> 包含你的数据的。 必须使用此方法将数据添加到 .NET Framework 2.0 之前版本的剪贴板上。

    [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
    [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

## <a name="see-also"></a>另请参阅

- [拖放操作和剪贴板支持](drag-and-drop-operations-and-clipboard-support.md)
- [如何：从剪贴板检索数据](how-to-retrieve-data-from-the-clipboard.md)
