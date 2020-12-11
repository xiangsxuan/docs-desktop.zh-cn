---
title: 使用图形容器
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: cfad7254057a31ea8268784cd4b6849850f3e2aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970771"
---
# <a name="using-graphics-containers"></a>使用图形容器
<xref:System.Drawing.Graphics>对象提供一些方法，例如 <xref:System.Drawing.Graphics.DrawLine%2A> 、 <xref:System.Drawing.Graphics.DrawImage%2A> 和， <xref:System.Drawing.Graphics.DrawString%2A> 用于显示矢量图像、光栅图像和文本。 <xref:System.Drawing.Graphics>对象还具有多个属性，这些属性会影响所绘制项的质量和方向。 例如，"平滑模式" 属性确定是否将抗锯齿应用于线条和曲线，而 "世界转换" 属性会影响绘制的项的位置和旋转。  
  
 <xref:System.Drawing.Graphics>对象与特定的显示设备相关联。 使用 <xref:System.Drawing.Graphics> 对象在窗口中绘制时， <xref:System.Drawing.Graphics> 对象也与该特定窗口相关联。  
  
 <xref:System.Drawing.Graphics>对象可以被视为容器，因为它包含一组影响绘图的属性，并且该对象链接到特定于设备的信息。 可以 <xref:System.Drawing.Graphics> 通过调用对象的方法，在现有对象内创建辅助容器 <xref:System.Drawing.Graphics.BeginContainer%2A> <xref:System.Drawing.Graphics> 。  
  
## <a name="in-this-section"></a>本节内容  
 [管理 Graphics 对象的状态](managing-the-state-of-a-graphics-object.md)  
 介绍如何管理对象的质量设置、剪辑区域和转换 <xref:System.Drawing.Graphics> 。  
  
 [使用嵌套的 Graphics 容器](using-nested-graphics-containers.md)  
 演示如何使用容器来控制对象的状态 <xref:System.Drawing.Graphics> 。
