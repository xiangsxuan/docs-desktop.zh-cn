---
title: 如何：将曲线路径平展为直线
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: d59a802618ddd5080c651e822ed4c09641f7f170
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971698"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="acb8d-102">如何：将曲线路径平展为直线</span><span class="sxs-lookup"><span data-stu-id="acb8d-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="acb8d-103"><xref:System.Drawing.Drawing2D.GraphicsPath>对象存储一系列直线和贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="acb8d-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="acb8d-104">您可以将几种类型的曲线 (省略号、弧形、基数样条) 添加到路径，但每个曲线在存储在路径中之前都将转换为贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="acb8d-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="acb8d-105">平展路径包括将路径中的每个贝塞尔样条转换为一系列直线。</span><span class="sxs-lookup"><span data-stu-id="acb8d-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="acb8d-106">下图显示了平展前后的路径。</span><span class="sxs-lookup"><span data-stu-id="acb8d-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="acb8d-107">![直线和曲线](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="acb8d-107">![Straight Lines and Curves](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="acb8d-108">平展路径</span><span class="sxs-lookup"><span data-stu-id="acb8d-108">To Flatten a Path</span></span>  
  
- <span data-ttu-id="acb8d-109">调用 <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> 对象的方法 <xref:System.Drawing.Drawing2D.GraphicsPath> 。</span><span class="sxs-lookup"><span data-stu-id="acb8d-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="acb8d-110"><xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>方法接收 flatness 参数，该参数指定平展路径与原始路径之间的最大距离。</span><span class="sxs-lookup"><span data-stu-id="acb8d-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb8d-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="acb8d-111">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [<span data-ttu-id="acb8d-112">直线、曲线和图形</span><span class="sxs-lookup"><span data-stu-id="acb8d-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="acb8d-113">构造并绘制轨迹</span><span class="sxs-lookup"><span data-stu-id="acb8d-113">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
