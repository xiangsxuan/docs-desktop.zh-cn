---
title: 以编程方式向 DomainUpDown 控件添加项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 2e9f51fa051bf9b62e95f289db97bffd83450036
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971786"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>如何：以编程方式向 Windows 窗体 DomainUpDown 控件添加项
您可以 <xref:System.Windows.Forms.DomainUpDown> 在代码中向 Windows 窗体控件添加项。 调用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 类的或 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 方法 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> ，将项添加到控件的 <xref:System.Windows.Forms.DomainUpDown.Items%2A> 属性。 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>方法将一项添加到集合的末尾，而 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 方法在指定位置添加一个项。  
  
### <a name="to-add-a-new-item"></a>添加新项  
  
1. 使用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 方法可将项添加到项列表的末尾。  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     -或-  
  
2. 使用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 方法将一项插入到列表中的指定位置。  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [DomainUpDown 控件](domainupdown-control-windows-forms.md)
- [DomainUpDown 控件概述](domainupdown-control-overview-windows-forms.md)
