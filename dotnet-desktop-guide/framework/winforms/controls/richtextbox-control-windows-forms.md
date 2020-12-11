---
title: RichTextBox 控件
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- RichTextBox control [Windows Forms]
- rich edit controls
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
ms.openlocfilehash: 9d26ec7bfc4d75b304bbc9dc98dbbeaed64effe7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971513"
---
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="d24a4-102">RichTextBox 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="d24a4-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="d24a4-103">Windows 窗体 `RichTextBox` 控件用于显示、输入和操作带有格式设置的文本。</span><span class="sxs-lookup"><span data-stu-id="d24a4-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="d24a4-104">`RichTextBox`控件执行控件的所有操作 <xref:System.Windows.Forms.TextBox> ，但它还可以显示字体、颜色和链接; 从文件中加载文本和嵌入图像; 撤消和重做编辑操作; 以及查找指定字符。</span><span class="sxs-lookup"><span data-stu-id="d24a4-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="d24a4-105">`RichTextBox`控件通常用于提供文本操作和显示功能，类似于 word 处理应用程序（如 Microsoft word）。</span><span class="sxs-lookup"><span data-stu-id="d24a4-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="d24a4-106">与 <xref:System.Windows.Forms.TextBox> 控件类似， `RichTextBox` 控件可以显示滚动条; 但与控件不同 <xref:System.Windows.Forms.TextBox> ，默认情况下会显示水平滚动条和垂直滚动条，并具有其他滚动条设置。</span><span class="sxs-lookup"><span data-stu-id="d24a4-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d24a4-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="d24a4-107">In This Section</span></span>  
 [<span data-ttu-id="d24a4-108">RichTextBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="d24a4-108">RichTextBox Control Overview</span></span>](richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="d24a4-109">介绍控件的一般概念 `RichTextBox` ，该控件允许用户输入、显示和操作具有格式设置选项的文本。</span><span class="sxs-lookup"><span data-stu-id="d24a4-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="d24a4-110">如何：确定 Windows 窗体 RichTextBox 控件中的格式设置特性何时更改</span><span class="sxs-lookup"><span data-stu-id="d24a4-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="d24a4-111">说明如何在控件中跟踪字体和段落格式设置的更改 `RichTextBox` 。</span><span class="sxs-lookup"><span data-stu-id="d24a4-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="d24a4-112">如何：在 Windows 窗体 RichTextBox 控件中显示滚动条</span><span class="sxs-lookup"><span data-stu-id="d24a4-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="d24a4-113">介绍可用于控件中滚动条的多种选项 `RichTextBox` 。</span><span class="sxs-lookup"><span data-stu-id="d24a4-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="d24a4-114">如何：使用 Windows 窗体 RichTextBox 控件显示 Web 样式的链接</span><span class="sxs-lookup"><span data-stu-id="d24a4-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="d24a4-115">说明如何从控件链接到网站 `RichTextBox` 。</span><span class="sxs-lookup"><span data-stu-id="d24a4-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="d24a4-116">如何：使用 Windows 窗体 RichTextBox 控件启用拖放操作</span><span class="sxs-lookup"><span data-stu-id="d24a4-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="d24a4-117">提供有关将数据拖动到控件中的说明 `RichTextBox` 。</span><span class="sxs-lookup"><span data-stu-id="d24a4-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="d24a4-118">如何：将文件加载到 Windows 窗体 RichTextBox 控件中</span><span class="sxs-lookup"><span data-stu-id="d24a4-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="d24a4-119">提供有关将现有文件加载到控件中的说明 `RichTextBox` 。</span><span class="sxs-lookup"><span data-stu-id="d24a4-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="d24a4-120">如何：使用 Windows 窗体 RichTextBox 控件保存文件</span><span class="sxs-lookup"><span data-stu-id="d24a4-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="d24a4-121">提供有关将控件内容保存 `RichTextBox` 到文件中的说明。</span><span class="sxs-lookup"><span data-stu-id="d24a4-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="d24a4-122">如何：设置 Windows 窗体 RichTextBox 控件的字体特性</span><span class="sxs-lookup"><span data-stu-id="d24a4-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="d24a4-123">描述如何设置控件中文本的字体系列、大小、样式和颜色 `RichTextBox` 。</span><span class="sxs-lookup"><span data-stu-id="d24a4-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="d24a4-124">如何：使用 Windows 窗体 RichTextBox 控件设置缩进、悬挂缩进和点符段落</span><span class="sxs-lookup"><span data-stu-id="d24a4-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="d24a4-125">介绍如何设置控件中的段落格式 `RichTextBox` 。</span><span class="sxs-lookup"><span data-stu-id="d24a4-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d24a4-126">参考</span><span class="sxs-lookup"><span data-stu-id="d24a4-126">Reference</span></span>  
 <span data-ttu-id="d24a4-127"><xref:System.Windows.Forms.RichTextBox> 类</span><span class="sxs-lookup"><span data-stu-id="d24a4-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="d24a4-128">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="d24a4-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d24a4-129">相关章节</span><span class="sxs-lookup"><span data-stu-id="d24a4-129">Related Sections</span></span>  
 [<span data-ttu-id="d24a4-130">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="d24a4-130">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="d24a4-131">提供 Windows 窗体控件的完整列表，附带其使用情况相关信息的链接。</span><span class="sxs-lookup"><span data-stu-id="d24a4-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="d24a4-132">TextBox 控件</span><span class="sxs-lookup"><span data-stu-id="d24a4-132">TextBox Control</span></span>](textbox-control-windows-forms.md)  
 <span data-ttu-id="d24a4-133">介绍控件的一般概念 <xref:System.Windows.Forms.TextBox> ，该控件允许用户的可编辑多行输入。</span><span class="sxs-lookup"><span data-stu-id="d24a4-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>
