---
title: 使用嵌套的 Graphics 容器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], nested containers
- graphics [Windows Forms], clipping
- graphics [Windows Forms], transformations in nested objects
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
ms.openlocfilehash: 460ebb37ee62691a1e282f756840121fd378ebd8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971373"
---
# <a name="using-nested-graphics-containers"></a>使用嵌套的 Graphics 容器
GDI + 提供可用于在对象中暂时替换或增加部分状态的容器 <xref:System.Drawing.Graphics> 。 可以通过调用对象的方法来创建容器 <xref:System.Drawing.Graphics.BeginContainer%2A> <xref:System.Drawing.Graphics> 。 可以重复调用 <xref:System.Drawing.Graphics.BeginContainer%2A> 来形成嵌套容器。 对的每个调用都 <xref:System.Drawing.Graphics.BeginContainer%2A> 必须与对的调用配对 <xref:System.Drawing.Graphics.EndContainer%2A> 。  
  
## <a name="transformations-in-nested-containers"></a>嵌套容器中的转换  
 下面的示例在 <xref:System.Drawing.Graphics> 该对象中创建一个对象和一个容器 <xref:System.Drawing.Graphics> 。 对象的世界变换 <xref:System.Drawing.Graphics> 是在 x 方向上平移100单位，在 y 方向上为80单位。 容器的世界变换是30度的旋转。 此代码将调用 `DrawRectangle(pen, -60, -30, 120, 60)` 两次。 对的第一次调用在 <xref:System.Drawing.Graphics.DrawRectangle%2A> 容器中，即，调用在对和的调用之间 <xref:System.Drawing.Graphics.BeginContainer%2A> <xref:System.Drawing.Graphics.EndContainer%2A> 。 对的第二次调用在 <xref:System.Drawing.Graphics.DrawRectangle%2A> 调用之后 <xref:System.Drawing.Graphics.EndContainer%2A> 。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 在前面的代码中，从容器内绘制的矩形将首先由容器的世界变换转换 (旋转) 然后由对象的世界转换 <xref:System.Drawing.Graphics> (转换) 。 从容器外绘制的矩形仅由对象的世界变换转换 <xref:System.Drawing.Graphics> (平移) 。 下图显示了两个矩形：
  
 ![显示嵌套容器的插图。](./media/using-nested-graphics-containers/nested-containers-illustration.png)  
  
## <a name="clipping-in-nested-containers"></a>嵌套容器中的剪辑  
 下面的示例演示嵌套容器如何处理剪辑区域。 此代码在 <xref:System.Drawing.Graphics> 该对象中创建一个对象和一个容器 <xref:System.Drawing.Graphics> 。 对象的剪辑区域 <xref:System.Drawing.Graphics> 是一个矩形，容器的剪辑区域是一个椭圆。 此代码对方法进行两次调用 <xref:System.Drawing.Graphics.DrawLine%2A> 。 对的第一次调用在 <xref:System.Drawing.Graphics.DrawLine%2A> 容器中，第二次调用在 <xref:System.Drawing.Graphics.DrawLine%2A> 调用) 之后 (容器外部 <xref:System.Drawing.Graphics.EndContainer%2A> 。 第一行由两个剪辑区域的交集裁剪。 第二行仅被对象的矩形剪辑区域剪裁 <xref:System.Drawing.Graphics> 。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 下图显示了这两个剪裁行：
  
 ![显示具有剪裁线条的嵌套容器的插图。](./media/using-nested-graphics-containers/nested-container-clipped-lines.png)  
  
 如前面的两个示例所示，转换和剪辑区域在嵌套容器中具有累积性。 如果设置容器和对象的世界变换 <xref:System.Drawing.Graphics> ，则这两种转换都将应用于从容器内绘制的项。 将首先应用容器的转换，并将 <xref:System.Drawing.Graphics> 应用对象的转换。 如果设置容器和对象的剪辑区域 <xref:System.Drawing.Graphics> ，则两个剪辑区域的交集将剪裁从容器内绘制的项。  
  
## <a name="quality-settings-in-nested-containers"></a>嵌套容器中的质量设置  
 <xref:System.Drawing.Graphics.SmoothingMode%2A> <xref:System.Drawing.Graphics.TextRenderingHint%2A> 在嵌套容器中 (、和 like) 的质量设置不是累积性的; 相反，容器的质量设置会暂时替换对象的质量设置 <xref:System.Drawing.Graphics> 。 创建新容器时，该容器的质量设置将设置为 "默认值"。 例如，假设您有一个 <xref:System.Drawing.Graphics> 具有平滑模式的对象 <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> 。 创建容器时，容器中的平滑模式为默认平滑模式。 您可以随意设置容器的平滑模式，并且将根据您设置的模式绘制从容器内提取的任何项。 调用之后绘制的项 <xref:System.Drawing.Graphics.EndContainer%2A> 将根据 (<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>) 在调用之前已存在的平滑模式进行绘制 <xref:System.Drawing.Graphics.BeginContainer%2A> 。  
  
## <a name="several-layers-of-nested-containers"></a>嵌套容器的多个层  
 不限于对象中的一个容器 <xref:System.Drawing.Graphics> 。 你可以创建一系列容器，每个容器都嵌套在前面，你可以指定每个嵌套容器的世界转换、剪辑区域和质量设置。 如果从最内层的容器内部调用一个绘图方法，则将按顺序应用转换，从最内层的容器开始，到最外层的容器结束。 从最内部的容器内部绘制的项将被所有剪辑区域的交集剪裁掉。  
  
 下面的示例创建一个 <xref:System.Drawing.Graphics> 对象，并将其文本呈现提示设置为 <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> 。 此代码创建两个容器，一个嵌套在另一个中。 外部容器的文本呈现提示设置为 <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel> ，并且内部容器的文本呈现提示设置为 <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> 。 该代码绘制三个字符串：一个来自内部容器，一个来自外部容器，另一个来自 <xref:System.Drawing.Graphics> 对象本身。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 下图显示了这三个字符串。 从内部容器和对象绘制的字符串 <xref:System.Drawing.Graphics> 会通过抗锯齿进行平滑处理。 由于 <xref:System.Drawing.Graphics.TextRenderingHint%2A> 属性设置为，因此，从外部容器绘制的字符串不会通过抗锯齿进行平滑处理 <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel> 。  
  
 ![显示从嵌套容器绘制的字符串的插图。](./media/using-nested-graphics-containers/nested-containers-three-strings.png)  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Graphics>
- [管理 Graphics 对象的状态](managing-the-state-of-a-graphics-object.md)
