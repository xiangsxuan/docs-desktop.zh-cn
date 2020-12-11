---
title: 坐标
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: c95888f31bfc867e9c028d53072ab3d710256708
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970513"
---
# <a name="windows-forms-coordinates"></a>Windows 窗体坐标
Windows 窗体的坐标系统基于设备坐标，在 Windows 窗体中绘制时的基本度量单位是 (通常为设备单位，像素) 。 屏幕上的点按 x 和 y 坐标对进行说明，其中 x 坐标向右递增，y 坐标从上到下递增。 根据您指定的是屏幕坐标还是工作区坐标，原点相对于屏幕的位置会有所不同。  
  
## <a name="screen-coordinates"></a>屏幕坐标  
 Windows 窗体应用程序以屏幕坐标的形式指定窗口在屏幕上的位置。 对于屏幕坐标，原点是屏幕的左上角。 窗口的完整位置通常由一个结构描述，该 <xref:System.Drawing.Rectangle> 结构包含定义窗口的左上角和右下角的两个点的屏幕坐标。  
  
## <a name="client-coordinates"></a>工作区坐标  
 Windows 窗体应用程序使用客户端坐标指定窗体或控件中点的位置。 工作区坐标原点是控件或窗体工作区的左上角。 客户端坐标可确保应用程序在窗体或控件中绘制时可以使用一致的坐标值，而不管窗体或控件在屏幕上的位置。  
  
 工作区的维度也由 <xref:System.Drawing.Rectangle> 包含区域的工作区坐标的结构描述。 在所有情况下，矩形的左上角坐标都包含在工作区中，同时排除右下坐标。 图形操作不包括工作区的右边缘和下边缘。 例如， <xref:System.Drawing.Graphics.FillRectangle%2A> 方法将填充指定矩形的右边缘和下边缘，但不包括这些边缘。  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a>从一种坐标类型映射到另一种坐标  
 有时，可能需要从屏幕坐标映射到工作区坐标。 通过使用 <xref:System.Windows.Forms.Control.PointToClient%2A> 类中提供的和方法，可以轻松实现此目的 <xref:System.Windows.Forms.Control.PointToScreen%2A> <xref:System.Windows.Forms.Control> 。 例如，的 <xref:System.Windows.Forms.Control.MousePosition%2A> 属性 <xref:System.Windows.Forms.Control> 以屏幕坐标的形式报告，但你可能希望将其转换为工作区坐标。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Control.PointToClient%2A>
- <xref:System.Windows.Forms.Control.PointToScreen%2A>
