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
# <a name="constructing-and-drawing-curves"></a>构造并绘制曲线
GDI + 支持多种曲线类型：椭圆、弧形、基数样条和贝塞尔样条。 椭圆由其边框定义;弧形是由起始角度和扫描角度定义的椭圆的一部分。 基数样条由点数组和张力参数定义：曲线平滑传递到数组中的每个点，而张力参数影响曲线弯曲的方式。 贝塞尔样条由两个端点和两个控制点定义，曲线不穿过控制点，但当曲线从一个端点向另一个端点时，控制点将影响方向和弯曲。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：绘制基数自由绘制曲线](how-to-draw-cardinal-splines.md)  
 描述基数样条以及如何绘制它们。  
  
 [如何：绘制单一贝塞尔自由绘制曲线](how-to-draw-a-single-bezier-spline.md)  
 介绍贝塞尔样条以及如何绘制一个样条。  
  
 [如何：绘制一系列贝塞尔自由绘制曲线](how-to-draw-a-sequence-of-bezier-splines.md)  
 说明如何按顺序绘制多个贝塞尔样条。
