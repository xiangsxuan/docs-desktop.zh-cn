---
title: Label 控件概述
ms.date: 03/30/2017
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
ms.openlocfilehash: 1ca14553c7cb51d2b7a329950aeaec4c0439762a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972628"
---
# <a name="label-control-overview-windows-forms"></a><span data-ttu-id="b9290-102">Label 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="b9290-102">Label Control Overview (Windows Forms)</span></span>
<span data-ttu-id="b9290-103">Windows 窗体 <xref:System.Windows.Forms.Label> 控件用于显示用户无法编辑的文本或图像。</span><span class="sxs-lookup"><span data-stu-id="b9290-103">Windows Forms <xref:System.Windows.Forms.Label> controls are used to display text or images that cannot be edited by the user.</span></span> <span data-ttu-id="b9290-104">它们用于标识窗体上的对象-例如，提供特定控件在被单击时所要执行的操作的说明，或者显示为响应应用程序中的运行时事件或进程而显示的信息。</span><span class="sxs-lookup"><span data-stu-id="b9290-104">They are used to identify objects on a form — to provide a description of what a certain control will do if clicked, for example, or to display information in response to a run-time event or process in your application.</span></span> <span data-ttu-id="b9290-105">例如，您可以使用标签将描述性标题添加到文本框、列表框、组合框等。</span><span class="sxs-lookup"><span data-stu-id="b9290-105">For example, you can use labels to add descriptive captions to text boxes, list boxes, combo boxes, and so on.</span></span> <span data-ttu-id="b9290-106">还可以编写代码来更改标签显示的文本，以响应运行时的事件。</span><span class="sxs-lookup"><span data-stu-id="b9290-106">You can also write code that changes the text displayed by a label in response to events at run time.</span></span> <span data-ttu-id="b9290-107">例如，如果应用程序需要几分钟时间来处理更改，则可以在标签中显示处理状态消息。</span><span class="sxs-lookup"><span data-stu-id="b9290-107">For example, if your application takes a few minutes to process a change, you can display a processing-status message in a label.</span></span>  
  
## <a name="working-with-the-label-control"></a><span data-ttu-id="b9290-108">使用标签控件</span><span class="sxs-lookup"><span data-stu-id="b9290-108">Working with the Label Control</span></span>  
 <span data-ttu-id="b9290-109">由于 <xref:System.Windows.Forms.Label> 控件不能接收焦点，因此也可以使用它来创建其他控件的访问键。</span><span class="sxs-lookup"><span data-stu-id="b9290-109">Because the <xref:System.Windows.Forms.Label> control cannot receive the focus, it can also be used to create access keys for other controls.</span></span> <span data-ttu-id="b9290-110">访问键允许用户通过按 ALT 键和访问键来选择另一个控件。</span><span class="sxs-lookup"><span data-stu-id="b9290-110">An access key allows a user to select the other control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="b9290-111">有关详细信息，请参阅 [创建 Windows 窗体控件的访问键](how-to-create-access-keys-for-windows-forms-controls.md) 和 [如何：创建具有 Windows 窗体标签控件的访问键](how-to-create-access-keys-with-windows-forms-label-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="b9290-111">For more information, see [Creating Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md) and [How to: Create Access Keys with Windows Forms Label Controls](how-to-create-access-keys-with-windows-forms-label-controls.md).</span></span>  
  
 <span data-ttu-id="b9290-112">标签中显示的标题包含在 <xref:System.Windows.Forms.Label.Text%2A> 属性中。</span><span class="sxs-lookup"><span data-stu-id="b9290-112">The caption displayed in the label is contained in the <xref:System.Windows.Forms.Label.Text%2A> property.</span></span> <span data-ttu-id="b9290-113"><xref:System.Windows.Forms.Label.TextAlign%2A>属性允许您设置标签中文本的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="b9290-113">The <xref:System.Windows.Forms.Label.TextAlign%2A> property allows you to set the alignment of the text within the label.</span></span> <span data-ttu-id="b9290-114">有关详细信息，请参阅 [如何：设置 Windows 窗体控件显示的文本](how-to-set-the-text-displayed-by-a-windows-forms-control.md)。</span><span class="sxs-lookup"><span data-stu-id="b9290-114">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9290-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9290-115">See also</span></span>

- <xref:System.Windows.Forms.Label>
- [<span data-ttu-id="b9290-116">如何：调整 Windows 窗体标签控件大小以适应其内容</span><span class="sxs-lookup"><span data-stu-id="b9290-116">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="b9290-117">如何：使用 Windows 窗体 Label 控件创建访问键</span><span class="sxs-lookup"><span data-stu-id="b9290-117">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
