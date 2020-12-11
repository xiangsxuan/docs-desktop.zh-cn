---
title: 如何：从元素移除装饰器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: 256dd6fa0117f88aec2ef6b60c6dcd4c33b57855
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972939"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a><span data-ttu-id="70fae-102">如何：从元素移除装饰器</span><span class="sxs-lookup"><span data-stu-id="70fae-102">How to: Remove an Adorner from an Element</span></span>
<span data-ttu-id="70fae-103">此示例演示如何以编程方式从指定的中删除特定的装饰器 <xref:System.Windows.UIElement> 。</span><span class="sxs-lookup"><span data-stu-id="70fae-103">This example shows how to programmatically remove a specific adorner from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70fae-104">示例</span><span class="sxs-lookup"><span data-stu-id="70fae-104">Example</span></span>  
 <span data-ttu-id="70fae-105">此详细的代码示例删除由返回的装饰器数组中的第一个装饰器 <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> 。</span><span class="sxs-lookup"><span data-stu-id="70fae-105">This verbose code example removes the first adorner in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="70fae-106">此示例将在已命名的 MyTextBox 上检索装饰器 <xref:System.Windows.UIElement> 。 </span><span class="sxs-lookup"><span data-stu-id="70fae-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="70fae-107">如果对的调用中指定的元素 <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> 没有装饰器， `null` 则返回。</span><span class="sxs-lookup"><span data-stu-id="70fae-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="70fae-108">此代码显式检查 null 数组，最适用于预计空数组相对较为常见的应用程序。</span><span class="sxs-lookup"><span data-stu-id="70fae-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a><span data-ttu-id="70fae-109">示例</span><span class="sxs-lookup"><span data-stu-id="70fae-109">Example</span></span>  
 <span data-ttu-id="70fae-110">此简洁的代码示例在功能上等效于上面所示的详细示例。</span><span class="sxs-lookup"><span data-stu-id="70fae-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="70fae-111">此代码不显式检查 null 数组，因此 <xref:System.NullReferenceException> 可能会引发异常。</span><span class="sxs-lookup"><span data-stu-id="70fae-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="70fae-112">此代码最适合于应极少出现空数组的应用程序。</span><span class="sxs-lookup"><span data-stu-id="70fae-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a><span data-ttu-id="70fae-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70fae-113">See also</span></span>

- [<span data-ttu-id="70fae-114">装饰器概述</span><span class="sxs-lookup"><span data-stu-id="70fae-114">Adorners Overview</span></span>](adorners-overview.md)
