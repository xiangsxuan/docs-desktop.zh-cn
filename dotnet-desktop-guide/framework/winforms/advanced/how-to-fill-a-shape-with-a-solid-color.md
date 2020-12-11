---
title: 如何：用纯色填充形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
ms.openlocfilehash: d6fe7a252029ff80f21d99f7342fabb1d29fbe24
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971445"
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a>如何：用纯色填充形状
若要使用纯色填充形状，请创建一个 <xref:System.Drawing.SolidBrush> 对象，然后将该 <xref:System.Drawing.SolidBrush> 对象作为参数传递给该类的一个填充方法 <xref:System.Drawing.Graphics> 。 下面的示例演示如何使用红色填充椭圆。  
  
## <a name="example"></a>示例  
 在下面的代码中， <xref:System.Drawing.SolidBrush.%23ctor%2A> 构造函数采用 <xref:System.Drawing.Color> 对象作为其唯一的参数。 方法使用的值 <xref:System.Drawing.Color.FromArgb%2A> 表示颜色的 alpha、红色、绿色和蓝色成分。 其中每个值必须介于0到255之间。 第一个255表示颜色完全不透明，第二个255指示红色组件处于完全强度。 这两个零表示绿色和蓝色分量的强度均为0。  
  
 传递给方法 (0，0，100，60) 的四个数字 <xref:System.Drawing.Graphics.FillEllipse%2A> 指定椭圆的边框的位置和大小。 该矩形的左上角为 (0，0) ，宽度为100，高度为60。  
  
 [!code-csharp[System.Drawing.UsingABrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅

- [使用画笔填充形状](using-a-brush-to-fill-shapes.md)
