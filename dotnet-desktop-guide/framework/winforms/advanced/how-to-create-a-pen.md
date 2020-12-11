---
title: 如何：创建钢笔
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating pens
- pens [Windows Forms], creating
- Pen object
ms.assetid: 7fbea8b7-7ac1-4413-9c17-733a850381e3
ms.openlocfilehash: 69fe6157c710ae63df9dbf391a5d355d1c3f9765
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970581"
---
# <a name="how-to-create-a-pen"></a>如何：创建钢笔
此示例将创建一个 <xref:System.Drawing.Pen> 对象。  
  
## <a name="example"></a>示例  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## <a name="robust-programming"></a>可靠编程  
 使用完使用系统资源的对象（如对象）后， <xref:System.Drawing.Pen> 应 <xref:System.Drawing.Pen.Dispose%2A> 对其调用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Pen>
- [图形编程入门](getting-started-with-graphics-programming.md)
- [GDI+ 中的笔、直线和矩形](pens-lines-and-rectangles-in-gdi.md)
