---
title: 如何：启用文本修整
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimming text
- trimming text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 25fff566868e792004a915fee195485c4a1f385f
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973451"
---
# <a name="how-to-enable-text-trimming"></a>如何：启用文本修整

此示例演示枚举中可用值的用法和效果 <xref:System.Windows.TextTrimming> 。

## <a name="example"></a>示例

下面的示例定义了一个 <xref:System.Windows.Controls.TextBlock> 具有 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 属性集的元素。

[!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]

<xref:System.Windows.TextTrimming>下面演示了如何在代码中设置相应的属性。

[!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
[!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]

目前有三个用于修整文本的选项： **CharacterEllipsis**、 **WordEllipsis** 和 **None**。

如果 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 设置为 **CharacterEllipsis**，则会在距离修整边缘最近的字符处修整文本，并以省略号继续。  此设置旨在修整文本以使其更适应修整边界，但可能会导致某些单词仅部分修整。  下图显示了此设置与 <xref:System.Windows.Controls.TextBlock> 上面定义的类似的效果。

![示例：TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")

如果 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 设置为 **WordEllipsis**，则在最接近修整边缘的第一个完整单词末尾，将修整文本，并以省略号继续。  此设置不会显示部分剪裁的单词，但通常不会将文本裁剪为与修整边缘密切相同的 **CharacterEllipsis** 设置。  下图显示了此设置对上述定义的影响 <xref:System.Windows.Controls.TextBlock> 。

![示例：TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")

如果 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 设置为 " **无**"，则不执行任何文本修整。  在这种情况下，只会将文本裁切到父文本容器的边界。  下图显示了此设置与 <xref:System.Windows.Controls.TextBlock> 上面定义的类似的效果。

![示例：TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")
