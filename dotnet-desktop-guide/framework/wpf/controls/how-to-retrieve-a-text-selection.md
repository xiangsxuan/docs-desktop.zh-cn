---
title: 如何：检索文本选定内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
ms.openlocfilehash: b86dc729c49d8e3953cad8c4c34d07660b2af482
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668391"
---
# <a name="how-to-retrieve-a-text-selection"></a>如何：检索文本选定内容
此示例演示了使用 <xref:System.Windows.Controls.TextBox.SelectedText%2A> 属性来检索用户在控件中选定的文本的一种方法 <xref:System.Windows.Controls.TextBox> 。  
  
## <a name="example"></a>示例  
 下面的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 示例演示 <xref:System.Windows.Controls.TextBox> 包含要选择的一些文本的控件的定义，以及一个 <xref:System.Windows.Controls.Button> 具有指定方法的控件 <xref:System.Windows.Controls.Button.OnClick%2A> 。  
  
 在此示例中，将使用带有关联 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件处理程序的按钮来检索所选文本。 当用户单击该按钮时，该 <xref:System.Windows.Controls.Button.OnClick%2A> 方法会将文本框中的任何选定文本复制到一个字符串中。  (单击按钮) 来检索文本选择的特定情况，以及使用该选择执行的操作 (将文本选择复制到字符串) ，可以轻松地对其进行修改以适应各种方案。  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a>示例  
 下面的 c # 示例显示 <xref:System.Windows.Controls.Button.OnClick%2A> 了在的中为此示例中定义的按钮的事件处理程序 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a>请参阅

- [TextBox 概述](textbox-overview.md)
- [RichTextBox 概述](richtextbox-overview.md)
