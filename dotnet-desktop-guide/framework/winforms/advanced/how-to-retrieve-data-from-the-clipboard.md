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
# <a name="how-to-retrieve-data-from-the-clipboard"></a>如何：从剪贴板检索数据

<xref:System.Windows.Forms.Clipboard>类提供可用于与 Windows 操作系统剪贴板功能进行交互的方法。 许多应用程序使用剪贴板作为数据的临时存储库。 例如，在剪切和粘贴操作期间，word 处理器使用剪贴板。 剪贴板还有助于将信息从一个应用程序传输到另一个应用程序。

某些应用程序以多种格式将数据存储在剪贴板上，以增加可能使用数据的其他应用程序的数目。 剪贴板格式是标识格式的字符串。 使用标识格式的应用程序可以检索剪贴板上关联的数据。 <xref:System.Windows.Forms.DataFormats>类提供预定义的格式名称供你使用。 你还可以使用自己的格式名，或者使用对象的类型作为其格式。 有关将数据添加到剪贴板的信息，请参阅 [如何：将数据添加到剪贴板](how-to-add-data-to-the-clipboard.md)。

若要确定剪贴板是否包含特定格式的数据，请使用 `Contains` *格式* 方法或 <xref:System.Windows.Forms.Clipboard.GetData%2A> 方法之一。 若要从剪贴板检索数据，请使用 `Get` *格式* 方法或 <xref:System.Windows.Forms.Clipboard.GetData%2A> 方法之一。 这些方法是 .NET Framework 2.0 中的新方法。

若要使用 .NET Framework 2.0 以前的版本访问剪贴板中的数据，请使用 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A?displayProperty=nameWithType> 方法并调用返回的的方法 <xref:System.Windows.Forms.IDataObject> 。 例如，若要确定特定格式在返回的对象中是否可用，请调用 <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> 方法。

> [!NOTE]
> 所有基于 Windows 的应用程序共享系统剪贴板。 因此，当你切换到另一个应用程序时，内容可能会更改。
>
> <xref:System.Windows.Forms.Clipboard>类只能在设置为单线程单元 (STA) 模式的线程中使用。 若要使用此类，请确保使用 `Main` 特性标记方法 <xref:System.STAThreadAttribute> 。

### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a>使用单个公共格式从剪贴板检索数据

1. 使用 <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A> 、 <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A> 、 <xref:System.Windows.Forms.Clipboard.GetImage%2A> 或 <xref:System.Windows.Forms.Clipboard.GetText%2A> 方法。 （可选）首先使用相应的 `Contains` *格式* 方法来确定是否有特定格式的数据。 这些方法仅在 .NET Framework 2.0 中提供。

    [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
    [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]

### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a>以自定义格式从剪贴板检索数据

1. 使用 <xref:System.Windows.Forms.Clipboard.GetData%2A> 带有自定义格式名称的方法。 此方法仅在 .NET Framework 2.0 中提供。

    还可以通过方法使用预定义的格式名 <xref:System.Windows.Forms.Clipboard.SetData%2A> 。 有关详细信息，请参阅 <xref:System.Windows.Forms.DataFormats>。

    [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
    [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a>以多种格式从剪贴板检索数据

1. 使用 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> 方法。 必须使用此方法从剪贴板上检索早于 .NET Framework 2.0 的版本的数据。

    [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
    [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

## <a name="see-also"></a>另请参阅

- [拖放操作和剪贴板支持](drag-and-drop-operations-and-clipboard-support.md)
- [如何：将数据添加到剪贴板](how-to-add-data-to-the-clipboard.md)
