---
title: 选择按钮控件的方式
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 145166d182f1ec51068ab3e0c23c12b471b69231
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972490"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>选择 Windows 窗体 Button 控件的方法
可以通过以下方式选择 Windows 窗体按钮：  
  
- 使用鼠标单击该按钮。  
  
- 在代码中调用该按钮的 <xref:System.Windows.Forms.Control.Click> 事件。  
  
- 按 TAB 键将焦点移到按钮上，然后按空格键或 ENTER 键以选择该按钮。  
  
- 按下访问键 (ALT + 按钮的带下划线的字母) 。 有关访问密钥的详细信息，请参阅 [如何：创建 Windows 窗体控件的访问键](how-to-create-access-keys-for-windows-forms-controls.md)。  
  
- 如果该按钮是窗体的 "接受" 按钮，则按 ENTER 可选择该按钮，即使其他控件具有焦点也是如此，除非其他控件是另一个按钮、多行文本框或捕获 ENTER 键的自定义控件。  
  
- 如果该按钮是窗体的 "取消" 按钮，则按 ESC 键会选择该按钮，即使另一个控件具有焦点也是如此。  
  
- 调用 <xref:System.Windows.Forms.Button.PerformClick%2A> 方法以编程方式选择按钮。  
  
## <a name="see-also"></a>另请参阅

- [Button 控件概述](button-control-overview-windows-forms.md)
- [如何：响应 Windows 窗体按钮的单击](how-to-respond-to-windows-forms-button-clicks.md)
- [Button 控件](button-control-windows-forms.md)
