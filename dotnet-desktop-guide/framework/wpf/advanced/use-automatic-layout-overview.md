---
title: 使用自动布局概述
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: 471deeb6cc19ff8d31caa7c1ea122b3f50754bec
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664062"
---
# <a name="use-automatic-layout-overview"></a><span data-ttu-id="2be2b-102">使用自动布局概述</span><span class="sxs-lookup"><span data-stu-id="2be2b-102">Use Automatic Layout Overview</span></span>

<span data-ttu-id="2be2b-103">本主题介绍了有关如何编写 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 具有可本地化的用户界面)  (ui 的应用程序的指南。</span><span class="sxs-lookup"><span data-stu-id="2be2b-103">This topic introduces guidelines for developers on how to write [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] applications with localizable user interfaces (UIs).</span></span> <span data-ttu-id="2be2b-104">过去，UI 的本地化是一个耗时的过程。</span><span class="sxs-lookup"><span data-stu-id="2be2b-104">In the past, localization of a UI was a time consuming process.</span></span> <span data-ttu-id="2be2b-105">UI 调整的每种语言都需要像素的像素调整。</span><span class="sxs-lookup"><span data-stu-id="2be2b-105">Each language that the UI was adapted for required a pixel by pixel adjustment.</span></span> <span data-ttu-id="2be2b-106">如今，使用正确的设计和右编码标准，可以构造 Ui，使本地化人员可以更少地调整大小和重新定位。</span><span class="sxs-lookup"><span data-stu-id="2be2b-106">Today with the right design and right coding standards, UIs can be constructed so that localizers have less resizing and repositioning to do.</span></span> <span data-ttu-id="2be2b-107">编写可以更方便地调整大小和重新定位的应用程序的方法称为自动布局，可以使用 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序设计实现此目的。</span><span class="sxs-lookup"><span data-stu-id="2be2b-107">The approach to writing applications that can be more easily resized and repositioned is called automatic layout, and can be achieved by using [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] application design.</span></span>

<a name="advantages_of_autolayout"></a>

## <a name="advantages-of-using-automatic-layout"></a><span data-ttu-id="2be2b-108">使用自动布局的优点</span><span class="sxs-lookup"><span data-stu-id="2be2b-108">Advantages of Using Automatic Layout</span></span>

<span data-ttu-id="2be2b-109">由于 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 呈现系统功能强大且灵活，因此它提供了在应用程序中布局元素的功能，可以根据不同语言的要求进行调整。</span><span class="sxs-lookup"><span data-stu-id="2be2b-109">Because the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] presentation system is powerful and flexible, it provides the ability to layout elements in an application that can be adjusted to fit the requirements of different languages.</span></span> <span data-ttu-id="2be2b-110">下面列出自动布局的部分优点。</span><span class="sxs-lookup"><span data-stu-id="2be2b-110">The following list points out some of the advantages of automatic layout.</span></span>

- <span data-ttu-id="2be2b-111">UI 以任何语言正确显示。</span><span class="sxs-lookup"><span data-stu-id="2be2b-111">UI displays well  in any language.</span></span>

- <span data-ttu-id="2be2b-112">减少了文本转换完后重新调整控件位置和大小的需要。</span><span class="sxs-lookup"><span data-stu-id="2be2b-112">Reduces the need to readjust position and size of controls after text is translated.</span></span>

- <span data-ttu-id="2be2b-113">减少了重新调整窗口大小的需要。</span><span class="sxs-lookup"><span data-stu-id="2be2b-113">Reduces the need to readjust window size.</span></span>

- <span data-ttu-id="2be2b-114">UI 布局在任何语言中都正确呈现。</span><span class="sxs-lookup"><span data-stu-id="2be2b-114">UI layout renders properly in any language.</span></span>

- <span data-ttu-id="2be2b-115">本地化过程可缩减为与进行字符串转换差不多。</span><span class="sxs-lookup"><span data-stu-id="2be2b-115">Localization can be reduced to the point that it is little more than string translation.</span></span>

<a name="autolayout_controls"></a>

## <a name="automatic-layout-and-controls"></a><span data-ttu-id="2be2b-116">自动布局和控件</span><span class="sxs-lookup"><span data-stu-id="2be2b-116">Automatic Layout and Controls</span></span>

