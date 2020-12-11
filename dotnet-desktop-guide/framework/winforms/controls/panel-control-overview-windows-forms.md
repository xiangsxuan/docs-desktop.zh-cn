---
title: Panel 控件概述
ms.date: 03/30/2017
f1_keywords:
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
ms.openlocfilehash: 3ea86e898e8a3e1ca90ba8e0a6240414702a1a73
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971768"
---
# <a name="panel-control-overview-windows-forms"></a>Panel 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.Panel> 控件用于为其他控件提供可识别的分组。 通常使用面板按功能细分窗体。 例如，你可能有一个订单窗体，它指定邮寄选项，例如要使用哪一整夜运输公司。 将面板中的所有选项分组后，用户可以获得逻辑视觉提示。 在设计时，可以轻松移动所有控件：移动控件时， <xref:System.Windows.Forms.Panel> 也会移动其包含的所有控件。 可以通过其属性访问面板中分组的控件 <xref:System.Windows.Forms.Control.Controls%2A> 。 此属性返回实例的集合 <xref:System.Windows.Forms.Control> ，因此您通常需要将此方法检索到的控件强制转换为其特定的类型。  
  
## <a name="panel-versus-groupbox"></a>面板与分组框  
 <xref:System.Windows.Forms.Panel>控件类似于 <xref:System.Windows.Forms.GroupBox> 控件; 但是，只有 <xref:System.Windows.Forms.Panel> 控件才能具有滚动条，而只有 <xref:System.Windows.Forms.GroupBox> 控件才能显示标题。  
  
## <a name="key-properties"></a>键属性  
 若要显示滚动条，请将 <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> 属性设置为 `true` 。 还可以通过设置 <xref:System.Windows.Forms.Control.BackColor%2A> 、和属性来自定义面板的外观 <xref:System.Windows.Forms.Control.BackgroundImage%2A> <xref:System.Windows.Forms.Panel.BorderStyle%2A> 。 有关和属性的详细 <xref:System.Windows.Forms.Control.BackColor%2A> 信息 <xref:System.Windows.Forms.Control.BackgroundImage%2A> ，请参阅 [如何：设置面板的背景](how-to-set-the-background-of-a-windows-forms-panel.md)。 <xref:System.Windows.Forms.Panel.BorderStyle%2A>属性确定面板是否轮廓 (<xref:System.Windows.Forms.BorderStyle.None>) 、纯线条 (<xref:System.Windows.Forms.BorderStyle.FixedSingle>) 或隐藏的线条 (<xref:System.Windows.Forms.BorderStyle.Fixed3D>) 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Panel>
- [GroupBox 控件](groupbox-control-windows-forms.md)
- [如何：通过使用设计器使用 Windows 窗体 Panel 控件对控件进行分组](group-controls-with-wf-panel-control-using-the-designer.md)
- [如何：使用设计器设置 Windows 窗体面板的背景](how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
