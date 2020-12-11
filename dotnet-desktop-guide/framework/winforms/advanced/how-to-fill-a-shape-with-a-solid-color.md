---
title: 如何：用纯色填充形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
ms.openlocfilehash: d6fe7a252029ff80f21d99f7342fabb1d29fbe24
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971445"
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a><span data-ttu-id="8fdad-102">如何：用纯色填充形状</span><span class="sxs-lookup"><span data-stu-id="8fdad-102">How to: Fill a Shape with a Solid Color</span></span>
<span data-ttu-id="8fdad-103">若要使用纯色填充形状，请创建一个 <xref:System.Drawing.SolidBrush> 对象，然后将该 <xref:System.Drawing.SolidBrush> 对象作为参数传递给该类的一个填充方法 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="8fdad-103">To fill a shape with a solid color, create a <xref:System.Drawing.SolidBrush> object, and then pass that <xref:System.Drawing.SolidBrush> object as an argument to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="8fdad-104">下面的示例演示如何使用红色填充椭圆。</span><span class="sxs-lookup"><span data-stu-id="8fdad-104">The following example shows how to fill an ellipse with the color red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fdad-105">示例</span><span class="sxs-lookup"><span data-stu-id="8fdad-105">Example</span></span>  
 <span data-ttu-id="8fdad-106">在下面的代码中， <xref:System.Drawing.SolidBrush.%23ctor%2A> 构造函数采用 <xref:System.Drawing.Color> 对象作为其唯一的参数。</span><span class="sxs-lookup"><span data-stu-id="8fdad-106">In the following code, the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor takes a <xref:System.Drawing.Color> object as its only argument.</span></span> <span data-ttu-id="8fdad-107">方法使用的值 <xref:System.Drawing.Color.FromArgb%2A> 表示颜色的 alpha、红色、绿色和蓝色成分。</span><span class="sxs-lookup"><span data-stu-id="8fdad-107">The values used by the <xref:System.Drawing.Color.FromArgb%2A> method represent the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="8fdad-108">其中每个值必须介于0到255之间。</span><span class="sxs-lookup"><span data-stu-id="8fdad-108">Each of these values must be in the range 0 through 255.</span></span> <span data-ttu-id="8fdad-109">第一个255表示颜色完全不透明，第二个255指示红色组件处于完全强度。</span><span class="sxs-lookup"><span data-stu-id="8fdad-109">The first 255 indicates that the color is fully opaque, and the second 255 indicates that the red component is at full intensity.</span></span> <span data-ttu-id="8fdad-110">这两个零表示绿色和蓝色分量的强度均为0。</span><span class="sxs-lookup"><span data-stu-id="8fdad-110">The two zeros indicate that the green and blue components both have an intensity of 0.</span></span>  
  
 <span data-ttu-id="8fdad-111">传递给方法 (0，0，100，60) 的四个数字 <xref:System.Drawing.Graphics.FillEllipse%2A> 指定椭圆的边框的位置和大小。</span><span class="sxs-lookup"><span data-stu-id="8fdad-111">The four numbers (0, 0, 100, 60) passed to the <xref:System.Drawing.Graphics.FillEllipse%2A> method specify the location and size of the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="8fdad-112">该矩形的左上角为 (0，0) ，宽度为100，高度为60。</span><span class="sxs-lookup"><span data-stu-id="8fdad-112">The rectangle has an upper-left corner of (0, 0), a width of 100, and a height of 60.</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8fdad-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="8fdad-113">Compiling the Code</span></span>  
 <span data-ttu-id="8fdad-114">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="8fdad-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fdad-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8fdad-115">See also</span></span>

- [<span data-ttu-id="8fdad-116">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="8fdad-116">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
