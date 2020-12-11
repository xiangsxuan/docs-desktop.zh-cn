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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973451"
---
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="3b388-102">如何：启用文本修整</span><span class="sxs-lookup"><span data-stu-id="3b388-102">How to: Enable Text Trimming</span></span>

<span data-ttu-id="3b388-103">此示例演示枚举中可用值的用法和效果 <xref:System.Windows.TextTrimming> 。</span><span class="sxs-lookup"><span data-stu-id="3b388-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>

## <a name="example"></a><span data-ttu-id="3b388-104">示例</span><span class="sxs-lookup"><span data-stu-id="3b388-104">Example</span></span>

<span data-ttu-id="3b388-105">下面的示例定义了一个 <xref:System.Windows.Controls.TextBlock> 具有 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 属性集的元素。</span><span class="sxs-lookup"><span data-stu-id="3b388-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>

[!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]

<span data-ttu-id="3b388-106"><xref:System.Windows.TextTrimming>下面演示了如何在代码中设置相应的属性。</span><span class="sxs-lookup"><span data-stu-id="3b388-106">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>

[!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
[!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]

<span data-ttu-id="3b388-107">目前有三个用于修整文本的选项： **CharacterEllipsis**、 **WordEllipsis** 和 **None**。</span><span class="sxs-lookup"><span data-stu-id="3b388-107">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>

<span data-ttu-id="3b388-108">如果 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 设置为 **CharacterEllipsis**，则会在距离修整边缘最近的字符处修整文本，并以省略号继续。</span><span class="sxs-lookup"><span data-stu-id="3b388-108">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="3b388-109">此设置旨在修整文本以使其更适应修整边界，但可能会导致某些单词仅部分修整。</span><span class="sxs-lookup"><span data-stu-id="3b388-109">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="3b388-110">下图显示了此设置与 <xref:System.Windows.Controls.TextBlock> 上面定义的类似的效果。</span><span class="sxs-lookup"><span data-stu-id="3b388-110">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="3b388-111">![示例：TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="3b388-111">![Example: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span></span>

<span data-ttu-id="3b388-112">如果 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 设置为 **WordEllipsis**，则在最接近修整边缘的第一个完整单词末尾，将修整文本，并以省略号继续。</span><span class="sxs-lookup"><span data-stu-id="3b388-112">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="3b388-113">此设置不会显示部分剪裁的单词，但通常不会将文本裁剪为与修整边缘密切相同的 **CharacterEllipsis** 设置。</span><span class="sxs-lookup"><span data-stu-id="3b388-113">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="3b388-114">下图显示了此设置对上述定义的影响 <xref:System.Windows.Controls.TextBlock> 。</span><span class="sxs-lookup"><span data-stu-id="3b388-114">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>

<span data-ttu-id="3b388-115">![示例：TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="3b388-115">![Example: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span></span>

<span data-ttu-id="3b388-116">如果 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 设置为 " **无**"，则不执行任何文本修整。</span><span class="sxs-lookup"><span data-stu-id="3b388-116">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="3b388-117">在这种情况下，只会将文本裁切到父文本容器的边界。</span><span class="sxs-lookup"><span data-stu-id="3b388-117">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="3b388-118">下图显示了此设置与 <xref:System.Windows.Controls.TextBlock> 上面定义的类似的效果。</span><span class="sxs-lookup"><span data-stu-id="3b388-118">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="3b388-119">![示例：TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="3b388-119">![Example: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span></span>
