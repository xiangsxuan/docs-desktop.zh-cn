---
title: 更改 ColorDialog 组件的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: 0402d7f3c03a0771512a03ac54e1b093c9fe6e9b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971889"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a>如何：更改 Windows 窗体 ColorDialog 组件的外观
可以 <xref:System.Windows.Forms.ColorDialog> 使用多个属性的属性来配置 Windows 窗体组件的外观。 此对话框包含两个部分：一个显示基本颜色，另一个允许用户定义自定义颜色。  
  
 大多数属性限制用户可从对话框中选择的颜色。 如果将 <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> 属性设置为 `true` ，则允许用户定义自定义颜色。 <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> `true` 如果展开对话框以定义自定义颜色，则属性为; 否则用户必须单击 "定义自定义颜色" 按钮。 当 <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> 属性设置为时 `true` ，该对话框将显示基本颜色集中的所有可用颜色。 如果将 <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> 属性设置为 `true` ，则用户无法选择抖动颜色; 只有纯色可供选择。  
  
 如果将 <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> 属性设置为 `true` ，则会在对话框中显示 "帮助" 按钮。 当用户单击 "帮助" 按钮时，将 <xref:System.Windows.Forms.ColorDialog> 引发组件的 <xref:System.Windows.Forms.CommonDialog.HelpRequest> 事件。  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a>配置 "颜色" 对话框的外观  
  
1. 将 <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> 、 <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> 、 <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> 和属性设置 <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> 为所需的值。  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ColorDialog>
- [ColorDialog 组件](colordialog-component-windows-forms.md)
- [ColorDialog 组件概述](colordialog-component-overview-windows-forms.md)
