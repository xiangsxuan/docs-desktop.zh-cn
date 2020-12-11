---
title: 调整标签控件大小以适应其内容
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 6a563693feaa5074f5d13f0b82cc4d0305a79c23
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972547"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="31510-102">如何：调整 Windows 窗体标签控件大小以适应其内容</span><span class="sxs-lookup"><span data-stu-id="31510-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="31510-103">Windows 窗体 <xref:System.Windows.Forms.Label> 控件可以是单行或多行，它可以是固定的，也可以自动调整自身大小以适应其标题。</span><span class="sxs-lookup"><span data-stu-id="31510-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="31510-104"><xref:System.Windows.Forms.Label.AutoSize%2A>属性可帮助您调整控件的大小以适合更大或更小的标题，这在标题会在运行时更改时特别有用。</span><span class="sxs-lookup"><span data-stu-id="31510-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="31510-105">使标签控件动态调整大小以适应其内容</span><span class="sxs-lookup"><span data-stu-id="31510-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1. <span data-ttu-id="31510-106">将其 <xref:System.Windows.Forms.Label.AutoSize%2A> 属性设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="31510-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="31510-107">如果 <xref:System.Windows.Forms.Label.AutoSize%2A> 设置为 `false` ，则在属性中指定的单词 <xref:System.Windows.Forms.Label.Text%2A> 会换行到下一行（如果可能），但控件不会增长。</span><span class="sxs-lookup"><span data-stu-id="31510-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31510-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31510-108">See also</span></span>

- [<span data-ttu-id="31510-109">如何：使用 Windows 窗体 Label 控件创建访问键</span><span class="sxs-lookup"><span data-stu-id="31510-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [<span data-ttu-id="31510-110">Label 控件概述</span><span class="sxs-lookup"><span data-stu-id="31510-110">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="31510-111">Label 控件</span><span class="sxs-lookup"><span data-stu-id="31510-111">Label Control</span></span>](label-control-windows-forms.md)
