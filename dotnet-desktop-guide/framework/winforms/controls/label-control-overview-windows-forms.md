---
title: Label 控件概述
ms.date: 03/30/2017
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
ms.openlocfilehash: 1ca14553c7cb51d2b7a329950aeaec4c0439762a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972628"
---
# <a name="label-control-overview-windows-forms"></a>Label 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.Label> 控件用于显示用户无法编辑的文本或图像。 它们用于标识窗体上的对象-例如，提供特定控件在被单击时所要执行的操作的说明，或者显示为响应应用程序中的运行时事件或进程而显示的信息。 例如，您可以使用标签将描述性标题添加到文本框、列表框、组合框等。 还可以编写代码来更改标签显示的文本，以响应运行时的事件。 例如，如果应用程序需要几分钟时间来处理更改，则可以在标签中显示处理状态消息。  
  
## <a name="working-with-the-label-control"></a>使用标签控件  
 由于 <xref:System.Windows.Forms.Label> 控件不能接收焦点，因此也可以使用它来创建其他控件的访问键。 访问键允许用户通过按 ALT 键和访问键来选择另一个控件。 有关详细信息，请参阅 [创建 Windows 窗体控件的访问键](how-to-create-access-keys-for-windows-forms-controls.md) 和 [如何：创建具有 Windows 窗体标签控件的访问键](how-to-create-access-keys-with-windows-forms-label-controls.md)。  
  
 标签中显示的标题包含在 <xref:System.Windows.Forms.Label.Text%2A> 属性中。 <xref:System.Windows.Forms.Label.TextAlign%2A>属性允许您设置标签中文本的对齐方式。 有关详细信息，请参阅 [如何：设置 Windows 窗体控件显示的文本](how-to-set-the-text-displayed-by-a-windows-forms-control.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Label>
- [如何：调整 Windows 窗体标签控件大小以适应其内容](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [如何：使用 Windows 窗体 Label 控件创建访问键](how-to-create-access-keys-with-windows-forms-label-controls.md)
