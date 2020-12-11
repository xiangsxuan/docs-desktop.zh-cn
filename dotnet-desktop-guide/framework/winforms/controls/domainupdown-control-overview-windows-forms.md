---
title: DomainUpDown 控件概述
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 86703a96d4845414d043161e0efa67bfde9278db
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971542"
---
# <a name="domainupdown-control-overview-windows-forms"></a>DomainUpDown 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.DomainUpDown> 控件本质上是一个文本框和一对按钮的组合，用于在列表中上下移动。 控件显示并设置选项列表中的文本字符串。 用户可以通过单击 "上移" 和 "下移" 按钮在列表中移动、按向上键和向下键或键入与列表中的项匹配的字符串，来选择字符串。 此控件的一种可能用途是从按字母顺序排序的名称列表中选择项。  
  
> [!NOTE]
> 若要对列表进行排序，请将 <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> 属性设置为 `true` 。  
  
 此控件的功能非常类似于列表框或组合框，但占用的空间非常少。  
  
## <a name="key-properties"></a>键属性  
 控件的键属性为 <xref:System.Windows.Forms.DomainUpDown.Items%2A> 、 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 和 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> 。 <xref:System.Windows.Forms.DomainUpDown.Items%2A>属性包含其文本值显示在控件中的对象的列表。 如果 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 设置为 `false` ，则控件会自动完成用户键入的文本，并将其与列表中的值匹配。 如果 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> 设置为，则在 `true` 最后一项之后滚动将转到列表中的第一项，反之亦然。 控件的主要方法是 <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> 和 <xref:System.Windows.Forms.DomainUpDown.DownButton%2A> 。  
  
 此控件只显示文本字符串。 如果需要显示数值的控件，请使用 <xref:System.Windows.Forms.NumericUpDown> 控件。 有关详细信息，请参阅 [NumericUpDown 控件概述](numericupdown-control-overview-windows-forms.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DomainUpDown>
- [DomainUpDown 控件](domainupdown-control-windows-forms.md)
