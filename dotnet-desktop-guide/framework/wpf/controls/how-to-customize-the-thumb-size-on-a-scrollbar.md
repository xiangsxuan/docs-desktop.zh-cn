---
title: 如何：自定义滚动条上的滚动块大小
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 60ae7c4e95801036c5deb0c485645297509b830c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973719"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a><span data-ttu-id="65b41-102">如何：自定义滚动条上的滚动块大小</span><span class="sxs-lookup"><span data-stu-id="65b41-102">How to: Customize the Thumb Size on a ScrollBar</span></span>
<span data-ttu-id="65b41-103">本主题说明如何将的设置 <xref:System.Windows.Controls.Primitives.Thumb> <xref:System.Windows.Controls.Primitives.ScrollBar> 为固定大小，以及如何为指定的最小大小 <xref:System.Windows.Controls.Primitives.Thumb> <xref:System.Windows.Controls.Primitives.ScrollBar> 。</span><span class="sxs-lookup"><span data-stu-id="65b41-103">This topic explains how to set the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar> to a fixed size and how to specify a minimum size for the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65b41-104">示例</span><span class="sxs-lookup"><span data-stu-id="65b41-104">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="65b41-105">说明</span><span class="sxs-lookup"><span data-stu-id="65b41-105">Description</span></span>  
 <span data-ttu-id="65b41-106">下面的示例创建一个 <xref:System.Windows.Controls.Primitives.ScrollBar> 具有 <xref:System.Windows.Controls.Primitives.Thumb> 固定大小的。</span><span class="sxs-lookup"><span data-stu-id="65b41-106">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a fixed size.</span></span> <span data-ttu-id="65b41-107">该示例将 <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> 的属性设置 <xref:System.Windows.Controls.Primitives.Thumb> 为 <xref:System.Double.NaN> ，并设置的高度 <xref:System.Windows.Controls.Primitives.Thumb> 。</span><span class="sxs-lookup"><span data-stu-id="65b41-107">The example sets the <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> property of the <xref:System.Windows.Controls.Primitives.Thumb> to <xref:System.Double.NaN> and sets the height of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  <span data-ttu-id="65b41-108">若要创建具有 <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.Primitives.Thumb> 固定宽度的水平，请设置的宽度 <xref:System.Windows.Controls.Primitives.Thumb> 。</span><span class="sxs-lookup"><span data-stu-id="65b41-108">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a fixed width, set the width of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="65b41-109">代码</span><span class="sxs-lookup"><span data-stu-id="65b41-109">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a><span data-ttu-id="65b41-110">说明</span><span class="sxs-lookup"><span data-stu-id="65b41-110">Description</span></span>  
 <span data-ttu-id="65b41-111">下面的示例创建一个 <xref:System.Windows.Controls.Primitives.ScrollBar> 具有 <xref:System.Windows.Controls.Primitives.Thumb> 最小大小的。</span><span class="sxs-lookup"><span data-stu-id="65b41-111">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a minimum size.</span></span> <span data-ttu-id="65b41-112">该示例设置的值 <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A> 。</span><span class="sxs-lookup"><span data-stu-id="65b41-112">The example sets the value of <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span></span> <span data-ttu-id="65b41-113">若要创建具有 <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.Primitives.Thumb> 最小宽度的水平，请设置 <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A> 。</span><span class="sxs-lookup"><span data-stu-id="65b41-113">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a minimum width, set the <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="65b41-114">代码</span><span class="sxs-lookup"><span data-stu-id="65b41-114">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="65b41-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65b41-115">See also</span></span>

- [<span data-ttu-id="65b41-116">ScrollBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="65b41-116">ScrollBar Styles and Templates</span></span>](scrollbar-styles-and-templates.md)
