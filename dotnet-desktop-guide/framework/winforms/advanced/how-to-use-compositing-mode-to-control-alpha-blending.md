---
title: 如何：使用复合模式控制 alpha 值混合处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 6863e59efa25323f80933bf8ab595316b430ef53
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971638"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a><span data-ttu-id="d6b6a-102">如何：使用复合模式控制 alpha 值混合处理</span><span class="sxs-lookup"><span data-stu-id="d6b6a-102">How to: Use Compositing Mode to Control Alpha Blending</span></span>
<span data-ttu-id="d6b6a-103">有时可能需要创建具有以下特征的非屏幕位图：</span><span class="sxs-lookup"><span data-stu-id="d6b6a-103">There may be times when you want to create an off-screen bitmap that has the following characteristics:</span></span>  
  
- <span data-ttu-id="d6b6a-104">颜色的 alpha 值小于255。</span><span class="sxs-lookup"><span data-stu-id="d6b6a-104">Colors have alpha values that are less than 255.</span></span>  
  
- <span data-ttu-id="d6b6a-105">创建位图时，颜色不会混合在一起。</span><span class="sxs-lookup"><span data-stu-id="d6b6a-105">Colors are not alpha blended with each other as you create the bitmap.</span></span>  
  
- <span data-ttu-id="d6b6a-106">显示已完成的位图后，位图中的颜色与显示设备上的背景色混合了 alpha。</span><span class="sxs-lookup"><span data-stu-id="d6b6a-106">When you display the finished bitmap, colors in the bitmap are alpha blended with the background colors on the display device.</span></span>  
  
 <span data-ttu-id="d6b6a-107">若要创建此类位图，请构造一个空白 <xref:System.Drawing.Bitmap> 对象，然后根据 <xref:System.Drawing.Graphics> 该位图构造对象。</span><span class="sxs-lookup"><span data-stu-id="d6b6a-107">To create such a bitmap, construct a blank <xref:System.Drawing.Bitmap> object, and then construct a <xref:System.Drawing.Graphics> object based on that bitmap.</span></span> <span data-ttu-id="d6b6a-108">将对象的合成模式设置 <xref:System.Drawing.Graphics> 为 <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="d6b6a-108">Set the compositing mode of the <xref:System.Drawing.Graphics> object to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6b6a-109">示例</span><span class="sxs-lookup"><span data-stu-id="d6b6a-109">Example</span></span>  
 <span data-ttu-id="d6b6a-110">下面的示例 <xref:System.Drawing.Graphics> 基于对象创建对象 <xref:System.Drawing.Bitmap> 。</span><span class="sxs-lookup"><span data-stu-id="d6b6a-110">The following example creates a <xref:System.Drawing.Graphics> object based on a <xref:System.Drawing.Bitmap> object.</span></span> <span data-ttu-id="d6b6a-111">该代码使用 <xref:System.Drawing.Graphics> 对象和两个半透明画笔 (alpha = 160) 在位图上绘制。</span><span class="sxs-lookup"><span data-stu-id="d6b6a-111">The code uses the <xref:System.Drawing.Graphics> object along with two semitransparent brushes (alpha = 160) to paint on the bitmap.</span></span> <span data-ttu-id="d6b6a-112">此代码使用半透明画笔填充红色椭圆和绿色椭圆。</span><span class="sxs-lookup"><span data-stu-id="d6b6a-112">The code fills a red ellipse and a green ellipse using the semitransparent brushes.</span></span> <span data-ttu-id="d6b6a-113">绿色椭圆与红色椭圆重叠，但绿色不与红色混合，因为对象的合成模式 <xref:System.Drawing.Graphics> 设置为 <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy> 。</span><span class="sxs-lookup"><span data-stu-id="d6b6a-113">The green ellipse overlaps the red ellipse, but the green is not blended with the red because the compositing mode of the <xref:System.Drawing.Graphics> object is set to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span></span>  
  
 <span data-ttu-id="d6b6a-114">此代码将在屏幕上绘制位图两次：一次在白色背景上，一次在颜色背景上。</span><span class="sxs-lookup"><span data-stu-id="d6b6a-114">The code draws the bitmap on the screen twice: once on a white background and once on a multicolored background.</span></span> <span data-ttu-id="d6b6a-115">位图中属于两个椭圆的像素的 alpha 分量为160，因此椭圆与屏幕上的背景颜色混合。</span><span class="sxs-lookup"><span data-stu-id="d6b6a-115">The pixels in the bitmap that are part of the two ellipses have an alpha component of 160, so the ellipses are blended with the background colors on the screen.</span></span>  
  
 <span data-ttu-id="d6b6a-116">下图显示了代码示例的输出。</span><span class="sxs-lookup"><span data-stu-id="d6b6a-116">The following illustration shows the output of the code example.</span></span> <span data-ttu-id="d6b6a-117">请注意，椭圆与背景混合在一起，但它们彼此之间并不混合。</span><span class="sxs-lookup"><span data-stu-id="d6b6a-117">Note that the ellipses are blended with the background, but they are not blended with each other.</span></span>  
  
 ![显示与背景混合的省略号的关系图，而不是彼此混合的关系图。](./media/how-to-use-compositing-mode-to-control-alpha-blending/ellipses-blended-background.png)  
  
 <span data-ttu-id="d6b6a-119">此代码示例包含以下语句：</span><span class="sxs-lookup"><span data-stu-id="d6b6a-119">The code example contains this statement:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 <span data-ttu-id="d6b6a-120">如果希望省略号与其他椭圆以及背景混合，请将该语句更改为以下内容：</span><span class="sxs-lookup"><span data-stu-id="d6b6a-120">If you want the ellipses to be blended with each other as well as with the background, change that statement to the following:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 <span data-ttu-id="d6b6a-121">下图显示了修改后的代码的输出。</span><span class="sxs-lookup"><span data-stu-id="d6b6a-121">The following illustration shows the output of the revised code.</span></span>  
  
 ![显示混合在一起并带有背景的省略号的关系图。](./media/how-to-use-compositing-mode-to-control-alpha-blending/blend-ellipses-background.png)  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d6b6a-123">编译代码</span><span class="sxs-lookup"><span data-stu-id="d6b6a-123">Compiling the Code</span></span>  
 <span data-ttu-id="d6b6a-124">前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="d6b6a-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b6a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6b6a-125">See also</span></span>

- <xref:System.Drawing.Color.FromArgb%2A>
- [<span data-ttu-id="d6b6a-126">Alpha 混合线条和填充</span><span class="sxs-lookup"><span data-stu-id="d6b6a-126">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
