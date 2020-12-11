---
title: 批注概述
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- highlights [WPF]
- documents [WPF], annotations
- sticky notes [WPF]
ms.assetid: 716bf474-29bd-4c74-84a4-8e0744bdad62
ms.openlocfilehash: 8cfd5ddd1d90e9995081cd47211e1d9b0462b100
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973408"
---
# <a name="annotations-overview"></a><span data-ttu-id="b5a78-102">批注概述</span><span class="sxs-lookup"><span data-stu-id="b5a78-102">Annotations Overview</span></span>

<span data-ttu-id="b5a78-103">在纸质文档上编写说明或注释毫不稀奇，我们几乎认为这是理所当然的。</span><span class="sxs-lookup"><span data-stu-id="b5a78-103">Writing notes or comments on paper documents is such a commonplace activity that we almost take it for granted.</span></span> <span data-ttu-id="b5a78-104">这些说明或注释就是“批注”，我们将其添加到文档，用于标注信息或突出显示兴趣项以供日后参考。</span><span class="sxs-lookup"><span data-stu-id="b5a78-104">These notes or comments are "annotations" that we add to a document to flag information or to highlight items of interest for later reference.</span></span> <span data-ttu-id="b5a78-105">虽然在打印文档上编写注释很简单也很平常，但是就算在所有电子文档上添加个人注释，功能上却通常有很多限制。</span><span class="sxs-lookup"><span data-stu-id="b5a78-105">Although writing notes on printed documents is easy and commonplace, the ability to add personal comments to electronic documents is typically very limited, if available at all.</span></span>  
  
 <span data-ttu-id="b5a78-106">本主题将回顾几种常见类型的批注，特别是粘滞便笺和突出显示内容，并说明 Microsoft 批注框架如何通过 Windows Presentation Foundation (WPF) 文档查看控件来帮助应用程序中的这些类型的批注。</span><span class="sxs-lookup"><span data-stu-id="b5a78-106">This topic reviews several common types of annotations, specifically sticky notes and highlights, and illustrates how the Microsoft Annotations Framework facilitates these types of annotations in applications through the Windows Presentation Foundation (WPF) document viewing controls.</span></span>  <span data-ttu-id="b5a78-107">支持批注的 WPF 文档查看控件包括 <xref:System.Windows.Controls.FlowDocumentReader> 和 <xref:System.Windows.Controls.FlowDocumentScrollViewer> ，以及派生自和的控件 <xref:System.Windows.Controls.Primitives.DocumentViewerBase> <xref:System.Windows.Controls.DocumentViewer> <xref:System.Windows.Controls.FlowDocumentPageViewer> 。</span><span class="sxs-lookup"><span data-stu-id="b5a78-107">WPF document viewing controls that support annotations include <xref:System.Windows.Controls.FlowDocumentReader> and <xref:System.Windows.Controls.FlowDocumentScrollViewer>, as well as controls derived from <xref:System.Windows.Controls.Primitives.DocumentViewerBase> such as <xref:System.Windows.Controls.DocumentViewer> and <xref:System.Windows.Controls.FlowDocumentPageViewer>.</span></span>  

<a name="caf1_type_stickynotes"></a>

## <a name="sticky-notes"></a><span data-ttu-id="b5a78-108">便笺</span><span class="sxs-lookup"><span data-stu-id="b5a78-108">Sticky Notes</span></span>  

 <span data-ttu-id="b5a78-109">平常的便笺是将信息写在小块彩纸上，随后将这张彩纸“粘贴”到文档。</span><span class="sxs-lookup"><span data-stu-id="b5a78-109">A typical sticky note contains information written on a small piece of colored paper that is then "stuck" to a document.</span></span> <span data-ttu-id="b5a78-110">数字便笺为电子文档提供了类似的功能，但具有更大的灵活性，可包含许多其他类型的内容，例如键入文本、手写附注 (例如，Tablet PC "ink" 笔划) 或 Web 链接。</span><span class="sxs-lookup"><span data-stu-id="b5a78-110">Digital sticky notes provide similar functionality for electronic documents, but with the added flexibility to include many other types of content such as typed text, handwritten notes (for example, Tablet PC "ink" strokes), or Web links.</span></span>  
  
 <span data-ttu-id="b5a78-111">下图显示了突出显示、文本便笺以及墨迹便笺批注的一些示例。</span><span class="sxs-lookup"><span data-stu-id="b5a78-111">The following illustration shows some examples of highlight, text sticky note, and ink sticky note annotations.</span></span>  
  
 <span data-ttu-id="b5a78-112">![突出显示、文本和墨迹便笺批注。](./media/caf-stickynote.jpg "CAF_StickyNote")</span><span class="sxs-lookup"><span data-stu-id="b5a78-112">![Highlight, text and ink sticky note annotations.](./media/caf-stickynote.jpg "CAF_StickyNote")</span></span>  
  
 <span data-ttu-id="b5a78-113">下面的示例演示了可用于在应用程序中启用批注支持的方法。</span><span class="sxs-lookup"><span data-stu-id="b5a78-113">The following example shows the method that you can use to enable annotation support in your application.</span></span>  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>

