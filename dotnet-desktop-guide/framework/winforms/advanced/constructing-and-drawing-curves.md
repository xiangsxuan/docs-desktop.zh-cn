---
title: 构造并绘制曲线
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: 4c1b0cc6c6f878569fcf0c392f1b6f9683ec8afc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970683"
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="d1aaa-102">构造并绘制曲线</span><span class="sxs-lookup"><span data-stu-id="d1aaa-102">Constructing and Drawing Curves</span></span>
<span data-ttu-id="d1aaa-103">GDI + 支持多种曲线类型：椭圆、弧形、基数样条和贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-103">GDI+ supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="d1aaa-104">椭圆由其边框定义;弧形是由起始角度和扫描角度定义的椭圆的一部分。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="d1aaa-105">基数样条由点数组和张力参数定义：曲线平滑传递到数组中的每个点，而张力参数影响曲线弯曲的方式。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="d1aaa-106">贝塞尔样条由两个端点和两个控制点定义，曲线不穿过控制点，但当曲线从一个端点向另一个端点时，控制点将影响方向和弯曲。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1aaa-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="d1aaa-107">In This Section</span></span>  
 [<span data-ttu-id="d1aaa-108">如何：绘制基数自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="d1aaa-108">How to: Draw Cardinal Splines</span></span>](how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="d1aaa-109">描述基数样条以及如何绘制它们。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="d1aaa-110">如何：绘制单一贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="d1aaa-110">How to: Draw a Single Bézier Spline</span></span>](how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="d1aaa-111">介绍贝塞尔样条以及如何绘制一个样条。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="d1aaa-112">如何：绘制一系列贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="d1aaa-112">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="d1aaa-113">说明如何按顺序绘制多个贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="d1aaa-113">Explains how to draw several Bézier splines in sequence.</span></span>
