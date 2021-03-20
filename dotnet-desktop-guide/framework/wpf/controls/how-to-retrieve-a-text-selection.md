---
title: 如何：检索文本选定内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
ms.openlocfilehash: b86dc729c49d8e3953cad8c4c34d07660b2af482
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668391"
---
# <a name="how-to-retrieve-a-text-selection"></a><span data-ttu-id="07804-102">如何：检索文本选定内容</span><span class="sxs-lookup"><span data-stu-id="07804-102">How to: Retrieve a Text Selection</span></span>
<span data-ttu-id="07804-103">此示例演示了使用 <xref:System.Windows.Controls.TextBox.SelectedText%2A> 属性来检索用户在控件中选定的文本的一种方法 <xref:System.Windows.Controls.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="07804-103">This example shows one way to use the <xref:System.Windows.Controls.TextBox.SelectedText%2A> property to retrieve text that the user has selected in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07804-104">示例</span><span class="sxs-lookup"><span data-stu-id="07804-104">Example</span></span>  
 <span data-ttu-id="07804-105">下面的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 示例演示 <xref:System.Windows.Controls.TextBox> 包含要选择的一些文本的控件的定义，以及一个 <xref:System.Windows.Controls.Button> 具有指定方法的控件 <xref:System.Windows.Controls.Button.OnClick%2A> 。</span><span class="sxs-lookup"><span data-stu-id="07804-105">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] example shows the definition of a <xref:System.Windows.Controls.TextBox> control that contains some text to select, and a <xref:System.Windows.Controls.Button> control with a specified <xref:System.Windows.Controls.Button.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="07804-106">在此示例中，将使用带有关联 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件处理程序的按钮来检索所选文本。</span><span class="sxs-lookup"><span data-stu-id="07804-106">In this example, a button with an associated <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler is used to retrieve the text selection.</span></span> <span data-ttu-id="07804-107">当用户单击该按钮时，该 <xref:System.Windows.Controls.Button.OnClick%2A> 方法会将文本框中的任何选定文本复制到一个字符串中。</span><span class="sxs-lookup"><span data-stu-id="07804-107">When the user clicks the button, the <xref:System.Windows.Controls.Button.OnClick%2A> method copies any selected text in the textbox into a string.</span></span> <span data-ttu-id="07804-108"> (单击按钮) 来检索文本选择的特定情况，以及使用该选择执行的操作 (将文本选择复制到字符串) ，可以轻松地对其进行修改以适应各种方案。</span><span class="sxs-lookup"><span data-stu-id="07804-108">The particular circumstances by which the text selection is retrieved (clicking a button), as well as the action taken with that selection (copying the text selection to a string), can easily be modified to accommodate a wide variety of scenarios.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a><span data-ttu-id="07804-109">示例</span><span class="sxs-lookup"><span data-stu-id="07804-109">Example</span></span>  
 <span data-ttu-id="07804-110">下面的 c # 示例显示 <xref:System.Windows.Controls.Button.OnClick%2A> 了在的中为此示例中定义的按钮的事件处理程序 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="07804-110">The following C# example shows an <xref:System.Windows.Controls.Button.OnClick%2A> event handler for the button defined in the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] for this example.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a><span data-ttu-id="07804-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="07804-111">See also</span></span>

- [<span data-ttu-id="07804-112">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="07804-112">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="07804-113">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="07804-113">RichTextBox Overview</span></span>](richtextbox-overview.md)
