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
# <a name="using-graphics-containers"></a><span data-ttu-id="4a5f0-102">使用图形容器</span><span class="sxs-lookup"><span data-stu-id="4a5f0-102">Using Graphics Containers</span></span>
<span data-ttu-id="4a5f0-103"><xref:System.Drawing.Graphics>对象提供一些方法，例如 <xref:System.Drawing.Graphics.DrawLine%2A> 、 <xref:System.Drawing.Graphics.DrawImage%2A> 和， <xref:System.Drawing.Graphics.DrawString%2A> 用于显示矢量图像、光栅图像和文本。</span><span class="sxs-lookup"><span data-stu-id="4a5f0-103">A <xref:System.Drawing.Graphics> object provides methods such as <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, and <xref:System.Drawing.Graphics.DrawString%2A> for displaying vector images, raster images, and text.</span></span> <span data-ttu-id="4a5f0-104"><xref:System.Drawing.Graphics>对象还具有多个属性，这些属性会影响所绘制项的质量和方向。</span><span class="sxs-lookup"><span data-stu-id="4a5f0-104">A <xref:System.Drawing.Graphics> object also has several properties that influence the quality and orientation of the items that are drawn.</span></span> <span data-ttu-id="4a5f0-105">例如，"平滑模式" 属性确定是否将抗锯齿应用于线条和曲线，而 "世界转换" 属性会影响绘制的项的位置和旋转。</span><span class="sxs-lookup"><span data-stu-id="4a5f0-105">For example, the smoothing mode property determines whether antialiasing is applied to lines and curves, and the world transformation property influences the position and rotation of the items that are drawn.</span></span>  
  
 <span data-ttu-id="4a5f0-106"><xref:System.Drawing.Graphics>对象与特定的显示设备相关联。</span><span class="sxs-lookup"><span data-stu-id="4a5f0-106">A <xref:System.Drawing.Graphics> object is associated with a particular display device.</span></span> <span data-ttu-id="4a5f0-107">使用 <xref:System.Drawing.Graphics> 对象在窗口中绘制时， <xref:System.Drawing.Graphics> 对象也与该特定窗口相关联。</span><span class="sxs-lookup"><span data-stu-id="4a5f0-107">When you use a <xref:System.Drawing.Graphics> object to draw in a window, the <xref:System.Drawing.Graphics> object is also associated with that particular window.</span></span>  
  
 <span data-ttu-id="4a5f0-108"><xref:System.Drawing.Graphics>对象可以被视为容器，因为它包含一组影响绘图的属性，并且该对象链接到特定于设备的信息。</span><span class="sxs-lookup"><span data-stu-id="4a5f0-108">A <xref:System.Drawing.Graphics> object can be thought of as a container because it holds a set of properties that influence drawing and it is linked to device-specific information.</span></span> <span data-ttu-id="4a5f0-109">可以 <xref:System.Drawing.Graphics> 通过调用对象的方法，在现有对象内创建辅助容器 <xref:System.Drawing.Graphics.BeginContainer%2A> <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="4a5f0-109">You can create a secondary container within an existing <xref:System.Drawing.Graphics> object by calling the <xref:System.Drawing.Graphics.BeginContainer%2A> method of that <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a5f0-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="4a5f0-110">In This Section</span></span>  
 [<span data-ttu-id="4a5f0-111">管理 Graphics 对象的状态</span><span class="sxs-lookup"><span data-stu-id="4a5f0-111">Managing the State of a Graphics Object</span></span>](managing-the-state-of-a-graphics-object.md)  
 <span data-ttu-id="4a5f0-112">介绍如何管理对象的质量设置、剪辑区域和转换 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="4a5f0-112">Describes how manage the quality settings, clipping area and transformations of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [<span data-ttu-id="4a5f0-113">使用嵌套的 Graphics 容器</span><span class="sxs-lookup"><span data-stu-id="4a5f0-113">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)  
 <span data-ttu-id="4a5f0-114">演示如何使用容器来控制对象的状态 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="4a5f0-114">Shows how to use containers to control the state of the <xref:System.Drawing.Graphics> object.</span></span>
