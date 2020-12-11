---
title: 如何：对文本使用抗锯齿效果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 632ed329173d134495a424b34ca7c71e402607bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971641"
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="3cb43-102">如何：对文本使用抗锯齿效果</span><span class="sxs-lookup"><span data-stu-id="3cb43-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="3cb43-103">*消除锯齿* 指的是对绘制的图形和文本的锯齿边缘进行平滑处理，以改善其外观或可读性。</span><span class="sxs-lookup"><span data-stu-id="3cb43-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="3cb43-104">利用托管 GDI + 类，可以呈现高质量的抗锯齿文本，以及较低质量的文本。</span><span class="sxs-lookup"><span data-stu-id="3cb43-104">With the managed GDI+ classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="3cb43-105">通常，高质量渲染比较低质量渲染所用的处理时间更长。</span><span class="sxs-lookup"><span data-stu-id="3cb43-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="3cb43-106">若要设置文本质量级别，请将 <xref:System.Drawing.Graphics.TextRenderingHint%2A> 的属性设置 <xref:System.Drawing.Graphics> 为枚举的元素之一 <xref:System.Drawing.Text.TextRenderingHint></span><span class="sxs-lookup"><span data-stu-id="3cb43-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cb43-107">示例</span><span class="sxs-lookup"><span data-stu-id="3cb43-107">Example</span></span>  
 <span data-ttu-id="3cb43-108">下面的代码示例用两个不同的质量设置来绘制文本。</span><span class="sxs-lookup"><span data-stu-id="3cb43-108">The following code example draws text with two different quality settings.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  

 <span data-ttu-id="3cb43-109">下图显示了该示例代码的输出：</span><span class="sxs-lookup"><span data-stu-id="3cb43-109">The following illustration shows the output of the example code:</span></span>  
  
 ![显示具有两种不同质量设置的文本的屏幕截图。](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3cb43-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="3cb43-111">Compiling the Code</span></span>  
 <span data-ttu-id="3cb43-112">前面的代码示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="3cb43-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb43-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cb43-113">See also</span></span>

- [<span data-ttu-id="3cb43-114">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="3cb43-114">Using Fonts and Text</span></span>](using-fonts-and-text.md)
