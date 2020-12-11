---
title: 如何：通过直线、曲线和形状创建图形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: c8cf7a7e08bed56fb704bba4e30ff369bc3fcf89
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970573"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a><span data-ttu-id="139fb-102">如何：通过直线、曲线和形状创建图形</span><span class="sxs-lookup"><span data-stu-id="139fb-102">How to: Create Figures from Lines, Curves, and Shapes</span></span>
<span data-ttu-id="139fb-103">若要创建图形，请构造 <xref:System.Drawing.Drawing2D.GraphicsPath> ，然后调用方法（如 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 和）， <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> 以将基元添加到路径。</span><span class="sxs-lookup"><span data-stu-id="139fb-103">To create a figure, construct a <xref:System.Drawing.Drawing2D.GraphicsPath>, and then call methods, such as <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, to add primitives to the path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="139fb-104">示例</span><span class="sxs-lookup"><span data-stu-id="139fb-104">Example</span></span>  
 <span data-ttu-id="139fb-105">下面的代码示例创建了包含图形的路径：</span><span class="sxs-lookup"><span data-stu-id="139fb-105">The following code examples create paths that have figures:</span></span>  
  
- <span data-ttu-id="139fb-106">第一个示例创建一个具有单个图形的路径。</span><span class="sxs-lookup"><span data-stu-id="139fb-106">The first example creates a path that has a single figure.</span></span> <span data-ttu-id="139fb-107">该图包含一个圆弧。圆弧的扫描角度为–180度，这在默认坐标系统中以逆时针表示。</span><span class="sxs-lookup"><span data-stu-id="139fb-107">The figure consists of a single arc. The arc has a sweep angle of –180 degrees, which is counterclockwise in the default coordinate system.</span></span>  
  
- <span data-ttu-id="139fb-108">第二个示例创建一个具有两个图形的路径。</span><span class="sxs-lookup"><span data-stu-id="139fb-108">The second example creates a path that has two figures.</span></span> <span data-ttu-id="139fb-109">第一个图形是一条弧后跟一个直线。</span><span class="sxs-lookup"><span data-stu-id="139fb-109">The first figure is an arc followed by a line.</span></span> <span data-ttu-id="139fb-110">第二个图形是一条后跟一条曲线的曲线。</span><span class="sxs-lookup"><span data-stu-id="139fb-110">The second figure is a line followed by a curve followed by a line.</span></span> <span data-ttu-id="139fb-111">第一个图形保持打开状态，并关闭第二个图形。</span><span class="sxs-lookup"><span data-stu-id="139fb-111">The first figure is left open, and the second figure is closed.</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="139fb-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="139fb-112">Compiling the Code</span></span>  
 <span data-ttu-id="139fb-113">前面的示例旨在与 Windows 窗体一起使用，并且它们需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="139fb-113">The previous examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="139fb-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="139fb-114">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="139fb-115">构造并绘制轨迹</span><span class="sxs-lookup"><span data-stu-id="139fb-115">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
- [<span data-ttu-id="139fb-116">使用笔绘制线条和形状</span><span class="sxs-lookup"><span data-stu-id="139fb-116">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
