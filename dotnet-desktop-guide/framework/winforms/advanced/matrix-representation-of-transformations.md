---
title: 转换的矩阵表示形式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- composite transformations
- transformations [Windows Forms], linear
- matrices
- translations in matrix representation
- transformations [Windows Forms], composite
- vectors
- linear transformations
- transformations [Windows Forms], matrix representation of
- transformations [Windows Forms], translation
- affine transformations
ms.assetid: 0659fe00-9e0c-41c4-9118-016f2404c905
ms.openlocfilehash: 24da407de24a924a68466e4301cc3f4a74cb2e94
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971622"
---
# <a name="matrix-representation-of-transformations"></a>转换的矩阵表示形式
M × n 矩阵是一组按 m 行和 n 列排列的数字。 下图显示了几个矩阵。  
  
 ![转换](./media/aboutgdip05-art04.gif "AboutGdip05_art04")  
  
 可以通过添加单个元素来添加大小相同的两个矩阵。 下图显示了矩阵添加的两个示例。  
  
 ![转换](./media/aboutgdip05-art05.gif "AboutGdip05_art05")  
  
 M × n 矩阵可以与 n × p 矩阵相乘，结果为 m × p 矩阵。 第一个矩阵中的列数必须与第二个矩阵中的行数相同。 例如，可以将4×2矩阵乘以2×3矩阵，以生成4×3矩阵。  
  
 可以将矩阵的平面和行和列中的点视为向量。 例如， (2，5) 是包含两个组件的矢量， (3、7、1) 是包含三个组件的矢量。 两个矢量的点积定义如下：  
  
  (a、b) • (c、d) = ac + bd  
  
  (a、b、c) • (d、e、f) = ad + 为 + cf  
  
 例如， (2，3) 和 (5，4) 为 (2) # B6 5) + (3) # B10 4) = 22 的点积。  (2、5、1) 和 (4，3，1)  (2) # B6 4) + (5) # B10 3) + (1) # B14 1) = 24 的点积。 请注意，两个矢量的点积是一个数字，而不是另一个矢量。 另请注意，仅当两个矢量具有相同数量的组件时，才可以计算点积。  
  
 让 (i，j) 是第 i 行和 jth 列中的 matrix A 中的条目。 例如， (3，2) 是矩阵 A 中第三行第2列的条目。 假设 A、B 和 C 是矩阵，而 AB = C。C 的项计算如下：  
  
 C (i，j) = (行 i) • (B 的 a 列 j)   
  
 下图显示了矩阵乘法的几个示例。  
  
 ![转换](./media/aboutgdip05-art06.gif "AboutGdip05_art06")  
  
 如果您将平面中的某个点视为1×2矩阵，则可以通过将该点与2×2矩阵相乘来转换该点。 下图显示了应用到点 (2，1) 的多个转换。  
  
 ![转换](./media/aboutgdip05-art07.gif "AboutGdip05_art07")  
  
 上图中显示的所有转换都是线性转换。 某些其他转换（如转换）不是线性的，并且不能表示为2×2矩阵的乘法。 假设要从点开始 (2，1) ，将其旋转90度，将其在 x 方向上转换为3个单位，并在 y 方向转换为4个单位。 可以通过使用矩阵乘法后跟矩阵加法实现此目的。  
  
 ![转换](./media/aboutgdip05-art08.gif "AboutGdip05_art08")  
  
 线性转换 (按 2 x 2 矩阵相乘) 后接 (添加1×2矩阵) 称为仿射转换。 将仿射转换存储在一对矩阵中的替代方法 (一个用于线性部分，另一个用于平移) ，用于在3×3矩阵中存储整个转换。 若要执行此操作，平面中的点必须存储在具有虚第三坐标的1×3矩阵中。 常见的方法是使所有第三个坐标等于1。 例如，点 (2，1) 由矩阵 [2 1 1] 表示。 下图显示了一个仿射转换 (旋转90度;在 x 方向上转换3个单位，在 y 方向上4个单位的) 表示为按单一3×3矩阵的乘法。  
  
 ![转换](./media/aboutgdip05-art09.gif "AboutGdip05_art09")  
  
 在前面的示例中，点 (2，1) 映射到点 (2，6) 。 请注意，3 x 3 矩阵的第三列包含数字0，0，1。 这对于仿射转换的 3 x 3 矩阵总是如此。 重要数字是第1列和第2列中的六个数字。 矩阵的左上2×2部分表示转换的线性部分，第三行中的前两个条目表示平移。  
  
 ![转换](./media/aboutgdip05-art10.gif "AboutGdip05_art10")  
  
 在 GDI + 中，可以在对象中存储仿射转换 <xref:System.Drawing.Drawing2D.Matrix> 。 由于表示仿射转换的矩阵的第三列始终 (0，0，1) ，因此，在构造对象时，只应在前两列中指定六个数字 <xref:System.Drawing.Drawing2D.Matrix> 。 语句 `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` 构造如上图所示的矩阵。  
  
## <a name="composite-transformations"></a>复合转换  
 复合转换是一系列转换，一个后跟另一个。 请考虑以下列表中的矩阵和转换：  
  
|||  
|-|-|  
|矩阵 A|旋转90度|  
|矩阵 B|在 x 方向上按系数2缩放|  
|Matrix C|在 y 方向上转换3个单位|  
  
 如果首先使用由矩阵 [2 1 1] 表示的点 (2，1) ，然后再乘以 A、B、C，则点 (2，1) 将按照列出的顺序进行三次转换。  
  
 [2 1 1]ABC = [-2 5 1]  
  
 不是将复合转换的三个部分存储在三个单独的矩阵中，而是可以将 A、B 和 C 相乘，以获取存储整个复合转换的单个3×3矩阵。 假设 ABC = D。然后，将一个点乘以 D，就会得到与点相乘的结果，然后再乘以 B，然后按 C。  
  
 [2 1 1]D = [-2 5 1]  
  
 下图显示了矩阵 A、B、C 和 D。  
  
 ![转换](./media/aboutgdip05-art12.gif "AboutGdip05_art12")  
  
 复合转换的矩阵可以通过乘以单个变换矩阵来形成，这意味着任何一系列仿射转换都可以存储在单个 <xref:System.Drawing.Drawing2D.Matrix> 对象中。  
  
> [!CAUTION]
> 复合转换的顺序很重要。 通常，旋转，然后缩放，然后平移与缩放、旋转和平移不同。 同样，矩阵相乘的顺序也非常重要。 通常，ABC 不同于背景。  
  
 <xref:System.Drawing.Drawing2D.Matrix>类提供若干用于生成复合转换的方法： <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A> 、、、、 <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A> <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A> <xref:System.Drawing.Drawing2D.Matrix.Scale%2A> <xref:System.Drawing.Drawing2D.Matrix.Shear%2A> 和 <xref:System.Drawing.Drawing2D.Matrix.Translate%2A> 。 下面的示例创建一个复合变换矩阵，该矩阵首先旋转30度，然后在 y 方向上按系数2缩放，然后在 x 方向平移5个单位：  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 下图显示了矩阵。  
  
 ![转换](./media/aboutgdip05-art13.gif "AboutGdip05_art13")  
  
## <a name="see-also"></a>另请参阅

- [坐标系和坐标转换](coordinate-systems-and-transformations.md)
- [在托管 GDI+ 中使用变换](using-transformations-in-managed-gdi.md)
