---
title: 如何：从 TextBox 获取线条集合
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: b7b2f1c2e071388635fb50b1e3573fd7f44334dd
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973315"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a><span data-ttu-id="c6bd7-102">如何：从 TextBox 获取线条集合</span><span class="sxs-lookup"><span data-stu-id="c6bd7-102">How to: Get a Collection of Lines from a TextBox</span></span>
<span data-ttu-id="c6bd7-103">此示例演示如何从获取文本行的集合 <xref:System.Windows.Controls.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="c6bd7-103">This example shows how to get a collection of lines of text from a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6bd7-104">示例</span><span class="sxs-lookup"><span data-stu-id="c6bd7-104">Example</span></span>  
 <span data-ttu-id="c6bd7-105">下面的示例演示了一个简单的方法，该方法采用 <xref:System.Windows.Controls.TextBox> 作为参数，并返回 <xref:System.Collections.Specialized.StringCollection> 包含 **文本框** 中的文本行的。</span><span class="sxs-lookup"><span data-stu-id="c6bd7-105">The following example shows a simple method that takes a <xref:System.Windows.Controls.TextBox> as the argument, and returns a <xref:System.Collections.Specialized.StringCollection> containing the lines of text in the **TextBox**.</span></span>  <span data-ttu-id="c6bd7-106"><xref:System.Windows.Controls.TextBox.LineCount%2A>属性用于确定 **文本框** 中当前有多少行， <xref:System.Windows.Controls.TextBox.GetLineText%2A> 然后使用方法提取每行并将其添加到行集合中。</span><span class="sxs-lookup"><span data-stu-id="c6bd7-106">The <xref:System.Windows.Controls.TextBox.LineCount%2A> property is used to determine how many lines are currently in the **TextBox**, and the <xref:System.Windows.Controls.TextBox.GetLineText%2A> method is then used to extract each line and add it to the collection of lines.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a><span data-ttu-id="c6bd7-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6bd7-107">See also</span></span>

- [<span data-ttu-id="c6bd7-108">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="c6bd7-108">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="c6bd7-109">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="c6bd7-109">RichTextBox Overview</span></span>](richtextbox-overview.md)
