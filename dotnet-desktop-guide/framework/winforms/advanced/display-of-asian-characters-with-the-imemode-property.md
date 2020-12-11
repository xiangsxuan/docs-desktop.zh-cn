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
# <a name="display-of-asian-characters-with-the-imemode-property"></a><span data-ttu-id="99099-102">通过 ImeMode 属性显示亚洲字符</span><span class="sxs-lookup"><span data-stu-id="99099-102">Display of Asian Characters with the ImeMode Property</span></span>
<span data-ttu-id="99099-103"><xref:System.Windows.Forms.Control.ImeMode%2A>窗体和控件使用属性来强制输入法编辑器的特定模式 (IME) 。</span><span class="sxs-lookup"><span data-stu-id="99099-103">The <xref:System.Windows.Forms.Control.ImeMode%2A> property is used by forms and controls to force a specific mode for an input method editor (IME).</span></span> <span data-ttu-id="99099-104">IME 是编写中文、日语和朝鲜语脚本的必备组件，因为这些编写系统具有的字符多于常规键盘可编码的字符。</span><span class="sxs-lookup"><span data-stu-id="99099-104">The IME is an essential component for writing Chinese, Japanese, and Korean scripts, since these writing systems have more characters than can be encoded for a regular keyboard.</span></span> <span data-ttu-id="99099-105">例如，可能想在特定文本框中仅允许使用 ASCII 字符。</span><span class="sxs-lookup"><span data-stu-id="99099-105">For example, you may want to allow only ASCII characters in a particular text box.</span></span> <span data-ttu-id="99099-106">在这种情况下，您可以将 <xref:System.Windows.Forms.Control.ImeMode%2A> 属性设置为 <xref:System.Windows.Forms.ImeMode> ，并且用户将只能为该特定文本框输入 ASCII 字符。</span><span class="sxs-lookup"><span data-stu-id="99099-106">In such a case you can set the <xref:System.Windows.Forms.Control.ImeMode%2A> property to <xref:System.Windows.Forms.ImeMode> and users will only be able to enter ASCII characters for that particular text box.</span></span> <span data-ttu-id="99099-107">属性的默认值 <xref:System.Windows.Forms.Control.ImeMode%2A> 为 <xref:System.Windows.Forms.ImeMode> ，因此，如果设置窗体的属性，则窗体上的所有控件都将继承该设置。</span><span class="sxs-lookup"><span data-stu-id="99099-107">The default value of the <xref:System.Windows.Forms.Control.ImeMode%2A> property is <xref:System.Windows.Forms.ImeMode>, so if you set the property for a form, all controls on the form will inherit that setting.</span></span> <span data-ttu-id="99099-108">有关详细信息，请参阅 <xref:System.Windows.Forms.Control.ImeMode%2A> ) 和 <xref:System.Windows.Forms.ImeMode> 。</span><span class="sxs-lookup"><span data-stu-id="99099-108">For more information, see <xref:System.Windows.Forms.Control.ImeMode%2A> ) and <xref:System.Windows.Forms.ImeMode>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99099-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99099-109">See also</span></span>

- [<span data-ttu-id="99099-110">全球化 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="99099-110">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)
