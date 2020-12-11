---
title: 使用世界变换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: f40d7e8cb814344365e8b88c2659751903b79d77
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971369"
---
# <a name="using-the-world-transformation"></a><span data-ttu-id="4a943-102">使用世界变换</span><span class="sxs-lookup"><span data-stu-id="4a943-102">Using the World Transformation</span></span>
<span data-ttu-id="4a943-103">世界转换是类的属性 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="4a943-103">The world transformation is a property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="4a943-104">指定世界转换的数值存储在一个 <xref:System.Drawing.Drawing2D.Matrix> 对象中，该对象表示一个3×3矩阵。</span><span class="sxs-lookup"><span data-stu-id="4a943-104">The numbers that specify the world transformation are stored in a <xref:System.Drawing.Drawing2D.Matrix> object, which represents a 3×3 matrix.</span></span> <span data-ttu-id="4a943-105"><xref:System.Drawing.Drawing2D.Matrix>和 <xref:System.Drawing.Graphics> 类有几种方法可用于设置世界变换矩阵中的数字。</span><span class="sxs-lookup"><span data-stu-id="4a943-105">The <xref:System.Drawing.Drawing2D.Matrix> and <xref:System.Drawing.Graphics> classes have several methods for setting the numbers in the world transformation matrix.</span></span>  
  
## <a name="different-types-of-transformations"></a><span data-ttu-id="4a943-106">不同类型的转换</span><span class="sxs-lookup"><span data-stu-id="4a943-106">Different Types of Transformations</span></span>  
 <span data-ttu-id="4a943-107">在下面的示例中，代码首先创建50×50矩形，并将其定位到 (0，0) 的原点。</span><span class="sxs-lookup"><span data-stu-id="4a943-107">In the following example, the code first creates a 50×50 rectangle and locates it at the origin (0, 0).</span></span> <span data-ttu-id="4a943-108">源位于工作区的左上角。</span><span class="sxs-lookup"><span data-stu-id="4a943-108">The origin is at the upper-left corner of the client area.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 <span data-ttu-id="4a943-109">下面的代码应用一个缩放转换，该转换在 x 方向上将矩形扩展为1.75，并在 y 方向上按0.5 缩小矩形。</span><span class="sxs-lookup"><span data-stu-id="4a943-109">The following code applies a scaling transformation that expands the rectangle by a factor of 1.75 in the x direction and shrinks the rectangle by a factor of 0.5 in the y direction:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 <span data-ttu-id="4a943-110">结果是一个矩形，该矩形的长度在 x 方向上，并且在 y 方向上比原始的更短。</span><span class="sxs-lookup"><span data-stu-id="4a943-110">The result is a rectangle that is longer in the x direction and shorter in the y direction than the original.</span></span>  
  
 <span data-ttu-id="4a943-111">若要旋转矩形而不是对其进行缩放，请使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="4a943-111">To rotate the rectangle instead of scaling it, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 <span data-ttu-id="4a943-112">若要转换该矩形，请使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="4a943-112">To translate the rectangle, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="4a943-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a943-113">See also</span></span>

- <xref:System.Drawing.Drawing2D.Matrix>
- [<span data-ttu-id="4a943-114">坐标系和坐标转换</span><span class="sxs-lookup"><span data-stu-id="4a943-114">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="4a943-115">在托管 GDI+ 中使用变换</span><span class="sxs-lookup"><span data-stu-id="4a943-115">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
