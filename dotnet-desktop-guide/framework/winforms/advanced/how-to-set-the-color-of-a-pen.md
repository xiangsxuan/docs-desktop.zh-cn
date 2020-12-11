---
title: 如何：设置钢笔颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: ee2d3f8cdf6dd10ca2a9ff0dd3e66b164c84f21b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971654"
---
# <a name="how-to-set-the-color-of-a-pen"></a><span data-ttu-id="9914e-102">如何：设置钢笔颜色</span><span class="sxs-lookup"><span data-stu-id="9914e-102">How to: Set the Color of a Pen</span></span>
<span data-ttu-id="9914e-103">此示例更改预先存在的对象的颜色 <xref:System.Drawing.Pen></span><span class="sxs-lookup"><span data-stu-id="9914e-103">This example changes the color of a pre-existing <xref:System.Drawing.Pen> object</span></span>  
  
## <a name="example"></a><span data-ttu-id="9914e-104">示例</span><span class="sxs-lookup"><span data-stu-id="9914e-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9914e-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="9914e-105">Compiling the Code</span></span>  
 <span data-ttu-id="9914e-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="9914e-106">This example requires:</span></span>  
  
- <span data-ttu-id="9914e-107">一个 <xref:System.Drawing.Pen> 名为的对象 `myPen` 。</span><span class="sxs-lookup"><span data-stu-id="9914e-107">A <xref:System.Drawing.Pen> object named `myPen`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9914e-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="9914e-108">Robust Programming</span></span>  
 <span data-ttu-id="9914e-109">你应 <xref:System.Drawing.Pen.Dispose%2A> 在使用系统资源的对象上调用 (例如，在 <xref:System.Drawing.Pen> 使用完对象后) 对象。</span><span class="sxs-lookup"><span data-stu-id="9914e-109">You should call <xref:System.Drawing.Pen.Dispose%2A> on objects that consume system resources (such as <xref:System.Drawing.Pen> objects) after you are finished using them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9914e-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9914e-110">See also</span></span>

- <xref:System.Drawing.Pen>
- [<span data-ttu-id="9914e-111">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="9914e-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="9914e-112">如何：创建钢笔</span><span class="sxs-lookup"><span data-stu-id="9914e-112">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="9914e-113">使用笔绘制线条和形状</span><span class="sxs-lookup"><span data-stu-id="9914e-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="9914e-114">GDI+ 中的笔、直线和矩形</span><span class="sxs-lookup"><span data-stu-id="9914e-114">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
