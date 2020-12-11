---
title: 如何：创建特定形状的 Windows 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], rounded
- Windows Forms, custom shapes
- Windows Forms, shaped
- shaped forms
- forms [Windows Forms], changing the shape of
- forms [Windows Forms], circular
- forms [Windows Forms], nonrectangular
- Windows Forms, nonrectangular shape
- Windows Forms, rounded
- Windows Forms, circular
- forms [Windows Forms], custom shapes
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
ms.openlocfilehash: 3c90e6d5d2613239e513f8ec30d67b58084cba5e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970576"
---
# <a name="how-to-create-a-shaped-windows-form"></a>如何：创建特定形状的 Windows 窗体
此示例为窗体提供了一个随窗体一起调整大小的椭圆形形状。  
  
## <a name="example"></a>示例  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 <xref:System.Windows.Forms> 和 <xref:System.Drawing> 命名空间的引用。  
  
 此示例将重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法以更改窗体的形状。 若要使用此代码，请复制方法声明以及方法内的绘制代码。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Region>
- <xref:System.Drawing>
- <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>
- <xref:System.Windows.Forms.Control.Region%2A>
- [图形编程入门](getting-started-with-graphics-programming.md)
