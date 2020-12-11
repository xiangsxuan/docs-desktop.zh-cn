---
title: 通过 ImeMode 属性显示亚洲字符
ms.date: 03/30/2017
helpviewer_keywords:
- Asian languages [Windows Forms], displaying with ImeMode
- Chinese characters [Windows Forms], displaying with ImeMode
- IME mode
- Japanese characters [Windows Forms], displaying with ImeMode
- international applications [Windows Forms], character display
- international characters
- Korean characters
- Asian languages
- Input Method Editor (IME), mode
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
ms.openlocfilehash: 25602e1a878443bd54411dfd6481581abebda5c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970345"
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a>通过 ImeMode 属性显示亚洲字符
<xref:System.Windows.Forms.Control.ImeMode%2A>窗体和控件使用属性来强制输入法编辑器的特定模式 (IME) 。 IME 是编写中文、日语和朝鲜语脚本的必备组件，因为这些编写系统具有的字符多于常规键盘可编码的字符。 例如，可能想在特定文本框中仅允许使用 ASCII 字符。 在这种情况下，您可以将 <xref:System.Windows.Forms.Control.ImeMode%2A> 属性设置为 <xref:System.Windows.Forms.ImeMode> ，并且用户将只能为该特定文本框输入 ASCII 字符。 属性的默认值 <xref:System.Windows.Forms.Control.ImeMode%2A> 为 <xref:System.Windows.Forms.ImeMode> ，因此，如果设置窗体的属性，则窗体上的所有控件都将继承该设置。 有关详细信息，请参阅 <xref:System.Windows.Forms.Control.ImeMode%2A> ) 和 <xref:System.Windows.Forms.ImeMode> 。  
  
## <a name="see-also"></a>另请参阅

- [全球化 Windows 窗体应用程序](globalizing-windows-forms.md)
