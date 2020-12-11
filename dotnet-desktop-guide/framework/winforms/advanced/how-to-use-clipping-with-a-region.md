---
title: 如何：对区域使用剪裁
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: e62be137b36a2f369c02151466154f6b3bab090b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971396"
---
# <a name="how-to-use-clipping-with-a-region"></a>如何：对区域使用剪裁
类的属性之一 <xref:System.Drawing.Graphics> 是剪辑区域。 给定对象完成的所有绘图 <xref:System.Drawing.Graphics> 仅限于该对象的剪辑区域 <xref:System.Drawing.Graphics> 。 可以通过调用方法设置剪辑区域 <xref:System.Drawing.Graphics.SetClip%2A> 。  
  
## <a name="example"></a>示例  
 下面的示例构造一个包含单个多边形的路径。 然后，代码基于该路径构造一个区域。 区域将传递给对象的 <xref:System.Drawing.Graphics.SetClip%2A> 方法 <xref:System.Drawing.Graphics> ，然后绘制两个字符串。  
  
 下图显示了剪切的字符串：  
  
 ![显示已剪裁字符串的屏幕截图。](./media/how-to-use-clipping-with-a-region/clipped-strings-polygon.png)  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>另请参阅

- [GDI+ 中的区域](regions-in-gdi.md)
- [使用区域](using-regions.md)
