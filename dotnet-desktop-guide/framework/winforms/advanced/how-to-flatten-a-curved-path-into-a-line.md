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
# <a name="how-to-flatten-a-curved-path-into-a-line"></a>如何：将曲线路径平展为直线
<xref:System.Drawing.Drawing2D.GraphicsPath>对象存储一系列直线和贝塞尔样条。 您可以将几种类型的曲线 (省略号、弧形、基数样条) 添加到路径，但每个曲线在存储在路径中之前都将转换为贝塞尔样条。 平展路径包括将路径中的每个贝塞尔样条转换为一系列直线。 下图显示了平展前后的路径。  
  
 ![直线和曲线](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")  
  
### <a name="to-flatten-a-path"></a>平展路径  
  
- 调用 <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> 对象的方法 <xref:System.Drawing.Drawing2D.GraphicsPath> 。 <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>方法接收 flatness 参数，该参数指定平展路径与原始路径之间的最大距离。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [直线、曲线和图形](lines-curves-and-shapes.md)
- [构造并绘制轨迹](constructing-and-drawing-paths.md)
