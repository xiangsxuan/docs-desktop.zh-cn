---
title: 在 RichTextBox 控件中显示滚动条
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 2185b572ef20765043d3df3dbfd8bf5b21cfac28
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972052"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>如何：在 Windows 窗体 RichTextBox 控件中显示滚动条
默认情况下，Windows 窗体 <xref:System.Windows.Forms.RichTextBox> 控件在需要时显示水平滚动条和垂直滚动条。 控件的属性有七个可能的值 <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> <xref:System.Windows.Forms.RichTextBox> ，如下表中所述。  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>在 RichTextBox 控件中显示滚动条  
  
1. 将 <xref:System.Windows.Forms.RichTextBox.Multiline%2A> 属性设置为 `true`。 如果将属性设置为，则不会显示任何类型的滚动条（包括水平） <xref:System.Windows.Forms.RichTextBox.Multiline%2A> `false` 。  
  
2. 将 <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> 属性设置为相应的 <xref:System.Windows.Forms.RichTextBoxScrollBars> 枚举值。  
  
    |值|描述|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both>（默认值）|仅当文本超过控件的宽度或长度时，显示水平或垂直滚动条，或同时显示两者。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|永远不会显示任何类型的滚动条。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|仅当文本超过控件的宽度时，才显示水平滚动条。  (这种情况下， <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 属性必须设置为 `false` 。 ) |  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|仅当文本超过控件的高度时显示垂直滚动条。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|当属性设置为时，将显示水平滚动条 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> `false` 。 当文本不超过控件的宽度时，滚动条将灰显。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|始终显示垂直滚动条。 当文本不超过控件的长度时，滚动条将灰显。|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|始终显示垂直滚动条。 当属性设置为时，将显示水平滚动条 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> `false` 。 当文本不超过控件的宽度或长度时，滚动条显示为灰色。|  
  
3. 将 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 属性设置为适当的值。  
  
    |值|描述|  
    |-----------|-----------------|  
    |`false`|控件中的文本不会自动调整以适应控件的宽度，因此它将向右滚动，直至到达换行符。 如果选择了 "水平滚动条" 或以上两者，请使用此值。|  
    |`true`（默认值）|控件中的文本会自动调整以适应控件的宽度。 不会显示水平滚动条。 如果选择了 "垂直滚动条" 或 "无"，则使用此值来显示一个或多个段落。|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox 控件](richtextbox-control-windows-forms.md)
- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
