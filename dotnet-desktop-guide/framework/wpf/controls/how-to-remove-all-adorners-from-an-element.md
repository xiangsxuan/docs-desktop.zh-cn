---
title: 如何：从元素移除所有装饰器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
ms.openlocfilehash: 8504bb1ec70de188033b2b092bbb66cf9da3dc11
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974053"
---
# <a name="how-to-remove-all-adorners-from-an-element"></a><span data-ttu-id="07b27-102">如何：从元素移除所有装饰器</span><span class="sxs-lookup"><span data-stu-id="07b27-102">How to: Remove all Adorners from an Element</span></span>
<span data-ttu-id="07b27-103">此示例演示如何以编程方式从指定的中移除所有装饰器 <xref:System.Windows.UIElement> 。</span><span class="sxs-lookup"><span data-stu-id="07b27-103">This example shows how to programmatically remove all adorners from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07b27-104">示例</span><span class="sxs-lookup"><span data-stu-id="07b27-104">Example</span></span>  
 <span data-ttu-id="07b27-105">此详细的代码示例删除由返回的装饰器数组中的所有装饰器 <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> 。</span><span class="sxs-lookup"><span data-stu-id="07b27-105">This verbose code example removes all of the adorners in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="07b27-106">此示例将在已命名的 MyTextBox 上检索装饰器 <xref:System.Windows.UIElement> 。 </span><span class="sxs-lookup"><span data-stu-id="07b27-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="07b27-107">如果对的调用中指定的元素 <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> 没有装饰器， `null` 则返回。</span><span class="sxs-lookup"><span data-stu-id="07b27-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="07b27-108">此代码显式检查 null 数组，最适用于预计空数组相对较为常见的应用程序。</span><span class="sxs-lookup"><span data-stu-id="07b27-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a><span data-ttu-id="07b27-109">示例</span><span class="sxs-lookup"><span data-stu-id="07b27-109">Example</span></span>  
 <span data-ttu-id="07b27-110">此简洁的代码示例在功能上等效于上面所示的详细示例。</span><span class="sxs-lookup"><span data-stu-id="07b27-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="07b27-111">此代码不显式检查 null 数组，因此 <xref:System.NullReferenceException> 可能会引发异常。</span><span class="sxs-lookup"><span data-stu-id="07b27-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="07b27-112">此代码最适合于应极少出现空数组的应用程序。</span><span class="sxs-lookup"><span data-stu-id="07b27-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a><span data-ttu-id="07b27-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="07b27-113">See also</span></span>

- [<span data-ttu-id="07b27-114">装饰器概述</span><span class="sxs-lookup"><span data-stu-id="07b27-114">Adorners Overview</span></span>](adorners-overview.md)
