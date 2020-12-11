---
title: 使用填充在控件周围创建边框
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- margins
- controls [Windows Forms], Margin property
- padding [Windows Forms], Windows Forms
- controls [Windows Forms], Padding property
- controls [Windows Forms], outlining
- Padding property [Windows Forms]
- margins [Windows Forms], Windows Forms
- Margin property [Windows Forms]
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
ms.openlocfilehash: 114186ab5784cf892cb01e9fe2648ce22cecc4b7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971876"
---
# <a name="how-to-create-a-border-around-a-windows-forms-control-using-padding"></a>如何：使用填充在 Windows 窗体控件周围创建边框
下面的代码示例演示如何在控件周围创建边框或边框 <xref:System.Windows.Forms.RichTextBox> 。 该示例将 <xref:System.Windows.Forms.Panel> 控件的属性的值设置 <xref:System.Windows.Forms.Padding> 为5，并将 <xref:System.Windows.Forms.Control.Dock%2A> 子控件的属性设置 <xref:System.Windows.Forms.RichTextBox> 为 <xref:System.Windows.Forms.DockStyle.Fill> 。 <xref:System.Windows.Forms.Control.BackColor%2A> <xref:System.Windows.Forms.Panel> 控件的设置为 <xref:System.Drawing.Color.Blue%2A> ，它在控件周围创建一个蓝色边框 <xref:System.Windows.Forms.RichTextBox> 。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.Padding#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Padding>
- [Windows 窗体控件中的边距和填充](margin-and-padding-in-windows-forms-controls.md)
