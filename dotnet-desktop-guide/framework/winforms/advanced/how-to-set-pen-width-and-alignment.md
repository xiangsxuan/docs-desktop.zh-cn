---
title: 如何：设置钢笔的宽度和对齐方式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: 1f1ea6e8ef0b94aa46a4bf8177d59e59297d6e3f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971664"
---
# <a name="how-to-set-pen-width-and-alignment"></a><span data-ttu-id="d39f0-102">如何：设置钢笔的宽度和对齐方式</span><span class="sxs-lookup"><span data-stu-id="d39f0-102">How to: Set Pen Width and Alignment</span></span>
<span data-ttu-id="d39f0-103">创建时 <xref:System.Drawing.Pen> ，可以将笔宽度作为参数的一个参数提供给构造函数。</span><span class="sxs-lookup"><span data-stu-id="d39f0-103">When you create a <xref:System.Drawing.Pen>, you can supply the pen width as one of the arguments to the constructor.</span></span> <span data-ttu-id="d39f0-104">还可以通过类的属性来更改笔的宽度 <xref:System.Drawing.Pen.Width%2A> <xref:System.Drawing.Pen> 。</span><span class="sxs-lookup"><span data-stu-id="d39f0-104">You can also change the pen width with the <xref:System.Drawing.Pen.Width%2A> property of the <xref:System.Drawing.Pen> class.</span></span>  
  
 <span data-ttu-id="d39f0-105">理论线条的宽度为0。</span><span class="sxs-lookup"><span data-stu-id="d39f0-105">A theoretical line has a width of 0.</span></span> <span data-ttu-id="d39f0-106">绘制线条宽度为1个像素时，这些像素将在理论线条上居中。</span><span class="sxs-lookup"><span data-stu-id="d39f0-106">When you draw a line that is 1 pixel wide, the pixels are centered on the theoretical line.</span></span> <span data-ttu-id="d39f0-107">如果绘制的线条宽度超过一个像素，则这些像素将在理论线条上居中，或显示在理论线条的一侧。</span><span class="sxs-lookup"><span data-stu-id="d39f0-107">If you draw a line that is more than one pixel wide, the pixels are either centered on the theoretical line or appear to one side of the theoretical line.</span></span> <span data-ttu-id="d39f0-108">您可以设置的 "笔对齐" 属性 <xref:System.Drawing.Pen> ，以确定使用该笔绘制的像素相对于理论线条的位置。</span><span class="sxs-lookup"><span data-stu-id="d39f0-108">You can set the pen alignment property of a <xref:System.Drawing.Pen> to determine how the pixels drawn with that pen will be positioned relative to theoretical lines.</span></span>  
  
 <span data-ttu-id="d39f0-109"><xref:System.Drawing.Drawing2D.PenAlignment.Center> <xref:System.Drawing.Drawing2D.PenAlignment.Outset> <xref:System.Drawing.Drawing2D.PenAlignment.Inset> 下面的代码示例中显示的值是枚举的成员 <xref:System.Drawing.Drawing2D.PenAlignment> 。</span><span class="sxs-lookup"><span data-stu-id="d39f0-109">The values <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, and <xref:System.Drawing.Drawing2D.PenAlignment.Inset> that appear in the following code examples are members of the <xref:System.Drawing.Drawing2D.PenAlignment> enumeration.</span></span>  
  
 <span data-ttu-id="d39f0-110">下面的代码示例绘制两次两次：一次使用宽度为1的黑色钢笔，一次使用宽度为10的绿色钢笔。</span><span class="sxs-lookup"><span data-stu-id="d39f0-110">The following code example draws a line twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
### <a name="to-vary-the-width-of-a-pen"></a><span data-ttu-id="d39f0-111">改变笔的宽度</span><span class="sxs-lookup"><span data-stu-id="d39f0-111">To vary the width of a pen</span></span>  
  
- <span data-ttu-id="d39f0-112">将属性的值设置 <xref:System.Drawing.Pen.Alignment%2A> 为 <xref:System.Drawing.Drawing2D.PenAlignment.Center> (默认) ，以指定用绿色钢笔绘制的像素将在理论线条上居中。</span><span class="sxs-lookup"><span data-stu-id="d39f0-112">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> (the default) to specify that pixels drawn with the green pen will be centered on the theoretical line.</span></span> <span data-ttu-id="d39f0-113">下图显示了生成的行。</span><span class="sxs-lookup"><span data-stu-id="d39f0-113">The following illustration shows the resulting line.</span></span>  
  
     ![带有绿色突出显示的黑色细线。](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-line.gif)  
  
     <span data-ttu-id="d39f0-115">下面的代码示例绘制两次矩形：一次使用宽度为1的黑色钢笔，一次使用宽度为10的绿色钢笔。</span><span class="sxs-lookup"><span data-stu-id="d39f0-115">The following code example draws a rectangle twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a><span data-ttu-id="d39f0-116">更改笔的对齐方式</span><span class="sxs-lookup"><span data-stu-id="d39f0-116">To change the alignment of a pen</span></span>  
  
- <span data-ttu-id="d39f0-117">将属性的值设置 <xref:System.Drawing.Pen.Alignment%2A> 为， <xref:System.Drawing.Drawing2D.PenAlignment.Center> 以指定用绿色笔绘制的像素将在矩形边界上居中。</span><span class="sxs-lookup"><span data-stu-id="d39f0-117">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> to specify that the pixels drawn with the green pen will be centered on the boundary of the rectangle.</span></span>  
  
     <span data-ttu-id="d39f0-118">下图显示了生成的矩形：</span><span class="sxs-lookup"><span data-stu-id="d39f0-118">The following illustration shows the resulting rectangle:</span></span>
  
     ![使用带有绿色突出显示的黑色细线条绘制的矩形。](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-rectangle.gif)  
  
     [!code-csharp[System.Drawing.UsingAPen#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a><span data-ttu-id="d39f0-120">创建嵌入笔</span><span class="sxs-lookup"><span data-stu-id="d39f0-120">To create an inset pen</span></span>  
  
- <span data-ttu-id="d39f0-121">通过修改上述代码示例中的第三条语句来更改绿色画笔的对齐方式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d39f0-121">Change the green pen's alignment by modifying the third statement in the preceding code example as follows:</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     <span data-ttu-id="d39f0-122">现在，在矩形的内部显示宽绿色线条中的像素，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="d39f0-122">Now the pixels in the wide green line appear on the inside of the rectangle as shown in the following illustration:</span></span>
  
     ![用黑色线条绘制的矩形，其中包含宽绿色线条。](./media/how-to-set-pen-width-and-alignment/green-pixels-inside-rectangle.gif)  
  
## <a name="see-also"></a><span data-ttu-id="d39f0-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d39f0-124">See also</span></span>

- [<span data-ttu-id="d39f0-125">使用笔绘制线条和形状</span><span class="sxs-lookup"><span data-stu-id="d39f0-125">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="d39f0-126">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="d39f0-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
