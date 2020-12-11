---
title: 使用世界变换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: f40d7e8cb814344365e8b88c2659751903b79d77
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971369"
---
# <a name="using-the-world-transformation"></a>使用世界变换
世界转换是类的属性 <xref:System.Drawing.Graphics> 。 指定世界转换的数值存储在一个 <xref:System.Drawing.Drawing2D.Matrix> 对象中，该对象表示一个3×3矩阵。 <xref:System.Drawing.Drawing2D.Matrix>和 <xref:System.Drawing.Graphics> 类有几种方法可用于设置世界变换矩阵中的数字。  
  
## <a name="different-types-of-transformations"></a>不同类型的转换  
 在下面的示例中，代码首先创建50×50矩形，并将其定位到 (0，0) 的原点。 源位于工作区的左上角。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 下面的代码应用一个缩放转换，该转换在 x 方向上将矩形扩展为1.75，并在 y 方向上按0.5 缩小矩形。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 结果是一个矩形，该矩形的长度在 x 方向上，并且在 y 方向上比原始的更短。  
  
 若要旋转矩形而不是对其进行缩放，请使用以下代码：  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 若要转换该矩形，请使用以下代码：  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Drawing2D.Matrix>
- [坐标系和坐标转换](coordinate-systems-and-transformations.md)
- [在托管 GDI+ 中使用变换](using-transformations-in-managed-gdi.md)
