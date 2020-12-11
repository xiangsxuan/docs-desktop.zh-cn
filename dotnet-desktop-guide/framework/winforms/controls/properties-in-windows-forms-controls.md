---
title: 控件的属性
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
ms.openlocfilehash: 3f9873ff032497a9cda6de199ed9db5ee9522d81
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970294"
---
# <a name="properties-in-windows-forms-controls"></a>Windows 窗体控件中的属性

Windows 窗体控件从基类继承了许多属性 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。 其中包括、、、、、、、、、、、等属性 <xref:System.Windows.Forms.Control.Font%2A> <xref:System.Windows.Forms.Control.ForeColor%2A> <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Control.Bounds%2A> <xref:System.Windows.Forms.Control.ClientRectangle%2A> <xref:System.Windows.Forms.Control.DisplayRectangle%2A> <xref:System.Windows.Forms.Control.Enabled%2A> <xref:System.Windows.Forms.Control.Focused%2A> <xref:System.Windows.Forms.Control.Height%2A> <xref:System.Windows.Forms.Control.Width%2A> <xref:System.Windows.Forms.Control.Visible%2A> <xref:System.Windows.Forms.Control.AutoSize%2A> 。 有关继承的属性的详细信息，请参阅 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。  
  
 可以在控件中重写继承的属性和定义新属性。  
  
## <a name="in-this-section"></a>本节内容  

 [定义属性](defining-a-property-in-windows-forms-controls.md)  
 演示如何为自定义控件或组件实现属性，以及如何将该属性集成到设计环境中。  
  
 [使用 ShouldSerialize 和 Reset 方法定义默认值](defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 演示如何为自定义控件或组件定义默认属性值。  
  
 [属性更改事件](property-changed-events.md)  
 介绍如何在属性值发生更改时启用属性更改通知。  
  
 [如何：公开构成控件的属性](how-to-expose-properties-of-constituent-controls.md)  
 演示如何在自定义复合控件中公开构成控件的属性。  
  
 [自定义控件中的方法实现](method-implementation-in-custom-controls.md)  
 介绍如何在自定义控件和组件中实现方法。  
  
## <a name="reference"></a>参考  

 <xref:System.Windows.Forms.UserControl>  
 介绍用于实现复合控件的基类。  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 记录指定 <xref:System.ComponentModel.TypeConverter> 要用于自定义属性类型的的属性。  
  
 <xref:System.ComponentModel.EditorAttribute>  
 记录属性，该属性指定 <xref:System.Drawing.Design.UITypeEditor> 要用于自定义属性的。  
  
## <a name="related-sections"></a>相关章节  

 [Windows 窗体控件中的特性](attributes-in-windows-forms-controls.md)  
 描述你可以应用到自定义控件和组件的属性或其他成员的特性。  
  
 [Design-Time Attributes for Components（组件的设计时属性）](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))  
 将列出的元数据特性应用到组件和控件，以便在设计时正确显示在可视化设计器中。  
  
 [扩展设计时支持](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))  
 描述如何实现提供设计时支持的类，例如编辑器和设计器。
