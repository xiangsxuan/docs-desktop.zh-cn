---
title: 如何：将 TextBox 控件设为只读
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 45fda33b5840bd89dac8d9e99f7dd1a8dd065838
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973090"
---
# <a name="how-to-make-a-textbox-control-read-only"></a>如何：将 TextBox 控件设为只读
此示例演示如何将控件配置 <xref:System.Windows.Controls.TextBox> 为不允许用户输入或修改。  
  
## <a name="example"></a>示例  
 若要防止用户修改控件的内容 <xref:System.Windows.Controls.TextBox> ，请将属性设置 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 为 **true**。  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A>特性仅影响用户输入; 不影响控件说明中设置的文本 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Controls.TextBox> 或通过属性以编程方式设置的文本 <xref:System.Windows.Controls.TextBox.Text%2A> 。  
  
 的默认值 <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> 为 **false**。  
  
## <a name="see-also"></a>请参阅

- [TextBox 概述](textbox-overview.md)
- [RichTextBox 概述](richtextbox-overview.md)
