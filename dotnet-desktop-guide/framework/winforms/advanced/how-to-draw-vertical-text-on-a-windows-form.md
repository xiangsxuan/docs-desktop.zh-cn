---
title: 如何：在 Windows 窗体上绘制垂直文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- StringFormat.FormatFlags
- Graphics.DrawString
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- strings [Windows Forms], drawing vertical
- text [Windows Forms], drawing
- text [Windows Forms], vertical text
ms.assetid: 717a6131-00f6-4373-b574-9894e8317799
ms.openlocfilehash: 660d7abae5463c976e60b7d9caeae8a798d122ca
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971454"
---
# <a name="how-to-draw-vertical-text-on-a-windows-form"></a><span data-ttu-id="e495a-102">如何：在 Windows 窗体上绘制垂直文本</span><span class="sxs-lookup"><span data-stu-id="e495a-102">How to: Draw Vertical Text on a Windows Form</span></span>
<span data-ttu-id="e495a-103">下面的代码示例演示如何使用的方法在窗体上绘制垂直文本 <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="e495a-103">The following code example shows how to draw vertical text on a form by using the <xref:System.Drawing.Graphics.DrawString%2A> method of <xref:System.Drawing.Graphics>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e495a-104">示例</span><span class="sxs-lookup"><span data-stu-id="e495a-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e495a-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="e495a-105">Compiling the Code</span></span>  
 <span data-ttu-id="e495a-106">不能在事件处理程序中调用此方法 <xref:System.Windows.Forms.Form.Load> 。</span><span class="sxs-lookup"><span data-stu-id="e495a-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="e495a-107">如果窗体调整或被其他窗体遮住，则不会重新绘制所绘制的内容。</span><span class="sxs-lookup"><span data-stu-id="e495a-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="e495a-108">若要自动重绘内容，应重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="e495a-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e495a-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="e495a-109">Robust Programming</span></span>  
 <span data-ttu-id="e495a-110">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="e495a-110">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="e495a-111">未安装 Arial 字体。</span><span class="sxs-lookup"><span data-stu-id="e495a-111">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e495a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e495a-112">See also</span></span>

- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="e495a-113">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="e495a-113">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="e495a-114">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="e495a-114">Using Fonts and Text</span></span>](using-fonts-and-text.md)