<span data-ttu-id="2be2b-117">利用自动布局，应用程序可以自动调整控件大小。</span><span class="sxs-lookup"><span data-stu-id="2be2b-117">Automatic layout enables an application to adjust the size of a control automatically.</span></span> <span data-ttu-id="2be2b-118">例如，控件可按字符串长度相应改变。</span><span class="sxs-lookup"><span data-stu-id="2be2b-118">For example, a control can change to accommodate the length of a string.</span></span> <span data-ttu-id="2be2b-119">利用此功能，本地化人员可转换字符串，而无需再调整控件大小以适应转换后的文本。</span><span class="sxs-lookup"><span data-stu-id="2be2b-119">This capability enables  localizers to translate the string; they no longer need to resize the control to fit the translated text.</span></span> <span data-ttu-id="2be2b-120">下面的示例创建一个带有英文内容的按钮。</span><span class="sxs-lookup"><span data-stu-id="2be2b-120">The following example creates a button with English content.</span></span>

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]

<span data-ttu-id="2be2b-121">在此示例中，只需更改文本即可生成一个西班牙文按钮。</span><span class="sxs-lookup"><span data-stu-id="2be2b-121">In the example, all you have to do to make a Spanish button is change the text.</span></span> <span data-ttu-id="2be2b-122">例如，</span><span class="sxs-lookup"><span data-stu-id="2be2b-122">For example,</span></span>

[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]

<span data-ttu-id="2be2b-123">下图显示了代码示例的输出：</span><span class="sxs-lookup"><span data-stu-id="2be2b-123">The following graphic shows the output of the code samples:</span></span>

![具有不同语言的文本的同一按钮](./media/use-automatic-layout-overview/auto-resizable-button.png)

<a name="autolayout_coding"></a>

## <a name="automatic-layout-and-coding-standards"></a><span data-ttu-id="2be2b-125">自动布局和编码标准</span><span class="sxs-lookup"><span data-stu-id="2be2b-125">Automatic Layout and Coding Standards</span></span>

<span data-ttu-id="2be2b-126">使用自动布局方法需要一组编码和设计标准和规则，以生成可完全本地化的 UI。</span><span class="sxs-lookup"><span data-stu-id="2be2b-126">Using the automatic layout approach requires a set of coding and design standards and rules to produce a fully localizable UI.</span></span> <span data-ttu-id="2be2b-127">下列准则可帮助完成自动布局编码。</span><span class="sxs-lookup"><span data-stu-id="2be2b-127">The following guidelines will aid your automatic layout coding.</span></span>

<span data-ttu-id="2be2b-128">**不要使用绝对位置**</span><span class="sxs-lookup"><span data-stu-id="2be2b-128">**Do not use absolute positions**</span></span>

- <span data-ttu-id="2be2b-129">不要使用 <xref:System.Windows.Controls.Canvas> ，因为它以绝对方式定位元素。</span><span class="sxs-lookup"><span data-stu-id="2be2b-129">Do not use <xref:System.Windows.Controls.Canvas> because it positions elements absolutely.</span></span>

- <span data-ttu-id="2be2b-130">使用 <xref:System.Windows.Controls.DockPanel> 、 <xref:System.Windows.Controls.StackPanel> 和 <xref:System.Windows.Controls.Grid> 定位控件。</span><span class="sxs-lookup"><span data-stu-id="2be2b-130">Use <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, and <xref:System.Windows.Controls.Grid> to position controls.</span></span>

