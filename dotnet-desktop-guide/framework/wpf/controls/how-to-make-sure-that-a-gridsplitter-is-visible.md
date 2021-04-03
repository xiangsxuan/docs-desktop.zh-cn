---
title: 如何：确保 GridSplitter 可见
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: 2085ac5cec206d8692a1267acf132688f0aa9082
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96974069"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a><span data-ttu-id="a376b-102">如何：确保 GridSplitter 可见</span><span class="sxs-lookup"><span data-stu-id="a376b-102">How to: Make Sure That a GridSplitter Is Visible</span></span>
<span data-ttu-id="a376b-103">此示例演示如何确保 <xref:System.Windows.Controls.GridSplitter> 中的其他控件不会隐藏控件 <xref:System.Windows.Controls.Grid> 。</span><span class="sxs-lookup"><span data-stu-id="a376b-103">This example shows how to make sure a <xref:System.Windows.Controls.GridSplitter> control is not hidden by the other controls in a <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a376b-104">示例</span><span class="sxs-lookup"><span data-stu-id="a376b-104">Example</span></span>  
 <span data-ttu-id="a376b-105"><xref:System.Windows.Controls.Panel.Children%2A>控件的按 <xref:System.Windows.Controls.Grid> 其在标记或代码中定义的顺序呈现。</span><span class="sxs-lookup"><span data-stu-id="a376b-105">The <xref:System.Windows.Controls.Panel.Children%2A> of a <xref:System.Windows.Controls.Grid> control are rendered in the order that they are defined in markup or code.</span></span> <span data-ttu-id="a376b-106"><xref:System.Windows.Controls.GridSplitter> 如果你未将控件定义为集合中的最后一个元素， <xref:System.Windows.Controls.Panel.Children%2A> 或者如果你为其他控件指定更高的控件，则这些控件可以隐藏控件 <xref:System.Windows.Controls.Panel.ZIndexProperty> 。</span><span class="sxs-lookup"><span data-stu-id="a376b-106"><xref:System.Windows.Controls.GridSplitter> controls can be hidden by other controls if you do not define them as the last elements in the <xref:System.Windows.Controls.Panel.Children%2A> collection or if you give other controls a higher <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span></span>  
  
 <span data-ttu-id="a376b-107">若要防止隐藏 <xref:System.Windows.Controls.GridSplitter> 控件，请执行以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="a376b-107">To prevent hidden <xref:System.Windows.Controls.GridSplitter> controls, do one of the following.</span></span>  
  
- <span data-ttu-id="a376b-108">请确保 <xref:System.Windows.Controls.GridSplitter> 控件是最后 <xref:System.Windows.Controls.Panel.Children%2A> 添加到中的 <xref:System.Windows.Controls.Grid> 。</span><span class="sxs-lookup"><span data-stu-id="a376b-108">Make sure that <xref:System.Windows.Controls.GridSplitter> controls are the last <xref:System.Windows.Controls.Panel.Children%2A> added to the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="a376b-109">下面的示例演示 <xref:System.Windows.Controls.GridSplitter> 作为的集合中的最后一个元素 <xref:System.Windows.Controls.Panel.Children%2A> <xref:System.Windows.Controls.Grid> 。</span><span class="sxs-lookup"><span data-stu-id="a376b-109">The following example shows the <xref:System.Windows.Controls.GridSplitter> as the last element in the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
- <span data-ttu-id="a376b-110">将 <xref:System.Windows.Controls.Panel.ZIndexProperty> 上的设置 <xref:System.Windows.Controls.GridSplitter> 为高于将隐藏它的控件。</span><span class="sxs-lookup"><span data-stu-id="a376b-110">Set the <xref:System.Windows.Controls.Panel.ZIndexProperty> on the <xref:System.Windows.Controls.GridSplitter> to be higher than a control that would otherwise hide it.</span></span> <span data-ttu-id="a376b-111">下面的示例为 <xref:System.Windows.Controls.GridSplitter> 控件提供的控件 <xref:System.Windows.Controls.Panel.ZIndexProperty> 比 <xref:System.Windows.Controls.Button> 控件高。</span><span class="sxs-lookup"><span data-stu-id="a376b-111">The following example gives the <xref:System.Windows.Controls.GridSplitter> control a higher <xref:System.Windows.Controls.Panel.ZIndexProperty> than the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
- <span data-ttu-id="a376b-112">设置控件上的边距（否则将隐藏）， <xref:System.Windows.Controls.GridSplitter> 以便 <xref:System.Windows.Controls.GridSplitter> 公开。</span><span class="sxs-lookup"><span data-stu-id="a376b-112">Set margins on the control that would otherwise hide the <xref:System.Windows.Controls.GridSplitter> so that the <xref:System.Windows.Controls.GridSplitter> is exposed.</span></span> <span data-ttu-id="a376b-113">下面的示例在控件上设置将以其他方式叠加并隐藏的边距 <xref:System.Windows.Controls.GridSplitter> 。</span><span class="sxs-lookup"><span data-stu-id="a376b-113">The following example sets margins on a control that would otherwise overlay and hide the <xref:System.Windows.Controls.GridSplitter>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a><span data-ttu-id="a376b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a376b-114">See also</span></span>

- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="a376b-115">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="a376b-115">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
