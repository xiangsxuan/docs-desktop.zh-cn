---
title: 更改 ToolTip 组件的延迟
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: 8ab0b0760e8c82d752eaada19f14cae57fa63fdc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971887"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>如何：更改 Windows 窗体 ToolTip 组件的延迟
可以为 Windows 窗体组件设置多个延迟值 <xref:System.Windows.Forms.ToolTip> 。 所有这些属性的度量单位是毫秒。 <xref:System.Windows.Forms.ToolTip.InitialDelay%2A>属性确定用户必须指向关联控件才能显示 ToolTip 字符串的时间长度。 <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A>属性设置当鼠标从工具提示关联的控件移到另一控件时，后续工具提示字符串显示的毫秒数。 <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A>属性确定显示工具提示字符串的时间长度。 您可以单独设置这些值，也可以通过设置属性的值来设置这些值 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> ; 其他延迟属性根据分配给该属性的值设置 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 。 例如，将设置为值 N 时，将设置为 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> n，并将 <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> 设置为 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 除以 5 (或 N/5) 的值，并 <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> 将设置为该属性的值为5倍的值 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> (或 5N) 。  
  
### <a name="to-set-the-delay"></a>设置延迟  
  
1. 设置以下属性，如本示例中所示。  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a>另请参阅

- [ToolTip 组件概述](tooltip-component-overview-windows-forms.md)
- [如何：在设计时为 Windows 窗体上的控件设置 ToolTip](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [ToolTip 组件](tooltip-component-windows-forms.md)
