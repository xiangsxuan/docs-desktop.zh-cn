---
title: PrintPreviewControl 控件概述
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: 8dfe5802a24d5ec85ed908fd04c5550e1fbec012
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972789"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>PrintPreviewControl 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.PrintPreviewControl> 用于显示 [PrintDocument](printdocument-component-windows-forms.md) ，因为它会在打印后显示。 此控件具有没有按钮或其他用户界面元素，因此通常仅在你想要编写自己的打印预览用户界面时才使用 <xref:System.Windows.Forms.PrintPreviewControl>。 如果需要标准用户界面，请使用 <xref:System.Windows.Forms.PrintPreviewDialog> 控件; 有关概述，请参阅 [PrintPreviewDialog 控件概述](printpreviewdialog-control-overview-windows-forms.md) 。  
  
## <a name="key-properties"></a>键属性  
 控件的键属性为 <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> ，用于设置要预览的文档。 文档必须为 <xref:System.Drawing.Printing.PrintDocument> 对象。 有关创建打印文档的概述，请参阅 [PrintDocument 组件概述](printdocument-component-overview-windows-forms.md) 和 [Windows 窗体打印支持](../advanced/windows-forms-print-support.md)。 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>和 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 属性确定控件上横向和纵向显示的页数。 抗锯齿可以使文本显示得更平滑，但也可以使显示速度变慢;若要使用它，请将 <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> 属性设置为 `true` 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.PrintPreviewControl>
- [PrintPreviewDialog 控件概述](printpreviewdialog-control-overview-windows-forms.md)
- [PrintPreviewControl 控件](printpreviewcontrol-control-windows-forms.md)
- [对话框控件和组件](dialog-box-controls-and-components-windows-forms.md)
