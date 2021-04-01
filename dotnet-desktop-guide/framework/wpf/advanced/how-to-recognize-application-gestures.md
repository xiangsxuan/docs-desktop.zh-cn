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
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973645"
---
# <a name="how-to-recognize-application-gestures"></a>如何：识别应用程序操作
下面的示例演示当用户在上执行笔势时如何擦除墨迹 <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> <xref:System.Windows.Controls.InkCanvas> 。 本示例假定 <xref:System.Windows.Controls.InkCanvas> `inkCanvas1` 在 XAML 文件中声明了一个名为的。  
  
## <a name="example"></a>示例  
 [!code-csharp[HowToRecognizeGestures#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Ink.ApplicationGesture>
- <xref:System.Windows.Controls.InkCanvas>
- <xref:System.Windows.Controls.InkCanvas.Gesture>
