---
title: 调整标签控件大小以适应其内容
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 6a563693feaa5074f5d13f0b82cc4d0305a79c23
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972547"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>如何：调整 Windows 窗体标签控件大小以适应其内容
Windows 窗体 <xref:System.Windows.Forms.Label> 控件可以是单行或多行，它可以是固定的，也可以自动调整自身大小以适应其标题。 <xref:System.Windows.Forms.Label.AutoSize%2A>属性可帮助您调整控件的大小以适合更大或更小的标题，这在标题会在运行时更改时特别有用。  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>使标签控件动态调整大小以适应其内容  
  
1. 将其 <xref:System.Windows.Forms.Label.AutoSize%2A> 属性设置为 `true` 。  
  
 如果 <xref:System.Windows.Forms.Label.AutoSize%2A> 设置为 `false` ，则在属性中指定的单词 <xref:System.Windows.Forms.Label.Text%2A> 会换行到下一行（如果可能），但控件不会增长。  
  
## <a name="see-also"></a>另请参阅

- [如何：使用 Windows 窗体 Label 控件创建访问键](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [Label 控件概述](label-control-overview-windows-forms.md)
- [Label 控件](label-control-windows-forms.md)
