---
title: 如何：使用 ScrollViewer 创建 Expander
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: ef0bc5d344f7d465de9209708430d3e61d40d4f7
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973558"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a><span data-ttu-id="0ced4-102">如何：使用 ScrollViewer 创建 Expander</span><span class="sxs-lookup"><span data-stu-id="0ced4-102">How to: Create an Expander with a ScrollViewer</span></span>
<span data-ttu-id="0ced4-103">此示例演示如何创建 <xref:System.Windows.Controls.Expander> 包含复杂内容（如图像和文本）的控件。</span><span class="sxs-lookup"><span data-stu-id="0ced4-103">This example shows how to create an <xref:System.Windows.Controls.Expander> control that contains complex content, such as an image and text.</span></span> <span data-ttu-id="0ced4-104">该示例还 <xref:System.Windows.Controls.Expander> 在控件中包含的内容 <xref:System.Windows.Controls.ScrollViewer> 。</span><span class="sxs-lookup"><span data-stu-id="0ced4-104">The example also encloses the content of the <xref:System.Windows.Controls.Expander> in a <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ced4-105">示例</span><span class="sxs-lookup"><span data-stu-id="0ced4-105">Example</span></span>  
 <span data-ttu-id="0ced4-106">下面的示例演示如何创建 <xref:System.Windows.Controls.Expander> 。</span><span class="sxs-lookup"><span data-stu-id="0ced4-106">The following example shows how to create an <xref:System.Windows.Controls.Expander>.</span></span> <span data-ttu-id="0ced4-107">该示例使用 <xref:System.Windows.Controls.Primitives.BulletDecorator> 包含图像和文本的控件来定义 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 。</span><span class="sxs-lookup"><span data-stu-id="0ced4-107">The example uses a <xref:System.Windows.Controls.Primitives.BulletDecorator> control, which contains an image and text, in order to define the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span></span> <span data-ttu-id="0ced4-108"><xref:System.Windows.Controls.ScrollViewer>控件提供用于滚动展开内容的方法。</span><span class="sxs-lookup"><span data-stu-id="0ced4-108">A <xref:System.Windows.Controls.ScrollViewer> control provides a method for scrolling the expanded content.</span></span>  
  
 <span data-ttu-id="0ced4-109">请注意，该示例在上设置 <xref:System.Windows.FrameworkElement.Height%2A> 属性， <xref:System.Windows.Controls.ScrollViewer> 而不是在内容上设置。</span><span class="sxs-lookup"><span data-stu-id="0ced4-109">Note that the example sets the <xref:System.Windows.FrameworkElement.Height%2A> property on the <xref:System.Windows.Controls.ScrollViewer> instead of on the content.</span></span> <span data-ttu-id="0ced4-110">如果对 <xref:System.Windows.FrameworkElement.Height%2A> 内容设置了，则不 <xref:System.Windows.Controls.ScrollViewer> 允许用户滚动内容。</span><span class="sxs-lookup"><span data-stu-id="0ced4-110">If the <xref:System.Windows.FrameworkElement.Height%2A> is set on the content, the <xref:System.Windows.Controls.ScrollViewer> does not allow the user to scroll the content.</span></span> <span data-ttu-id="0ced4-111">在 <xref:System.Windows.FrameworkElement.Width%2A> 控件上设置属性 <xref:System.Windows.Controls.Expander> ，此设置应用于 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 和扩展的内容。</span><span class="sxs-lookup"><span data-stu-id="0ced4-111">The <xref:System.Windows.FrameworkElement.Width%2A> property is set on the <xref:System.Windows.Controls.Expander> control and this setting applies to the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the expanded content.</span></span>  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a><span data-ttu-id="0ced4-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ced4-112">See also</span></span>

- <xref:System.Windows.Controls.Expander>
- [<span data-ttu-id="0ced4-113">Expander 概述</span><span class="sxs-lookup"><span data-stu-id="0ced4-113">Expander Overview</span></span>](expander-overview.md)
- [<span data-ttu-id="0ced4-114">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="0ced4-114">How-to Topics</span></span>](expander-how-to-topics.md)
