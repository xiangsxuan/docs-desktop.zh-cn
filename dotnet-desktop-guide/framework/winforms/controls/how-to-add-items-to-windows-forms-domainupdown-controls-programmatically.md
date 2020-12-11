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
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a><span data-ttu-id="2cd15-102">如何：以编程方式向 Windows 窗体 DomainUpDown 控件添加项</span><span class="sxs-lookup"><span data-stu-id="2cd15-102">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>
<span data-ttu-id="2cd15-103">您可以 <xref:System.Windows.Forms.DomainUpDown> 在代码中向 Windows 窗体控件添加项。</span><span class="sxs-lookup"><span data-stu-id="2cd15-103">You can add items to the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span> <span data-ttu-id="2cd15-104">调用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 类的或 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 方法 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> ，将项添加到控件的 <xref:System.Windows.Forms.DomainUpDown.Items%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="2cd15-104">Call the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to add items to the control's <xref:System.Windows.Forms.DomainUpDown.Items%2A> property.</span></span> <span data-ttu-id="2cd15-105"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A>方法将一项添加到集合的末尾，而 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 方法在指定位置添加一个项。</span><span class="sxs-lookup"><span data-stu-id="2cd15-105">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method adds an item to the end of a collection, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method adds an item at a specified position.</span></span>  
  
### <a name="to-add-a-new-item"></a><span data-ttu-id="2cd15-106">添加新项</span><span class="sxs-lookup"><span data-stu-id="2cd15-106">To add a new item</span></span>  
  
1. <span data-ttu-id="2cd15-107">使用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 方法可将项添加到项列表的末尾。</span><span class="sxs-lookup"><span data-stu-id="2cd15-107">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method to add an item to the end of the list of items.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     <span data-ttu-id="2cd15-108">-或-</span><span class="sxs-lookup"><span data-stu-id="2cd15-108">-or-</span></span>  
  
2. <span data-ttu-id="2cd15-109">使用 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 方法将一项插入到列表中的指定位置。</span><span class="sxs-lookup"><span data-stu-id="2cd15-109">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method to insert an item into the list at a specified position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2cd15-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cd15-110">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2cd15-111">DomainUpDown 控件</span><span class="sxs-lookup"><span data-stu-id="2cd15-111">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="2cd15-112">DomainUpDown 控件概述</span><span class="sxs-lookup"><span data-stu-id="2cd15-112">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
