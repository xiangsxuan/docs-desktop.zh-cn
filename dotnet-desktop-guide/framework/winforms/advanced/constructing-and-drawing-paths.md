---
title: 构造并绘制轨迹
ms.date: 03/30/2017
helpviewer_keywords:
- paths [Windows Forms], drawing
- drawing paths [Windows Forms]
- graphics paths [Windows Forms], creating
- graphics paths [Windows Forms], drawing
- examples [Windows Forms], drawing paths
ms.assetid: f16ec921-56cf-46d1-9741-d7316ad06b23
ms.openlocfilehash: a698b93aac29a0a7f5c959b29a3feb41eb447e8c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970353"
---
# <a name="constructing-and-drawing-paths"></a><span data-ttu-id="833af-102">构造并绘制轨迹</span><span class="sxs-lookup"><span data-stu-id="833af-102">Constructing and Drawing Paths</span></span>
<span data-ttu-id="833af-103">路径是一系列图形基元 (线条、矩形、曲线、文本) 等，可以作为单个单元进行操作和绘制。</span><span class="sxs-lookup"><span data-stu-id="833af-103">A path is a sequence of graphics primitives (lines, rectangles, curves, text, and the like) that can be manipulated and drawn as a single unit.</span></span> <span data-ttu-id="833af-104">路径可划分为打开或关闭的 *图表* 。</span><span class="sxs-lookup"><span data-stu-id="833af-104">A path can be divided into *figures* that are either open or closed.</span></span> <span data-ttu-id="833af-105">一个图形可以包含多个基元。</span><span class="sxs-lookup"><span data-stu-id="833af-105">A figure can contain several primitives.</span></span>  
  
 <span data-ttu-id="833af-106">可以通过调用类的方法来绘制路径 <xref:System.Drawing.Graphics.DrawPath%2A> <xref:System.Drawing.Graphics> ，并且可以通过调用类的方法来填充路径 <xref:System.Drawing.Graphics.FillPath%2A> <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="833af-106">You can draw a path by calling the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class, and you can fill a path by calling the <xref:System.Drawing.Graphics.FillPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="833af-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="833af-107">In This Section</span></span>  
 [<span data-ttu-id="833af-108">如何：通过直线、曲线和形状创建图形</span><span class="sxs-lookup"><span data-stu-id="833af-108">How to: Create Figures from Lines, Curves, and Shapes</span></span>](how-to-create-figures-from-lines-curves-and-shapes.md)  
 <span data-ttu-id="833af-109">演示如何使用 <xref:System.Drawing.Drawing2D.GraphicsPath> 创建图形。</span><span class="sxs-lookup"><span data-stu-id="833af-109">Shows how to use a <xref:System.Drawing.Drawing2D.GraphicsPath> to create figures.</span></span>  
  
 [<span data-ttu-id="833af-110">如何：填充开放图形</span><span class="sxs-lookup"><span data-stu-id="833af-110">How to: Fill Open Figures</span></span>](how-to-fill-open-figures.md)  
 <span data-ttu-id="833af-111">说明如何填充 <xref:System.Drawing.Drawing2D.GraphicsPath> 。</span><span class="sxs-lookup"><span data-stu-id="833af-111">Explains how to fill a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
 [<span data-ttu-id="833af-112">如何：将曲线路径平展为直线</span><span class="sxs-lookup"><span data-stu-id="833af-112">How to: Flatten a Curved Path into a Line</span></span>](how-to-flatten-a-curved-path-into-a-line.md)  
 <span data-ttu-id="833af-113">演示如何平展 <xref:System.Drawing.Drawing2D.GraphicsPath> 。</span><span class="sxs-lookup"><span data-stu-id="833af-113">Shows how to flatten a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="833af-114">参考</span><span class="sxs-lookup"><span data-stu-id="833af-114">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 <span data-ttu-id="833af-115">描述此类，并包含指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="833af-115">Describes this class and contains links to all of its members.</span></span>
