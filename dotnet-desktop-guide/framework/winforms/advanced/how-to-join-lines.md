---
title: 如何：联接线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
ms.openlocfilehash: 362ce0c701d6e5f640fecd143a60cf471045629c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971692"
---
# <a name="how-to-join-lines"></a><span data-ttu-id="d1fb6-102">如何：联接线</span><span class="sxs-lookup"><span data-stu-id="d1fb6-102">How to: Join Lines</span></span>
<span data-ttu-id="d1fb6-103">行联接是由两行构成的通用区域，它们的结束时间都达到或重叠。</span><span class="sxs-lookup"><span data-stu-id="d1fb6-103">A line join is the common area that is formed by two lines whose ends meet or overlap.</span></span> <span data-ttu-id="d1fb6-104">GDI + 提供三个线条联接样式：斜接、凹凸和圆形。</span><span class="sxs-lookup"><span data-stu-id="d1fb6-104">GDI+ provides three line join styles: miter, bevel, and round.</span></span> <span data-ttu-id="d1fb6-105">行联接样式是类的属性 <xref:System.Drawing.Pen> 。</span><span class="sxs-lookup"><span data-stu-id="d1fb6-105">Line join style is a property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="d1fb6-106">为对象指定线条联接样式时 <xref:System.Drawing.Pen> ，该联接样式将应用于 <xref:System.Drawing.Drawing2D.GraphicsPath> 使用该钢笔绘制的任何对象中的所有连接行。</span><span class="sxs-lookup"><span data-stu-id="d1fb6-106">When you specify a line join style for a <xref:System.Drawing.Pen> object, that join style will be applied to all the connected lines in any <xref:System.Drawing.Drawing2D.GraphicsPath> object drawn using that pen.</span></span>  
  
 <span data-ttu-id="d1fb6-107">下图显示了斜切行联接示例的结果。</span><span class="sxs-lookup"><span data-stu-id="d1fb6-107">The following illustration shows the results of the beveled line join example.</span></span>  
  
 ![显示联接线的插图。](./media/how-to-join-lines/joined-beveled-lines.gif)  
  
## <a name="example"></a><span data-ttu-id="d1fb6-109">示例</span><span class="sxs-lookup"><span data-stu-id="d1fb6-109">Example</span></span>  
 <span data-ttu-id="d1fb6-110">您可以通过使用类的属性指定行联接样式 <xref:System.Drawing.Pen.LineJoin%2A> <xref:System.Drawing.Pen> 。</span><span class="sxs-lookup"><span data-stu-id="d1fb6-110">You can specify the line join style by using the <xref:System.Drawing.Pen.LineJoin%2A> property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="d1fb6-111">该示例演示了水平线和竖线之间的斜切线条联接。</span><span class="sxs-lookup"><span data-stu-id="d1fb6-111">The example demonstrates a beveled line join between a horizontal line and a vertical line.</span></span> <span data-ttu-id="d1fb6-112">在下面的代码中，赋给属性的值 <xref:System.Drawing.Drawing2D.LineJoin.Bevel> <xref:System.Drawing.Pen.LineJoin%2A> 是枚举的成员 <xref:System.Drawing.Drawing2D.LineJoin> 。</span><span class="sxs-lookup"><span data-stu-id="d1fb6-112">In the following code, the value <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assigned to the <xref:System.Drawing.Pen.LineJoin%2A> property is a member of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration.</span></span> <span data-ttu-id="d1fb6-113">枚举的其他成员 <xref:System.Drawing.Drawing2D.LineJoin> 为 <xref:System.Drawing.Drawing2D.LineJoin.Miter> 和 <xref:System.Drawing.Drawing2D.LineJoin.Round> 。</span><span class="sxs-lookup"><span data-stu-id="d1fb6-113">The other members of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration are <xref:System.Drawing.Drawing2D.LineJoin.Miter> and <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d1fb6-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="d1fb6-114">Compiling the Code</span></span>  
 <span data-ttu-id="d1fb6-115">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="d1fb6-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1fb6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1fb6-116">See also</span></span>

- [<span data-ttu-id="d1fb6-117">使用笔绘制线条和形状</span><span class="sxs-lookup"><span data-stu-id="d1fb6-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
