---
title: RadioButton 控件概述
ms.date: 03/30/2017
f1_keywords:
- RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
ms.openlocfilehash: bbc93046b69d39caadde4986ff56f067fc206a9e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972870"
---
# <a name="radiobutton-control-overview-windows-forms"></a>RadioButton 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.RadioButton> 控件向用户提供两个或更多个互斥选项的集合。 尽管单选按钮和复选框可能看起来像是正常运行，但有一个重要的区别：当用户选择单选按钮时，不能同时选择同一组中的其他单选按钮。 与此相反，可以选择任意数量的复选框。 定义单选按钮组会告诉用户 "以下是一组选项，您可以从中选择一组，只有一个选项。"  
  
## <a name="using-the-control"></a>使用控件  
 <xref:System.Windows.Forms.RadioButton>单击控件时， <xref:System.Windows.Forms.RadioButton.Checked%2A> 将其属性设置为 `true` ，并 <xref:System.Windows.Forms.Control.Click> 调用事件处理程序。 <xref:System.Windows.Forms.RadioButton.CheckedChanged>当属性的值更改时，将引发事件 <xref:System.Windows.Forms.RadioButton.Checked%2A> 。 如果将 <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> 属性设置为 `true` (默认) ，则在选择单选按钮时，会自动清除组中的所有其他项。 通常仅 `false` 当验证代码用于确保所选单选按钮是允许的选项时，此属性才设置为。 使用属性设置控件中显示的文本 <xref:System.Windows.Forms.Control.Text%2A> ，该属性可以包含访问键快捷方式。 使用访问键，用户可以通过按 ALT 键和访问键来 "单击" 控件。 有关详细信息，请参阅 [如何：创建 Windows 窗体控件的访问键](how-to-create-access-keys-for-windows-forms-controls.md) 和 [如何：设置 Windows 窗体控件显示的文本](how-to-set-the-text-displayed-by-a-windows-forms-control.md)。  
  
 <xref:System.Windows.Forms.RadioButton>控件可以显示为命令按钮，如果选中此选项，则该按钮显示为按下（如果 <xref:System.Windows.Forms.RadioButton.Appearance%2A> 属性设置为） <xref:System.Windows.Forms.Appearance.Button> 。 单选按钮还可以使用和属性来显示图像 <xref:System.Windows.Forms.ButtonBase.Image%2A> <xref:System.Windows.Forms.ButtonBase.ImageList%2A> 。 有关详细信息，请参阅 [如何：设置 Windows 窗体控件显示的图像](how-to-set-the-image-displayed-by-a-windows-forms-control.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.RadioButton>
- [Panel 控件概述](panel-control-overview-windows-forms.md)
- [GroupBox 控件概述](groupbox-control-overview-windows-forms.md)
- [CheckBox 控件概述](checkbox-control-overview-windows-forms.md)
- [如何：创建 Windows 窗体控件的访问键](how-to-create-access-keys-for-windows-forms-controls.md)
- [如何：设置 Windows 窗体控件所显示的文本](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [如何：按功能分组 Windows 窗体 RadioButton 控件](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)
- [RadioButton 控件](radiobutton-control-windows-forms.md)
