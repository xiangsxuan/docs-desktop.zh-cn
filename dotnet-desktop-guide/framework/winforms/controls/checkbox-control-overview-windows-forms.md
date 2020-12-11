---
title: CheckBox 控件概述
ms.date: 03/30/2017
f1_keywords:
- CheckBox
helpviewer_keywords:
- CheckBox control [Windows Forms], about CheckBox control
- data binding [Windows Forms], checkbox controls
- check boxes [Windows Forms], about check boxes
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
ms.openlocfilehash: b42816cf1bc0ce1ab6db0a2a436b17b0d4370d59
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970711"
---
# <a name="checkbox-control-overview-windows-forms"></a>CheckBox 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.CheckBox> 控件指示特定条件处于打开开始关闭状态。 通常用于向用户显示 Yes/No 或 True/False 选项。 可以使用组中的复选框控件来显示用户可从中选择一个或多选的多个选项。  
  
 复选框控件类似于单选按钮控件，其中每个控件用于指示用户所做的选择。 它们的区别在于，一次只能选择一个组中的一个单选按钮。 但对于复选框控件，可能会选择任意数量的复选框。  
  
 可以使用简单的数据绑定将复选框连接到数据库中的元素。 可以使用控件对多个复选框进行分组 <xref:System.Windows.Forms.GroupBox> 。 这对于视觉外观和用户界面设计都很有用，因为可以在窗体设计器上一起移动分组控件。 有关详细信息，请参阅 [Windows 窗体数据绑定](../windows-forms-data-binding.md) 和 [分组框控件](groupbox-control-windows-forms.md)。  
  
 <xref:System.Windows.Forms.CheckBox>控件具有两个重要的属性： <xref:System.Windows.Forms.CheckBox.Checked%2A> 和 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 。 <xref:System.Windows.Forms.CheckBox.Checked%2A>属性返回 `true` 或 `false` 。 <xref:System.Windows.Forms.CheckBox.CheckState%2A>属性返回 <xref:System.Windows.Forms.CheckState.Checked> 或 <xref:System.Windows.Forms.CheckState.Unchecked> ; 或者，如果 <xref:System.Windows.Forms.CheckBox.ThreeState%2A> 属性设置为 `true` ，则 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 还可能返回 <xref:System.Windows.Forms.CheckState.Indeterminate> 。 处于不确定状态时，将显示带有一个灰显外观的框，指示该选项不可用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.CheckBox>
- [如何：使用 Windows 窗体 CheckBox 控件设置选项](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [如何：响应 Windows 窗体 CheckBox 的单击](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox 控件](checkbox-control-windows-forms.md)
