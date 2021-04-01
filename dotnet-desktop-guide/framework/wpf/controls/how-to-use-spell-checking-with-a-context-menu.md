---
title: 如何：使用上下文菜单中的拼写检查功能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
ms.openlocfilehash: 0c2ceb3e4091ee1d98bd0c786f51b3596cdedd08
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970489"
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a><span data-ttu-id="799b3-102">如何：使用上下文菜单中的拼写检查功能</span><span class="sxs-lookup"><span data-stu-id="799b3-102">How to: Use Spell Checking with a Context Menu</span></span>
<span data-ttu-id="799b3-103">默认情况下，当您在编辑控件（如或）中启用拼写检查时， <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> 您将获得上下文菜单中的拼写检查选项。</span><span class="sxs-lookup"><span data-stu-id="799b3-103">By default, when you enable spell checking in an editing control like <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>, you get spell-checking choices in the context menu.</span></span> <span data-ttu-id="799b3-104">例如，当用户右键单击拼写错误的单词时，它们会获得一组拼写建议或 **忽略所有** 的选项。</span><span class="sxs-lookup"><span data-stu-id="799b3-104">For example, when users right-click a misspelled word, they get a set of spelling suggestions or the option to **Ignore All**.</span></span> <span data-ttu-id="799b3-105">但是，当您用您自己的自定义上下文菜单替代默认上下文菜单时，此功能将丢失，您需要编写代码来重新启用上下文菜单中的拼写检查功能。</span><span class="sxs-lookup"><span data-stu-id="799b3-105">However, when you override the default context menu with your own custom context menu, this functionality is lost, and you need to write code to reenable the spell-checking feature in the context menu.</span></span> <span data-ttu-id="799b3-106">下面的示例演示如何在上启用此 <xref:System.Windows.Controls.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="799b3-106">The following example shows how to enable this on a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="799b3-107">示例</span><span class="sxs-lookup"><span data-stu-id="799b3-107">Example</span></span>  
 <span data-ttu-id="799b3-108">下面的示例演示了使用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Controls.TextBox> 一些用于实现上下文菜单的事件创建的。</span><span class="sxs-lookup"><span data-stu-id="799b3-108">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] that creates a <xref:System.Windows.Controls.TextBox> with some events that are used to implement the context menu.</span></span>  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="799b3-109">示例</span><span class="sxs-lookup"><span data-stu-id="799b3-109">Example</span></span>  
 <span data-ttu-id="799b3-110">下面的示例演示实现上下文菜单的代码。</span><span class="sxs-lookup"><span data-stu-id="799b3-110">The following example shows the code that implements the context menu.</span></span>  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 <span data-ttu-id="799b3-111">用于执行此操作的代码 <xref:System.Windows.Controls.RichTextBox> 类似于。</span><span class="sxs-lookup"><span data-stu-id="799b3-111">The code used for doing this with a <xref:System.Windows.Controls.RichTextBox> is similar.</span></span> <span data-ttu-id="799b3-112">主要区别在于传递给方法的参数 `GetSpellingError` 。</span><span class="sxs-lookup"><span data-stu-id="799b3-112">The main difference is in the parameter passed to the `GetSpellingError` method.</span></span> <span data-ttu-id="799b3-113">对于 <xref:System.Windows.Controls.TextBox> ，传递插入符号位置的整数索引：</span><span class="sxs-lookup"><span data-stu-id="799b3-113">For a <xref:System.Windows.Controls.TextBox>, pass the integer index of the caret position:</span></span>  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 <span data-ttu-id="799b3-114">对于 <xref:System.Windows.Controls.RichTextBox> ，传递 <xref:System.Windows.Documents.TextPointer> 指定插入符号位置的：</span><span class="sxs-lookup"><span data-stu-id="799b3-114">For a <xref:System.Windows.Controls.RichTextBox>, pass the <xref:System.Windows.Documents.TextPointer> that specifies the caret position:</span></span>  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a><span data-ttu-id="799b3-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="799b3-115">See also</span></span>

- [<span data-ttu-id="799b3-116">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="799b3-116">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="799b3-117">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="799b3-117">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="799b3-118">在文本编辑控件中启用拼写检查</span><span class="sxs-lookup"><span data-stu-id="799b3-118">Enable Spell Checking in a Text Editing Control</span></span>](how-to-enable-spell-checking-in-a-text-editing-control.md)
- [<span data-ttu-id="799b3-119">将自定义上下文菜单与 TextBox 结合使用</span><span class="sxs-lookup"><span data-stu-id="799b3-119">Use a Custom Context Menu with a TextBox</span></span>](how-to-use-a-custom-context-menu-with-a-textbox.md)
