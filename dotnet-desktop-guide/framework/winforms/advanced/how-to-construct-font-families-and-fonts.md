---
title: 如何：构造字体系列和字体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: 2d609525858c7a8ff77c0b86900b4fc7d6b4e39a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970334"
---
# <a name="how-to-construct-font-families-and-fonts"></a>如何：构造字体系列和字体
GDI + 将具有相同字样但不同样式的字体分组为字体系列。 例如，Arial 字体系列包含以下字体：  
  
- 宋体  
  
- 宋体  
  
- 宋体  
  
- 宋体  
  
 GDI + 使用四种样式形成系列：常规、粗体、斜体和粗体斜体。 不将形容词（如 *窄幅* 和 *舍入* ）视为样式;它们是系列名称的一部分。 例如，Arial 窄是包含以下成员的字体系列：  
  
- 宋体  
  
- 宋体  
  
- 宋体  
  
- 宋体  
  
 在使用 GDI + 绘制文本之前，需要构造一个 <xref:System.Drawing.FontFamily> 对象和一个 <xref:System.Drawing.Font> 对象。 <xref:System.Drawing.FontFamily>对象指定字样 (例如，Arial) ， <xref:System.Drawing.Font> 对象指定大小、样式和单位。  
  
## <a name="example"></a>示例  
 下面的示例构造一个常规样式 Arial 字体，大小为16像素。 在下面的代码中，传递给构造函数的第一个参数 <xref:System.Drawing.Font.%23ctor%2A> 是 <xref:System.Drawing.FontFamily> 对象。 第二个参数指定以第四个参数标识的单位度量的字体大小。 第三个参数标识样式。  
  
 <xref:System.Drawing.GraphicsUnit.Pixel> 是枚举的成员 <xref:System.Drawing.GraphicsUnit> ，并且 <xref:System.Drawing.FontStyle.Regular> 是枚举的成员 <xref:System.Drawing.FontStyle> 。  
  
 [!code-csharp[System.Drawing.FontsAndText#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>另请参阅

- [使用字体和文本](using-fonts-and-text.md)
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
