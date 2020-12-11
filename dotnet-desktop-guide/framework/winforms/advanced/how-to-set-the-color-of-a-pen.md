---
title: 如何：设置钢笔颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: ee2d3f8cdf6dd10ca2a9ff0dd3e66b164c84f21b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971654"
---
# <a name="how-to-set-the-color-of-a-pen"></a>如何：设置钢笔颜色
此示例更改预先存在的对象的颜色 <xref:System.Drawing.Pen>  
  
## <a name="example"></a>示例  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 一个 <xref:System.Drawing.Pen> 名为的对象 `myPen` 。  
  
## <a name="robust-programming"></a>可靠编程  
 你应 <xref:System.Drawing.Pen.Dispose%2A> 在使用系统资源的对象上调用 (例如，在 <xref:System.Drawing.Pen> 使用完对象后) 对象。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Pen>
- [图形编程入门](getting-started-with-graphics-programming.md)
- [如何：创建钢笔](how-to-create-a-pen.md)
- [使用笔绘制线条和形状](using-a-pen-to-draw-lines-and-shapes.md)
- [GDI+ 中的笔、直线和矩形](pens-lines-and-rectangles-in-gdi.md)
