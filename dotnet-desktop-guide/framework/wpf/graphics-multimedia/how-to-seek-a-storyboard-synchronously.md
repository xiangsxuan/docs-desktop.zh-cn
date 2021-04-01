---
title: 如何：同步搜寻演示图板
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- seeking Storyboards synchronously [WPF]
- Storyboards [WPF], seeking synchronously
ms.assetid: 03e06271-a946-4810-88ea-3fb4cfa9e0f1
ms.openlocfilehash: 8ac55346ac83ee94318de90655bde6053ef20687
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973215"
---
# <a name="how-to-seek-a-storyboard-synchronously"></a><span data-ttu-id="8cb6d-102">如何：同步搜寻演示图板</span><span class="sxs-lookup"><span data-stu-id="8cb6d-102">How to: Seek a Storyboard Synchronously</span></span>
<span data-ttu-id="8cb6d-103">下面的示例演示如何使用的 <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A> 方法 <xref:System.Windows.Media.Animation.Storyboard> 以同步方式搜索情节提要动画中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="8cb6d-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to seek to any position in a storyboard animation synchronously.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cb6d-104">示例</span><span class="sxs-lookup"><span data-stu-id="8cb6d-104">Example</span></span>  
 <span data-ttu-id="8cb6d-105">下面是此示例的 XAML 标记。</span><span class="sxs-lookup"><span data-stu-id="8cb6d-105">The following is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardSynchronouslyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml#seekstoryboardsynchronouslyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="8cb6d-106">示例</span><span class="sxs-lookup"><span data-stu-id="8cb6d-106">Example</span></span>  
 <span data-ttu-id="8cb6d-107">下面是上述 XAML 代码中所用的代码。</span><span class="sxs-lookup"><span data-stu-id="8cb6d-107">The following is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml.cs#seekstoryboardsynchronouslycodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardSynchronouslyExample.xaml.vb#seekstoryboardsynchronouslycodebehindexamplewholepage)]
