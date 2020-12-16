---
title: Label 控件
description: 了解适用于 .NET 的 Windows 窗体中的 Label 控件。 标签用于向用户标识可视元素。
ms.date: 10/26/2020
ms.topic: overview
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.openlocfilehash: 6f669b7aef1182c35e125ff8dd3ca5ccb299b898
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941959"
---
# <a name="label-control-overview-windows-forms-net"></a><span data-ttu-id="4eddb-104">Label 控件概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="4eddb-104">Label control overview (Windows Forms .NET)</span></span>

<span data-ttu-id="4eddb-105">Windows 窗体 <xref:System.Windows.Forms.Label> 控件用于显示用户无法编辑的文本。</span><span class="sxs-lookup"><span data-stu-id="4eddb-105">Windows Forms <xref:System.Windows.Forms.Label> controls are used to display text that cannot be edited by the user.</span></span> <span data-ttu-id="4eddb-106">它们用于标识窗体上的对象，并提供特定控件所代表内容或所执行操作的说明。</span><span class="sxs-lookup"><span data-stu-id="4eddb-106">They're used to identify objects on a form and to provide a description of what a certain control represents or does.</span></span> <span data-ttu-id="4eddb-107">例如，可使用标签将描述文字添加到文本框、列表框、组合框等。</span><span class="sxs-lookup"><span data-stu-id="4eddb-107">For example, you can use labels to add descriptive captions to text boxes, list boxes, combo boxes, and so on.</span></span> <span data-ttu-id="4eddb-108">还可编写代码来更改标签显示的文本，以响应运行时的事件。</span><span class="sxs-lookup"><span data-stu-id="4eddb-108">You can also write code that changes the text displayed by a label in response to events at run time.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="working-with-the-label-control"></a><span data-ttu-id="4eddb-109">使用 Label 控件</span><span class="sxs-lookup"><span data-stu-id="4eddb-109">Working with the Label Control</span></span>  

<span data-ttu-id="4eddb-110">由于 <xref:System.Windows.Forms.Label> 控件不能接收焦点，因此它可用于创建其他控件的访问键。</span><span class="sxs-lookup"><span data-stu-id="4eddb-110">Because the <xref:System.Windows.Forms.Label> control can't receive focus, it can be used to create access keys for other controls.</span></span> <span data-ttu-id="4eddb-111">借助访问键，用户可通过按 <kbd>Alt</kbd> 键和所选的访问键，按 Tab 键顺序聚焦下一个控件。</span><span class="sxs-lookup"><span data-stu-id="4eddb-111">An access key allows a user to focus the next control in tab order by pressing the <kbd>Alt</kbd> key with the chosen access key.</span></span> <span data-ttu-id="4eddb-112">有关详细信息，请参阅[使用标签聚焦控件](how-to-create-access-keys.md#use-a-label-to-focus-a-control)。</span><span class="sxs-lookup"><span data-stu-id="4eddb-112">For more information, see [Use a label to focus a control](how-to-create-access-keys.md#use-a-label-to-focus-a-control).</span></span>
  
<span data-ttu-id="4eddb-113">标签中显示的描述文字包含在 <xref:System.Windows.Forms.Label.Text%2A> 属性中。</span><span class="sxs-lookup"><span data-stu-id="4eddb-113">The caption displayed in the label is contained in the <xref:System.Windows.Forms.Label.Text%2A> property.</span></span> <span data-ttu-id="4eddb-114"><xref:System.Windows.Forms.Label.TextAlign%2A> 属性使你能够设置标签内文本的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="4eddb-114">The <xref:System.Windows.Forms.Label.TextAlign%2A> property allows you to set the alignment of the text within the label.</span></span> <span data-ttu-id="4eddb-115">有关详细信息，请参阅[如何：设置 Windows 窗体控件显示的文本](how-to-set-the-display-text.md)。</span><span class="sxs-lookup"><span data-stu-id="4eddb-115">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](how-to-set-the-display-text.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4eddb-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4eddb-116">See also</span></span>

- [<span data-ttu-id="4eddb-117">使用标签聚焦控件（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="4eddb-117">Use a label to focus a control (Windows Forms .NET)</span></span>](how-to-create-access-keys.md#use-a-label-to-focus-a-control)
- [<span data-ttu-id="4eddb-118">如何：设置控件显示的文本（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="4eddb-118">How to: Set the text displayed by a control (Windows Forms .NET)</span></span>](how-to-set-the-display-text.md)
- <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>
- <xref:System.Windows.Forms.Control.Scale%2A>
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>
