---
title: 如何：通过直线、曲线和形状创建图形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: c8cf7a7e08bed56fb704bba4e30ff369bc3fcf89
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970573"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a>如何：通过直线、曲线和形状创建图形
若要创建图形，请构造 <xref:System.Drawing.Drawing2D.GraphicsPath> ，然后调用方法（如 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 和）， <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> 以将基元添加到路径。  
  
## <a name="example"></a>示例  
 下面的代码示例创建了包含图形的路径：  
  
- 第一个示例创建一个具有单个图形的路径。 该图包含一个圆弧。圆弧的扫描角度为–180度，这在默认坐标系统中以逆时针表示。  
  
- 第二个示例创建一个具有两个图形的路径。 第一个图形是一条弧后跟一个直线。 第二个图形是一条后跟一条曲线的曲线。 第一个图形保持打开状态，并关闭第二个图形。  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它们需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [构造并绘制轨迹](constructing-and-drawing-paths.md)
- [使用笔绘制线条和形状](using-a-pen-to-draw-lines-and-shapes.md)
