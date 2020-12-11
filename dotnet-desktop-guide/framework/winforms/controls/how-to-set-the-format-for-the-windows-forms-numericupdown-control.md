---
title: 设置 NumericUpDown 控件的格式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 5ef1c801e96bef7b92e7e69dc36491144c456eeb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972565"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="52af1-102">如何：设置 Windows 窗体 NumericUpDown 控件的格式</span><span class="sxs-lookup"><span data-stu-id="52af1-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="52af1-103">你可以配置值在 Windows 窗体控件中的显示方式 <xref:System.Windows.Forms.NumericUpDown> 。</span><span class="sxs-lookup"><span data-stu-id="52af1-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="52af1-104"><xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A>属性确定小数点后显示的数字个数; 默认值为0。</span><span class="sxs-lookup"><span data-stu-id="52af1-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="52af1-105"><xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A>属性确定是否在每三位十进制数之间插入分隔符; 默认值为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="52af1-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="52af1-106">如果将属性设置为，则控件可以显示十六进制形式的值，而不是十进制格式 <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> `true` ; 默认值为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="52af1-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="52af1-107">设置数值的格式</span><span class="sxs-lookup"><span data-stu-id="52af1-107">To format the numeric value</span></span>  
  
- <span data-ttu-id="52af1-108">通过将 <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> 属性设置为整数并将 <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> 属性设置为或，来显示小 `true` 数值 `false` 。</span><span class="sxs-lookup"><span data-stu-id="52af1-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
    ```vb  
    NumericUpDown1.DecimalPlaces = 2  
    NumericUpDown1.ThousandsSeparator = True  
    ```  
  
    ```csharp  
    numericUpDown1.DecimalPlaces = 2;  
    numericUpDown1.ThousandsSeparator = true;  
    ```  
  
    ```cpp  
    numericUpDown1->DecimalPlaces = 2;  
    numericUpDown1->ThousandsSeparator = true;  
    ```  
  
     <span data-ttu-id="52af1-109">-或-</span><span class="sxs-lookup"><span data-stu-id="52af1-109">-or-</span></span>  
  
- <span data-ttu-id="52af1-110">通过将 <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> 属性设置为，显示十六进制值 `true` 。</span><span class="sxs-lookup"><span data-stu-id="52af1-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
    ```vb  
    NumericUpDown1.Hexadecimal = True  
    ```  
  
    ```csharp  
    numericUpDown1.Hexadecimal = true;  
    ```  
  
    ```cpp  
    numericUpDown1->Hexadecimal = true;  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="52af1-111">即使值以十六进制形式显示在窗体上，对属性执行的任何测试也 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 将测试其小数值。</span><span class="sxs-lookup"><span data-stu-id="52af1-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52af1-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52af1-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="52af1-113">NumericUpDown 控件</span><span class="sxs-lookup"><span data-stu-id="52af1-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="52af1-114">NumericUpDown 控件概述</span><span class="sxs-lookup"><span data-stu-id="52af1-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
