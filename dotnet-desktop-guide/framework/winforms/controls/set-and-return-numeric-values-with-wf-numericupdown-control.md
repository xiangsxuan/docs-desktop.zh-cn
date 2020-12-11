---
title: 通过 NumericUpDown 控件设置和返回数值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric values [Windows Forms], Windows Forms
- Windows Forms, numeric values
- Windows Forms controls, NumericUpDown
- NumericUpDown control [Windows Forms], setting and returning values
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
ms.openlocfilehash: a0b264fec9619b467c293bcb96278c4517775ac3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972912"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a>如何：使用 Windows 窗体 NumericUpDown 控件设置和返回数值
Windows 窗体控件的数值 <xref:System.Windows.Forms.NumericUpDown> 取决于其 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 属性。 您可以为控件的值编写条件测试，就像对任何其他属性一样。 <xref:System.Windows.Forms.NumericUpDown.Value%2A>设置属性后，可以通过编写代码对其执行操作来直接调整该属性，也可以调用 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> 和 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> 方法。  
  
### <a name="to-set-the-numeric-value"></a>设置数值  
  
1. <xref:System.Windows.Forms.NumericUpDown.Value%2A>在代码或属性窗口中为属性分配一个值。  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     -或-  
  
2. 调用 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> 或 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> 方法，按属性中指定的数量增加或减少值 <xref:System.Windows.Forms.NumericUpDown.Increment%2A> 。  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a>返回数值  
  
- <xref:System.Windows.Forms.NumericUpDown.Value%2A>在代码中访问属性。  
  
    ```vb  
    If NumericUpDown1.Value >= 65 Then  
       MessageBox.Show("Age is: " & NumericUpDown1.Value.ToString)  
    Else  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.")  
    End If  
    ```  
  
    ```csharp  
    if(numericUpDown1.Value >= 65)  
    {  
       MessageBox.Show("Age is: " + numericUpDown1.Value.ToString());  
    }  
    else  
    {  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
    ```cpp  
    if(numericUpDown1->Value >= 65)  
    {  
       MessageBox::Show(String::Concat("Age is: ",  
          numericUpDown1->Value.ToString()));  
    }  
    else  
    {  
       MessageBox::Show  
          ("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [NumericUpDown 控件](numericupdown-control-windows-forms.md)
- [NumericUpDown 控件概述](numericupdown-control-overview-windows-forms.md)
