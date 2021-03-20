---
title: 路径标记语法
description: 了解可用于在 (WPF) Windows Presentation Foundation 中指定精简路径几何图形的强大且复杂的迷你语言。
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: 675354c3508b4a52ff05e6b810e0abe1c0a2c309
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668664"
---
# <a name="path-markup-syntax"></a><span data-ttu-id="5ef44-103">路径标记语法</span><span class="sxs-lookup"><span data-stu-id="5ef44-103">Path Markup Syntax</span></span>
<span data-ttu-id="5ef44-104">在 WPF 的 " [形状和基本绘图" 概述](shapes-and-basic-drawing-in-wpf-overview.md) 和 [几何概述](geometry-overview.md)中讨论了路径，不过，本主题详细介绍了可用于指定路径几何的强大且复杂的迷你语言（使用简洁地） [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-104">Paths are discussed in [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md) and the [Geometry Overview](geometry-overview.md), however, this topic describes in detail the powerful and complex mini-language you can use to specify path geometries more compactly using [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a><span data-ttu-id="5ef44-105">必备条件</span><span class="sxs-lookup"><span data-stu-id="5ef44-105">Prerequisites</span></span>  
 <span data-ttu-id="5ef44-106">若要了解本主题，应熟悉对象的基本功能 <xref:System.Windows.Media.Geometry> 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-106">To understand this topic, you should be familiar with the basic features of <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="5ef44-107">有关详细信息，请参阅 [几何概述](geometry-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5ef44-107">For more information, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="abouthisdocument"></a>
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a><span data-ttu-id="5ef44-108">StreamGeometry and PathFigureCollection Mini-Languages</span><span class="sxs-lookup"><span data-stu-id="5ef44-108">StreamGeometry and PathFigureCollection Mini-Languages</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="5ef44-109">提供两个提供用于描述几何路径的迷你语言的类： <xref:System.Windows.Media.StreamGeometry> 和 <xref:System.Windows.Media.PathFigureCollection> 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-109">provides two classes that provide mini-languages for describing geometric paths: <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.PathFigureCollection>.</span></span>  
  
- <span data-ttu-id="5ef44-110"><xref:System.Windows.Media.StreamGeometry>设置类型的属性（ <xref:System.Windows.Media.Geometry> 如 <xref:System.Windows.UIElement.Clip%2A> 属性） <xref:System.Windows.UIElement> 或 <xref:System.Windows.Shapes.Path.Data%2A> 元素的属性时，请使用迷你语言 <xref:System.Windows.Shapes.Path> 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-110">You use the <xref:System.Windows.Media.StreamGeometry> mini-language when setting a property of type <xref:System.Windows.Media.Geometry>, such as the <xref:System.Windows.UIElement.Clip%2A> property of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Shapes.Path.Data%2A> property of a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="5ef44-111">下面的示例使用特性语法创建 <xref:System.Windows.Media.StreamGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-111">The following example uses attribute syntax to create a <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
- <span data-ttu-id="5ef44-112"><xref:System.Windows.Media.PathFigureCollection>当设置的属性时，请使用迷你语言 <xref:System.Windows.Media.PathGeometry.Figures%2A> <xref:System.Windows.Media.PathGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-112">You use the <xref:System.Windows.Media.PathFigureCollection> mini-language when setting the <xref:System.Windows.Media.PathGeometry.Figures%2A> property of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="5ef44-113">下面的示例使用特性语法为创建 <xref:System.Windows.Media.PathFigureCollection> <xref:System.Windows.Media.PathGeometry> 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-113">The following example uses a attribute syntax to create a <xref:System.Windows.Media.PathFigureCollection> for a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 <span data-ttu-id="5ef44-114">从前面的示例中可以看出，两种微型语言非常相似。</span><span class="sxs-lookup"><span data-stu-id="5ef44-114">As you can see from the preceding examples, the two mini-languages are very similar.</span></span> <span data-ttu-id="5ef44-115">在可以使用的任何情况下，始终都可以使用， <xref:System.Windows.Media.PathGeometry> 因此， <xref:System.Windows.Media.StreamGeometry> 您应该使用哪一种？</span><span class="sxs-lookup"><span data-stu-id="5ef44-115">It's always possible to use a <xref:System.Windows.Media.PathGeometry> in any situation where you could use a <xref:System.Windows.Media.StreamGeometry>; so which one should you use?</span></span> <span data-ttu-id="5ef44-116">如果在 <xref:System.Windows.Media.StreamGeometry> 创建后不需要修改路径，则使用; <xref:System.Windows.Media.PathGeometry> 如果确实需要修改路径，请使用。</span><span class="sxs-lookup"><span data-stu-id="5ef44-116">Use a <xref:System.Windows.Media.StreamGeometry> when you don't need to modify the path after creating it; use a <xref:System.Windows.Media.PathGeometry> if you do need to modify the path.</span></span>  
  
 <span data-ttu-id="5ef44-117">有关和对象之间的差异的详细信息 <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> ，请参阅 [几何概述](geometry-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5ef44-117">For more information about the differences between <xref:System.Windows.Media.PathGeometry> and <xref:System.Windows.Media.StreamGeometry> objects, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
### <a name="a-note-about-white-space"></a><span data-ttu-id="5ef44-118">有关空格的注意事项</span><span class="sxs-lookup"><span data-stu-id="5ef44-118">A Note about White Space</span></span>  
 <span data-ttu-id="5ef44-119">为简洁起见，随后的语法部分中显示一个空格，但在显示一个空格的地方，多个空格也可以接受。</span><span class="sxs-lookup"><span data-stu-id="5ef44-119">For brevity, a single space is shown in the syntax sections that follow, but multiple spaces are also acceptable wherever a single space is shown.</span></span>  
  
 <span data-ttu-id="5ef44-120">不一定要用逗号或空格来分隔两个数字，但这种情况只能在生成的字符串明确时执行。</span><span class="sxs-lookup"><span data-stu-id="5ef44-120">Two numbers don’t actually have to be separated by a comma or white space, but this can only be done when the resulting string is unambiguous.</span></span> <span data-ttu-id="5ef44-121">例如， `2..3` 实际上是两个数字： "2"。</span><span class="sxs-lookup"><span data-stu-id="5ef44-121">For instance, `2..3` is actually two numbers: "2."</span></span> <span data-ttu-id="5ef44-122">和“.3”。</span><span class="sxs-lookup"><span data-stu-id="5ef44-122">And ".3".</span></span> <span data-ttu-id="5ef44-123">同样， `2-3` 为 "2" 和 "-3"。</span><span class="sxs-lookup"><span data-stu-id="5ef44-123">Similarly, `2-3` is "2" and "-3".</span></span> <span data-ttu-id="5ef44-124">命令前面或后面也无需加空格。</span><span class="sxs-lookup"><span data-stu-id="5ef44-124">Spaces are not required before or after commands, either.</span></span>  
  
### <a name="syntax"></a><span data-ttu-id="5ef44-125">语法</span><span class="sxs-lookup"><span data-stu-id="5ef44-125">Syntax</span></span>  
 <span data-ttu-id="5ef44-126">[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)]的特性用法语法由一个 <xref:System.Windows.Media.StreamGeometry> 可选 <xref:System.Windows.Media.FillRule> 值和一个或多个图形说明组成。</span><span class="sxs-lookup"><span data-stu-id="5ef44-126">The [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.StreamGeometry> is composed of an optional <xref:System.Windows.Media.FillRule> value and one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="5ef44-127">StreamGeometry XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="5ef44-127">StreamGeometry XAML Attribute Usage</span></span>|  
|-----------------------------------------|  
|<span data-ttu-id="5ef44-128">`<`*object* *属性* `="` [ `fillRule` ] `figureDescription` [ `figureDescription` ] \*`" ... />`</span><span class="sxs-lookup"><span data-stu-id="5ef44-128">`<` *object* *property* `="`[ `fillRule`] `figureDescription`[ `figureDescription`]\* `" ... />`</span></span>|  
  
 <span data-ttu-id="5ef44-129">[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)]的特性用法语法 <xref:System.Windows.Media.PathFigureCollection> 由一个或多个图形说明组成。</span><span class="sxs-lookup"><span data-stu-id="5ef44-129">The [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.PathFigureCollection> is composed of one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="5ef44-130">PathFigureCollection XAML Attribute Usage</span><span class="sxs-lookup"><span data-stu-id="5ef44-130">PathFigureCollection XAML Attribute Usage</span></span>|  
|-----------------------------------------------|  
|<span data-ttu-id="5ef44-131">`<`*object* *属性* `="` `figureDescription` [ `figureDescription` ] \*`" ... />`</span><span class="sxs-lookup"><span data-stu-id="5ef44-131">`<` *object* *property* `="` `figureDescription`[ `figureDescription`]\* `" ... />`</span></span>|  
  
|<span data-ttu-id="5ef44-132">术语</span><span class="sxs-lookup"><span data-stu-id="5ef44-132">Term</span></span>|<span data-ttu-id="5ef44-133">说明</span><span class="sxs-lookup"><span data-stu-id="5ef44-133">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5ef44-134">*fillRule*</span><span class="sxs-lookup"><span data-stu-id="5ef44-134">*fillRule*</span></span>|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-135">指定是否 <xref:System.Windows.Media.StreamGeometry> 使用 <xref:System.Windows.Media.FillRule.EvenOdd> 或 <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-135">Specifies whether the <xref:System.Windows.Media.StreamGeometry> uses the <xref:System.Windows.Media.FillRule.EvenOdd> or <xref:System.Windows.Media.FillRule.Nonzero><xref:System.Windows.Media.PathGeometry.FillRule%2A>.</span></span><br /><br /> <span data-ttu-id="5ef44-136">-   `F0` 指定 <xref:System.Windows.Media.FillRule.EvenOdd> 填充规则。</span><span class="sxs-lookup"><span data-stu-id="5ef44-136">-   `F0` specifies the <xref:System.Windows.Media.FillRule.EvenOdd> fill rule.</span></span><br /><span data-ttu-id="5ef44-137">-   `F1` 指定 <xref:System.Windows.Media.FillRule.Nonzero> 填充规则。</span><span class="sxs-lookup"><span data-stu-id="5ef44-137">-   `F1` specifies the <xref:System.Windows.Media.FillRule.Nonzero> fill rule.</span></span><br /><br /> <span data-ttu-id="5ef44-138">如果省略此命令，则子路径将使用默认行为，即 <xref:System.Windows.Media.FillRule.EvenOdd> 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-138">If you omit this command, the subpath uses the default behavior, which is <xref:System.Windows.Media.FillRule.EvenOdd>.</span></span> <span data-ttu-id="5ef44-139">如果指定该命令，须先设置命令。</span><span class="sxs-lookup"><span data-stu-id="5ef44-139">If you specify this command, you must place it first.</span></span>|  
|<span data-ttu-id="5ef44-140">*figureDescription*</span><span class="sxs-lookup"><span data-stu-id="5ef44-140">*figureDescription*</span></span>|<span data-ttu-id="5ef44-141">图形由一个移动命令，绘制命令和一个可选的关闭命令组成。</span><span class="sxs-lookup"><span data-stu-id="5ef44-141">A figure composed of a move command, draw commands, and an optional close command.</span></span><br /><br /> <span data-ttu-id="5ef44-142">`moveCommand` `drawCommands`  `[` `closeCommand` `]`</span><span class="sxs-lookup"><span data-stu-id="5ef44-142">`moveCommand` `drawCommands`  `[` `closeCommand` `]`</span></span>|  
|<span data-ttu-id="5ef44-143">*moveCommand*</span><span class="sxs-lookup"><span data-stu-id="5ef44-143">*moveCommand*</span></span>|<span data-ttu-id="5ef44-144">用于指定图形起点的移动命令。</span><span class="sxs-lookup"><span data-stu-id="5ef44-144">A move command that specifies the start point of the figure.</span></span> <span data-ttu-id="5ef44-145">请参阅 [移动命令](#themovecommand) 部分。</span><span class="sxs-lookup"><span data-stu-id="5ef44-145">See the [Move Command](#themovecommand) section.</span></span>|  
|<span data-ttu-id="5ef44-146">*drawCommands*</span><span class="sxs-lookup"><span data-stu-id="5ef44-146">*drawCommands*</span></span>|<span data-ttu-id="5ef44-147">用于描述图形内容的一个或多个绘图命令。</span><span class="sxs-lookup"><span data-stu-id="5ef44-147">One or more drawing commands that describe the figure's contents.</span></span> <span data-ttu-id="5ef44-148">请参阅 [绘图命令](#drawcommands) 部分。</span><span class="sxs-lookup"><span data-stu-id="5ef44-148">See the [Draw Commands](#drawcommands) section.</span></span>|  
|<span data-ttu-id="5ef44-149">*closeCommand*</span><span class="sxs-lookup"><span data-stu-id="5ef44-149">*closeCommand*</span></span>|<span data-ttu-id="5ef44-150">用于关闭图形的可选关闭命令。</span><span class="sxs-lookup"><span data-stu-id="5ef44-150">An optional close command that closes figure.</span></span> <span data-ttu-id="5ef44-151">请参阅 [关闭命令](#closecommand) 部分。</span><span class="sxs-lookup"><span data-stu-id="5ef44-151">See the [Close Command](#closecommand) section.</span></span>|  
  
<a name="themovecommand"></a>
## <a name="move-command"></a><span data-ttu-id="5ef44-152">移动命令</span><span class="sxs-lookup"><span data-stu-id="5ef44-152">Move Command</span></span>  
 <span data-ttu-id="5ef44-153">指定新图形的起点。</span><span class="sxs-lookup"><span data-stu-id="5ef44-153">Specifies the start point of a new figure.</span></span>  
  
|<span data-ttu-id="5ef44-154">语法</span><span class="sxs-lookup"><span data-stu-id="5ef44-154">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="5ef44-155">`M`*startPoint*</span><span class="sxs-lookup"><span data-stu-id="5ef44-155">`M` *startPoint*</span></span><br /><br /> <span data-ttu-id="5ef44-156">- 或 -</span><span class="sxs-lookup"><span data-stu-id="5ef44-156">- or -</span></span><br /><br /> <span data-ttu-id="5ef44-157">`m`*startPoint*</span><span class="sxs-lookup"><span data-stu-id="5ef44-157">`m` *startPoint*</span></span>|  
  
|<span data-ttu-id="5ef44-158">术语</span><span class="sxs-lookup"><span data-stu-id="5ef44-158">Term</span></span>|<span data-ttu-id="5ef44-159">说明</span><span class="sxs-lookup"><span data-stu-id="5ef44-159">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5ef44-160">*startPoint*</span><span class="sxs-lookup"><span data-stu-id="5ef44-160">*startPoint*</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-161">新图形的起点。</span><span class="sxs-lookup"><span data-stu-id="5ef44-161">The start point of a new figure.</span></span>|  
  
 <span data-ttu-id="5ef44-162">大写字母 `M` 指示 `startPoint` 是绝对值; 如果不存在，则为小写， `m` 表示与前一个点的 `startPoint` 偏移量，或 (0，0) 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-162">An uppercase `M` indicates that `startPoint` is an absolute value; a lowercase `m` indicates that `startPoint` is an offset to the previous point, or (0,0) if none exists.</span></span> <span data-ttu-id="5ef44-163">如果在移动命令之后列出多个点，可以绘制一条连接到这些点的直线，尽管已指定了直线命令。</span><span class="sxs-lookup"><span data-stu-id="5ef44-163">If you list multiple points after the move command, a line is drawn to those points though you specified the line command.</span></span>  
  
<a name="drawcommands"></a>
## <a name="draw-commands"></a><span data-ttu-id="5ef44-164">绘制命令</span><span class="sxs-lookup"><span data-stu-id="5ef44-164">Draw Commands</span></span>  
 <span data-ttu-id="5ef44-165">绘制命令可以由几个形状命令组成。</span><span class="sxs-lookup"><span data-stu-id="5ef44-165">A draw command can consist of several shape commands.</span></span> <span data-ttu-id="5ef44-166">以下形状命令可用：直线、水平线、竖线、三次贝塞尔曲线、二次贝塞尔曲线、平滑三次贝塞尔曲线、平滑二次贝塞尔曲线和椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="5ef44-166">The following shape commands are available: line, horizontal line, vertical line, cubic Bezier curve, quadratic Bezier curve, smooth cubic Bezier curve, smooth quadratic Bezier curve, and elliptical arc.</span></span>  
  
 <span data-ttu-id="5ef44-167">可以使用大写或小写字母输入每个命令：大写字母表示绝对值，小写字母表示相对值：该线段的控制点相对于前面示例的终点。</span><span class="sxs-lookup"><span data-stu-id="5ef44-167">You enter each command by using either an uppercase or a lowercase letter: uppercase letters denote absolute values and lowercase letters denote relative values: the control points for that segment are relative to the end point of the preceding example.</span></span> <span data-ttu-id="5ef44-168">如果按顺序输入同一类型的多个命令，则可以忽略重复的命令条目;例如， `L 100,200 300,400` 等效于 `L 100,200 L 300,400` 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-168">When sequentially entering more than one command of the same type, you can omit the duplicate command entry; for example, `L 100,200 300,400` is equivalent to `L 100,200 L 300,400`.</span></span> <span data-ttu-id="5ef44-169">下表描述了 **移动** 和 **绘制** 命令。</span><span class="sxs-lookup"><span data-stu-id="5ef44-169">The following table describes the **move** and **draw** commands.</span></span>  
  
### <a name="line-command"></a><span data-ttu-id="5ef44-170">直线命令</span><span class="sxs-lookup"><span data-stu-id="5ef44-170">Line Command</span></span>  
 <span data-ttu-id="5ef44-171">在当前点和指定的终点之间创建一条直线。</span><span class="sxs-lookup"><span data-stu-id="5ef44-171">Creates a straight line between the current point and the specified end point.</span></span> <span data-ttu-id="5ef44-172">`l 20 30` 和 `L 20,30` 是有效 **行** 命令的示例。</span><span class="sxs-lookup"><span data-stu-id="5ef44-172">`l 20 30` and `L 20,30` are examples of valid **line** commands.</span></span>  
  
|<span data-ttu-id="5ef44-173">语法</span><span class="sxs-lookup"><span data-stu-id="5ef44-173">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="5ef44-174">`L`*终结点*</span><span class="sxs-lookup"><span data-stu-id="5ef44-174">`L` *endPoint*</span></span><br /><br /> <span data-ttu-id="5ef44-175">- 或 -</span><span class="sxs-lookup"><span data-stu-id="5ef44-175">- or -</span></span><br /><br /> <span data-ttu-id="5ef44-176">`l`*终结点*</span><span class="sxs-lookup"><span data-stu-id="5ef44-176">`l` *endPoint*</span></span>|  
  
|<span data-ttu-id="5ef44-177">术语</span><span class="sxs-lookup"><span data-stu-id="5ef44-177">Term</span></span>|<span data-ttu-id="5ef44-178">说明</span><span class="sxs-lookup"><span data-stu-id="5ef44-178">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5ef44-179">*终结点*</span><span class="sxs-lookup"><span data-stu-id="5ef44-179">*endPoint*</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-180">线条的终点。</span><span class="sxs-lookup"><span data-stu-id="5ef44-180">The end point of the line.</span></span>|  

<span data-ttu-id="5ef44-181">大写字母 `L` 指示 `endPoint` 是绝对值; 如果不存在，则为小写， `l` 表示与前一个点的 `endPoint` 偏移量，或 (0，0) 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-181">An uppercase `L` indicates that `endPoint` is an absolute value; a lowercase `l` indicates that `endPoint` is an offset to the previous point, or (0,0) if none exists.</span></span>

### <a name="horizontal-line-command"></a><span data-ttu-id="5ef44-182">水平线命令</span><span class="sxs-lookup"><span data-stu-id="5ef44-182">Horizontal Line Command</span></span>  
 <span data-ttu-id="5ef44-183">在当前点和指定的 x 坐标之间创建一条水平线。</span><span class="sxs-lookup"><span data-stu-id="5ef44-183">Creates a horizontal line between the current point and the specified x-coordinate.</span></span> <span data-ttu-id="5ef44-184">`H 90` 是有效水平线命令的示例。</span><span class="sxs-lookup"><span data-stu-id="5ef44-184">`H 90` is an example of a valid horizontal line command.</span></span>

|<span data-ttu-id="5ef44-185">语法</span><span class="sxs-lookup"><span data-stu-id="5ef44-185">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="5ef44-186">`H`  *x*</span><span class="sxs-lookup"><span data-stu-id="5ef44-186">`H`  *x*</span></span><br /><br /> <span data-ttu-id="5ef44-187">- 或 -</span><span class="sxs-lookup"><span data-stu-id="5ef44-187">- or -</span></span><br /><br /> <span data-ttu-id="5ef44-188">`h`  *x-blade*</span><span class="sxs-lookup"><span data-stu-id="5ef44-188">`h`  *x*</span></span>|  
  
|<span data-ttu-id="5ef44-189">术语</span><span class="sxs-lookup"><span data-stu-id="5ef44-189">Term</span></span>|<span data-ttu-id="5ef44-190">说明</span><span class="sxs-lookup"><span data-stu-id="5ef44-190">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5ef44-191">*x*</span><span class="sxs-lookup"><span data-stu-id="5ef44-191">*x*</span></span>|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-192">线条终点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="5ef44-192">The x-coordinate of the end point of the line.</span></span>|  
  
<span data-ttu-id="5ef44-193">大写字母 `H` 指示 `x` 是绝对值; 如果不存在，则为小写， `h` 表示与前一个点的 `x` 偏移量，或 (0，0) 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-193">An uppercase `H` indicates that `x` is an absolute value; a lowercase `h` indicates that `x` is an offset to the previous point, or (0,0) if none exists.</span></span>
  
### <a name="vertical-line-command"></a><span data-ttu-id="5ef44-194">竖线命令</span><span class="sxs-lookup"><span data-stu-id="5ef44-194">Vertical Line Command</span></span>  
 <span data-ttu-id="5ef44-195">在当前点和指定的 y 坐标之间创建一条竖线。</span><span class="sxs-lookup"><span data-stu-id="5ef44-195">Creates a vertical line between the current point and the specified y-coordinate.</span></span> <span data-ttu-id="5ef44-196">`v 90` 是有效竖线命令的示例。</span><span class="sxs-lookup"><span data-stu-id="5ef44-196">`v 90` is an example of a valid vertical line command.</span></span>

|<span data-ttu-id="5ef44-197">语法</span><span class="sxs-lookup"><span data-stu-id="5ef44-197">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="5ef44-198">`V`  *y*</span><span class="sxs-lookup"><span data-stu-id="5ef44-198">`V`  *y*</span></span><br /><br /> <span data-ttu-id="5ef44-199">- 或 -</span><span class="sxs-lookup"><span data-stu-id="5ef44-199">- or -</span></span><br /><br /> <span data-ttu-id="5ef44-200">`v`  *y*</span><span class="sxs-lookup"><span data-stu-id="5ef44-200">`v`  *y*</span></span>|  
  
|<span data-ttu-id="5ef44-201">术语</span><span class="sxs-lookup"><span data-stu-id="5ef44-201">Term</span></span>|<span data-ttu-id="5ef44-202">说明</span><span class="sxs-lookup"><span data-stu-id="5ef44-202">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5ef44-203">*y*</span><span class="sxs-lookup"><span data-stu-id="5ef44-203">*y*</span></span>|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-204">直线终点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="5ef44-204">The y-coordinate of the end point of the line.</span></span>|  

<span data-ttu-id="5ef44-205">大写字母 `V` 指示 `y` 是绝对值; 如果不存在，则为小写， `v` 表示与前一个点的 `y` 偏移量，或 (0，0) 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-205">An uppercase `V` indicates that `y` is an absolute value; a lowercase `v` indicates that `y` is an offset to the previous point, or (0,0) if none exists.</span></span>  

### <a name="cubic-bezier-curve-command"></a><span data-ttu-id="5ef44-206">三次贝塞尔曲线命令</span><span class="sxs-lookup"><span data-stu-id="5ef44-206">Cubic Bezier Curve Command</span></span>  
 <span data-ttu-id="5ef44-207">使用两个指定控制点 (`controlPoint` 1 和 2) 在当前点和指定的终点之间创建三次方贝塞尔曲线 `controlPoint` 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-207">Creates a cubic Bezier curve between the current point and the specified end point by using the two specified control points (`controlPoint`1 and `controlPoint`2).</span></span> <span data-ttu-id="5ef44-208">`C 100,200 200,400 300,200` 是有效曲线命令的示例。</span><span class="sxs-lookup"><span data-stu-id="5ef44-208">`C 100,200 200,400 300,200` is an example of a valid curve command.</span></span>  
  
|<span data-ttu-id="5ef44-209">语法</span><span class="sxs-lookup"><span data-stu-id="5ef44-209">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="5ef44-210">`C``controlPoint`1 `controlPoint` 2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="5ef44-210">`C` `controlPoint`1`controlPoint`2`endPoint`</span></span><br /><br /> <span data-ttu-id="5ef44-211">- 或 -</span><span class="sxs-lookup"><span data-stu-id="5ef44-211">- or -</span></span><br /><br /> <span data-ttu-id="5ef44-212">`c``controlPoint`1 `controlPoint` 2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="5ef44-212">`c` `controlPoint`1`controlPoint`2`endPoint`</span></span>|  
  
|<span data-ttu-id="5ef44-213">术语</span><span class="sxs-lookup"><span data-stu-id="5ef44-213">Term</span></span>|<span data-ttu-id="5ef44-214">说明</span><span class="sxs-lookup"><span data-stu-id="5ef44-214">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5ef44-215">`controlPoint`1</span><span class="sxs-lookup"><span data-stu-id="5ef44-215">`controlPoint`1</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-216">曲线的第一个控制点，它决定曲线的起始切线。</span><span class="sxs-lookup"><span data-stu-id="5ef44-216">The first control point of the curve, which determines the starting tangent of the curve.</span></span>|  
|<span data-ttu-id="5ef44-217">`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="5ef44-217">`controlPoint`2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-218">曲线的第二个控制点，它决定曲线的结束切线。</span><span class="sxs-lookup"><span data-stu-id="5ef44-218">The second control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-219">绘制曲线将通过的点。</span><span class="sxs-lookup"><span data-stu-id="5ef44-219">The point to which the curve is drawn.</span></span>|  
  
### <a name="quadratic-bezier-curve-command"></a><span data-ttu-id="5ef44-220">二次贝塞尔曲线命令</span><span class="sxs-lookup"><span data-stu-id="5ef44-220">Quadratic Bezier Curve Command</span></span>  
 <span data-ttu-id="5ef44-221">使用指定的控制点 () 在当前点和指定的终点之间创建二次贝塞尔曲线 `controlPoint` 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-221">Creates a quadratic Bezier curve between the current point and the specified end point by using the specified control point (`controlPoint`).</span></span> <span data-ttu-id="5ef44-222">`q 100,200 300,200` 为有效二次贝塞尔曲线命令的示例。</span><span class="sxs-lookup"><span data-stu-id="5ef44-222">`q 100,200 300,200` is an example of a valid quadratic Bezier curve command.</span></span>  
  
|<span data-ttu-id="5ef44-223">语法</span><span class="sxs-lookup"><span data-stu-id="5ef44-223">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="5ef44-224">`Q` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="5ef44-224">`Q` `controlPoint` `endPoint`</span></span><br /><br /> <span data-ttu-id="5ef44-225">- 或 -</span><span class="sxs-lookup"><span data-stu-id="5ef44-225">- or -</span></span><br /><br /> <span data-ttu-id="5ef44-226">`q` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="5ef44-226">`q` `controlPoint` `endPoint`</span></span>|  
  
|<span data-ttu-id="5ef44-227">术语</span><span class="sxs-lookup"><span data-stu-id="5ef44-227">Term</span></span>|<span data-ttu-id="5ef44-228">说明</span><span class="sxs-lookup"><span data-stu-id="5ef44-228">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-229">曲线的控制点，它决定曲线的开始和结束切线。</span><span class="sxs-lookup"><span data-stu-id="5ef44-229">The control point of the curve, which determines the starting and ending tangents of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-230">绘制曲线将通过的点。</span><span class="sxs-lookup"><span data-stu-id="5ef44-230">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-cubic-bezier-curve-command"></a><span data-ttu-id="5ef44-231">平滑三次贝塞尔曲线命令</span><span class="sxs-lookup"><span data-stu-id="5ef44-231">Smooth cubic Bezier curve Command</span></span>  
 <span data-ttu-id="5ef44-232">在当前点和指定的终点之间创建三次贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="5ef44-232">Creates a cubic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="5ef44-233">假设第一控制点为相对当前点前一命令的第二控制点的反射。</span><span class="sxs-lookup"><span data-stu-id="5ef44-233">The first control point is assumed to be the reflection of the second control point of the previous command relative to the current point.</span></span> <span data-ttu-id="5ef44-234">如果没有前一命令或如果前一命令不是三次贝塞尔曲线命令或平滑三次贝塞尔曲线命令，则假设第一个控制点与当前点重合。</span><span class="sxs-lookup"><span data-stu-id="5ef44-234">If there is no previous command or if the previous command was not a cubic Bezier curve command or a smooth cubic Bezier curve command, assume the first control point is coincident with the current point.</span></span> <span data-ttu-id="5ef44-235">第二个控制点是曲线结束点的控制点，由 `controlPoint` 2 指定。</span><span class="sxs-lookup"><span data-stu-id="5ef44-235">The second control point, the control point for the end of the curve, is specified by `controlPoint`2.</span></span> <span data-ttu-id="5ef44-236">例如， `S 100,200 200,300` 是有效的平滑三次贝塞尔曲线命令。</span><span class="sxs-lookup"><span data-stu-id="5ef44-236">For example, `S 100,200 200,300` is a valid smooth cubic Bezier curve command.</span></span>  
  
|<span data-ttu-id="5ef44-237">语法</span><span class="sxs-lookup"><span data-stu-id="5ef44-237">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="5ef44-238">`S``controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="5ef44-238">`S` `controlPoint`2`endPoint`</span></span><br /><br /> <span data-ttu-id="5ef44-239">- 或 -</span><span class="sxs-lookup"><span data-stu-id="5ef44-239">- or -</span></span><br /><br /> <span data-ttu-id="5ef44-240">`s``controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="5ef44-240">`s` `controlPoint`2`endPoint`</span></span>|  
  
|<span data-ttu-id="5ef44-241">术语</span><span class="sxs-lookup"><span data-stu-id="5ef44-241">Term</span></span>|<span data-ttu-id="5ef44-242">说明</span><span class="sxs-lookup"><span data-stu-id="5ef44-242">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5ef44-243">`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="5ef44-243">`controlPoint`2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-244">曲线的控制点，它决定曲线的结束切线。</span><span class="sxs-lookup"><span data-stu-id="5ef44-244">The control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-245">绘制曲线将通过的点。</span><span class="sxs-lookup"><span data-stu-id="5ef44-245">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a><span data-ttu-id="5ef44-246">平滑二次贝塞尔曲线命令</span><span class="sxs-lookup"><span data-stu-id="5ef44-246">Smooth quadratic Bezier curve Command</span></span>  
 <span data-ttu-id="5ef44-247">在当前点和指定的终点之间创建二次贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="5ef44-247">Creates a quadratic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="5ef44-248">假设控制点为相对于当前点前一命令的控制点的反射。</span><span class="sxs-lookup"><span data-stu-id="5ef44-248">The control point is assumed to be the reflection of the control point of the previous command relative to the current point.</span></span> <span data-ttu-id="5ef44-249">如果没有前一命令或如果前一命令不是二次贝塞尔曲线命令或平滑二次贝塞尔曲线命令，则控制点与当前点重合。</span><span class="sxs-lookup"><span data-stu-id="5ef44-249">If there is no previous command or if the previous command was not a quadratic Bezier curve command or a smooth quadratic Bezier curve command, the control point is coincident with the current point.</span></span>  
  
|<span data-ttu-id="5ef44-250">语法</span><span class="sxs-lookup"><span data-stu-id="5ef44-250">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="5ef44-251">`T` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="5ef44-251">`T` `controlPoint` `endPoint`</span></span><br /><br /> <span data-ttu-id="5ef44-252">- 或 -</span><span class="sxs-lookup"><span data-stu-id="5ef44-252">- or -</span></span><br /><br /> <span data-ttu-id="5ef44-253">`t` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="5ef44-253">`t` `controlPoint` `endPoint`</span></span>|  
  
|<span data-ttu-id="5ef44-254">术语</span><span class="sxs-lookup"><span data-stu-id="5ef44-254">Term</span></span>|<span data-ttu-id="5ef44-255">说明</span><span class="sxs-lookup"><span data-stu-id="5ef44-255">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-256">曲线的控制点，决定曲线的起点和曲线的切线。</span><span class="sxs-lookup"><span data-stu-id="5ef44-256">The control point of the curve, which determines the starting and tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-257">绘制曲线将通过的点。</span><span class="sxs-lookup"><span data-stu-id="5ef44-257">The point to which the curve is drawn.</span></span>|  
  
### <a name="elliptical-arc-command"></a><span data-ttu-id="5ef44-258">椭圆弧命令</span><span class="sxs-lookup"><span data-stu-id="5ef44-258">Elliptical Arc Command</span></span>  
 <span data-ttu-id="5ef44-259">在当前点和指定的终点之间创建一个椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="5ef44-259">Creates an elliptical arc between the current point and the specified end point.</span></span>  
  
|<span data-ttu-id="5ef44-260">语法</span><span class="sxs-lookup"><span data-stu-id="5ef44-260">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="5ef44-261">`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="5ef44-261">`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span></span><br /><br /> <span data-ttu-id="5ef44-262">- 或 -</span><span class="sxs-lookup"><span data-stu-id="5ef44-262">- or -</span></span><br /><br /> <span data-ttu-id="5ef44-263">`a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="5ef44-263">`a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span></span>|  
  
|<span data-ttu-id="5ef44-264">术语</span><span class="sxs-lookup"><span data-stu-id="5ef44-264">Term</span></span>|<span data-ttu-id="5ef44-265">说明</span><span class="sxs-lookup"><span data-stu-id="5ef44-265">Description</span></span>|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-266">圆弧的 x 轴和 y 轴半径。</span><span class="sxs-lookup"><span data-stu-id="5ef44-266">The x- and y-radius of the arc.</span></span>|  
|`rotationAngle`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-267">椭圆的旋转，以度为单位。</span><span class="sxs-lookup"><span data-stu-id="5ef44-267">The rotation of the ellipse, in degrees.</span></span>|  
|`isLargeArcFlag`|<span data-ttu-id="5ef44-268">如果圆弧角度应为 180 度或更大，请设置为 1，否则设置为 0。</span><span class="sxs-lookup"><span data-stu-id="5ef44-268">Set to 1 if the angle of the arc should be 180 degrees or greater; otherwise, set to 0.</span></span>|  
|`sweepDirectionFlag`|<span data-ttu-id="5ef44-269">如果以正角方向绘制圆弧，请设置为 1；否则设置为 0。</span><span class="sxs-lookup"><span data-stu-id="5ef44-269">Set to 1 if the arc is drawn in a positive-angle direction; otherwise, set to 0.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-270">绘制弧将通过的点。</span><span class="sxs-lookup"><span data-stu-id="5ef44-270">The point to which the arc is drawn.</span></span>|  
  
<a name="closecommand"></a>
## <a name="the-close-command"></a><span data-ttu-id="5ef44-271">关闭命令</span><span class="sxs-lookup"><span data-stu-id="5ef44-271">The Close Command</span></span>  
 <span data-ttu-id="5ef44-272">结束当前图形，并创建一条将当前点连接到图形起点的直线。</span><span class="sxs-lookup"><span data-stu-id="5ef44-272">Ends the current figure and creates a line that connects the current point to the starting point of the figure.</span></span> <span data-ttu-id="5ef44-273">此命令可以在图形最后一段与第一段之间创建一条连接线（角）。</span><span class="sxs-lookup"><span data-stu-id="5ef44-273">This command creates a line-join (corner) between the last segment and the first segment of the figure.</span></span>  
  
|<span data-ttu-id="5ef44-274">语法</span><span class="sxs-lookup"><span data-stu-id="5ef44-274">Syntax</span></span>|  
|------------|  
|`Z`<br /><br /> <span data-ttu-id="5ef44-275">- 或 -</span><span class="sxs-lookup"><span data-stu-id="5ef44-275">- or -</span></span><br /><br /> `z`|  

<a name="pointsyntax"></a>
## <a name="point-syntax"></a><span data-ttu-id="5ef44-276">点语法</span><span class="sxs-lookup"><span data-stu-id="5ef44-276">Point Syntax</span></span>  
 <span data-ttu-id="5ef44-277">描述 (0，0) 为左上角的点的 x 和 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="5ef44-277">Describes the x- and y-coordinates of a point where (0,0) is the top left corner.</span></span>
  
|<span data-ttu-id="5ef44-278">语法</span><span class="sxs-lookup"><span data-stu-id="5ef44-278">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="5ef44-279">`x` `,` `y`</span><span class="sxs-lookup"><span data-stu-id="5ef44-279">`x` `,` `y`</span></span><br /><br /> <span data-ttu-id="5ef44-280">- 或 -</span><span class="sxs-lookup"><span data-stu-id="5ef44-280">- or -</span></span><br /><br /> <span data-ttu-id="5ef44-281">`x` `y`</span><span class="sxs-lookup"><span data-stu-id="5ef44-281">`x` `y`</span></span>|  
  
|<span data-ttu-id="5ef44-282">术语</span><span class="sxs-lookup"><span data-stu-id="5ef44-282">Term</span></span>|<span data-ttu-id="5ef44-283">说明</span><span class="sxs-lookup"><span data-stu-id="5ef44-283">Description</span></span>|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-284">该点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="5ef44-284">The x-coordinate of the point.</span></span>|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="5ef44-285">该点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="5ef44-285">The y-coordinate of the point.</span></span>|  
  
<a name="specialvalues"></a>
## <a name="special-values"></a><span data-ttu-id="5ef44-286">特殊值</span><span class="sxs-lookup"><span data-stu-id="5ef44-286">Special Values</span></span>  
 <span data-ttu-id="5ef44-287">除了标准数值外，还可使用以下特殊值。</span><span class="sxs-lookup"><span data-stu-id="5ef44-287">Instead of a standard numerical value, you can also use the following special values.</span></span> <span data-ttu-id="5ef44-288">这些值区分大小写。</span><span class="sxs-lookup"><span data-stu-id="5ef44-288">These values are case-sensitive.</span></span>  
  
 <span data-ttu-id="5ef44-289">无限</span><span class="sxs-lookup"><span data-stu-id="5ef44-289">Infinity</span></span>  
 <span data-ttu-id="5ef44-290">表示 <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-290">Represents <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="5ef44-291">-Infinity</span><span class="sxs-lookup"><span data-stu-id="5ef44-291">-Infinity</span></span>  
 <span data-ttu-id="5ef44-292">表示 <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-292">Represents <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="5ef44-293">NaN</span><span class="sxs-lookup"><span data-stu-id="5ef44-293">NaN</span></span>  
 <span data-ttu-id="5ef44-294">表示 <xref:System.Double.NaN?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="5ef44-294">Represents <xref:System.Double.NaN?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="5ef44-295">也可使用科学计数法。</span><span class="sxs-lookup"><span data-stu-id="5ef44-295">You may also use scientific notation.</span></span> <span data-ttu-id="5ef44-296">例如，`+1.e17` 是有效值。</span><span class="sxs-lookup"><span data-stu-id="5ef44-296">For example, `+1.e17` is a valid value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ef44-297">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ef44-297">See also</span></span>

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [<span data-ttu-id="5ef44-298">WPF 中的形状和基本图形概述</span><span class="sxs-lookup"><span data-stu-id="5ef44-298">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="5ef44-299">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="5ef44-299">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="5ef44-300">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="5ef44-300">How-to Topics</span></span>](geometries-how-to-topics.md)
