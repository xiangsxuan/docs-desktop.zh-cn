---
title: 如何：填充开放图形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: 6ecea7d3edb0c3e25fb4e69ff12b88019e530021
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971446"
---
# <a name="how-to-fill-open-figures"></a><span data-ttu-id="c1bff-102">如何：填充开放图形</span><span class="sxs-lookup"><span data-stu-id="c1bff-102">How to: Fill Open Figures</span></span>
<span data-ttu-id="c1bff-103">可以通过将对象传递给方法来填充路径 <xref:System.Drawing.Drawing2D.GraphicsPath> <xref:System.Drawing.Graphics.FillPath%2A> 。</span><span class="sxs-lookup"><span data-stu-id="c1bff-103">You can fill a path by passing a <xref:System.Drawing.Drawing2D.GraphicsPath> object to the <xref:System.Drawing.Graphics.FillPath%2A> method.</span></span> <span data-ttu-id="c1bff-104"><xref:System.Drawing.Graphics.FillPath%2A>方法根据当前为路径设置 (替换或缠绕) 填充模式来填充路径。</span><span class="sxs-lookup"><span data-stu-id="c1bff-104">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the fill mode (alternate or winding) currently set for the path.</span></span> <span data-ttu-id="c1bff-105">如果路径有任何打开的图形，则会像关闭这些图形一样填充路径。</span><span class="sxs-lookup"><span data-stu-id="c1bff-105">If the path has any open figures, the path is filled as if those figures were closed.</span></span> <span data-ttu-id="c1bff-106">GDI + 通过绘制从其结束点到起始点的直线来关闭一个图形。</span><span class="sxs-lookup"><span data-stu-id="c1bff-106">GDI+ closes a figure by drawing a straight line from its ending point to its starting point.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1bff-107">示例</span><span class="sxs-lookup"><span data-stu-id="c1bff-107">Example</span></span>  
 <span data-ttu-id="c1bff-108">下面的示例创建一个路径，该路径具有一个 (弧线) 的闭合图形，另一个闭合图形 (一个椭圆) 。</span><span class="sxs-lookup"><span data-stu-id="c1bff-108">The following example creates a path that has one open figure (an arc) and one closed figure (an ellipse).</span></span> <span data-ttu-id="c1bff-109"><xref:System.Drawing.Graphics.FillPath%2A>方法根据默认填充模式填充路径，即 <xref:System.Drawing.Drawing2D.FillMode.Alternate> 。</span><span class="sxs-lookup"><span data-stu-id="c1bff-109">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the default fill mode, which is <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span></span>  
  
 <span data-ttu-id="c1bff-110">下图显示了该示例代码的输出。</span><span class="sxs-lookup"><span data-stu-id="c1bff-110">The following illustration shows the output of the example code.</span></span> <span data-ttu-id="c1bff-111">请注意，根据) ，路径是根据 <xref:System.Drawing.Drawing2D.FillMode.Alternate> 从其结束点到起始点的直线闭合的闭合图形 (填充的。</span><span class="sxs-lookup"><span data-stu-id="c1bff-111">Note that the path is filled (according to <xref:System.Drawing.Drawing2D.FillMode.Alternate>) as if the open figure were closed by a straight line from its ending point to its starting point.</span></span>  
  
 ![显示 FillPath 方法输出的关系图](./media/how-to-fill-open-figures/fill-path-alternate-mode.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c1bff-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="c1bff-113">Compiling the Code</span></span>  
 <span data-ttu-id="c1bff-114">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="c1bff-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1bff-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1bff-115">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="c1bff-116">GDI+ 中的图形路径</span><span class="sxs-lookup"><span data-stu-id="c1bff-116">Graphics Paths in GDI+</span></span>](graphics-paths-in-gdi.md)
