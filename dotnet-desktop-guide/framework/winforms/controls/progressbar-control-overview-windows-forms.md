---
title: ProgressBar 控件概述
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: a0c4a0401d06614ab3ad148b932ebc64080c592c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970298"
---
# <a name="progressbar-control-overview-windows-forms"></a>ProgressBar 控件概述（Windows 窗体）
> [!IMPORTANT]
> <xref:System.Windows.Forms.ToolStripProgressBar> 控件取代了 <xref:System.Windows.Forms.ProgressBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ProgressBar> 控件以实现向后兼容并供将来使用。  
  
 "Windows 窗体" <xref:System.Windows.Forms.ProgressBar> 控件通过在水平栏中显示适当数量的矩形来指示进程的进度。 完成此过程后，将填充该条形。 进度栏通常用于使用户了解等待进程完成的时间，例如，在加载大型文件时。  
  
> [!NOTE]
> <xref:System.Windows.Forms.ProgressBar>控件只能在窗体上水平定向。  
  
## <a name="key-properties-and-methods"></a>键属性和方法  
 控件的键属性 <xref:System.Windows.Forms.ProgressBar> 为 <xref:System.Windows.Forms.ProgressBar.Value%2A> 、 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 和 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 。 <xref:System.Windows.Forms.ProgressBar.Minimum%2A>和 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 属性设置进度栏可显示的最大值和最小值。 <xref:System.Windows.Forms.ProgressBar.Value%2A>属性表示完成该操作所进行的进度。 由于控件中显示的栏是由块组成的，因此控件显示的值 <xref:System.Windows.Forms.ProgressBar> 仅接近 <xref:System.Windows.Forms.ProgressBar.Value%2A> 属性的当前值。 根据控件的大小 <xref:System.Windows.Forms.ProgressBar> ， <xref:System.Windows.Forms.ProgressBar.Value%2A> 属性将确定何时显示下一个块。  
  
 更新当前进度值的最常见方法是编写代码以设置 <xref:System.Windows.Forms.ProgressBar.Value%2A> 属性。 在加载大型文件的示例中，可以将最大大小设置为文件大小（kb）。 例如，如果将 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 属性设置为100，则 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 属性设置为10， <xref:System.Windows.Forms.ProgressBar.Value%2A> 属性设置为50，将显示5个矩形。 这是可显示的数字的一半。  
  
 不过，还可以通过其他方式修改控件显示的值，而不是 <xref:System.Windows.Forms.ProgressBar> <xref:System.Windows.Forms.ProgressBar.Value%2A> 直接设置属性。 <xref:System.Windows.Forms.ProgressBar.Step%2A>属性可用于指定值以递增 <xref:System.Windows.Forms.ProgressBar.Value%2A> 属性。 然后，调用 <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> 方法会递增值。 若要更改增量值，可以使用 <xref:System.Windows.Forms.ProgressBar.Increment%2A> 方法并指定一个值，以便为 <xref:System.Windows.Forms.ProgressBar.Value%2A> 属性递增。  
  
 以图形方式向用户通知当前操作的另一个控件是 <xref:System.Windows.Forms.StatusBar> 控件。  
  
> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusStrip>和 <xref:System.Windows.Forms.ToolStripStatusLabel> 控件替换和添加了 <xref:System.Windows.Forms.StatusBar> 和控件的功能 <xref:System.Windows.Forms.StatusBarPanel> ; 但是， <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> 如果你选择，和控件将保留以实现向后兼容性和将来使用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ProgressBar>
- [ProgressBar 控件](progressbar-control-windows-forms.md)
