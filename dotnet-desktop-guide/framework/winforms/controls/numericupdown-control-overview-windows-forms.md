---
title: NumericUpDown 控件概述
ms.date: 03/30/2017
f1_keywords:
- NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
ms.openlocfilehash: 3e24fa543df9028e9866d91ec60c3cf88578ac56
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972603"
---
# <a name="numericupdown-control-overview-windows-forms"></a>NumericUpDown 控件概述（Windows 窗体）
<xref:System.Windows.Forms.NumericUpDown>控件看起来就像是一个文本框和一对箭头，用户可以单击该组合来调整值。 控件显示并设置固定数值值选择列表中的单个数值。 用户可以通过单击向上键和向下箭头、按向上键和向下键，或在控件的文本框部分中键入一个数字来增加和减少数字。 单击向上箭头键可将数字移动到最大值;单击向下箭头键会将数字向下移动到最小值。  
  
 由于其功能多样，此控制是一种很好的选择，例如，如果想要为音乐播放器应用程序创建音量控制。 <xref:System.Windows.Forms.NumericUpDown>在许多 Windows 控制面板应用程序中都使用该控件。  
  
## <a name="key-properties-and-methods"></a>键属性和方法  
 控件的文本框中显示的数字可以是多种格式，包括十六进制。 有关详细信息，请参阅 [如何：设置 Windows 窗体 NumericUpDown 控件的格式](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)。 控件的键属性为 <xref:System.Windows.Forms.NumericUpDown.Value%2A> ， <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (默认值 100) <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (默认值 0) ， <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (默认值 1) 。 <xref:System.Windows.Forms.NumericUpDown.Value%2A>属性设置在控件中选定的当前数目。 <xref:System.Windows.Forms.NumericUpDown.Increment%2A>当用户单击向上或向下箭头时，属性将设置调整数字的量。 当焦点离开控件时，将根据最小和最大数值验证任何类型化输入。 当用户使用属性连续按向上或向下箭头时，可以提高控件在数字间移动的速度 <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> 。 控件的主要方法是 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> 和 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown 控件](numericupdown-control-windows-forms.md)
- [如何：设置 Windows 窗体 NumericUpDown 控件的格式](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)
- [TextBox 控件](textbox-control-windows-forms.md)
