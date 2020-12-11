---
title: Alpha 混合线条和填充
ms.date: 03/30/2017
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
ms.openlocfilehash: 66061341ee6539e2172c537a0b2a6ec9ff87565c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970614"
---
# <a name="alpha-blending-lines-and-fills"></a><span data-ttu-id="88b28-102">Alpha 混合线条和填充</span><span class="sxs-lookup"><span data-stu-id="88b28-102">Alpha Blending Lines and Fills</span></span>
<span data-ttu-id="88b28-103">在 GDI + 中，颜色是一个32位值，其中每个字母分别为 alpha、红色、绿色和蓝色。</span><span class="sxs-lookup"><span data-stu-id="88b28-103">In GDI+, a color is a 32-bit value with 8 bits each for alpha, red, green, and blue.</span></span> <span data-ttu-id="88b28-104">Alpha 值指示颜色的透明度—颜色与背景色混合的程度。</span><span class="sxs-lookup"><span data-stu-id="88b28-104">The alpha value indicates the transparency of the color — the extent to which the color is blended with the background color.</span></span> <span data-ttu-id="88b28-105">Alpha 值的范围为0到255，其中0表示完全透明的颜色，255表示完全不透明的颜色。</span><span class="sxs-lookup"><span data-stu-id="88b28-105">Alpha values range from 0 through 255, where 0 represents a fully transparent color, and 255 represents a fully opaque color.</span></span>  
  
 <span data-ttu-id="88b28-106">Alpha 混合是源和背景色数据的逐像素混合。</span><span class="sxs-lookup"><span data-stu-id="88b28-106">Alpha blending is a pixel-by-pixel blending of source and background color data.</span></span> <span data-ttu-id="88b28-107">对于给定的源颜色，三个组件中的每个 (红、绿、蓝) 根据以下公式与背景色的相应组件混合：</span><span class="sxs-lookup"><span data-stu-id="88b28-107">Each of the three components (red, green, blue) of a given source color is blended with the corresponding component of the background color according to the following formula:</span></span>  
  
 <span data-ttu-id="88b28-108">displayColor = sourceColor × alpha/255 + backgroundColor x (255 – alpha) /255</span><span class="sxs-lookup"><span data-stu-id="88b28-108">displayColor = sourceColor × alpha / 255 + backgroundColor × (255 – alpha) / 255</span></span>  
  
 <span data-ttu-id="88b28-109">例如，假设源颜色的红色分量为150，背景色的红色分量为100。</span><span class="sxs-lookup"><span data-stu-id="88b28-109">For example, suppose the red component of the source color is 150 and the red component of the background color is 100.</span></span> <span data-ttu-id="88b28-110">如果 alpha 值为200，则生成的颜色的红色分量按如下方式计算：</span><span class="sxs-lookup"><span data-stu-id="88b28-110">If the alpha value is 200, the red component of the resultant color is calculated as follows:</span></span>  
  
 <span data-ttu-id="88b28-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span><span class="sxs-lookup"><span data-stu-id="88b28-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88b28-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="88b28-112">In This Section</span></span>  
 [<span data-ttu-id="88b28-113">如何：绘制不透明和半透明的线条</span><span class="sxs-lookup"><span data-stu-id="88b28-113">How to: Draw Opaque and Semitransparent Lines</span></span>](how-to-draw-opaque-and-semitransparent-lines.md)  
 <span data-ttu-id="88b28-114">演示如何绘制 alpha 混合线条。</span><span class="sxs-lookup"><span data-stu-id="88b28-114">Shows how to draw alpha-blended lines.</span></span>  
  
 [<span data-ttu-id="88b28-115">如何：用不透明和半透明的画笔绘制</span><span class="sxs-lookup"><span data-stu-id="88b28-115">How to: Draw with Opaque and Semitransparent Brushes</span></span>](how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 <span data-ttu-id="88b28-116">说明如何与画笔混合。</span><span class="sxs-lookup"><span data-stu-id="88b28-116">Explains how to alpha-blend with brushes.</span></span>  
  
 [<span data-ttu-id="88b28-117">如何：使用复合模式控制 alpha 值混合处理</span><span class="sxs-lookup"><span data-stu-id="88b28-117">How to: Use Compositing Mode to Control Alpha Blending</span></span>](how-to-use-compositing-mode-to-control-alpha-blending.md)  
 <span data-ttu-id="88b28-118">描述如何使用控制 alpha 混合 <xref:System.Drawing.Drawing2D.CompositingMode> 。</span><span class="sxs-lookup"><span data-stu-id="88b28-118">Describes how to control alpha blending using <xref:System.Drawing.Drawing2D.CompositingMode>.</span></span>  
  
 [<span data-ttu-id="88b28-119">如何：使用颜色矩阵设置图像中的 Alpha 值</span><span class="sxs-lookup"><span data-stu-id="88b28-119">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>](how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 <span data-ttu-id="88b28-120">说明如何使用 <xref:System.Drawing.Imaging.ColorMatrix> 对象控制 alpha 混合。</span><span class="sxs-lookup"><span data-stu-id="88b28-120">Explains how to use a <xref:System.Drawing.Imaging.ColorMatrix> object to control alpha blending.</span></span>
