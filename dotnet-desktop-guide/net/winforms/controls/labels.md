---
title: Label 控件
description: 了解适用于 .NET 的 Windows 窗体中的 Label 控件。 标签用于向用户标识可视元素。
ms.date: 10/26/2020
ms.topic: overview
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.openlocfilehash: 6f669b7aef1182c35e125ff8dd3ca5ccb299b898
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941959"
---
# <a name="label-control-overview-windows-forms-net"></a>Label 控件概述（Windows 窗体 .NET）

Windows 窗体 <xref:System.Windows.Forms.Label> 控件用于显示用户无法编辑的文本。 它们用于标识窗体上的对象，并提供特定控件所代表内容或所执行操作的说明。 例如，可使用标签将描述文字添加到文本框、列表框、组合框等。 还可编写代码来更改标签显示的文本，以响应运行时的事件。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="working-with-the-label-control"></a>使用 Label 控件  

由于 <xref:System.Windows.Forms.Label> 控件不能接收焦点，因此它可用于创建其他控件的访问键。 借助访问键，用户可通过按 <kbd>Alt</kbd> 键和所选的访问键，按 Tab 键顺序聚焦下一个控件。 有关详细信息，请参阅[使用标签聚焦控件](how-to-create-access-keys.md#use-a-label-to-focus-a-control)。
  
标签中显示的描述文字包含在 <xref:System.Windows.Forms.Label.Text%2A> 属性中。 <xref:System.Windows.Forms.Label.TextAlign%2A> 属性使你能够设置标签内文本的对齐方式。 有关详细信息，请参阅[如何：设置 Windows 窗体控件显示的文本](how-to-set-the-display-text.md)。

## <a name="see-also"></a>另请参阅

- [使用标签聚焦控件（Windows 窗体 .NET）](how-to-create-access-keys.md#use-a-label-to-focus-a-control)
- [如何：设置控件显示的文本（Windows 窗体 .NET）](how-to-set-the-display-text.md)
- <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>
- <xref:System.Windows.Forms.Control.Scale%2A>
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>
