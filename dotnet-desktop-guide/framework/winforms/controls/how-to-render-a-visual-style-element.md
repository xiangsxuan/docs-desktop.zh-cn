---
title: 如何：呈现视觉样式元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- visual themes [Windows Forms], applying to elements of Windows Forms applications
- professional appearance [Windows Forms], applying to elements of Windows Forms applications
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
ms.openlocfilehash: a2b9524b6a3e3c77d3c68c4d9e138b8c0e2a9373
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971138"
---
# <a name="how-to-render-a-visual-style-element"></a>如何：呈现视觉样式元素
<xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType>命名空间公开 <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> 表示 Windows 用户界面 (UI) 视觉样式支持的元素的对象。 本主题演示如何使用 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> 类呈现表示 "开始" <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> 菜单 **中的** "注销" 和 " **关闭** " 按钮的。  
  
### <a name="to-render-a-visual-style-element"></a>呈现视觉样式元素  
  
1. 创建 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> 并将其设置为要绘制的元素。 请注意 <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> 属性和方法的用法 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> ; <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> 如果禁用了视觉样式或未定义元素，则构造函数将引发异常。  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2. 调用 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> 方法以呈现 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> 当前表示的元素。  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 派生自类的自定义控件 <xref:System.Windows.Forms.Control> 。  
  
- <xref:System.Windows.Forms.Form>承载自定义控件的。  
  
- 对 <xref:System?displayProperty=nameWithType> 、 <xref:System.Drawing?displayProperty=nameWithType> 、 <xref:System.Windows.Forms?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> 命名空间的引用。  
  
## <a name="see-also"></a>另请参阅

- [使用视觉样式呈现控件](rendering-controls-with-visual-styles.md)
