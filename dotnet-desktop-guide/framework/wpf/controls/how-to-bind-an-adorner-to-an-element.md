---
title: 如何：将装饰器绑定到元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: 951643602b09a522d23a6449aefa4be41e051a40
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972894"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="00288-102">如何：将装饰器绑定到元素</span><span class="sxs-lookup"><span data-stu-id="00288-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="00288-103">此示例演示如何以编程方式将装饰器绑定到指定的 <xref:System.Windows.UIElement> 。</span><span class="sxs-lookup"><span data-stu-id="00288-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00288-104">示例</span><span class="sxs-lookup"><span data-stu-id="00288-104">Example</span></span>  
 <span data-ttu-id="00288-105">若要将装饰器绑定到特定的 <xref:System.Windows.UIElement> ，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="00288-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1. <span data-ttu-id="00288-106">调用 `static` 方法 <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 以获取 <xref:System.Windows.Documents.AdornerLayer> 要装饰的的对象 <xref:System.Windows.UIElement> 。</span><span class="sxs-lookup"><span data-stu-id="00288-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="00288-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 遍历可视化树（从指定的 **UIElement** 开始），并返回它找到的第一个装饰器层。</span><span class="sxs-lookup"><span data-stu-id="00288-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="00288-108">（如果未发现装饰器层，该方法将返回 null。）</span><span class="sxs-lookup"><span data-stu-id="00288-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2. <span data-ttu-id="00288-109">调用 <xref:System.Windows.Documents.AdornerLayer.Add%2A> 方法以将装饰器绑定到目标 **UIElement**。</span><span class="sxs-lookup"><span data-stu-id="00288-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="00288-110">下面的示例将如上所示) 的 (SimpleCircleAdorner 绑定到一个 <xref:System.Windows.Controls.TextBox> 命名的 *myTextBox*。</span><span class="sxs-lookup"><span data-stu-id="00288-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
> <span data-ttu-id="00288-111">目前不支持使用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 将装饰器绑定到另一个元素。</span><span class="sxs-lookup"><span data-stu-id="00288-111">Using [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00288-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00288-112">See also</span></span>

- [<span data-ttu-id="00288-113">装饰器概述</span><span class="sxs-lookup"><span data-stu-id="00288-113">Adorners Overview</span></span>](adorners-overview.md)
