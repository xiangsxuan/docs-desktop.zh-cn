---
title: 从 DomainUpDown 控件中删除项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: e52af5c5add4fda93e2b51c8afdb90c92e8d2f62
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970540"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a>如何：从 Windows 窗体 DomainUpDown 控件移除项
可以 <xref:System.Windows.Forms.DomainUpDown> 通过调用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 类的或方法，从 Windows 窗体控件中移除项 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 。 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A>方法将删除特定的项，而 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 方法会按项的位置删除该项。  
  
### <a name="to-remove-an-item"></a>删除项  
  
- 使用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 类的方法 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 可按名称删除项。  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     -或-  
  
- 使用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 方法可通过项的位置删除项。  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [DomainUpDown 控件](domainupdown-control-windows-forms.md)
- [DomainUpDown 控件概述](domainupdown-control-overview-windows-forms.md)
