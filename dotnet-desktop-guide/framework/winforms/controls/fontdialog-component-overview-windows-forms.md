---
title: FontDialog 组件概述
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 664b756dc068ca283e4f43edbdd0f3266f5d1142
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970060"
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="fda30-102">FontDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="fda30-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="fda30-103">Windows 窗体 <xref:System.Windows.Forms.FontDialog> 组件是预配置的对话框，该对话框是标准的 Windows **字体** 对话框，用于公开系统上当前安装的字体。</span><span class="sxs-lookup"><span data-stu-id="fda30-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="fda30-104">在基于 Windows 的应用程序中使用它作为字体选择的简单解决方案，而不是配置自己的对话框。</span><span class="sxs-lookup"><span data-stu-id="fda30-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="fda30-105">默认情况下，该对话框将显示字体、字形和字号的列表框;用于效果的复选框，如删除线和下划线;脚本的下拉列表;以及字体显示方式的示例。</span><span class="sxs-lookup"><span data-stu-id="fda30-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="fda30-106"> (脚本是指可用于给定字体的不同字符脚本，例如希伯来语或日语。 ) 若要显示 "字体" 对话框，请调用 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="fda30-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="fda30-107">键属性</span><span class="sxs-lookup"><span data-stu-id="fda30-107">Key Properties</span></span>  
 <span data-ttu-id="fda30-108">组件具有多个配置其外观的属性。</span><span class="sxs-lookup"><span data-stu-id="fda30-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="fda30-109">设置对话框选择的属性为 <xref:System.Windows.Forms.FontDialog.Font%2A> 和 <xref:System.Windows.Forms.FontDialog.Color%2A> 。</span><span class="sxs-lookup"><span data-stu-id="fda30-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="fda30-110">此 <xref:System.Windows.Forms.FontDialog.Font%2A> 属性设置字体、样式、大小、脚本和效果; 例如， `Arial, 10pt, style=Italic, Strikeout` 。</span><span class="sxs-lookup"><span data-stu-id="fda30-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fda30-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fda30-111">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="fda30-112">FontDialog 组件</span><span class="sxs-lookup"><span data-stu-id="fda30-112">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)
