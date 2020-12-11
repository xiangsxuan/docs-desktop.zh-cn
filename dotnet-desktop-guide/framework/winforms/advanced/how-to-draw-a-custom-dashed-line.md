---
title: 如何：绘制自定义虚线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: d2184a8d7d7f24b8f631818608ab4bcdb89857c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970310"
---
# <a name="how-to-draw-a-custom-dashed-line"></a><span data-ttu-id="3983b-102">如何：绘制自定义虚线</span><span class="sxs-lookup"><span data-stu-id="3983b-102">How to: Draw a Custom Dashed Line</span></span>
<span data-ttu-id="3983b-103">GDI + 提供了在枚举中列出的若干虚线样式 <xref:System.Drawing.Drawing2D.DashStyle> 。</span><span class="sxs-lookup"><span data-stu-id="3983b-103">GDI+ provides several dash styles that are listed in the <xref:System.Drawing.Drawing2D.DashStyle> enumeration.</span></span> <span data-ttu-id="3983b-104">如果这些标准虚线样式不能满足您的需要，则可以创建自定义破折号模式。</span><span class="sxs-lookup"><span data-stu-id="3983b-104">If those standard dash styles do not suit your needs, you can create a custom dash pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3983b-105">示例</span><span class="sxs-lookup"><span data-stu-id="3983b-105">Example</span></span>  
 <span data-ttu-id="3983b-106">若要绘制自定义虚线，请将短划线和空格的长度置于数组中，并将该数组指定为对象的 <xref:System.Drawing.Pen.DashPattern%2A> 属性的值 <xref:System.Drawing.Pen> 。</span><span class="sxs-lookup"><span data-stu-id="3983b-106">To draw a custom dashed line, put the lengths of the dashes and spaces in an array and assign the array as the value of the <xref:System.Drawing.Pen.DashPattern%2A> property of a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="3983b-107">下面的示例根据数组绘制自定义虚线 `{5, 2, 15, 4}` 。</span><span class="sxs-lookup"><span data-stu-id="3983b-107">The following example draws a custom dashed line based on the array `{5, 2, 15, 4}`.</span></span> <span data-ttu-id="3983b-108">如果将数组的元素乘以笔宽度5，则会获得 `{25, 10, 75, 20}` 。</span><span class="sxs-lookup"><span data-stu-id="3983b-108">If you multiply the elements of the array by the pen width of 5, you get `{25, 10, 75, 20}`.</span></span> <span data-ttu-id="3983b-109">显示的短划线替换长度介于25到75之间，空格备用的长度为10到20。</span><span class="sxs-lookup"><span data-stu-id="3983b-109">The displayed dashes alternate in length between 25 and 75, and the spaces alternate in length between 10 and 20.</span></span>  
  
 <span data-ttu-id="3983b-110">下图显示了生成的虚线。</span><span class="sxs-lookup"><span data-stu-id="3983b-110">The following illustration shows the resulting dashed line.</span></span> <span data-ttu-id="3983b-111">请注意，最后一个短划线的长度必须小于25个单位，以便该行可以 (405，5) 结束。</span><span class="sxs-lookup"><span data-stu-id="3983b-111">Note that the final dash has to be shorter than 25 units so that the line can end at (405, 5).</span></span>  
  
 <span data-ttu-id="3983b-112">![显示虚线的插图。](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")</span><span class="sxs-lookup"><span data-stu-id="3983b-112">![Illustration that shows a dashed line.](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3983b-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="3983b-113">Compiling the Code</span></span>  
 <span data-ttu-id="3983b-114">创建 Windows 窗体并处理窗体的 <xref:System.Windows.Forms.Control.Paint> 事件。</span><span class="sxs-lookup"><span data-stu-id="3983b-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="3983b-115">将前面的代码粘贴到 <xref:System.Windows.Forms.Control.Paint> 事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="3983b-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3983b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3983b-116">See also</span></span>

- [<span data-ttu-id="3983b-117">使用笔绘制线条和形状</span><span class="sxs-lookup"><span data-stu-id="3983b-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