## <a name="highlights"></a><span data-ttu-id="b5a78-114">亮点</span><span class="sxs-lookup"><span data-stu-id="b5a78-114">Highlights</span></span>  

 <span data-ttu-id="b5a78-115">当人们在纸质文档上作标记时，往往使用创造性的方法来突出显示兴趣项，例如对于句子中的某些字词，加下划线、高亮显示、圈出，或者将在空白的地方绘制标记或符号。</span><span class="sxs-lookup"><span data-stu-id="b5a78-115">People use creative methods to draw attention to items of interest when they mark up a paper document, such as underlining, highlighting, circling words in a sentence, or drawing marks or notations in the margin.</span></span>  <span data-ttu-id="b5a78-116">Microsoft 批注框架中的突出显示批注提供了一个类似的功能，用于标记 WPF 文档查看控件中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="b5a78-116">Highlight annotations in Microsoft Annotations Framework provide a similar feature for marking up information displayed in WPF document viewing controls.</span></span>  
  
 <span data-ttu-id="b5a78-117">下图演示了一个突出显示批注的示例。</span><span class="sxs-lookup"><span data-stu-id="b5a78-117">The following illustration shows an example of a highlight annotation.</span></span>  
  
 <span data-ttu-id="b5a78-118">![突出显示批注](./media/caf-callouts.png "CAF_Callouts")</span><span class="sxs-lookup"><span data-stu-id="b5a78-118">![Highlight Annotation](./media/caf-callouts.png "CAF_Callouts")</span></span>  
  
 <span data-ttu-id="b5a78-119">用户通常通过首先选择某个文本或感兴趣的项来创建批注，然后右键单击以显示 <xref:System.Windows.Controls.ContextMenu> 批注选项的。</span><span class="sxs-lookup"><span data-stu-id="b5a78-119">Users typically create annotations by first selecting some text or an item of interest, and then right-clicking to display a <xref:System.Windows.Controls.ContextMenu> of annotation options.</span></span>  <span data-ttu-id="b5a78-120">下面的示例演示了如何 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 使用 <xref:System.Windows.Controls.ContextMenu> 路由命令声明，用户可以访问这些命令来创建和管理批注。</span><span class="sxs-lookup"><span data-stu-id="b5a78-120">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] you can use to declare a <xref:System.Windows.Controls.ContextMenu> with routed commands that users can access to create and manage annotations.</span></span>  
  
 [!code-xaml[DocViewerAnnotationsXps#CreateDeleteAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>

## <a name="data-anchoring"></a><span data-ttu-id="b5a78-121">数据锚定</span><span class="sxs-lookup"><span data-stu-id="b5a78-121">Data Anchoring</span></span>  

 <span data-ttu-id="b5a78-122">批注框架将批注绑定到用户选择的数据，而不只是显示在显示视图上的某个位置。</span><span class="sxs-lookup"><span data-stu-id="b5a78-122">The Annotations Framework binds annotations to the data that the user selects, not just to a position on the display view.</span></span> <span data-ttu-id="b5a78-123">因此，如果文档视图更改（例如，当用户滚动显示窗口或者调整其大小时），批注将仍然跟随它绑定到的所选数据。</span><span class="sxs-lookup"><span data-stu-id="b5a78-123">Therefore, if the document view changes, such as when the user scrolls or resizes the display window, the annotation stays with the data selection to which it is bound.</span></span> <span data-ttu-id="b5a78-124">例如，下图显示了用户在所选文本上做的批注。</span><span class="sxs-lookup"><span data-stu-id="b5a78-124">For example, the following graphic illustrates an annotation that the user has made on a text selection.</span></span> <span data-ttu-id="b5a78-125">当文档视图更改时（滚动、调整大小、缩放或者移动），突出显示批注将与最初所选数据一起移动。</span><span class="sxs-lookup"><span data-stu-id="b5a78-125">When the document view changes (scrolls, resizes, scales, or otherwise moves), the highlight annotation moves with the original data selection.</span></span>  
  
 <span data-ttu-id="b5a78-126">![批注数据锚定](./media/caf-dataanchoring.png "CAF_DataAnchoring")</span><span class="sxs-lookup"><span data-stu-id="b5a78-126">![Annotation Data Anchoring](./media/caf-dataanchoring.png "CAF_DataAnchoring")</span></span>  
  
<a name="matching_annotations_with_annotated_objects"></a>

## <a name="matching-annotations-with-annotated-objects"></a><span data-ttu-id="b5a78-127">匹配批注与批注对象</span><span class="sxs-lookup"><span data-stu-id="b5a78-127">Matching Annotations with Annotated Objects</span></span>  

 <span data-ttu-id="b5a78-128">你可以将批注与对应的批注对象匹配。</span><span class="sxs-lookup"><span data-stu-id="b5a78-128">You can match annotations with the corresponding annotated objects.</span></span> <span data-ttu-id="b5a78-129">以具有注释窗格的简单文档读取器应用程序为例。</span><span class="sxs-lookup"><span data-stu-id="b5a78-129">For example, consider a simple document reader application that has a comments pane.</span></span> <span data-ttu-id="b5a78-130">注释窗格可能是一个列表框，用于显示锚定到文档的批注列表的文本。</span><span class="sxs-lookup"><span data-stu-id="b5a78-130">The comments pane might be a list box that displays the text from a list of annotations that are anchored to a document.</span></span> <span data-ttu-id="b5a78-131">如果用户在列表框中选择一项，应用程序将显示相应的批注对象所锚定到的文档段落。</span><span class="sxs-lookup"><span data-stu-id="b5a78-131">If the user selects an item in the list box, then the application brings into view the paragraph in the document that the corresponding annotation object is anchored to.</span></span>  
  
 <span data-ttu-id="b5a78-132">下面的示例演示如何实现充当注释窗格的此类列表框的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b5a78-132">The following example demonstrates how to implement the event handler of such a list box that serves as the comments pane.</span></span>  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 <span data-ttu-id="b5a78-133">另一个示例方案包括允许通过电子邮件在文档读取器之间交换批注和便笺的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b5a78-133">Another example scenario involves applications that enable the exchange of annotations and sticky notes between document readers through email.</span></span> <span data-ttu-id="b5a78-134">凭借此功能，这些应用程序可以将读取器导航到包含要交换的批注的页面。</span><span class="sxs-lookup"><span data-stu-id="b5a78-134">This feature enables these applications to navigate the reader to the page that contains the annotation that is being exchanged.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5a78-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5a78-135">See also</span></span>

- <xref:System.Windows.Controls.Primitives.DocumentViewerBase>
- <xref:System.Windows.Controls.DocumentViewer>
- <xref:System.Windows.Controls.FlowDocumentPageViewer>
- <xref:System.Windows.Controls.FlowDocumentScrollViewer>
- <xref:System.Windows.Controls.FlowDocumentReader>
- <xref:System.Windows.Annotations.IAnchorInfo>
- [<span data-ttu-id="b5a78-136">批注架构</span><span class="sxs-lookup"><span data-stu-id="b5a78-136">Annotations Schema</span></span>](annotations-schema.md)
- [<span data-ttu-id="b5a78-137">ContextMenu 概述</span><span class="sxs-lookup"><span data-stu-id="b5a78-137">ContextMenu Overview</span></span>](../controls/contextmenu-overview.md)
- [<span data-ttu-id="b5a78-138">命令概述</span><span class="sxs-lookup"><span data-stu-id="b5a78-138">Commanding Overview</span></span>](commanding-overview.md)
- [<span data-ttu-id="b5a78-139">流文档概述</span><span class="sxs-lookup"><span data-stu-id="b5a78-139">Flow Document Overview</span></span>](flow-document-overview.md)
- <span data-ttu-id="b5a78-140">[如何：将命令添加到菜单项](/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b5a78-140">[How to: Add a Command to a MenuItem](/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))</span></span>
