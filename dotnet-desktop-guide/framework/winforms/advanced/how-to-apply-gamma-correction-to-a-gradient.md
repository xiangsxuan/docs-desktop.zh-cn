---
title: 如何：对渐变应用 gamma 矫正
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: e812e441233c1d29a67dac639048e20a659549f0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970907"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="98d41-102">如何：对渐变应用 gamma 矫正</span><span class="sxs-lookup"><span data-stu-id="98d41-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="98d41-103">可以通过将画笔的属性设置为，为线性渐变画笔启用伽玛更正 <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> `true` 。</span><span class="sxs-lookup"><span data-stu-id="98d41-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="98d41-104">您可以通过将属性设置为来禁用伽玛更正 <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> `false` 。</span><span class="sxs-lookup"><span data-stu-id="98d41-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="98d41-105">默认情况下禁用伽玛更正。</span><span class="sxs-lookup"><span data-stu-id="98d41-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98d41-106">示例</span><span class="sxs-lookup"><span data-stu-id="98d41-106">Example</span></span>  

<span data-ttu-id="98d41-107">下面的示例是从控件的事件处理程序调用的方法 <xref:System.Windows.Forms.Control.Paint> 。</span><span class="sxs-lookup"><span data-stu-id="98d41-107">The following example is a method that is called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="98d41-108">该示例创建一个线性渐变画笔，并使用该画笔来填充两个矩形。</span><span class="sxs-lookup"><span data-stu-id="98d41-108">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="98d41-109">填充第一个矩形时没有伽玛矫正，第二个矩形用伽玛更正填充。</span><span class="sxs-lookup"><span data-stu-id="98d41-109">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="98d41-110">下图显示了两个填充的矩形。</span><span class="sxs-lookup"><span data-stu-id="98d41-110">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="98d41-111">没有伽玛矫正的顶部矩形在中间显示为暗。</span><span class="sxs-lookup"><span data-stu-id="98d41-111">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="98d41-112">具有伽玛矫正的底部矩形似乎具有更一致的强度。</span><span class="sxs-lookup"><span data-stu-id="98d41-112">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 ![两个渐变填充矩形，具有和不带伽玛更正。](./media/how-to-apply-gamma-correction-to-a-gradient/two-rectangles-gamma-gradient.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="98d41-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="98d41-114">Compiling the Code</span></span>  
 <span data-ttu-id="98d41-115">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="98d41-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98d41-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98d41-116">See also</span></span>

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="98d41-117">使用渐变画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="98d41-117">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
