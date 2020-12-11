---
title: 如何：使用钢笔绘制线条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
ms.openlocfilehash: 263c0fbda377e64753cd2d607f633117b4b44253
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971644"
---
# <a name="how-to-use-a-pen-to-draw-lines"></a><span data-ttu-id="200cd-102">如何：使用钢笔绘制线条</span><span class="sxs-lookup"><span data-stu-id="200cd-102">How to: Use a Pen to Draw Lines</span></span>
<span data-ttu-id="200cd-103">若要绘制线条，需要 <xref:System.Drawing.Graphics> 对象和 <xref:System.Drawing.Pen> 对象。</span><span class="sxs-lookup"><span data-stu-id="200cd-103">To draw lines, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="200cd-104"><xref:System.Drawing.Graphics>对象提供 <xref:System.Drawing.Graphics.DrawLine%2A> 方法，而 <xref:System.Drawing.Pen> 对象存储行的功能，如颜色和宽度。</span><span class="sxs-lookup"><span data-stu-id="200cd-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawLine%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="200cd-105">示例</span><span class="sxs-lookup"><span data-stu-id="200cd-105">Example</span></span>  
 <span data-ttu-id="200cd-106">下面的示例从 (20，10) 到 (300，100) 绘制一条线。</span><span class="sxs-lookup"><span data-stu-id="200cd-106">The following example draws a line from (20, 10) to (300, 100).</span></span> <span data-ttu-id="200cd-107">第一条语句使用 <xref:System.Drawing.Pen.%23ctor%2A> 类构造函数创建黑色笔。</span><span class="sxs-lookup"><span data-stu-id="200cd-107">The first statement uses the <xref:System.Drawing.Pen.%23ctor%2A> class constructor to create a black pen.</span></span> <span data-ttu-id="200cd-108">传递给构造函数的一个参数 <xref:System.Drawing.Pen.%23ctor%2A> 是 <xref:System.Drawing.Color> 使用方法创建的对象 <xref:System.Drawing.Color.FromArgb%2A> 。</span><span class="sxs-lookup"><span data-stu-id="200cd-108">The one argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object created with the <xref:System.Drawing.Color.FromArgb%2A> method.</span></span> <span data-ttu-id="200cd-109">用于创建对象的值 <xref:System.Drawing.Color> （ (255，0，0，0) ）对应于颜色的 alpha、红色、绿色和蓝色成分。</span><span class="sxs-lookup"><span data-stu-id="200cd-109">The values used to create the <xref:System.Drawing.Color> object — (255, 0, 0, 0) — correspond to the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="200cd-110">这些值定义不透明的黑色笔。</span><span class="sxs-lookup"><span data-stu-id="200cd-110">These values define an opaque black pen.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="200cd-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="200cd-111">Compiling the Code</span></span>  
 <span data-ttu-id="200cd-112">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="200cd-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="200cd-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="200cd-113">See also</span></span>

- <xref:System.Drawing.Pen>
- [<span data-ttu-id="200cd-114">使用笔绘制线条和形状</span><span class="sxs-lookup"><span data-stu-id="200cd-114">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="200cd-115">GDI+ 中的笔、直线和矩形</span><span class="sxs-lookup"><span data-stu-id="200cd-115">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
