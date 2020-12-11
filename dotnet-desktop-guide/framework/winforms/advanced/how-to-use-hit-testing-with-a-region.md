---
title: 如何：对区域使用命中测试
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 136f15f1364fb2aed791b4a61d0f11411b055967
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971390"
---
# <a name="how-to-use-hit-testing-with-a-region"></a>如何：对区域使用命中测试
命中测试的目的是确定光标是否位于给定对象（如图标或按钮）上。  
  
## <a name="example"></a>示例  
 下面的示例通过构造两个矩形区域的并集来创建一个加形区域。 假定变量 `point` 保存最近单击的位置。 代码将检查是否 `point` 在加号区域中。 如果点位于 (命中) 的区域中，则使用不透明的红色画笔填充区域。 否则，将用半透明的红色画笔填充区域。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Region>
- [GDI+ 中的区域](regions-in-gdi.md)
- [如何：对区域使用剪裁](how-to-use-clipping-with-a-region.md)
