---
title: 如何：从 TextBox 获取线条集合
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: b7b2f1c2e071388635fb50b1e3573fd7f44334dd
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973315"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a>如何：从 TextBox 获取线条集合
此示例演示如何从获取文本行的集合 <xref:System.Windows.Controls.TextBox> 。  
  
## <a name="example"></a>示例  
 下面的示例演示了一个简单的方法，该方法采用 <xref:System.Windows.Controls.TextBox> 作为参数，并返回 <xref:System.Collections.Specialized.StringCollection> 包含 **文本框** 中的文本行的。  <xref:System.Windows.Controls.TextBox.LineCount%2A>属性用于确定 **文本框** 中当前有多少行， <xref:System.Windows.Controls.TextBox.GetLineText%2A> 然后使用方法提取每行并将其添加到行集合中。  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a>另请参阅

- [TextBox 概述](textbox-overview.md)
- [RichTextBox 概述](richtextbox-overview.md)
