---
title: 如何：将 TextBox 控件设为只读
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 45fda33b5840bd89dac8d9e99f7dd1a8dd065838
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973090"
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="c8b8d-102">如何：将 TextBox 控件设为只读</span><span class="sxs-lookup"><span data-stu-id="c8b8d-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="c8b8d-103">此示例演示如何将控件配置 <xref:System.Windows.Controls.TextBox> 为不允许用户输入或修改。</span><span class="sxs-lookup"><span data-stu-id="c8b8d-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8b8d-104">示例</span><span class="sxs-lookup"><span data-stu-id="c8b8d-104">Example</span></span>  
 <span data-ttu-id="c8b8d-105">若要防止用户修改控件的内容 <xref:System.Windows.Controls.TextBox> ，请将属性设置 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 为 **true**。</span><span class="sxs-lookup"><span data-stu-id="c8b8d-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="c8b8d-106"><xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>特性仅影响用户输入; 不影响控件说明中设置的文本 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Controls.TextBox> 或通过属性以编程方式设置的文本 <xref:System.Windows.Controls.TextBox.Text%2A> 。</span><span class="sxs-lookup"><span data-stu-id="c8b8d-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="c8b8d-107">的默认值 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 为 **false**。</span><span class="sxs-lookup"><span data-stu-id="c8b8d-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8b8d-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8b8d-108">See also</span></span>

- [<span data-ttu-id="c8b8d-109">TextBox 概述</span><span class="sxs-lookup"><span data-stu-id="c8b8d-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="c8b8d-110">RichTextBox 概述</span><span class="sxs-lookup"><span data-stu-id="c8b8d-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
