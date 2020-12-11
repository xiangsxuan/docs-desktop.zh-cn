---
title: 坐标系类型
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
ms.openlocfilehash: ca5cd1839661123f0df4a86df60771b6313fb01a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971590"
---
# <a name="types-of-coordinate-systems"></a>坐标系类型
GDI + 使用三个坐标空间： "世界"、"页面" 和 "设备"。 世界坐标是用于对特定图形世界进行建模的坐标，是您传递到 .NET Framework 中的方法的坐标。 页面坐标指的是绘图图面的坐标系统，如窗体或控件。 设备坐标是在其上绘制的物理设备（如屏幕或纸张）所使用的坐标。 进行调用时 `myGraphics.DrawLine(myPen, 0, 0, 160, 80)` ，传递给方法的点 <xref:System.Drawing.Graphics.DrawLine%2A> （ `(0, 0)` 和 `(160, 80)` ）在世界坐标空间中。 在 GDI + 可以在屏幕上绘制线条之前，坐标会经过一系列转换。 一种称为 "世界转换" 的转换，将世界坐标转换为页面坐标，另一个称为 "页面转换" 的转换将页面坐标转换为设备坐标。  
  
## <a name="transforms-and-coordinate-systems"></a>转换和协调系统  
 假设您想要使用的坐标系统的原点在客户端区域的主体中，而不是左上角。 例如，您希望原点为从工作区左边缘100像素，而从工作区顶部开始50像素。 下图显示了此类坐标系统。  
  
 ![坐标系统](./media/aboutgdip05-art01.gif "AboutGdip05_art01")  
  
 当你进行调用时 `myGraphics.DrawLine(myPen, 0, 0, 160, 80)` ，你将收到下图所示的行。  
  
 ![坐标系统](./media/aboutgdip05-art02.gif "AboutGdip05_art02")  
  
 三个坐标空间中线条的端点坐标如下：  
  
|||  
|-|-|  
|World| (0，0) 到 (160，80) |  
|页面| (100，50) 到 (260，130) |  
|设备| (100，50) 到 (260，130) |  
  
 请注意，页面坐标空间的原点在工作区的左上角;这种情况总是如此。 另请注意，由于度量单位是像素，因此设备坐标与页坐标相同。 如果将度量单位设置为像素 (例如，英寸) ，则设备坐标将不同于页面坐标。  
  
 将世界坐标映射到页面坐标的世界变换保存在类的属性中 <xref:System.Drawing.Graphics.Transform%2A> <xref:System.Drawing.Graphics> 。 在前面的示例中，世界变换是在 x 方向上转换100单位，在 y 方向上为50单位。 下面的示例设置对象的世界转换 <xref:System.Drawing.Graphics> ，然后使用该 <xref:System.Drawing.Graphics> 对象绘制上图中显示的线条：  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 页面转换将页面坐标映射到设备坐标。 <xref:System.Drawing.Graphics>类提供 <xref:System.Drawing.Graphics.PageUnit%2A> <xref:System.Drawing.Graphics.PageScale%2A> 用于操作页转换的和属性。 <xref:System.Drawing.Graphics>类还提供了两个只读属性， <xref:System.Drawing.Graphics.DpiX%2A> 和 <xref:System.Drawing.Graphics.DpiY%2A> 用于检查显示设备每英寸的水平和垂直点。  
  
 您可以使用 <xref:System.Drawing.Graphics.PageUnit%2A> 类的属性 <xref:System.Drawing.Graphics> 来指定除像素以外的度量单位。  
  
> [!NOTE]
> 不能将 <xref:System.Drawing.Graphics.PageUnit%2A> 属性设置为 <xref:System.Drawing.GraphicsUnit.World> ，因为这不是物理单元，将导致异常。  
  
 下面的示例将 (0，0) 绘制一条线， (2，1) ，其中，点 (2，1) 从点 (0，0) ：  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
> 如果在构造笔时未指定笔宽，则前面的示例将绘制一条宽一英寸的线条。 可以在构造函数的第二个参数中指定笔宽 <xref:System.Drawing.Pen> ：  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 如果我们假定显示设备在水平方向上每英寸96点，垂直方向每英寸96点，则上一示例中线条的端点在三个坐标空间中具有以下坐标：  
  
|||  
|-|-|  
|World| (0，0)  (2，1) |  
|页面| (0，0)  (2，1) |  
|设备| (0，0) 到 (192，96) |  
  
 请注意，因为世界坐标空间的原点位于工作区的左上角，所以页面坐标与世界坐标相同。  
  
 可以结合世界转换和页面转换来实现各种效果。 例如，假设您想要使用英寸作为度量单位，并且您希望坐标系统的原点从工作区左边缘2英寸，从工作区顶部开始1/2 英寸。 下面的示例将设置对象的世界转换和页面转换 <xref:System.Drawing.Graphics> ，然后将 (0，0) 的线条绘制 (2，1) ：  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 下图显示了线条和坐标系统。  
  
 ![坐标系统](./media/aboutgdip05-art03.gif "AboutGdip05_art03")  
  
 如果我们假定显示设备在水平方向上每英寸96点，垂直方向每英寸96点，则上一示例中线条的端点在三个坐标空间中具有以下坐标：  
  
|||  
|-|-|  
|World| (0，0)  (2，1) |  
|页面| (2，0.5) 到 (4，1.5) |  
|设备| (192，48) 到 (384，144) |  
  
## <a name="see-also"></a>另请参阅

- [坐标系和坐标转换](coordinate-systems-and-transformations.md)
- [转换的矩阵表示形式](matrix-representation-of-transformations.md)
