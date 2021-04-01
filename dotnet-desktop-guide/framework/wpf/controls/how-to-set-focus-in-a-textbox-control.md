---
title: 如何：设置 TextBox 控件中的焦点
description: 了解如何使用 Focus 方法在 Windows Presentation Foundation TextBox 控件上设置焦点。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus [WPF], setting
- TextBox control [WPF], setting focus
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
ms.openlocfilehash: e4c6a174ba0353b89225d2337f138f9feeac947c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972782"
---
# <a name="how-to-set-focus-in-a-textbox-control"></a><span data-ttu-id="2a385-103">如何：设置 TextBox 控件中的焦点</span><span class="sxs-lookup"><span data-stu-id="2a385-103">How to: Set Focus in a TextBox Control</span></span>
<span data-ttu-id="2a385-104">此示例演示如何使用 <xref:System.Windows.UIElement.Focus%2A> 方法在控件上设置焦点 <xref:System.Windows.Controls.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="2a385-104">This example shows how to use the <xref:System.Windows.UIElement.Focus%2A> method to set focus on a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a385-105">示例</span><span class="sxs-lookup"><span data-stu-id="2a385-105">Example</span></span>  
 <span data-ttu-id="2a385-106">下面的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 示例介绍一个 <xref:System.Windows.Controls.TextBox> 名为 *tbFocusMe* 的简单控件。</span><span class="sxs-lookup"><span data-stu-id="2a385-106">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] example describes a simple <xref:System.Windows.Controls.TextBox> control named *tbFocusMe*</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a><span data-ttu-id="2a385-107">示例</span><span class="sxs-lookup"><span data-stu-id="2a385-107">Example</span></span>  
 <span data-ttu-id="2a385-108">下面的示例调用 <xref:System.Windows.UIElement.Focus%2A> 方法，以将焦点设置到 <xref:System.Windows.Controls.TextBox> 名为 *tbFocusMe* 的控件上。</span><span class="sxs-lookup"><span data-stu-id="2a385-108">The following example calls the <xref:System.Windows.UIElement.Focus%2A> method to set the focus on the <xref:System.Windows.Controls.TextBox> control with the Name *tbFocusMe*.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a><span data-ttu-id="2a385-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a385-109">See also</span></span>

- <xref:System.Windows.UIElement.Focusable%2A>
- <xref:System.Windows.UIElement.IsFocused%2A>
- [<span data-ttu-id="2a385-110">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="2a385-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="2a385-111">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="2a385-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
