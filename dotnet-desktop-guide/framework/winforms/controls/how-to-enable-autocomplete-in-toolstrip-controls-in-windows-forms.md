---
title: 如何：在 ToolStrip 控件中启用自动完成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoComplete [Windows Forms], examples
- toolbars [Windows Forms], AutoComplete
- examples [Windows Forms], toolbars
- AutoComplete [Windows Forms], enabling in toolbars
- ToolStripComboBox class [Windows Forms], examples
- ToolStrip control [Windows Forms], AutoComplete
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
ms.openlocfilehash: 18b17aaea9d2354c03bb43f3fdd8d3779697cf58
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971181"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a><span data-ttu-id="0433a-102">如何：在 Windows 窗体的 ToolStrip 控件中启用自动完成</span><span class="sxs-lookup"><span data-stu-id="0433a-102">How to: Enable AutoComplete in ToolStrip Controls in Windows Forms</span></span>
<span data-ttu-id="0433a-103">以下过程将和结合 <xref:System.Windows.Forms.ToolStripLabel> 使用 <xref:System.Windows.Forms.ToolStripComboBox> ，以便显示项目列表，如最近访问的网站。</span><span class="sxs-lookup"><span data-stu-id="0433a-103">The following procedure combines a <xref:System.Windows.Forms.ToolStripLabel> with a <xref:System.Windows.Forms.ToolStripComboBox> that can be dropped down to show a list of items, such as recently visited Web sites.</span></span> <span data-ttu-id="0433a-104">如果用户键入的字符与列表中某个项的第一个字符相匹配，则会立即显示该项。</span><span class="sxs-lookup"><span data-stu-id="0433a-104">If the user types a character that matches the first character of one of the items in the list, the item is immediately displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0433a-105">自动完成功能 `ToolStrip` 的工作方式与使用传统控件（如和）的方法相同 <xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="0433a-105">Automatic completion works with `ToolStrip` controls in the same way that it works with traditional controls such as <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a><span data-ttu-id="0433a-106">在 ToolStrip 控件中启用自动完成</span><span class="sxs-lookup"><span data-stu-id="0433a-106">To enable AutoComplete in a ToolStrip control</span></span>  
  
1. <span data-ttu-id="0433a-107">创建一个 <xref:System.Windows.Forms.ToolStrip> 控件并向其中添加项。</span><span class="sxs-lookup"><span data-stu-id="0433a-107">Create a <xref:System.Windows.Forms.ToolStrip> control and add items to it.</span></span>  
  
    ```vb  
    ToolStrip1 = New System.Windows.Forms.ToolStrip  
    ToolStrip1.Items.AddRange(New System.Windows.Forms.ToolStripItem()_  
        {ToolStripLabel1, ToolStripComboBox1})  
    ```  
  
    ```csharp  
    toolStrip1 = new System.Windows.Forms.ToolStrip();  
    toolStrip1.Items.AddRange(new System.Windows.Forms.ToolStripItem[]
        {toolStripLabel1, toolStripComboBox1});  
    ```  
  
2. <span data-ttu-id="0433a-108">将 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 标签的属性和组合框设置为，以 <xref:System.Windows.Forms.ToolStripItemOverflow.Never> 使列表始终可用，而不考虑窗体的大小。</span><span class="sxs-lookup"><span data-stu-id="0433a-108">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the label and the combo box to <xref:System.Windows.Forms.ToolStripItemOverflow.Never> so that the list is always available regardless of the form's size.</span></span>  
  
    ```vb  
    ToolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ToolStripComboBox1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    toolStripComboBox1.Overflow = System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
3. <span data-ttu-id="0433a-109">向控件的 Items 集合添加单词 <xref:System.Windows.Forms.ToolStripComboBox> 。</span><span class="sxs-lookup"><span data-stu-id="0433a-109">Add words to the Items collection of the <xref:System.Windows.Forms.ToolStripComboBox> control.</span></span>  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. <span data-ttu-id="0433a-110">将 <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> 组合框的属性设置为 <xref:System.Windows.Forms.AutoCompleteMode.Append> 。</span><span class="sxs-lookup"><span data-stu-id="0433a-110">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteMode.Append>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. <span data-ttu-id="0433a-111">将 <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> 组合框的属性设置为 <xref:System.Windows.Forms.AutoCompleteSource.ListItems> 。</span><span class="sxs-lookup"><span data-stu-id="0433a-111">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteSource.ListItems>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0433a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0433a-112">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [<span data-ttu-id="0433a-113">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="0433a-113">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="0433a-114">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="0433a-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="0433a-115">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="0433a-115">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