<span data-ttu-id="2be2b-131">有关各种面板的讨论，请参阅 [面板概述](../controls/panels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2be2b-131">For a discussion about various types of panels, see [Panels Overview](../controls/panels-overview.md).</span></span>

<span data-ttu-id="2be2b-132">**不要为窗口设置固定大小**</span><span class="sxs-lookup"><span data-stu-id="2be2b-132">**Do not set a fixed size for a window**</span></span>

- <span data-ttu-id="2be2b-133">使用 <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="2be2b-133">Use <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2be2b-134">例如：</span><span class="sxs-lookup"><span data-stu-id="2be2b-134">For example:</span></span>

  [!code-xaml[LocalizationGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

<span data-ttu-id="2be2b-135">**添加 <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span><span class="sxs-lookup"><span data-stu-id="2be2b-135">**Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span></span>

- <span data-ttu-id="2be2b-136">将添加 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 到应用程序的根元素。</span><span class="sxs-lookup"><span data-stu-id="2be2b-136">Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A> to the root element of your application.</span></span>

  <span data-ttu-id="2be2b-137">WPF 提供了一种简便的方法来支持水平、双向和垂直布局。</span><span class="sxs-lookup"><span data-stu-id="2be2b-137">WPF provides a convenient way to support horizontal, bidirectional, and vertical layouts.</span></span> <span data-ttu-id="2be2b-138">在表示框架中， <xref:System.Windows.FrameworkElement.FlowDirection%2A> 属性可用于定义布局。</span><span class="sxs-lookup"><span data-stu-id="2be2b-138">In presentation framework, the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property can be used to define layout.</span></span> <span data-ttu-id="2be2b-139">流方向模式包括：</span><span class="sxs-lookup"><span data-stu-id="2be2b-139">The flow-direction patterns are:</span></span>

  - <span data-ttu-id="2be2b-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) —拉丁语、东亚等的水平布局。</span><span class="sxs-lookup"><span data-stu-id="2be2b-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) — horizontal layout for Latin, East Asian, and so forth.</span></span>

  - <span data-ttu-id="2be2b-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb) -针对阿拉伯语、希伯来语等的双向。</span><span class="sxs-lookup"><span data-stu-id="2be2b-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb) — bidirectional for Arabic, Hebrew, and so forth.</span></span>

<span data-ttu-id="2be2b-142">**使用复合字体而不是物理字体**</span><span class="sxs-lookup"><span data-stu-id="2be2b-142">**Use composite fonts instead of physical fonts**</span></span>

- <span data-ttu-id="2be2b-143">对于复合字体， <xref:System.Windows.Controls.Control.FontFamily%2A> 无需本地化属性。</span><span class="sxs-lookup"><span data-stu-id="2be2b-143">With composite fonts, the <xref:System.Windows.Controls.Control.FontFamily%2A> property does not need to be localized.</span></span>

- <span data-ttu-id="2be2b-144">开发人员可以使用以下字体之一，也可以创建自己的字体。</span><span class="sxs-lookup"><span data-stu-id="2be2b-144">Developers can use one of the following fonts or create their own.</span></span>

  - <span data-ttu-id="2be2b-145">Global User Interface</span><span class="sxs-lookup"><span data-stu-id="2be2b-145">Global User Interface</span></span>
  - <span data-ttu-id="2be2b-146">Global San Serif</span><span class="sxs-lookup"><span data-stu-id="2be2b-146">Global San Serif</span></span>
  - <span data-ttu-id="2be2b-147">Global Serif</span><span class="sxs-lookup"><span data-stu-id="2be2b-147">Global Serif</span></span>

<span data-ttu-id="2be2b-148">**添加 xml： lang**</span><span class="sxs-lookup"><span data-stu-id="2be2b-148">**Add xml:lang**</span></span>

- <span data-ttu-id="2be2b-149">`xml:lang`在 UI 的根元素中添加特性，如 `xml:lang="en-US"` 用于英语应用程序的。</span><span class="sxs-lookup"><span data-stu-id="2be2b-149">Add the `xml:lang` attribute in the root element of your UI, such as `xml:lang="en-US"` for an English application.</span></span>

- <span data-ttu-id="2be2b-150">由于复合字体使用 `xml:lang` 来确定要使用的字体，因此请将此属性设置为支持多语言方案。</span><span class="sxs-lookup"><span data-stu-id="2be2b-150">Because composite fonts use `xml:lang` to determine what font to use, set this property to support multilingual scenarios.</span></span>

<a name="autolay_grids"></a>

## <a name="automatic-layout-and-grids"></a><span data-ttu-id="2be2b-151">自动布局和网格</span><span class="sxs-lookup"><span data-stu-id="2be2b-151">Automatic Layout and Grids</span></span>

<span data-ttu-id="2be2b-152"><xref:System.Windows.Controls.Grid>元素对于自动布局非常有用，因为它允许开发人员定位元素。</span><span class="sxs-lookup"><span data-stu-id="2be2b-152">The <xref:System.Windows.Controls.Grid> element, is useful for automatic layout because it enables a developer to position elements.</span></span> <span data-ttu-id="2be2b-153"><xref:System.Windows.Controls.Grid>控件可以使用列和行排列在其子元素之间分布可用空间。</span><span class="sxs-lookup"><span data-stu-id="2be2b-153">A <xref:System.Windows.Controls.Grid> control is capable of distributing the available space among its child elements, using a column and row arrangement.</span></span> <span data-ttu-id="2be2b-154">UI 元素可以跨多个单元格，并且可以在网格中包含网格。</span><span class="sxs-lookup"><span data-stu-id="2be2b-154">The UI elements can span multiple cells, and it is possible to have grids within grids.</span></span> <span data-ttu-id="2be2b-155">网格非常有用，因为它们使你能够创建和定位复杂的 UI。</span><span class="sxs-lookup"><span data-stu-id="2be2b-155">Grids are useful because they enable you to create and position complex UI.</span></span> <span data-ttu-id="2be2b-156">下面的示例演示使用网格来定位某些按钮和文本。</span><span class="sxs-lookup"><span data-stu-id="2be2b-156">The following example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="2be2b-157">请注意，单元格的高度和宽度设置为 <xref:System.Windows.GridUnitType.Auto> ; 因此，包含带图像按钮的单元格会调整以适应图像。</span><span class="sxs-lookup"><span data-stu-id="2be2b-157">Notice that the height and width of the cells are set to <xref:System.Windows.GridUnitType.Auto>; therefore, the cell that contains the button with an image adjusts to fit the image.</span></span>

[!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]

<span data-ttu-id="2be2b-158">下图显示了以上代码生成的网格。</span><span class="sxs-lookup"><span data-stu-id="2be2b-158">The following graphic shows the grid produced by the previous code.</span></span>

<span data-ttu-id="2be2b-159">![网格示例](./media/glob-grid.png "glob_grid") 格</span><span class="sxs-lookup"><span data-stu-id="2be2b-159">![Grid example](./media/glob-grid.png "glob_grid") Grid</span></span>

<a name="autolay_grids_issharedsizescope"></a>

## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a><span data-ttu-id="2be2b-160">使用 IsSharedSizeScope 属性的自动布局和网格</span><span class="sxs-lookup"><span data-stu-id="2be2b-160">Automatic Layout and Grids Using the IsSharedSizeScope Property</span></span>

<span data-ttu-id="2be2b-161"><xref:System.Windows.Controls.Grid>元素在可本地化的应用程序中非常有用，可以创建调整以适应内容的控件。</span><span class="sxs-lookup"><span data-stu-id="2be2b-161">A <xref:System.Windows.Controls.Grid> element is useful in localizable applications to create controls that adjust to fit content.</span></span> <span data-ttu-id="2be2b-162">不过，有时可能希望控件无论包含什么内容都可以保持特定大小。</span><span class="sxs-lookup"><span data-stu-id="2be2b-162">However, at times you want controls to maintain a particular size regardless of content.</span></span> <span data-ttu-id="2be2b-163">例如，对于“确定”、“取消”和“浏览”按钮，可能不希望按钮根据内容调整大小。</span><span class="sxs-lookup"><span data-stu-id="2be2b-163">For example, if you have "OK", "Cancel" and "Browse" buttons you probably do not want the buttons sized to fit the content.</span></span> <span data-ttu-id="2be2b-164">在这种情况下， <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> 附加属性可用于在多个网格元素之间共享相同的大小。</span><span class="sxs-lookup"><span data-stu-id="2be2b-164">In this case the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> attached property is useful for sharing the same sizing among multiple grid elements.</span></span> <span data-ttu-id="2be2b-165">下面的示例演示如何在多个元素之间共享列和行大小调整数据 <xref:System.Windows.Controls.Grid> 。</span><span class="sxs-lookup"><span data-stu-id="2be2b-165">The following example demonstrates how to share column and row sizing data between multiple <xref:System.Windows.Controls.Grid> elements.</span></span>

[!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]

> [!NOTE]
> <span data-ttu-id="2be2b-166">有关完整的代码示例，请参阅 [在网格之间共享大小调整属性](../controls/how-to-share-sizing-properties-between-grids.md)。</span><span class="sxs-lookup"><span data-stu-id="2be2b-166">For the complete code sample, see [Share Sizing Properties Between Grids](../controls/how-to-share-sizing-properties-between-grids.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2be2b-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="2be2b-167">See also</span></span>

- [<span data-ttu-id="2be2b-168">WPF 的全球化</span><span class="sxs-lookup"><span data-stu-id="2be2b-168">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="2be2b-169">使用自动布局创建按钮</span><span class="sxs-lookup"><span data-stu-id="2be2b-169">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
- [<span data-ttu-id="2be2b-170">使用网格进行自动布局</span><span class="sxs-lookup"><span data-stu-id="2be2b-170">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
