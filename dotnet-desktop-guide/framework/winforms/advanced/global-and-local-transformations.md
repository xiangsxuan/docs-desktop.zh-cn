---
title: 全局变换和局部变换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
ms.openlocfilehash: f62efb31e95b0797272997fadbc28459579a0de0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970810"
---
# <a name="global-and-local-transformations"></a>全局变换和局部变换
全局转换是应用于给定对象绘制的每个项的转换 <xref:System.Drawing.Graphics> 。 与此相反，本地转换是应用于要绘制的特定项的转换。  
  
## <a name="global-transformations"></a>全局转换  
 若要创建全局转换，请构造 <xref:System.Drawing.Graphics> 对象，然后操作其 <xref:System.Drawing.Graphics.Transform%2A> 属性。 <xref:System.Drawing.Graphics.Transform%2A>属性是一个 <xref:System.Drawing.Drawing2D.Matrix> 对象，因此它可以保存任何仿射转换序列。 存储在属性中的转换 <xref:System.Drawing.Graphics.Transform%2A> 称为 "世界转换"。 <xref:System.Drawing.Graphics>类提供若干用于构建复合世界转换的方法： <xref:System.Drawing.Graphics.MultiplyTransform%2A> 、 <xref:System.Drawing.Graphics.RotateTransform%2A> 、 <xref:System.Drawing.Graphics.ScaleTransform%2A> 和 <xref:System.Drawing.Graphics.TranslateTransform%2A> 。 下面的示例将一个椭圆绘制两次：在创建世界变换之前和之后。 变换首先在 y 方向上按比例为0.5，然后在 x 方向上平移50个单位，然后旋转30度。  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 下图显示了转换中涉及的矩阵。  
  
 ![转换](./media/aboutgdip05-art14.gif "AboutGdip05_art14")  
  
> [!NOTE]
> 在前面的示例中，椭圆围绕坐标系统的原点旋转，后者位于工作区的左上角。 这产生的结果与围绕椭圆中心旋转椭圆的结果不同。  
  
## <a name="local-transformations"></a>本地转换  
 局部转换应用于要绘制的特定项。 例如， <xref:System.Drawing.Drawing2D.GraphicsPath> 对象具有一个可 <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> 用于转换该路径的数据点的方法。 下面的示例绘制一个没有转换的矩形和一个带有旋转转换的路径。  (假设没有世界转换。 )   
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 可以结合使用世界转换和局部转换来实现各种结果。 例如，您可以使用世界变换来修改坐标系统，使用局部转换来旋转和缩放在新坐标系统上绘制的对象。  
  
 假设您想要一个坐标系统，该系统的原点为200像素，距工作区的左边缘和工作区顶部150像素。 而且，假设您希望度量单位为像素，而 x 轴指向右侧，y 轴指向上方，则为。 默认坐标系统的 y 轴向下移动，因此您需要在水平轴上执行反射。 下图显示了此类反射的矩阵。  
  
 ![转换](./media/aboutgdip05-art15.gif "AboutGdip05_art15")  
  
 接下来，假设你需要向右和150个单位执行平移200单元。  
  
 下面的示例通过设置对象的世界变换来确定刚刚介绍的坐标系统 <xref:System.Drawing.Graphics> 。  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 下面的代码 (放置在前面示例的末尾) 创建一个路径，该路径包含一个矩形，该矩形的左上角位于新坐标系统的原点。 该矩形只填充一次，不使用本地转换，一次则使用本地转换。 局部转换由2的水平缩放，后跟30度的旋转。  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 下图显示了新的坐标系统和两个矩形。  
  
 ![转换](./media/aboutgdip05-art16.gif "AboutGdip05_art16")  
  
## <a name="see-also"></a>另请参阅

- [坐标系和坐标转换](coordinate-systems-and-transformations.md)
- [在托管 GDI+ 中使用变换](using-transformations-in-managed-gdi.md)
