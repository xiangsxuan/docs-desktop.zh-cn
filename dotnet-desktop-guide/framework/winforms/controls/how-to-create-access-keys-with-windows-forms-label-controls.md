---
title: 使用标签控件创建访问键
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: 800afc03e71435e2721456b93bb9704af01f714a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971230"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>如何：使用 Windows 窗体 Label 控件创建访问键
Windows 窗体 <xref:System.Windows.Forms.Label> 控件可用于定义其他控件的访问键。 在 "标签" 控件中定义访问键时，用户可以按 ALT 键加上指定的字符，以按 tab 键顺序将焦点移到其后的控件上。 由于标签无法接收焦点，因此焦点会自动移到 tab 键顺序中的下一个控件。 使用此方法可以将访问键分配给文本框、组合框、列表框和数据网格。  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>为具有标签的控件分配访问键  
  
1. 首先绘制标签，然后绘制另一个控件。  
  
     -或-  
  
     按任意顺序绘制控件，并将 <xref:System.Windows.Forms.Control.TabIndex%2A> 标签的属性设置为一个小于另一个控件的。  
  
2. 将标签的 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 属性设置为 `true` 。  
  
3. 在标签的属性中使用与号 ( # A0) <xref:System.Windows.Forms.Label.Text%2A> ，为标签分配访问键。 有关详细信息，请参阅 [创建 Windows 窗体控件的访问键](how-to-create-access-keys-for-windows-forms-controls.md)。  
  
    > [!NOTE]
    > 您可能希望在 "标签" 控件中显示 "&"，而不是使用它们来创建访问密钥。 如果将 "标签" 控件绑定到数据集中包含 "与" 符号的字段，则可能会发生这种情况。 若要在 "标签" 控件中显示 "&"，请将 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 属性设置为 `false` 。 如果希望显示 "&" 和 "访问密钥"，请将 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 属性设置为 `true` ，并使用一个 " ( # A0") 指定访问键，并使用 "and" 符显示两个字符。  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a>另请参阅

- [如何：调整 Windows 窗体标签控件大小以适应其内容](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Label 控件概述](label-control-overview-windows-forms.md)
- [Label 控件](label-control-windows-forms.md)
