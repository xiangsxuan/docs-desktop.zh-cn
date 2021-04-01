---
title: 如何：搜寻演示图板
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], seeking
- seeking Storyboards [WPF]
ms.assetid: 887bb39a-0c2a-4ae8-956d-1d9f6f8ebbfc
ms.openlocfilehash: a57272c17a5bc6f5baaa21fb77233fc5693d1914
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96971720"
---
# <a name="how-to-seek-a-storyboard"></a><span data-ttu-id="23778-102">如何：搜寻演示图板</span><span class="sxs-lookup"><span data-stu-id="23778-102">How to: Seek a Storyboard</span></span>
<span data-ttu-id="23778-103">下面的示例演示如何使用的 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 方法 <xref:System.Windows.Media.Animation.Storyboard> 跳转到演示图板动画中的任意位置。</span><span class="sxs-lookup"><span data-stu-id="23778-103">The following example shows how to use the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method of a <xref:System.Windows.Media.Animation.Storyboard> to jump to any position in a storyboard animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23778-104">示例</span><span class="sxs-lookup"><span data-stu-id="23778-104">Example</span></span>  
 <span data-ttu-id="23778-105">下面是此示例的 XAML 标记。</span><span class="sxs-lookup"><span data-stu-id="23778-105">Below is the XAML markup for the sample.</span></span>  
  
 [!code-xaml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="23778-106">示例</span><span class="sxs-lookup"><span data-stu-id="23778-106">Example</span></span>  
 <span data-ttu-id="23778-107">下面是上述 XAML 代码中所用的代码。</span><span class="sxs-lookup"><span data-stu-id="23778-107">Below is the code used with the XAML code above.</span></span>  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="23778-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="23778-108">See also</span></span>

- [<span data-ttu-id="23778-109">同步搜寻情节提要</span><span class="sxs-lookup"><span data-stu-id="23778-109">Seek a Storyboard Synchronously</span></span>](how-to-seek-a-storyboard-synchronously.md)
