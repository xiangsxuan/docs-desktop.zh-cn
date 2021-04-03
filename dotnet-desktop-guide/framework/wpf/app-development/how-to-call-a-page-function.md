---
title: 如何：调用页函数
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- calling page functions [WPF]
- page functions [WPF], calling
- functions [WPF], calling
ms.assetid: a4808397-c6d5-406a-83e0-0091f0c15ae4
ms.openlocfilehash: 0370fe0bcbdf5105ae1b65bb90346663b2786a63
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973030"
---
# <a name="how-to-call-a-page-function"></a><span data-ttu-id="1ed72-102">如何：调用页函数</span><span class="sxs-lookup"><span data-stu-id="1ed72-102">How to: Call a Page Function</span></span>
<span data-ttu-id="1ed72-103">此示例演示如何从页面调用 page 函数 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="1ed72-103">This example shows how to call a page function from a [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ed72-104">示例</span><span class="sxs-lookup"><span data-stu-id="1ed72-104">Example</span></span>  
 <span data-ttu-id="1ed72-105">您可以使用统一资源标识符 (URI) 导航到页面函数，就像导航到某个页面一样。</span><span class="sxs-lookup"><span data-stu-id="1ed72-105">You can navigate to a page function using a uniform resource identifier (URI), just as you can when you navigate to a page.</span></span> <span data-ttu-id="1ed72-106">下面的示例说明了这一点。</span><span class="sxs-lookup"><span data-stu-id="1ed72-106">This is shown in the following example.</span></span>  
  
 [!code-csharp[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#navigatetoapagefunctionlikeapagecodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#navigatetoapagefunctionlikeapagecodebehind)]  
  
 <span data-ttu-id="1ed72-107">如果需要将数据传递到页函数，可以创建它的实例并通过设置属性来传递数据。</span><span class="sxs-lookup"><span data-stu-id="1ed72-107">If you need to pass data to the page function, you can create an instance of it and pass the data by setting a property.</span></span> <span data-ttu-id="1ed72-108">或者，如下面的示例所示，可以使用非参数构造函数传递数据。</span><span class="sxs-lookup"><span data-stu-id="1ed72-108">Or, as the following example shows, you can pass the data using a non-parameterless constructor.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#callapagefunctioncodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#callapagefunctioncodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="1ed72-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ed72-109">See also</span></span>

- <xref:System.Windows.Navigation.PageFunction%601>
