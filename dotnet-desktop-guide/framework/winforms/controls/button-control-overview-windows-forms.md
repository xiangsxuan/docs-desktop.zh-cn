---
title: Button 控件概述
ms.date: 03/30/2017
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
ms.openlocfilehash: 4ba7b333e5414efb4814d64ce50c55e08b27f859
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971555"
---
# <a name="button-control-overview-windows-forms"></a>Button 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.Button> 控件允许用户通过单击来执行某项操作。 单击该按钮时，看上去它像是被按下并释放。 每当用户单击某个按钮时， <xref:System.Windows.Forms.Control.Click> 就会调用事件处理程序。 将代码放在 <xref:System.Windows.Forms.Control.Click> 事件处理程序中，以执行您选择的任何操作。  
  
 按钮上显示的文本包含在 <xref:System.Windows.Forms.Control.Text%2A> 属性中。 如果文本超出按钮宽度，则会换行到下一行。 但是，如果控件无法容纳其整体高度，则会将其剪切。 有关详细信息，请参阅 [如何：设置 Windows 窗体控件显示的文本](how-to-set-the-text-displayed-by-a-windows-forms-control.md)。 <xref:System.Windows.Forms.Control.Text%2A>属性可以包含访问键，这允许用户通过按 ALT 键和访问键来 "单击" 控件。 有关详细信息，请参阅 [如何：创建 Windows 窗体控件的访问键](how-to-create-access-keys-for-windows-forms-controls.md)。 文本的外观由 <xref:System.Windows.Forms.Control.Font%2A> 属性和 <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> 属性控制。  
  
 <xref:System.Windows.Forms.Button>控件还可以使用和属性来显示 <xref:System.Windows.Forms.ButtonBase.Image%2A> 图像 <xref:System.Windows.Forms.ButtonBase.ImageList%2A> 。 有关详细信息，请参阅 [如何：设置 Windows 窗体控件显示的图像](how-to-set-the-image-displayed-by-a-windows-forms-control.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Button>
- [如何：响应 Windows 窗体按钮的单击](how-to-respond-to-windows-forms-button-clicks.md)
- [选择 Windows 窗体 Button 控件的方法](ways-to-select-a-windows-forms-button-control.md)
- [如何：使用设计器将 Windows 窗体按钮指定为“接受”按钮](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [如何：使用设计器将 Windows 窗体按钮指定为“取消”按钮](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Button 控件](button-control-windows-forms.md)
