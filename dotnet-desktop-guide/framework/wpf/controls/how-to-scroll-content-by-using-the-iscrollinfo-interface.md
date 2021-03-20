---
title: 如何：使用 IScrollInfo 接口来滚动内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
ms.openlocfilehash: f45bb6dfd70084675ea9a9215ffa616de3e3753c
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668456"
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a><span data-ttu-id="5f89b-102">如何：使用 IScrollInfo 接口来滚动内容</span><span class="sxs-lookup"><span data-stu-id="5f89b-102">How to: Scroll Content by Using the IScrollInfo Interface</span></span>
<span data-ttu-id="5f89b-103">此示例演示如何使用接口滚动内容 <xref:System.Windows.Controls.Primitives.IScrollInfo> 。</span><span class="sxs-lookup"><span data-stu-id="5f89b-103">This example shows how to scroll content by using the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f89b-104">示例</span><span class="sxs-lookup"><span data-stu-id="5f89b-104">Example</span></span>  
 <span data-ttu-id="5f89b-105">下面的示例演示接口的功能 <xref:System.Windows.Controls.Primitives.IScrollInfo> 。</span><span class="sxs-lookup"><span data-stu-id="5f89b-105">The following example demonstrates the features of the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span> <span data-ttu-id="5f89b-106">此示例在 <xref:System.Windows.Controls.StackPanel> 中创建 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 嵌套在父级中的元素 <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="5f89b-106">The example creates a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] that is nested in a parent <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="5f89b-107">的子元素 <xref:System.Windows.Controls.StackPanel> 可以通过使用接口所定义的方法以逻辑方式滚动 <xref:System.Windows.Controls.Primitives.IScrollInfo> ，并强制转换为 <xref:System.Windows.Controls.StackPanel> 代码中的 (`sp1`) 的实例。</span><span class="sxs-lookup"><span data-stu-id="5f89b-107">The child elements of the <xref:System.Windows.Controls.StackPanel> can be scrolled logically by using the methods defined by the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface and cast to the instance of <xref:System.Windows.Controls.StackPanel> (`sp1`) in code.</span></span>  
  
 [!code-xaml[IScrollInfoMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="5f89b-108"><xref:System.Windows.Controls.Button>文件中的每个都 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 触发一个关联的自定义方法，该方法控制中的滚动行为 <xref:System.Windows.Controls.StackPanel> 。</span><span class="sxs-lookup"><span data-stu-id="5f89b-108">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] file triggers an associated custom method that controls scrolling behavior in <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="5f89b-109">下面的示例演示如何使用 <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> 和 <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> 方法; 它还一般显示了如何使用类定义的所有定位方法 <xref:System.Windows.Controls.Primitives.IScrollInfo> 。</span><span class="sxs-lookup"><span data-stu-id="5f89b-109">The following example shows how to use the <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> and <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> methods; it also generically shows how to use all the positioning methods that the <xref:System.Windows.Controls.Primitives.IScrollInfo> class defines.</span></span>  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="5f89b-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f89b-110">See also</span></span>

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- <xref:System.Windows.Controls.StackPanel>
- [<span data-ttu-id="5f89b-111">ScrollViewer 概述</span><span class="sxs-lookup"><span data-stu-id="5f89b-111">ScrollViewer Overview</span></span>](scrollviewer-overview.md)
- [<span data-ttu-id="5f89b-112">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="5f89b-112">How-to Topics</span></span>](scrollviewer-how-to-topics.md)
- [<span data-ttu-id="5f89b-113">面板概述</span><span class="sxs-lookup"><span data-stu-id="5f89b-113">Panels Overview</span></span>](panels-overview.md)
