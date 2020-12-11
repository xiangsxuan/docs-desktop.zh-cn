---
title: 使用设计器将一个按钮指定为 "接受" 按钮
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 27a5de51f8c5b2c84cc205e09ac1a2179c315752
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970092"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a>如何：使用设计器将 Windows 窗体按钮指定为“接受”按钮
在任何 Windows 窗体上，都可以 <xref:System.Windows.Forms.Button> 将控件指定为 "接受" 按钮，也称为 "默认" 按钮。 用户按 ENTER 键时，将单击默认按钮，而不考虑窗体上的其他哪个控件具有焦点。 这种情况的例外是，具有焦点的控件是另一个按钮，在这种情况下，将单击带有焦点的按钮（或多行文本框）或捕获 ENTER 键的自定义控件。

## <a name="to-designate-the-accept-button"></a>指定 "接受" 按钮

1. 选择该按钮所在的窗体。

2. 在 " **属性** " 窗口中，将窗体的 <xref:System.Windows.Forms.Form.AcceptButton%2A> 属性设置为 <xref:System.Windows.Forms.Button> 控件的名称。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Button 控件概述](button-control-overview-windows-forms.md)
- [选择 Windows 窗体 Button 控件的方法](ways-to-select-a-windows-forms-button-control.md)
- [如何：响应 Windows 窗体按钮的单击](how-to-respond-to-windows-forms-button-clicks.md)
- [如何：使用设计器将 Windows 窗体按钮指定为“取消”按钮](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Button 控件](button-control-windows-forms.md)
