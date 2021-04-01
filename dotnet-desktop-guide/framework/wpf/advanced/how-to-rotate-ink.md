---
title: 如何：旋转墨迹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], rotating
- rotating ink [WPF]
ms.assetid: fac36cc9-dd01-41ca-9bde-9d33e3790bbe
ms.openlocfilehash: 041147b7d5938d7d28d57169da1f1e880d69fe2b
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970476"
---
# <a name="how-to-rotate-ink"></a>如何：旋转墨迹
## <a name="example"></a>示例  
 下面的示例将墨迹从复制 <xref:System.Windows.Controls.InkCanvas> 到包含的 <xref:System.Windows.Controls.Canvas> <xref:System.Windows.Controls.InkPresenter> 。  当应用程序复制墨迹时，它还会顺时针旋转墨迹90度。  
  
 [!code-xaml[HowToRotateInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[HowToRotateInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml.cs#2)]  
  
## <a name="example"></a>示例  
 下面的示例是一个在 <xref:System.Windows.Documents.Adorner> 上旋转笔划的自定义 <xref:System.Windows.Controls.InkPresenter> 。  
  
 [!code-csharp[AdornerForStrokes#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/RotatingAdornerForStrokes.cs#1)]
 [!code-vb[AdornerForStrokes#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/RotatingAdornerForStrokes.vb#1)]  
  
 下面的示例是一个 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 定义的文件， <xref:System.Windows.Controls.InkPresenter> 并使用墨迹填充该文件。 `Window_Loaded`事件处理程序将自定义装饰器添加到 <xref:System.Windows.Controls.InkPresenter> 。  
  
 [!code-xaml[AdornerForStrokes#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[AdornerForStrokes#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml.cs#3)]
 [!code-vb[AdornerForStrokes#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/Window1.xaml.vb#3)]
