---
title: 如何：设置 TextBox 控件的文本内容
description: 了解如何使用 Text 属性设置 Windows Presentation Foundation TextBox 控件的初始文本内容。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 1e2ebdf2e66f4668b215767919c358ac34e5bd38
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973588"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="6149c-103">如何：设置 TextBox 控件的文本内容</span><span class="sxs-lookup"><span data-stu-id="6149c-103">How to: Set the Text Content of a TextBox Control</span></span>

<span data-ttu-id="6149c-104">此示例演示如何使用 <xref:System.Windows.Controls.TextBox.Text%2A> 属性来设置控件的初始文本内容 <xref:System.Windows.Controls.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="6149c-104">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>

> [!NOTE]
> <span data-ttu-id="6149c-105">尽管该 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 示例的版本可以在 `<TextBox.Text>` 每个按钮内容的文本周围使用标记 <xref:System.Windows.Controls.TextBox> ，但这并不是必需的，因为将 <xref:System.Windows.Controls.TextBox> 特性应用于 <xref:System.Windows.Markup.ContentPropertyAttribute> <xref:System.Windows.Controls.TextBox.Text%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="6149c-105">Although the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="6149c-106">有关详细信息，请参阅 [XAML 概述 (WPF) ](/dotnet/desktop-wpf/fundamentals/xaml)。</span><span class="sxs-lookup"><span data-stu-id="6149c-106">For more information, see [XAML Overview (WPF)](/dotnet/desktop-wpf/fundamentals/xaml).</span></span>

## <a name="example"></a><span data-ttu-id="6149c-107">示例</span><span class="sxs-lookup"><span data-stu-id="6149c-107">Example</span></span>

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a><span data-ttu-id="6149c-108">示例</span><span class="sxs-lookup"><span data-stu-id="6149c-108">Example</span></span>

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a><span data-ttu-id="6149c-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6149c-109">See also</span></span>

- [<span data-ttu-id="6149c-110">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="6149c-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="6149c-111">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="6149c-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
