---
title: 如何：识别应用程序操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
ms.openlocfilehash: 647e7c9c1d785cebfdc362dc48511d865f3945dc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973645"
---
# <a name="how-to-recognize-application-gestures"></a><span data-ttu-id="60ce1-102">如何：识别应用程序操作</span><span class="sxs-lookup"><span data-stu-id="60ce1-102">How To: Recognize Application Gestures</span></span>
<span data-ttu-id="60ce1-103">下面的示例演示当用户在上执行笔势时如何擦除墨迹 <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> <xref:System.Windows.Controls.InkCanvas> 。</span><span class="sxs-lookup"><span data-stu-id="60ce1-103">The following example demonstrates how to erase ink when a user makes a <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> gesture on an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="60ce1-104">本示例假定 <xref:System.Windows.Controls.InkCanvas> `inkCanvas1` 在 XAML 文件中声明了一个名为的。</span><span class="sxs-lookup"><span data-stu-id="60ce1-104">This example assumes an <xref:System.Windows.Controls.InkCanvas>, called `inkCanvas1`, is declared in the XAML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60ce1-105">示例</span><span class="sxs-lookup"><span data-stu-id="60ce1-105">Example</span></span>  
 [!code-csharp[HowToRecognizeGestures#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="60ce1-106">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60ce1-106">See also</span></span>

- <xref:System.Windows.Ink.ApplicationGesture>
- <xref:System.Windows.Controls.InkCanvas>
- <xref:System.Windows.Controls.InkCanvas.Gesture>
