---
title: RichTextBox 控件概述
ms.date: 03/30/2017
f1_keywords:
- RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
ms.openlocfilehash: 0d40967d97622b23e9dcb07e861f190327e6baba
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972000"
---
# <a name="richtextbox-control-overview-windows-forms"></a>RichTextBox 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.RichTextBox> 控件用于显示、输入和操作带有格式设置的文本。 <xref:System.Windows.Forms.RichTextBox>控件执行控件的所有操作 <xref:System.Windows.Forms.TextBox> ，但它还可以显示字体、颜色和链接; 从文件中加载文本和嵌入图像; 以及查找指定字符。 <xref:System.Windows.Forms.RichTextBox>控件通常用于提供文本操作和显示功能，类似于 word 处理应用程序（如 Microsoft word）。 与 <xref:System.Windows.Forms.TextBox> 控件一样， <xref:System.Windows.Forms.RichTextBox> 控件可以显示滚动条; 但与控件不同 <xref:System.Windows.Forms.TextBox> ，其默认设置是根据需要同时显示水平滚动条和垂直滚动条，并且具有其他滚动条设置。  
  
## <a name="working-with-the-richtextbox-control"></a>使用 RichTextBox 控件  
 与控件一样 <xref:System.Windows.Forms.TextBox> ，显示的文本由 <xref:System.Windows.Forms.RichTextBox.Text%2A> 属性设置。 <xref:System.Windows.Forms.RichTextBox>控件具有大量用于设置文本格式的属性。 有关这些属性的详细信息，请参阅[如何：为 Windows 窗体 RichTextBox 控件设置字体特性](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)和[如何：在 Windows 窗体 RichTextBox 控件中设置缩进、悬挂缩进和带项目符号的段落](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)。 若要操作文件， <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> 和 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 方法可以显示和写入多个文件格式（包括纯文本、Unicode 纯文本和 rtf)  (rtf 格式）。 中列出了可能的文件格式 <xref:System.Windows.Forms.RichTextBoxStreamType> 。 您可以使用 <xref:System.Windows.Forms.RichTextBox.Find%2A> 方法来查找文本字符串或特定字符。  
  
 还可以 <xref:System.Windows.Forms.RichTextBox> 通过将 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> 属性设置为 `true` ，并编写代码来处理事件，从而将控件用于 Web 样式链接 <xref:System.Windows.Forms.RichTextBox.LinkClicked> 。 有关详细信息，请参阅[如何：使用 Windows 窗体 RichTextBox 控件显示 Web 样式的链接](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)。 可以通过将属性设置为，阻止用户操作控件中的部分或全部文本 <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> `true` 。  
  
 <xref:System.Windows.Forms.RichTextBox>通过调用和方法，可以撤消和重做控件中大多数编辑 <xref:System.Windows.Forms.TextBoxBase.Undo%2A> 操作 <xref:System.Windows.Forms.RichTextBox.Redo%2A> 。 <xref:System.Windows.Forms.RichTextBox.CanRedo%2A>方法使你可以确定用户已撤消的上一个操作是否可以重新应用到控件。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox 控件](richtextbox-control-windows-forms.md)
- [TextBox 控件概述](textbox-control-overview-windows-forms.md)
