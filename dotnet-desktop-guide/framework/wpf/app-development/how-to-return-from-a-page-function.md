---
title: 如何：从页函数返回
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- returning from page functions [WPF]
- page functions [WPF], returning from
- functions [WPF], returning from
ms.assetid: 87804905-7e8f-417b-b0e3-5622da686396
ms.openlocfilehash: 8539395625ead3b71e8e50b36567c098eb13da01
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973863"
---
# <a name="how-to-return-from-a-page-function"></a><span data-ttu-id="a7330-102">如何：从页函数返回</span><span class="sxs-lookup"><span data-stu-id="a7330-102">How to: Return from a Page Function</span></span>
<span data-ttu-id="a7330-103">本示例显示如何从页函数返回结果。</span><span class="sxs-lookup"><span data-stu-id="a7330-103">This example shows how to return a result from a page function.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7330-104">示例</span><span class="sxs-lookup"><span data-stu-id="a7330-104">Example</span></span>  
 <span data-ttu-id="a7330-105">若要从页函数返回，需要调用 <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 并传递的实例 <xref:System.Windows.Navigation.ReturnEventArgs%601> 。</span><span class="sxs-lookup"><span data-stu-id="a7330-105">To return from a page function, you need to call <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> and pass an instance of <xref:System.Windows.Navigation.ReturnEventArgs%601>.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#PageFunctionReturnAResultXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml#pagefunctionreturnaresultxaml1)]  
[!code-xaml[HOWTOPageFunctionSnippets#PageFunctionReturnAResultXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml#pagefunctionreturnaresultxaml2)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#PageFunctionReturnAResultCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml.cs#pagefunctionreturnaresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#PageFunctionReturnAResultCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/GetStringPageFunction.xaml.vb#pagefunctionreturnaresultcodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="a7330-106">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7330-106">See also</span></span>

- <xref:System.Windows.Navigation.PageFunction%601>