---
title: 为什么转换顺序非常重要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], order significance
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
ms.openlocfilehash: 08927ebaa460e19e558dce22f39c13c31f0e49d0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971351"
---
# <a name="why-transformation-order-is-significant"></a>为什么转换顺序非常重要
单个 <xref:System.Drawing.Drawing2D.Matrix> 对象可以存储单个转换或转换序列。 后者称为复合转换。 复合转换的矩阵通过将各个转换的矩阵相乘获得。  
  
## <a name="composite-transform-examples"></a>复合转换示例  
 在复合转换中，各个转换的顺序非常重要。 例如，如果您首先旋转，然后缩放，然后再翻译，则会得到不同于第一次平移、旋转和缩放的结果。 在 GDI + 中，复合转换是从左到右生成的。 如果 S、R 和 T 分别为 "缩放"、"旋转" 和 "平移" 矩阵，则产品 SRT (按顺序) 是首次缩放、旋转然后平移的复合转换的矩阵。 产品 SRT 所生成的矩阵与产品 TRS 生成的矩阵不同。  
  
 一个原因是重要的是，旋转和缩放等转换是相对坐标系统的原点完成的。 缩放位于原点中心的对象将生成与缩放离开原点的对象不同的结果。 同样，旋转位于原点中心的对象会产生不同的结果，而不是旋转远离原点的对象。  
  
 下面的示例将缩放、旋转和平移 (按该顺序) ，以形成复合转换。 <xref:System.Drawing.Drawing2D.MatrixOrder.Append>传递给方法的参数 <xref:System.Drawing.Graphics.RotateTransform%2A> 指示旋转将遵循缩放。 同样， <xref:System.Drawing.Drawing2D.MatrixOrder.Append> 传递给方法的参数 <xref:System.Drawing.Graphics.TranslateTransform%2A> 指示转换将在旋转后执行。 <xref:System.Drawing.Drawing2D.MatrixOrder.Append> 和 <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> 是枚举的成员 <xref:System.Drawing.Drawing2D.MatrixOrder> 。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 下面的示例与前面的示例一样，调用了相同的方法，但调用的顺序相反。 首先转换后的运算顺序，再旋转，然后按比例调整，这会产生与第一次缩放不同的结果，然后旋转、平移。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 反转复合转换中各个转换顺序的一种方法是反转方法调用序列的顺序。 控制操作顺序的另一种方法是更改矩阵顺序参数。 下面的示例与前面的示例相同，不同之处在于已 <xref:System.Drawing.Drawing2D.MatrixOrder.Append> 更改为 <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> 。 矩阵乘法按照顺序 SRT 完成，其中 S、R 和 T 分别是用于缩放、旋转和平移的矩阵。 复合转换的顺序依次为 "缩放"、"旋转" 和 "转换"。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 前面的示例的结果与本主题中的第一个示例的结果相同。 这是因为我们反转了方法调用的顺序和矩阵相乘的顺序。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Drawing2D.Matrix>
- [坐标系和坐标转换](coordinate-systems-and-transformations.md)
- [在托管 GDI+ 中使用变换](using-transformations-in-managed-gdi.md)
