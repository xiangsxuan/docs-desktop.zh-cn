---
title: 如何：获取页函数的返回值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- functions [WPF], getting return values of
- page functions [WPF], getting return values of
- return values of page functions [WPF]
- getting [WPF], return values of page functions
ms.assetid: 75470af6-256c-4c46-87e7-705080723a1c
ms.openlocfilehash: 054ffe16690425e118fcac481b2a5ff63f9450f2
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970242"
---
# <a name="how-to-get-the-return-value-of-a-page-function"></a><span data-ttu-id="2feaa-102">如何：获取页函数的返回值</span><span class="sxs-lookup"><span data-stu-id="2feaa-102">How to: Get the Return Value of a Page Function</span></span>
<span data-ttu-id="2feaa-103">本示例显示如何获取页函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="2feaa-103">This example shows how to get the result that is returned by a page function.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2feaa-104">示例</span><span class="sxs-lookup"><span data-stu-id="2feaa-104">Example</span></span>  
 <span data-ttu-id="2feaa-105">若要获取从 page 函数返回的结果，需要处理要 <xref:System.Windows.Navigation.PageFunction%601.Return> 调用的 page 函数。</span><span class="sxs-lookup"><span data-stu-id="2feaa-105">To get the result that is returned from a page function, you need to handle <xref:System.Windows.Navigation.PageFunction%601.Return> of the page function you are calling.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#getpagefunctionresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#getpagefunctionresultcodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="2feaa-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="2feaa-106">See also</span></span>

- <xref:System.Windows.Navigation.PageFunction%601>
