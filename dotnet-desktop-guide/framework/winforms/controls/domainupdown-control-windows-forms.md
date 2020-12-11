---
title: DomainUpDown 控件
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: b538350a84e341d6b2759a7db28f8799f3777a86
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971539"
---
# <a name="domainupdown-control-windows-forms"></a>DomainUpDown 控件（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.DomainUpDown> 控件看起来像是一个文本框和一对按钮的组合，用于在列表中向上或向下移动。 控件显示并设置选项列表中的文本字符串。 用户可以通过单击 "上移" 和 "下移" 按钮在列表中移动、按向上键和向下键或键入与列表中的项匹配的字符串，来选择字符串。 此控件的一种可能用途是从按字母顺序排序的名称列表中选择项。  (若要对列表进行排序，请将 <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> 属性设置为 `true` 。 ) 此控件的功能非常类似于列表框或组合框，但占用的空间非常少。  
  
 控件的键属性为 <xref:System.Windows.Forms.DomainUpDown.Items%2A> 、 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 和 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> 。 <xref:System.Windows.Forms.DomainUpDown.Items%2A>属性包含其文本值显示在控件中的对象的列表。 如果 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 设置为 `false` ，则控件会自动完成用户键入的文本，并将其与列表中的值匹配。 如果 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> 设置为，则在 `true` 最后一项之后滚动将转到列表中的第一项，反之亦然。 控件的主要方法是 <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> 和 <xref:System.Windows.Forms.DomainUpDown.DownButton%2A> 。  
  
 此控件只显示文本字符串。 如果需要显示数值的控件，请使用 <xref:System.Windows.Forms.NumericUpDown> 控件。 有关详细信息，请参阅 [NumericUpDown 控件](numericupdown-control-windows-forms.md) 。  
  
## <a name="in-this-section"></a>本节内容  
 [DomainUpDown 控件概述](domainupdown-control-overview-windows-forms.md)  
 介绍控件的一般概念 <xref:System.Windows.Forms.DomainUpDown> ，该控件允许用户浏览文本字符串列表并从中进行选择。  
  
 [如何：以编程方式向 Windows 窗体 DomainUpDown 控件添加项](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 描述如何指定 <xref:System.Windows.Forms.DomainUpDown> 控件应显示的文本字符串。  
  
 [如何：从 Windows 窗体 DomainUpDown 控件移除项](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 介绍如何 <xref:System.Windows.Forms.DomainUpDown> 在代码中删除控件中的项。  
  
## <a name="reference"></a>参考  
 <xref:System.Windows.Forms.DomainUpDown>  
 对此类进行描述，并提供指向其所有成员的链接。  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 描述此类，并提供指向其所有成员的链接。  
  
## <a name="related-sections"></a>相关章节  
 [可在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)  
 提供 Windows 窗体控件的完整列表，附带其使用情况相关信息的链接。
