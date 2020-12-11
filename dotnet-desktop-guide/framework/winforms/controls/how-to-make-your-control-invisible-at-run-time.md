---
title: 如何：使控件在运行时不可见
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
ms.openlocfilehash: e9af529541a40a951d6defea180dbbef04c8f3be
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970563"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a>如何：使控件在运行时不可见
有时，可能需要创建一个在运行时不可见的用户控件。 例如，警报时钟的控件可能不可见，除非警报发出警报。 这可以通过设置属性轻松完成 <xref:System.Windows.Forms.Control.Visible%2A> 。 如果 <xref:System.Windows.Forms.Control.Visible%2A> 属性为 `true` ，则控件将显示为 "正常"。 如果 `false` 为，则控件将隐藏。 尽管控件中的代码在不可见时仍可能运行，但你将无法通过用户界面与控件进行交互。 若要创建仍响应用户输入的不可见控件 (例如，鼠标单击) ，应创建透明控件。 有关详细信息，请参阅为 [控件提供透明背景](how-to-give-your-control-a-transparent-background.md)。  
  
### <a name="to-make-your-control-invisible-at-run-time"></a>使控件在运行时不可见  
  
1. 将 <xref:System.Windows.Forms.Control.Visible%2A> 属性设置为 `false`。  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Control.Visible%2A>
- [使用 .NET Framework 开发自定义 Windows 窗体控件](developing-custom-windows-forms-controls.md)
- [如何：使控件拥有透明背景](how-to-give-your-control-a-transparent-background.md)
