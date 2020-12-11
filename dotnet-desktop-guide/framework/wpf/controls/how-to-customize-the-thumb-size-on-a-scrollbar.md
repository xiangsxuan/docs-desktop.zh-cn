---
title: 如何：自定义滚动条上的滚动块大小
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 60ae7c4e95801036c5deb0c485645297509b830c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973719"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a><span data-ttu-id="9ff20-102">如何：自定义滚动条上的滚动块大小</span><span class="sxs-lookup"><span data-stu-id="9ff20-102">How to: Customize the Thumb Size on a ScrollBar</span></span>
<span data-ttu-id="9ff20-103">本主题说明如何将的设置 <xref:System.Windows.Controls.Primitives.Thumb> <xref:System.Windows.Controls.Primitives.ScrollBar> 为固定大小，以及如何为指定的最小大小 <xref:System.Windows.Controls.Primitives.Thumb> <xref:System.Windows.Controls.Primitives.ScrollBar> 。</span><span class="sxs-lookup"><span data-stu-id="9ff20-103">This topic explains how to set the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar> to a fixed size and how to specify a minimum size for the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ff20-104">示例</span><span class="sxs-lookup"><span data-stu-id="9ff20-104">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="9ff20-105">描述</span><span class="sxs-lookup"><span data-stu-id="9ff20-105">Description</span></span>  
 <span data-ttu-id="9ff20-106">下面的示例创建一个 <xref:System.Windows.Controls.Primitives.ScrollBar> 具有 <xref:System.Windows.Controls.Primitives.Thumb> 固定大小的。</span><span class="sxs-lookup"><span data-stu-id="9ff20-106">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a fixed size.</span></span> <span data-ttu-id="9ff20-107">该示例将 <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> 的属性设置 <xref:System.Windows.Controls.Primitives.Thumb> 为 <xref:System.Double.NaN> ，并设置的高度 <xref:System.Windows.Controls.Primitives.Thumb> 。</span><span class="sxs-lookup"><span data-stu-id="9ff20-107">The example sets the <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> property of the <xref:System.Windows.Controls.Primitives.Thumb> to <xref:System.Double.NaN> and sets the height of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  <span data-ttu-id="9ff20-108">若要创建具有 <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.Primitives.Thumb> 固定宽度的水平，请设置的宽度 <xref:System.Windows.Controls.Primitives.Thumb> 。</span><span class="sxs-lookup"><span data-stu-id="9ff20-108">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a fixed width, set the width of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="9ff20-109">代码</span><span class="sxs-lookup"><span data-stu-id="9ff20-109">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a><span data-ttu-id="9ff20-110">说明</span><span class="sxs-lookup"><span data-stu-id="9ff20-110">Description</span></span>  
 <span data-ttu-id="9ff20-111">下面的示例创建一个 <xref:System.Windows.Controls.Primitives.ScrollBar> 具有 <xref:System.Windows.Controls.Primitives.Thumb> 最小大小的。</span><span class="sxs-lookup"><span data-stu-id="9ff20-111">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a minimum size.</span></span> <span data-ttu-id="9ff20-112">该示例设置的值 <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A> 。</span><span class="sxs-lookup"><span data-stu-id="9ff20-112">The example sets the value of <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span></span> <span data-ttu-id="9ff20-113">若要创建具有 <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.Primitives.Thumb> 最小宽度的水平，请设置 <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A> 。</span><span class="sxs-lookup"><span data-stu-id="9ff20-113">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a minimum width, set the <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="9ff20-114">代码</span><span class="sxs-lookup"><span data-stu-id="9ff20-114">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9ff20-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ff20-115">See also</span></span>

- [<span data-ttu-id="9ff20-116">ScrollBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="9ff20-116">ScrollBar Styles and Templates</span></span>](scrollbar-styles-and-templates.md)
