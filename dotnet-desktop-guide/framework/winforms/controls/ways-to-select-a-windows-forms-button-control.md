---
title: 选择按钮控件的方式
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 145166d182f1ec51068ab3e0c23c12b471b69231
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972490"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="ecaf7-102">选择 Windows 窗体 Button 控件的方法</span><span class="sxs-lookup"><span data-stu-id="ecaf7-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="ecaf7-103">可以通过以下方式选择 Windows 窗体按钮：</span><span class="sxs-lookup"><span data-stu-id="ecaf7-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
- <span data-ttu-id="ecaf7-104">使用鼠标单击该按钮。</span><span class="sxs-lookup"><span data-stu-id="ecaf7-104">Use a mouse to click the button.</span></span>  
  
- <span data-ttu-id="ecaf7-105">在代码中调用该按钮的 <xref:System.Windows.Forms.Control.Click> 事件。</span><span class="sxs-lookup"><span data-stu-id="ecaf7-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
- <span data-ttu-id="ecaf7-106">按 TAB 键将焦点移到按钮上，然后按空格键或 ENTER 键以选择该按钮。</span><span class="sxs-lookup"><span data-stu-id="ecaf7-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
- <span data-ttu-id="ecaf7-107">按下访问键 (ALT + 按钮的带下划线的字母) 。</span><span class="sxs-lookup"><span data-stu-id="ecaf7-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="ecaf7-108">有关访问密钥的详细信息，请参阅 [如何：创建 Windows 窗体控件的访问键](how-to-create-access-keys-for-windows-forms-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="ecaf7-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
- <span data-ttu-id="ecaf7-109">如果该按钮是窗体的 "接受" 按钮，则按 ENTER 可选择该按钮，即使其他控件具有焦点也是如此，除非其他控件是另一个按钮、多行文本框或捕获 ENTER 键的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="ecaf7-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
- <span data-ttu-id="ecaf7-110">如果该按钮是窗体的 "取消" 按钮，则按 ESC 键会选择该按钮，即使另一个控件具有焦点也是如此。</span><span class="sxs-lookup"><span data-stu-id="ecaf7-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
- <span data-ttu-id="ecaf7-111">调用 <xref:System.Windows.Forms.Button.PerformClick%2A> 方法以编程方式选择按钮。</span><span class="sxs-lookup"><span data-stu-id="ecaf7-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecaf7-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ecaf7-112">See also</span></span>

- [<span data-ttu-id="ecaf7-113">Button 控件概述</span><span class="sxs-lookup"><span data-stu-id="ecaf7-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="ecaf7-114">如何：响应 Windows 窗体按钮的单击</span><span class="sxs-lookup"><span data-stu-id="ecaf7-114">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="ecaf7-115">Button 控件</span><span class="sxs-lookup"><span data-stu-id="ecaf7-115">Button Control</span></span>](button-control-windows-forms.md)
