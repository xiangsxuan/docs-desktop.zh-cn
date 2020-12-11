---
title: ToolTip 组件概述
ms.date: 03/30/2017
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
ms.openlocfilehash: 731f7ad0ce6670000d8c3d3e901e1506f7ef470a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973049"
---
# <a name="tooltip-component-overview-windows-forms"></a>ToolTip 组件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.ToolTip> 组件在用户指向控件时显示文本。 ToolTip 可与任何控件关联。 此组件的示例用法：若要在窗体上节省空间，可以在按钮上显示小图标，并使用工具提示来解释该按钮的功能。  
  
## <a name="working-with-the-tooltip-component"></a>使用 ToolTip 组件  
 <xref:System.Windows.Forms.ToolTip>组件 `ToolTip` 为 Windows 窗体或其他容器上的多个控件提供了一个属性。 例如，如果将一个组件放 <xref:System.Windows.Forms.ToolTip> 在窗体上，则可以在控件上显示 "在此处键入你的名称" <xref:System.Windows.Forms.TextBox> 和 "单击此处保存更改" <xref:System.Windows.Forms.Button> 。  
  
 组件的关键方法 <xref:System.Windows.Forms.ToolTip> 是 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 和 <xref:System.Windows.Forms.ToolTip.GetToolTip%2A> 。 您可以使用 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 方法来设置为控件显示的工具提示。 有关详细信息，请参阅 [如何：在设计时在 Windows 窗体上设置控件的工具提示](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)。 键属性为 <xref:System.Windows.Forms.ToolTip.Active%2A> ，它必须设置为以 `true` 显示工具提示，并 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 设置显示工具提示字符串的时间长度、用户必须指向控件以显示工具提示的时间，以及显示后续工具提示窗口所需的时间。 有关详细信息，请参阅 [如何：更改 Windows 窗体 ToolTip 组件的延迟](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolTip>
- [如何：在设计时为 Windows 窗体上的控件设置 ToolTip](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [如何：更改 Windows 窗体 ToolTip 组件的延迟](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
