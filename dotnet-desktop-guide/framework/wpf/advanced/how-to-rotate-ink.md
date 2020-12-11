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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970476"
---
# <a name="how-to-rotate-ink"></a><span data-ttu-id="a1da9-102">如何：旋转墨迹</span><span class="sxs-lookup"><span data-stu-id="a1da9-102">How to: Rotate Ink</span></span>
## <a name="example"></a><span data-ttu-id="a1da9-103">示例</span><span class="sxs-lookup"><span data-stu-id="a1da9-103">Example</span></span>  
 <span data-ttu-id="a1da9-104">下面的示例将墨迹从复制 <xref:System.Windows.Controls.InkCanvas> 到包含的 <xref:System.Windows.Controls.Canvas> <xref:System.Windows.Controls.InkPresenter> 。</span><span class="sxs-lookup"><span data-stu-id="a1da9-104">The following example copies the ink from an <xref:System.Windows.Controls.InkCanvas> to a <xref:System.Windows.Controls.Canvas> that contains an <xref:System.Windows.Controls.InkPresenter>.</span></span>  <span data-ttu-id="a1da9-105">当应用程序复制墨迹时，它还会顺时针旋转墨迹90度。</span><span class="sxs-lookup"><span data-stu-id="a1da9-105">When the application copies the ink, it also rotates the ink 90 degrees clockwise.</span></span>  
  
 [!code-xaml[HowToRotateInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[HowToRotateInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="a1da9-106">示例</span><span class="sxs-lookup"><span data-stu-id="a1da9-106">Example</span></span>  
 <span data-ttu-id="a1da9-107">下面的示例是一个在 <xref:System.Windows.Documents.Adorner> 上旋转笔划的自定义 <xref:System.Windows.Controls.InkPresenter> 。</span><span class="sxs-lookup"><span data-stu-id="a1da9-107">The following example is a custom <xref:System.Windows.Documents.Adorner> that rotates the strokes on an <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[AdornerForStrokes#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/RotatingAdornerForStrokes.cs#1)]
 [!code-vb[AdornerForStrokes#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/RotatingAdornerForStrokes.vb#1)]  
  
 <span data-ttu-id="a1da9-108">下面的示例是一个 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 定义的文件， <xref:System.Windows.Controls.InkPresenter> 并使用墨迹填充该文件。</span><span class="sxs-lookup"><span data-stu-id="a1da9-108">The following example is a [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file that defines an <xref:System.Windows.Controls.InkPresenter> and populates it with ink.</span></span> <span data-ttu-id="a1da9-109">`Window_Loaded`事件处理程序将自定义装饰器添加到 <xref:System.Windows.Controls.InkPresenter> 。</span><span class="sxs-lookup"><span data-stu-id="a1da9-109">The `Window_Loaded` event handler adds the custom adorner to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-xaml[AdornerForStrokes#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[AdornerForStrokes#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml.cs#3)]
 [!code-vb[AdornerForStrokes#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/Window1.xaml.vb#3)]
