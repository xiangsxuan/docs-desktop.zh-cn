---
title: 如何：创建线性渐变
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: e55d27b454579268658192ae56daa52e0b28bb83
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970653"
---
# <a name="how-to-create-a-linear-gradient"></a>如何：创建线性渐变
GDI + 提供水平、垂直和对角线线性渐变。 默认情况下，线性渐变中的颜色会统一发生变化。 但是，您可以自定义线性渐变，以便以非均匀方式更改颜色。  

> [!NOTE]
> 本文中的示例是从控件的事件处理程序调用的方法 <xref:System.Windows.Forms.Control.Paint> 。  

下面的示例使用水平线性渐变画笔填充线条、椭圆和矩形。  
  
<xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A>构造函数接收四个参数：两个点和两种颜色。 第一个点 (0，10) 与第一种彩色 (红色) ，第二个点 (200，10) 与第二种颜色 (蓝色) 关联。 正如您所料，从 (0、10) 绘制到 (200，10) 将从红色逐渐变为蓝色。  
  
  (0，10) 和 (200，10) 点的数十不重要。 重要的是，这两个点具有相同的第二个坐标：连接它们的线是水平的。 当水平坐标从0到200时，椭圆和矩形还会从红色逐渐变为蓝色。  
  
 下图显示了线条、椭圆和矩形。 请注意，当水平坐标超过200时，颜色渐变会重复自身。  
  
 ![线条、椭圆和使用颜色渐变填充的矩形。](./media/how-to-create-a-linear-gradient/gradient-line-ellipse-rectangle.png)  
  
## <a name="to-use-horizontal-linear-gradients"></a>使用水平线性渐变  
  
- 分别在第三个和第四个参数中传递不透明的蓝和蓝蓝。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 在前面的示例中，当你从0的水平坐标移动到200的水平坐标时，颜色组件会线性变化。 例如，第一个坐标为介于0到200之间的点，其蓝色分量为介于0到255之间。  
  
 使用 GDI + 可以调整颜色不同于渐变边缘的方式。 假设要创建一个渐变画笔，使其根据下表从黑色更改为红色。  
  
|水平坐标|RGB 组件|  
|---------------------------|--------------------|  
|0|(0, 0, 0)|  
|40|(128, 0, 0)|  
|200|(255, 0, 0)|  
  
 请注意，当水平坐标只是从0到200的20% 时，红色部分为半度。  
  
 下面的示例将 <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> 属性设置为将三个相对强度与三个相对位置相关联。 如上表所示，0.5 的相对强度与0.2 的相对位置相关联。 代码使用渐变画笔填充椭圆和矩形。  
  
 下图显示了生成的椭圆形和矩形。  
  
 ![用水平渐变填充的椭圆和矩形。](./media/how-to-create-a-linear-gradient/gradient-ellipse-rectangle.png)  

## <a name="to-customize-linear-gradients"></a>自定义线性渐变  
  
- 将不透明的黑色和不透明红分别作为第三个和第四个参数传递。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 以上示例中的渐变是水平的;也就是说，当沿任意水平线条移动时，颜色会逐渐变化。 还可以定义垂直渐变和对角渐变。  
  
 下面的示例将 (0，0) 的点和 (200，100) 传递到 <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> 构造函数。 蓝色与 (0，0) 相关联，绿色与 (200，100) 关联。 带有笔宽度 10) 的线条 (，并使用线性渐变画笔填充椭圆。  
  
 下图显示了线条和椭圆。 请注意，当沿与通过 (0，0) 和 (200，100) 的直线传递的任何直线移动时，椭圆中的颜色会逐渐变化。  
  
 ![用对角颜色渐变填充的线条和椭圆。](./media/how-to-create-a-linear-gradient/gradient-line-ellipse.png)  
  
## <a name="to-create-diagonal-linear-gradients"></a>创建对角方向线性渐变  
  
- 分别以第三个和第四个参数的形式传入不透明蓝色和不透明绿色。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>另请参阅

- [使用渐变画笔填充形状](using-a-gradient-brush-to-fill-shapes.md)
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
