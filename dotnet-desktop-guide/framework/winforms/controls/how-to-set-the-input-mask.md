---
title: 如何：设置输入掩码
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 06dee48765653ac7a659246cc3dfe865c795ca21
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972564"
---
# <a name="how-to-set-the-input-mask"></a>如何：设置输入掩码
掩码文本框控件是一个增强型文本框控件，支持用于接受或拒绝用户输入的声明性语法。 设置 Mask 属性可以指定允许的用户输入，而无需在应用程序中编写任何自定义验证逻辑。 有关详细信息，请参阅类的 "备注" 部分 <xref:System.Windows.Forms.MaskedTextBox> 。  
  
## <a name="setting-the-mask-property-manually"></a>手动设置 Mask 属性  
 如果你熟悉 Mask 属性支持的字符，则可以手动输入。 有关 Mask 属性支持的字符摘要，请参阅属性的 "备注" 部分 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 。  
  
### <a name="to-set-the-mask-property-manually"></a>手动设置 Mask 属性  
  
1. 在 " **设计** " 视图中，选择 <xref:System.Windows.Forms.MaskedTextBox> 。  
  
2. 在 " **属性** " 窗口中，找到 " <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 属性"。  
  
3. 键入所需的掩码。 例如，键入 `###`。  
  
## <a name="using-the-input-mask-dialog-box"></a>使用 "输入掩码" 对话框  
 "输入掩码" 对话框提供一些预定义的输入掩码。 还可以更改预定义掩码或手动输入自己的掩码。  
  
### <a name="to-open-the-input-mask-dialog-box"></a>打开 "输入掩码" 对话框  
  
1. 在 " **设计** " 视图中，选择 <xref:System.Windows.Forms.MaskedTextBox> 。  
  
    1. 单击智能标记以打开 **MaskedTextBox 任务** 面板。  
  
    2. 单击 " **设置掩码**"。  
  
     \- 或 -  
  
    1. 在 " **属性** " 窗口中，选择 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 属性。  
  
    2. 单击 "属性值" 列中的省略号按钮。  
  
     此时将显示 " **输入掩码** " 对话框。  
  
### <a name="to-use-the-input-mask-dialog-box"></a>使用 "输入掩码" 对话框  
  
1.  (可选) 单击列表中的某个预定义掩码。  
  
2.  (可选) 在 " **掩码** " 框中编辑预定义掩码。  
  
3.  (可选) 在 " **掩码** " 框中键入新的掩码。 也就是说，您不必使用其中一个预定义掩码。  
  
    > [!NOTE]
    > "预览" 框显示用户在中看到的字符 <xref:System.Windows.Forms.MaskedTextBox> 。 这些字符是帮助用户正确输入数据的指南。  
  
4. 选中或清除 " **使用 ValidatingType** " 复选框。 " **使用 ValidatingType** " 复选框指定数据类型是否用于验证用户输入的数据。 有关更多信息，请参见 <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 属性。  
  
5. 单击“确定”。  
  
     掩码在 "**属性**" 窗口的 " **mask** " 属性中输入。  
  
## <a name="see-also"></a>另请参阅

- [演练：使用 MaskedTextBox 控件](walkthrough-working-with-the-maskedtextbox-control.md)
