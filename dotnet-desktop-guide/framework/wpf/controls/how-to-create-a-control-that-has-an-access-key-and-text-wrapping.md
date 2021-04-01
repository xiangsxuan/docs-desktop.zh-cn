---
title: 如何：创建具有访问键和文本换行的控件
ms.date: 03/30/2017
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
ms.openlocfilehash: 86239374ca9cb3bd3d71415496e32d4a27fbae5a
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973980"
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a>如何：创建具有访问键和文本换行的控件

此示例演示如何创建具有访问键且支持文本换行的控件。 该示例使用 <xref:System.Windows.Controls.Label> 控件来说明这些概念。  
  
## <a name="example"></a>示例  

 **将文本换行添加到标签**  
  
 <xref:System.Windows.Controls.Label>控件不支持文本换行。 如果需要一个多次换行的标签，可以嵌套其他支持文本换行的元素，并将该元素放在标签内。 下面的示例演示如何使用 <xref:System.Windows.Controls.TextBlock> 来创建一个环绕多行文本的标签。  
  
 [!code-xaml[LabelSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 **将访问键和文本换行添加到标签**  
  
 如果需要 <xref:System.Windows.Controls.Label> 具有访问密钥)  (助记键的，请使用中的 <xref:System.Windows.Controls.AccessText> 元素 <xref:System.Windows.Controls.Label> 。  
  
 控件（如、、、、、、 <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.Button> 和） <xref:System.Windows.Controls.RadioButton> <xref:System.Windows.Controls.CheckBox> <xref:System.Windows.Controls.MenuItem> <xref:System.Windows.Controls.TabItem> <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.GroupBox> 具有默认控件模板。 这些模板包含一个 <xref:System.Windows.Controls.ContentPresenter> 。 可对其设置的属性之一 <xref:System.Windows.Controls.ContentPresenter> 是 <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A> = "true"，可用于指定控件的访问键。  
  
 下面的示例演示如何创建一个 <xref:System.Windows.Controls.Label> 具有访问键且支持文本换行的。 若要启用文本换行，示例设置了 <xref:System.Windows.Controls.AccessText.TextWrapping%2A> 属性，并使用下划线字符来指定访问密钥。 （紧跟下划线字符后面的字符就是访问键。）  
  
 [!code-xaml[LabelSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a>请参阅

- [如何：设置 Label 的目标属性](/previous-versions/dotnet/netframework-3.5/ms752101(v=vs.90))
