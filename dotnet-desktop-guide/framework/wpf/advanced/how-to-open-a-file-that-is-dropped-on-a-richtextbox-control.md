---
title: 如何：打开放置在 RichTextBox 控件上的文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], RichTextBox
- RichTextBox [WPF], drag-and-drop
- drag-and-drop [WPF], open a dropped file
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
ms.openlocfilehash: e3d0e9597b7ed69368f1755e146433d6e4bad9f6
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973653"
---
# <a name="how-to-open-a-file-that-is-dropped-on-a-richtextbox-control"></a><span data-ttu-id="7b577-102">如何：打开放置在 RichTextBox 控件上的文件</span><span class="sxs-lookup"><span data-stu-id="7b577-102">How to: Open a File That is Dropped on a RichTextBox Control</span></span>

<span data-ttu-id="7b577-103">在中， [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.TextBox> 、 <xref:System.Windows.Controls.RichTextBox> 和 <xref:System.Windows.Documents.FlowDocument> 控件都具有内置的拖放功能。</span><span class="sxs-lookup"><span data-stu-id="7b577-103">In [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], the <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> controls all have built-in drag-and-drop functionality.</span></span> <span data-ttu-id="7b577-104">内置功能可用于在控件内部和之间拖放文本。</span><span class="sxs-lookup"><span data-stu-id="7b577-104">The built-in functionality enables drag-and-drop of text within and between the controls.</span></span> <span data-ttu-id="7b577-105">但是，它不会通过将文件放在控件上来打开文件。</span><span class="sxs-lookup"><span data-stu-id="7b577-105">However, it does not enable opening a file by dropping the file on the control.</span></span> <span data-ttu-id="7b577-106">这些控件还将拖放事件标记为已处理。</span><span class="sxs-lookup"><span data-stu-id="7b577-106">These controls also mark the drag-and-drop events as handled.</span></span> <span data-ttu-id="7b577-107">因此，默认情况下，不能添加自己的事件处理程序来提供打开已删除文件的功能。</span><span class="sxs-lookup"><span data-stu-id="7b577-107">As a result, by default, you cannot add your own event handlers to provide functionality to open dropped files.</span></span>

<span data-ttu-id="7b577-108">若要为这些控件中的拖放事件添加其他处理，请使用 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> 方法添加拖放事件的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7b577-108">To add additional handling for drag-and-drop events in these controls, use the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method to add your event handlers for the drag-and-drop events.</span></span> <span data-ttu-id="7b577-109">将参数设置为，以便为已 `handledEventsToo` 标记为由 `true` 事件路由中的其他元素处理的路由事件调用指定的处理程序。</span><span class="sxs-lookup"><span data-stu-id="7b577-109">Set the `handledEventsToo` parameter to `true` to have the specified handler be invoked for a routed event that has already been marked as handled by another element along the event route.</span></span>

> [!TIP]
> <span data-ttu-id="7b577-110">可以 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.Documents.FlowDocument> 通过处理拖放事件的预览版本并将预览事件标记为 "已处理" 来替换、和的内置拖放功能。</span><span class="sxs-lookup"><span data-stu-id="7b577-110">You can replace the built-in drag-and-drop functionality of <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Documents.FlowDocument> by handling the preview versions of the drag-and-drop events and marking the preview events as handled.</span></span> <span data-ttu-id="7b577-111">但是，这将禁用内置的拖放功能，不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="7b577-111">However, this will disable the built-in drag-and-drop functionality, and is not recommended.</span></span>

## <a name="example"></a><span data-ttu-id="7b577-112">示例</span><span class="sxs-lookup"><span data-stu-id="7b577-112">Example</span></span>

<span data-ttu-id="7b577-113">下面的示例演示如何在中为和事件添加处理程序 <xref:System.Windows.DragDrop.DragOver> <xref:System.Windows.DragDrop.Drop> <xref:System.Windows.Controls.RichTextBox> 。</span><span class="sxs-lookup"><span data-stu-id="7b577-113">The following example demonstrates how to add handlers for the <xref:System.Windows.DragDrop.DragOver> and <xref:System.Windows.DragDrop.Drop> events on a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="7b577-114">此示例使用 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> 方法并将参数设置 `handledEventsToo` 为， `true` 以便即使将 <xref:System.Windows.Controls.RichTextBox> 这些事件标记为已处理，也会调用事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7b577-114">This example uses the <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> method and sets the `handledEventsToo` parameter to `true` so that the events handlers will be invoked even though the <xref:System.Windows.Controls.RichTextBox> marks these events as handled.</span></span> <span data-ttu-id="7b577-115">事件处理程序中的代码将添加功能，以打开在上放置的文本文件 <xref:System.Windows.Controls.RichTextBox> 。</span><span class="sxs-lookup"><span data-stu-id="7b577-115">The code in the event handlers adds functionality to open a text file that is dropped on the <xref:System.Windows.Controls.RichTextBox>.</span></span>

<span data-ttu-id="7b577-116">若要测试此示例，请从 Windows 资源管理器将文本文件或 rtf) 文件 (RTF 格式拖到 <xref:System.Windows.Controls.RichTextBox> 。</span><span class="sxs-lookup"><span data-stu-id="7b577-116">To test this example, drag a text file or a rich text format (RTF) file from Windows Explorer to the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="7b577-117">文件将在中打开 <xref:System.Windows.Controls.RichTextBox> 。</span><span class="sxs-lookup"><span data-stu-id="7b577-117">The file will be opened in the <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="7b577-118">如果在删除文件之前按下 SHIFT 键，则文件将以纯文本形式打开。</span><span class="sxs-lookup"><span data-stu-id="7b577-118">If you press the SHIFT key before the dropping the file, the file will be opened as plain text.</span></span>

[!code-xaml[DragDropSnippets#RtbXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]

[!code-csharp[DragDropSnippets#RtbHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
[!code-vb[DragDropSnippets#RtbHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]
