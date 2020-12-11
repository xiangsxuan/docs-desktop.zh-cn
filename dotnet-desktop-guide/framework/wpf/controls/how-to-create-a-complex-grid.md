---
title: 如何创建复杂网格
description: 示例演示如何使用网格控件创建外观类似于月历的布局。
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: ab5490d608b21fe8b29a078dc1f0147f038c27a3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973979"
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="fb301-103">如何创建复杂网格</span><span class="sxs-lookup"><span data-stu-id="fb301-103">How to create a complex Grid</span></span>

<span data-ttu-id="fb301-104">此示例演示如何使用 <xref:System.Windows.Controls.Grid> 控件创建外观类似于月历的布局。</span><span class="sxs-lookup"><span data-stu-id="fb301-104">This example shows how to use a <xref:System.Windows.Controls.Grid> control to create a layout that looks like a monthly calendar.</span></span>

## <a name="example"></a><span data-ttu-id="fb301-105">示例</span><span class="sxs-lookup"><span data-stu-id="fb301-105">Example</span></span>

<span data-ttu-id="fb301-106">下面的示例使用和类定义八个行和八个列 <xref:System.Windows.Controls.RowDefinition> <xref:System.Windows.Controls.ColumnDefinition> 。</span><span class="sxs-lookup"><span data-stu-id="fb301-106">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="fb301-107">它将 <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> 附加属性与元素一起使用， <xref:System.Windows.Shapes.Rectangle> 这些元素填充各种列和行的背景。</span><span class="sxs-lookup"><span data-stu-id="fb301-107">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="fb301-108">这种设计之所以可行，是因为中的每个单元都可以存在多个元素 <xref:System.Windows.Controls.Grid> ，这是与之间的一个主要区别 <xref:System.Windows.Controls.Grid> <xref:System.Windows.Documents.Table> 。</span><span class="sxs-lookup"><span data-stu-id="fb301-108">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>

<span data-ttu-id="fb301-109">该示例对列和行使用垂直渐变， <xref:System.Windows.Shapes.Shape.Fill%2A> 以改进日历的视觉对象表示和可读性。</span><span class="sxs-lookup"><span data-stu-id="fb301-109">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="fb301-110">带样式 <xref:System.Windows.Controls.TextBlock> 的元素表示一周中的日期和天数。</span><span class="sxs-lookup"><span data-stu-id="fb301-110">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="fb301-111"><xref:System.Windows.Controls.TextBlock> 元素通过使用在 <xref:System.Windows.FrameworkElement.Margin%2A> 应用程序的样式中定义的属性和对齐属性，在单元格中绝对定位。</span><span class="sxs-lookup"><span data-stu-id="fb301-111"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>

[!code-xaml[GridComplex#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]

<span data-ttu-id="fb301-112">下图显示了生成的控件，它是一个可自定义的日历：</span><span class="sxs-lookup"><span data-stu-id="fb301-112">The following image shows the resulting control, a customizable calendar:</span></span>

![生成的控件的屏幕截图](././media/how-to-create-a-complex-grid/wpf-manual-calendar.png)

## <a name="see-also"></a><span data-ttu-id="fb301-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb301-114">See also</span></span>

- <xref:System.Windows.Controls.Grid?displayProperty=nameWithType>
- <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>
- [<span data-ttu-id="fb301-115">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="fb301-115">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="fb301-116">面板概述</span><span class="sxs-lookup"><span data-stu-id="fb301-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="fb301-117">表概述</span><span class="sxs-lookup"><span data-stu-id="fb301-117">Table Overview</span></span>](../advanced/table-overview.md)
