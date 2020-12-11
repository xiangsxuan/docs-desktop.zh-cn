---
title: 如何：创建采用专业样式的 ToolStrip 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
ms.openlocfilehash: 4e4e899d583eb87b3ced7161f1fd274c0bcc591c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971872"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="5d2dc-102">如何：创建采用专业样式的 ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="5d2dc-102">How to: Create a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="5d2dc-103">可以通过编写自己的派生自 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 类型的类，赋予应用程序的 <xref:System.Windows.Forms.ToolStrip> 控件一个专业的外观和行为（外观和感受）。</span><span class="sxs-lookup"><span data-stu-id="5d2dc-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior (look and feel) by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="5d2dc-104">Visual Studio 中提供了此功能的广泛支持。</span><span class="sxs-lookup"><span data-stu-id="5d2dc-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="5d2dc-105">请参阅[演练：创建具有专业样式的 ToolStrip 控件](walkthrough-creating-a-professionally-styled-toolstrip-control.md)。</span><span class="sxs-lookup"><span data-stu-id="5d2dc-105">See [Walkthrough: Creating a Professionally Styled ToolStrip Control](walkthrough-creating-a-professionally-styled-toolstrip-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d2dc-106">示例</span><span class="sxs-lookup"><span data-stu-id="5d2dc-106">Example</span></span>  
 <span data-ttu-id="5d2dc-107">下面的代码示例演示如何使用 <xref:System.Windows.Forms.ToolStrip> 控件创建一个复合控件，该控件模拟 Microsoft® Outlook®提供的 **导航窗格** 。</span><span class="sxs-lookup"><span data-stu-id="5d2dc-107">The following code example demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that mimics the **Navigation Pane** provided by Microsoft® Outlook®.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5d2dc-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="5d2dc-108">Compiling the Code</span></span>  
 <span data-ttu-id="5d2dc-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="5d2dc-109">This example requires:</span></span>  
  
- <span data-ttu-id="5d2dc-110">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="5d2dc-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d2dc-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d2dc-111">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="5d2dc-112">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="5d2dc-112">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="5d2dc-113">如何：向窗体提供标准菜单项</span><span class="sxs-lookup"><span data-stu-id="5d2dc-113">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
