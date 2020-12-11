---
title: 如何：清除自定义控件上的墨迹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
ms.openlocfilehash: 60e2af64cb0c5b313f4f1201cab70da6a88f61e7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973480"
---
# <a name="how-to-erase-ink-on-a-custom-control"></a>如何：清除自定义控件上的墨迹
<xref:System.Windows.Ink.IncrementalStrokeHitTester>确定当前绘制的笔划是否与另一个笔画相交。  这适用于创建一个控件，该控件使用户能够擦除笔划的各个部分，即用户在 <xref:System.Windows.Controls.InkCanvas> 设置为时可以在上的方式 <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint> 。  
  
## <a name="example"></a>示例  
 下面的示例创建一个自定义控件，该控件允许用户擦除笔画的各个部分。  此示例创建一个控件，该控件在初始化时包含墨迹。  若要创建收集墨迹的控件，请参阅 [创建墨迹输入控件](creating-an-ink-input-control.md)。  
  
 [!code-csharp[HowToEraseInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
