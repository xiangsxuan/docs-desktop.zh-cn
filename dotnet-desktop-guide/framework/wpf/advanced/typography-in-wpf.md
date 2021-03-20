---
title: 版式
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 8f459c1742afd0b14b063812b47754a4fc52a413
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664159"
---
# <a name="typography-in-wpf"></a><span data-ttu-id="49778-102">WPF 中的版式</span><span class="sxs-lookup"><span data-stu-id="49778-102">Typography in WPF</span></span>

<span data-ttu-id="49778-103">本主题介绍 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 的主要版式功能。</span><span class="sxs-lookup"><span data-stu-id="49778-103">This topic introduces the major typographic features of [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="49778-104">这些功能包括改进的文本呈现质量和性能、OpenType 版式支持、增强的国际文本、增强的字体支持和新的文本应用程序编程接口)  (Api。</span><span class="sxs-lookup"><span data-stu-id="49778-104">These features include improved quality and performance of text rendering, OpenType typography support, enhanced international text, enhanced font support, and new text application programming interfaces (APIs).</span></span>  
  
<a name="Improved_Quality_and_Performance_of_Text"></a>

## <a name="improved-quality-and-performance-of-text"></a><span data-ttu-id="49778-105">改进的文本质量和性能</span><span class="sxs-lookup"><span data-stu-id="49778-105">Improved Quality and Performance of Text</span></span>  

 <span data-ttu-id="49778-106">中的文本 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 使用 Microsoft ClearType 呈现，从而增强了文本的清晰度和可读性。</span><span class="sxs-lookup"><span data-stu-id="49778-106">Text in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] is rendered using Microsoft ClearType, which enhances the clarity and readability of text.</span></span> <span data-ttu-id="49778-107">ClearType 是由 Microsoft 开发的一种软件技术，可提高现有 Lcd 上的文本可读性 (Crystal 显示屏) ，如笔记本电脑屏幕、Pocket PC 屏幕和平板显示器。</span><span class="sxs-lookup"><span data-stu-id="49778-107">ClearType is a software technology developed by Microsoft that improves the readability of text on existing LCDs (Liquid Crystal Displays), such as laptop screens, Pocket PC screens and flat panel monitors.</span></span> <span data-ttu-id="49778-108">ClearType 使用子像素呈现，这允许通过在像素的小数部分对齐字符，以更高的保真度将文本显示为真正的形状。</span><span class="sxs-lookup"><span data-stu-id="49778-108">ClearType uses sub-pixel rendering which allows text to be displayed with a greater fidelity to its true shape by aligning characters on a fractional part of a pixel.</span></span> <span data-ttu-id="49778-109">超高的分辨率增加了文本显示中细节的清晰度，使其更便于长时间阅读。</span><span class="sxs-lookup"><span data-stu-id="49778-109">The extra resolution increases the sharpness of the tiny details in text display, making it much easier to read over long durations.</span></span> <span data-ttu-id="49778-110">中 ClearType 的另一个改进 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 是 y 方向抗锯齿，这会平滑文本字符中浅曲线的顶部和底部。</span><span class="sxs-lookup"><span data-stu-id="49778-110">Another improvement of ClearType in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] is y-direction anti-aliasing, which smoothes the tops and bottoms of shallow curves in text characters.</span></span> <span data-ttu-id="49778-111">有关 ClearType 功能的更多详细信息，请参阅 [Cleartype 概述](cleartype-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="49778-111">For more details on ClearType features, see [ClearType Overview](cleartype-overview.md).</span></span>  
  
 ![采用 ClearType y 向抗锯齿的文本](./media/typography-in-wpf/text-y-direction-antialiasing.gif)  
<span data-ttu-id="49778-113">采用 ClearType y 向抗锯齿的文本</span><span class="sxs-lookup"><span data-stu-id="49778-113">Text with ClearType y-direction antialiasing</span></span>  
  
 <span data-ttu-id="49778-114">所有文本呈现管道都可以在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 中实现硬件加速，前提是计算机满足所需硬件的最低要求。</span><span class="sxs-lookup"><span data-stu-id="49778-114">The entire text rendering pipeline can be hardware-accelerated in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] provided your machine meets the minimum level of hardware required.</span></span> <span data-ttu-id="49778-115">不能使用硬件执行加速的呈现会退回软件呈现。</span><span class="sxs-lookup"><span data-stu-id="49778-115">Rendering that cannot be performed using hardware falls back to software rendering.</span></span> <span data-ttu-id="49778-116">硬件加速会影响文本呈现管道的所有阶段（从存储单个标志符号、将标志符号组合到标志符号运行、应用效果），以将 ClearType 混合算法应用于最终显示的输出。</span><span class="sxs-lookup"><span data-stu-id="49778-116">Hardware-acceleration affects all phases of the text rendering pipeline—from storing individual glyphs, compositing glyphs into glyph runs, applying effects, to applying the ClearType blending algorithm to the final displayed output.</span></span> <span data-ttu-id="49778-117">有关硬件加速的详细信息，请参阅[图形呈现层](graphics-rendering-tiers.md)。</span><span class="sxs-lookup"><span data-stu-id="49778-117">For more information on hardware acceleration, see [Graphics Rendering Tiers](graphics-rendering-tiers.md).</span></span>  
  
 ![文本呈现管线示意图](./media/typography-in-wpf/text-rendering-pipeline.png)  
  
 <span data-ttu-id="49778-119">此外，动画文本（无论是按字符还是按字形进行动画处理）可充分利用由 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 启用的图形硬件功能。</span><span class="sxs-lookup"><span data-stu-id="49778-119">In addition, animated text, whether by character or glyph, takes full advantage of the graphics hardware capability enabled by [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="49778-120">因此，可生成平滑的文本动画。</span><span class="sxs-lookup"><span data-stu-id="49778-120">This results in smooth text animation.</span></span>  
  
<a name="Rich_Typography"></a>

## <a name="rich-typography"></a><span data-ttu-id="49778-121">丰富的版式</span><span class="sxs-lookup"><span data-stu-id="49778-121">Rich Typography</span></span>  

 <span data-ttu-id="49778-122">OpenType 字体格式是 TrueType®字体格式的扩展。</span><span class="sxs-lookup"><span data-stu-id="49778-122">The OpenType font format is an extension of the TrueType® font format.</span></span> <span data-ttu-id="49778-123">OpenType 字体格式由 Microsoft 和 Adobe 共同开发，提供丰富的高级版式功能。</span><span class="sxs-lookup"><span data-stu-id="49778-123">The OpenType font format was developed jointly by Microsoft and Adobe, and provides a rich assortment of advanced typographic features.</span></span> <span data-ttu-id="49778-124"><xref:System.Windows.Documents.Typography>对象公开了 OpenType 字体的许多高级功能，如样式替代和花体。</span><span class="sxs-lookup"><span data-stu-id="49778-124">The <xref:System.Windows.Documents.Typography> object exposes many of the advanced features of OpenType fonts, such as stylistic alternates and swashes.</span></span> <span data-ttu-id="49778-125">Windows SDK 提供了一组结合了丰富功能的示例 OpenType 字体，如 Pericles 和 Pescadero 字体。</span><span class="sxs-lookup"><span data-stu-id="49778-125">The Windows SDK provides a set of sample OpenType fonts that are designed with rich features, such as the Pericles and Pescadero fonts.</span></span> <span data-ttu-id="49778-126">有关详细信息，请参阅[示例 OpenType 字体包](sample-opentype-font-pack.md)。</span><span class="sxs-lookup"><span data-stu-id="49778-126">For more information, see [Sample OpenType Font Pack](sample-opentype-font-pack.md).</span></span>  
  
 <span data-ttu-id="49778-127">Pericles OpenType 字体包含其他一些标志符号，它们提供标准字形集的样式备用项。</span><span class="sxs-lookup"><span data-stu-id="49778-127">The Pericles OpenType font contains additional glyphs that provide stylistic alternates to the standard set of glyphs.</span></span> <span data-ttu-id="49778-128">以下文本显示样式备用字形。</span><span class="sxs-lookup"><span data-stu-id="49778-128">The following text displays stylistic alternate glyphs.</span></span>  
  
 <span data-ttu-id="49778-129">![使用 OpenType 样式备用标志符号的文本](./media/typography-in-wpf/opentype-stylistic-alternate-glyphs.gif "使用 OpenType 样式备用标志符号的文本")</span><span class="sxs-lookup"><span data-stu-id="49778-129">![Text using OpenType stylistic alternate glyphs](./media/typography-in-wpf/opentype-stylistic-alternate-glyphs.gif "Text using OpenType stylistic alternate glyphs")</span></span>  
  
 <span data-ttu-id="49778-130">花体是使用精美修饰的装饰性字形，通常与书法相关。</span><span class="sxs-lookup"><span data-stu-id="49778-130">Swashes are decorative glyphs that use elaborate ornamentation often associated with calligraphy.</span></span> <span data-ttu-id="49778-131">以下文本显示 Pescadero 字体的标准和花体字形。</span><span class="sxs-lookup"><span data-stu-id="49778-131">The following text displays standard and swash glyphs for the Pescadero font.</span></span>  
  
 <span data-ttu-id="49778-132">![使用 OpenType 标准字形和花体连字的文本](./media/typography-in-wpf/opentype-standard-swash-glyphs.gif "使用 OpenType 标准和花体连字的文本")</span><span class="sxs-lookup"><span data-stu-id="49778-132">![Text using OpenType standard and swash glyphs](./media/typography-in-wpf/opentype-standard-swash-glyphs.gif "Text using OpenType standard and swash glyphs")</span></span>  
  
 <span data-ttu-id="49778-133">有关 OpenType 功能的更多详细信息，请参阅 [Opentype 字体功能](opentype-font-features.md)。</span><span class="sxs-lookup"><span data-stu-id="49778-133">For more details on OpenType features, see [OpenType Font Features](opentype-font-features.md).</span></span>  
  
<a name="Enhanced_International_Text_Support"></a>

## <a name="enhanced-international-text-support"></a><span data-ttu-id="49778-134">增强的国际文本支持</span><span class="sxs-lookup"><span data-stu-id="49778-134">Enhanced International Text Support</span></span>  

 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="49778-135">通过提供下列功能来提供增强的国际文本支持：</span><span class="sxs-lookup"><span data-stu-id="49778-135">provides enhanced international text support by providing the following features:</span></span>  
  
- <span data-ttu-id="49778-136">使用自适应测量功能，在所有书写系统中实现自动行距调整。</span><span class="sxs-lookup"><span data-stu-id="49778-136">Automatic line-spacing in all writing systems, using adaptive measurement.</span></span>  
  
- <span data-ttu-id="49778-137">对国际文本的广泛支持。</span><span class="sxs-lookup"><span data-stu-id="49778-137">Broad support for international text.</span></span> <span data-ttu-id="49778-138">有关详细信息，请参阅 [WPF 的全球化](globalization-for-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="49778-138">For more information, see [Globalization for WPF](globalization-for-wpf.md).</span></span>  
  
- <span data-ttu-id="49778-139">根据不同的语言进行分行、连字和对齐。</span><span class="sxs-lookup"><span data-stu-id="49778-139">Language-guided line breaking, hyphenation, and justification.</span></span>  
  
<a name="Enhanced_Font_Support"></a>

## <a name="enhanced-font-support"></a><span data-ttu-id="49778-140">增强的字体支持</span><span class="sxs-lookup"><span data-stu-id="49778-140">Enhanced Font Support</span></span>  

 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="49778-141">通过提供下列功能来提供增强的字体支持：</span><span class="sxs-lookup"><span data-stu-id="49778-141">provides enhanced font support by providing the following features:</span></span>  
  
- <span data-ttu-id="49778-142">所有文本均采用 Unicode。</span><span class="sxs-lookup"><span data-stu-id="49778-142">Unicode for all text.</span></span> <span data-ttu-id="49778-143">字体行为和选择不再需要字符集或代码页。</span><span class="sxs-lookup"><span data-stu-id="49778-143">Font behavior and selection no longer require charset or codepage.</span></span>  
  
- <span data-ttu-id="49778-144">字体行为与全局设置（如系统区域设置）无关。</span><span class="sxs-lookup"><span data-stu-id="49778-144">Font behavior independent of global settings, such as system locale.</span></span>  
  
- <span data-ttu-id="49778-145">分隔 <xref:System.Windows.FontWeight> 、 <xref:System.Windows.FontStretch> 和 <xref:System.Windows.FontStyle> 类型用于定义 <xref:System.Windows.Media.FontFamily> 。</span><span class="sxs-lookup"><span data-stu-id="49778-145">Separate <xref:System.Windows.FontWeight>, <xref:System.Windows.FontStretch>, and <xref:System.Windows.FontStyle> types for defining a <xref:System.Windows.Media.FontFamily>.</span></span> <span data-ttu-id="49778-146">这比 Win32 编程提供了更大的灵活性，其中斜体和粗体的布尔组合用于定义字体系列。</span><span class="sxs-lookup"><span data-stu-id="49778-146">This provides greater flexibility than in Win32 programming, in which Boolean combinations of italic and bold are used to define a font family.</span></span>  
  
- <span data-ttu-id="49778-147">在处理书写方向（横向与纵向）时不受字体名称的影响。</span><span class="sxs-lookup"><span data-stu-id="49778-147">Writing direction (horizontal versus vertical) handled independent of font name.</span></span>  
  
- <span data-ttu-id="49778-148">使用复合字体技术在可移植 XML 文件中链接字体和字体回退。</span><span class="sxs-lookup"><span data-stu-id="49778-148">Font linking and font fallback in a portable XML file, using composite font technology.</span></span> <span data-ttu-id="49778-149">使用复合字体可以构造全面的多语言字体。</span><span class="sxs-lookup"><span data-stu-id="49778-149">Composite fonts allow for the construction of full range multilingual fonts.</span></span> <span data-ttu-id="49778-150">复合字体还提供一种可避免显示缺失字形的机制。</span><span class="sxs-lookup"><span data-stu-id="49778-150">Composite fonts also provide a mechanism that avoids displaying missing glyphs.</span></span> <span data-ttu-id="49778-151">有关详细信息，请参阅类中的备注 <xref:System.Windows.Media.FontFamily> 。</span><span class="sxs-lookup"><span data-stu-id="49778-151">For more information, see the remarks in the <xref:System.Windows.Media.FontFamily> class.</span></span>  
  
- <span data-ttu-id="49778-152">使用一组单语言字体，根据复合字体生成国际字体。</span><span class="sxs-lookup"><span data-stu-id="49778-152">International fonts built from composite fonts, using a group of single-language fonts.</span></span> <span data-ttu-id="49778-153">在开发多语言字体时，该功能可节省资源成本。</span><span class="sxs-lookup"><span data-stu-id="49778-153">This saves on resource costs when developing fonts for multiple languages.</span></span>  
  
- <span data-ttu-id="49778-154">在文档中嵌入复合字体，从而能够提供文档可移植性。</span><span class="sxs-lookup"><span data-stu-id="49778-154">Composite fonts embedded in a document, thereby providing document portability.</span></span> <span data-ttu-id="49778-155">有关详细信息，请参阅类中的备注 <xref:System.Windows.Media.FontFamily> 。</span><span class="sxs-lookup"><span data-stu-id="49778-155">For more information, see the remarks in the <xref:System.Windows.Media.FontFamily> class.</span></span>  
  
<a name="New_Text_APIs"></a>

## <a name="new-text-application-programming-interfaces-apis"></a><span data-ttu-id="49778-156">新的文本应用程序编程接口 (API)</span><span class="sxs-lookup"><span data-stu-id="49778-156">New Text Application Programming Interfaces (APIs)</span></span>  

 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="49778-157">提供了多个文本 Api，供开发人员在其应用程序中包含文本时使用。</span><span class="sxs-lookup"><span data-stu-id="49778-157">provides several text APIs for developers to use when including text in their applications.</span></span> <span data-ttu-id="49778-158">这些 Api 分为三个类别：</span><span class="sxs-lookup"><span data-stu-id="49778-158">These APIs are grouped into three categories:</span></span>  
  
- <span data-ttu-id="49778-159">**布局和用户界面**。</span><span class="sxs-lookup"><span data-stu-id="49778-159">**Layout and user interface**.</span></span> <span data-ttu-id="49778-160">图形用户界面 (GUI) 的常见文本控件。</span><span class="sxs-lookup"><span data-stu-id="49778-160">The common text controls for the graphical user interface (GUI).</span></span>  
  
- <span data-ttu-id="49778-161">**轻量文本绘制**。</span><span class="sxs-lookup"><span data-stu-id="49778-161">**Lightweight text drawing**.</span></span> <span data-ttu-id="49778-162">可直接在对象上绘制文本。</span><span class="sxs-lookup"><span data-stu-id="49778-162">Allows you to draw text directly to objects.</span></span>  
  
- <span data-ttu-id="49778-163">**高级文本格式设置**。</span><span class="sxs-lookup"><span data-stu-id="49778-163">**Advanced text formatting**.</span></span> <span data-ttu-id="49778-164">可实现自定义文本引擎。</span><span class="sxs-lookup"><span data-stu-id="49778-164">Allows you to implement a custom text engine.</span></span>  
  
### <a name="layout-and-user-interface"></a><span data-ttu-id="49778-165">布局和用户界面</span><span class="sxs-lookup"><span data-stu-id="49778-165">Layout and User Interface</span></span>  

 <span data-ttu-id="49778-166">在功能的最高级别上，文本 Api 提供公共 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 控件，例如 <xref:System.Windows.Controls.Label> 、 <xref:System.Windows.Controls.TextBlock> 和 <xref:System.Windows.Controls.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="49778-166">At the highest level of functionality, the text APIs provide common [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] controls such as <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBlock>, and <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="49778-167">这些控件提供应用程序中的基本 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 元素，并提供一种表示文本和与文本交互的简便方法。</span><span class="sxs-lookup"><span data-stu-id="49778-167">These controls provide the basic [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elements within an application, and offer an easy way to present and interact with text.</span></span> <span data-ttu-id="49778-168">控件（如 <xref:System.Windows.Controls.RichTextBox> 和）可 <xref:System.Windows.Controls.PasswordBox> 实现更高级或专用文本处理。</span><span class="sxs-lookup"><span data-stu-id="49778-168">Controls such as <xref:System.Windows.Controls.RichTextBox> and <xref:System.Windows.Controls.PasswordBox> enable more advanced or specialized text-handling.</span></span> <span data-ttu-id="49778-169">和类（如 <xref:System.Windows.Documents.TextRange> 、 <xref:System.Windows.Documents.TextSelection> 和） <xref:System.Windows.Documents.TextPointer> 启用有用的文本操作。</span><span class="sxs-lookup"><span data-stu-id="49778-169">And classes such as <xref:System.Windows.Documents.TextRange>, <xref:System.Windows.Documents.TextSelection>, and <xref:System.Windows.Documents.TextPointer> enable useful text manipulation.</span></span> <span data-ttu-id="49778-170">这些 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 控件提供 <xref:System.Windows.Controls.Control.FontFamily%2A> 、和等属性 <xref:System.Windows.Controls.Control.FontSize%2A> <xref:System.Windows.Controls.Control.FontStyle%2A> ，使您能够控制用于呈现文本的字体。</span><span class="sxs-lookup"><span data-stu-id="49778-170">These [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] controls provide properties such as <xref:System.Windows.Controls.Control.FontFamily%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, and <xref:System.Windows.Controls.Control.FontStyle%2A>, which enable you to control the font that is used to render the text.</span></span>  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a><span data-ttu-id="49778-171">使用位图效果、转换和文本效果</span><span class="sxs-lookup"><span data-stu-id="49778-171">Using Bitmap Effects, Transforms, and Text Effects</span></span>  

 <span data-ttu-id="49778-172">通过 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]，可以借助位图效果、转换和文本效果等功能，来创建悦目的文本用法。</span><span class="sxs-lookup"><span data-stu-id="49778-172">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] allows you to create visually interesting uses of text by uses features such as bitmap effects, transforms, and text effects.</span></span> <span data-ttu-id="49778-173">下面的示例演示了应用于文本的典型类型的投影效果。</span><span class="sxs-lookup"><span data-stu-id="49778-173">The following example shows a typical type of a drop shadow effect applied to text.</span></span>  
  
 ![柔和度 &#61; 0.25 的文本阴影](./media/typography-in-wpf/drop-shadow-text-effect.jpg)
  
 <span data-ttu-id="49778-175">下面的示例演示了应用于文本的投影效果和噪音。</span><span class="sxs-lookup"><span data-stu-id="49778-175">The following example shows a drop shadow effect and noise applied to text.</span></span>  
  
 ![有噪音的文本阴影](./media/typography-in-wpf/drop-shadow-noise-text.jpg)
  
 <span data-ttu-id="49778-177">下面的示例演示了应用于文本的外发光效果。</span><span class="sxs-lookup"><span data-stu-id="49778-177">The following example shows an outer glow effect applied to text.</span></span>  
  
 ![使用 OuterGlowBitmapEffect 的文本阴影](./media/typography-in-wpf/text-shadow-glow-effect.jpg)
  
 <span data-ttu-id="49778-179">以下示例显示了应用于文本的模糊效果。</span><span class="sxs-lookup"><span data-stu-id="49778-179">The following example shows a blur effect applied to text.</span></span>  
  
 ![使用 BlurBitmapEffect 的文本阴影](./media/typography-in-wpf/text-shadow-blur-effect.jpg)  

 <span data-ttu-id="49778-181">下面的示例演示沿 X 轴放大 150% 得到第二行文本，沿 Y 轴放大 150% 得到第三行文本。</span><span class="sxs-lookup"><span data-stu-id="49778-181">The following example shows the second line of text scaled by 150% along the x-axis, and the third line of text scaled by 150% along the y-axis.</span></span>  
  
 ![使用 ScaleTransform 缩放的文本](./media/typography-in-wpf/scaled-text-scaletransform.jpg)
  
 <span data-ttu-id="49778-183">以下示例演示沿 X 轴倾斜的文本。</span><span class="sxs-lookup"><span data-stu-id="49778-183">The following example shows text skewed along the x-axis.</span></span>  
  
 ![使用 SkewTransform 扭曲的文本](./media/typography-in-wpf/skewed-transformed-text.jpg)
  
 <span data-ttu-id="49778-185"><xref:System.Windows.Media.TextEffect>对象是一个帮助器对象，它允许您将文本视为文本字符串中的一个或多个字符组。</span><span class="sxs-lookup"><span data-stu-id="49778-185">A <xref:System.Windows.Media.TextEffect> object is a helper object that allows you to treat text as one or more groups of characters in a text string.</span></span> <span data-ttu-id="49778-186">下面的示例演示发生旋转的单个字符。</span><span class="sxs-lookup"><span data-stu-id="49778-186">The following example shows an individual character being rotated.</span></span> <span data-ttu-id="49778-187">每个字符都将以 1 秒为间隔单独旋转。</span><span class="sxs-lookup"><span data-stu-id="49778-187">Each character is rotated independently at 1-second intervals.</span></span>  
  
 ![旋转文本的文本效果屏幕快照](./media/typography-in-wpf/rotating-text-effect.jpg)
  
#### <a name="using-flow-documents"></a><span data-ttu-id="49778-189">使用流文档</span><span class="sxs-lookup"><span data-stu-id="49778-189">Using Flow Documents</span></span>  

 <span data-ttu-id="49778-190">除了公共 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 控件外， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 还提供了一个用于文本呈现的布局控件— <xref:System.Windows.Documents.FlowDocument> 元素。</span><span class="sxs-lookup"><span data-stu-id="49778-190">In addition to the common [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] controls, [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] offers a layout control for text presentation—the <xref:System.Windows.Documents.FlowDocument> element.</span></span> <span data-ttu-id="49778-191"><xref:System.Windows.Documents.FlowDocument>元素与 <xref:System.Windows.Controls.DocumentViewer> 元素一起为大量具有不同布局要求的文本提供控件。</span><span class="sxs-lookup"><span data-stu-id="49778-191">The <xref:System.Windows.Documents.FlowDocument> element, in conjunction with the <xref:System.Windows.Controls.DocumentViewer> element, provides a control for large amounts of text with varying layout requirements.</span></span> <span data-ttu-id="49778-192">布局控件通过 <xref:System.Windows.Documents.Typography> 其他控件的对象和字体相关属性提供对高级版式的访问 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="49778-192">Layout controls provide access to advanced typography through the <xref:System.Windows.Documents.Typography> object and font-related properties of other [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] controls.</span></span>  
  
 <span data-ttu-id="49778-193">下面的示例演示了中托管的文本内容 <xref:System.Windows.Controls.FlowDocumentReader> ，它提供了搜索、导航、分页和内容缩放支持。</span><span class="sxs-lookup"><span data-stu-id="49778-193">The following example shows text content hosted in a <xref:System.Windows.Controls.FlowDocumentReader>, which provides search, navigation, pagination, and content scaling support.</span></span>  
  
 ![显示 OpenType 字体的屏幕截图。](./media/typography-in-wpf/typography-text-flowdocumentreader.png)
  
 <span data-ttu-id="49778-195">有关详细信息，请参阅 [WPF 中的文档](documents-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="49778-195">For more information, see [Documents in WPF](documents-in-wpf.md).</span></span>  
  
### <a name="lightweight-text-drawing"></a><span data-ttu-id="49778-196">轻量文本绘制</span><span class="sxs-lookup"><span data-stu-id="49778-196">Lightweight Text Drawing</span></span>  

 <span data-ttu-id="49778-197">使用对象的方法可以将文本直接绘制到 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 对象 <xref:System.Windows.Media.DrawingContext.DrawText%2A> <xref:System.Windows.Media.DrawingContext> 。</span><span class="sxs-lookup"><span data-stu-id="49778-197">You can draw text directly to [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] objects by using the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of the <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="49778-198">若要使用此方法，请创建 <xref:System.Windows.Media.FormattedText> 对象。</span><span class="sxs-lookup"><span data-stu-id="49778-198">To use this method, you create a <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="49778-199">使用该对象可以绘制多行文本，可对文本中的每个字符单独设置格式。</span><span class="sxs-lookup"><span data-stu-id="49778-199">This object allows you to draw multi-line text, in which each character in the text can be individually formatted.</span></span> <span data-ttu-id="49778-200">对象的功能 <xref:System.Windows.Media.FormattedText> 包含 WINDOWS API 中 DrawText 标志的许多功能。</span><span class="sxs-lookup"><span data-stu-id="49778-200">The functionality of the <xref:System.Windows.Media.FormattedText> object contains much of the functionality of the DrawText flags in the Windows API.</span></span> <span data-ttu-id="49778-201">此外，对象还 <xref:System.Windows.Media.FormattedText> 包含省略号支持等功能，其中在文本超出其边界时显示省略号。</span><span class="sxs-lookup"><span data-stu-id="49778-201">In addition, the <xref:System.Windows.Media.FormattedText> object contains functionality such as ellipsis support, in which an ellipsis is displayed when text exceeds its bounds.</span></span> <span data-ttu-id="49778-202">下面的示例演示应用多种格式的文本，其中第二个和第三个单词应用了线性渐变。</span><span class="sxs-lookup"><span data-stu-id="49778-202">The following example shows text that has several formats applied to it, including a linear gradient on the second and third words.</span></span>  
  
 ![使用 FormattedText 对象显示的文本](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)
  
 <span data-ttu-id="49778-204">您可以将格式化文本转换为 <xref:System.Windows.Media.Geometry> 对象，从而允许您创建其他类型的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="49778-204">You can convert formatted text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually interesting text.</span></span> <span data-ttu-id="49778-205">例如，可以根据 <xref:System.Windows.Media.Geometry> 文本字符串的轮廓创建对象。</span><span class="sxs-lookup"><span data-stu-id="49778-205">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 ![使用线性渐变画笔的文本轮廓](./media/typography-in-wpf/text-outline-linear-gradient.jpg)  
  
 <span data-ttu-id="49778-207">以下示例说明了几种通过修改已转换文本的笔划、填充和突出显示来创建悦目的视觉效果的方法。</span><span class="sxs-lookup"><span data-stu-id="49778-207">The following examples illustrate several ways of creating interesting visual effects by modifying the stroke, fill, and highlight of converted text.</span></span>  
  
 ![对填充和笔画使用不同颜色的文本](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![笔画应用了图像画笔的文本](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![将图像画笔应用于笔划和突出显示的文本](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 <span data-ttu-id="49778-211">有关对象的详细信息 <xref:System.Windows.Media.FormattedText> ，请参阅 [绘制格式化文本](drawing-formatted-text.md)。</span><span class="sxs-lookup"><span data-stu-id="49778-211">For more information on the <xref:System.Windows.Media.FormattedText> object, see [Drawing Formatted Text](drawing-formatted-text.md).</span></span>  
  
### <a name="advanced-text-formatting"></a><span data-ttu-id="49778-212">高级文本格式设置</span><span class="sxs-lookup"><span data-stu-id="49778-212">Advanced Text Formatting</span></span>  

 <span data-ttu-id="49778-213">在文本 Api 的最高级级别，提供了 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 使用 <xref:System.Windows.Media.TextFormatting.TextFormatter> 对象和命名空间中的其他类型创建自定义文本布局的功能 <xref:System.Windows.Media.TextFormatting> 。</span><span class="sxs-lookup"><span data-stu-id="49778-213">At the most advanced level of the text APIs, [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] offers you the ability to create custom text layout by using the <xref:System.Windows.Media.TextFormatting.TextFormatter> object and other types in the <xref:System.Windows.Media.TextFormatting> namespace.</span></span> <span data-ttu-id="49778-214"><xref:System.Windows.Media.TextFormatting.TextFormatter>和关联的类允许您实现自定义文本布局，该布局支持您自己定义的字符格式、段落样式、换行符规则和其他用于国际化文本的布局功能。</span><span class="sxs-lookup"><span data-stu-id="49778-214">The <xref:System.Windows.Media.TextFormatting.TextFormatter> and associated classes allow you to implement custom text layout that supports your own definition of character formats, paragraph styles, line breaking rules, and other layout features for international text.</span></span> <span data-ttu-id="49778-215">只有在极少数情况下才需要重写 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 文本布局支持的默认实现。</span><span class="sxs-lookup"><span data-stu-id="49778-215">There are very few cases in which you would want to override the default implementation of the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] text layout support.</span></span> <span data-ttu-id="49778-216">但是，如果要创建文本编辑控件或应用程序，则可能需要非默认的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 实现。</span><span class="sxs-lookup"><span data-stu-id="49778-216">However, if you were creating a text editing control or application, you might require a different implementation than the default [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] implementation.</span></span>  
  
 <span data-ttu-id="49778-217">与传统的文本 API 不同， <xref:System.Windows.Media.TextFormatting.TextFormatter> 通过一组回调方法与文本布局客户端进行交互。</span><span class="sxs-lookup"><span data-stu-id="49778-217">Unlike a traditional text API, the <xref:System.Windows.Media.TextFormatting.TextFormatter> interacts with a text layout client through a set of callback methods.</span></span> <span data-ttu-id="49778-218">它要求客户端在类的实现中提供这些方法 <xref:System.Windows.Media.TextFormatting.TextSource> 。</span><span class="sxs-lookup"><span data-stu-id="49778-218">It requires the client to provide these methods in an implementation of the <xref:System.Windows.Media.TextFormatting.TextSource> class.</span></span> <span data-ttu-id="49778-219">下图说明了客户端应用程序和之间的文本布局交互 <xref:System.Windows.Media.TextFormatting.TextFormatter> 。</span><span class="sxs-lookup"><span data-stu-id="49778-219">The following diagram illustrates the text layout interaction between the client application and <xref:System.Windows.Media.TextFormatting.TextFormatter>.</span></span>  
  
 ![文本布局客户端和 TextFormatter 示意图](./media/typography-in-wpf/text-layout-text-formatter-interaction.png)  
  
 <span data-ttu-id="49778-221">有关创建自定义文本布局的详细信息，请参阅[高级文本格式设置](advanced-text-formatting.md)。</span><span class="sxs-lookup"><span data-stu-id="49778-221">For more details on creating custom text layout, see [Advanced Text Formatting](advanced-text-formatting.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49778-222">请参阅</span><span class="sxs-lookup"><span data-stu-id="49778-222">See also</span></span>

- <xref:System.Windows.Media.FormattedText>
- <xref:System.Windows.Media.TextFormatting.TextFormatter>
- [<span data-ttu-id="49778-223">ClearType 概述</span><span class="sxs-lookup"><span data-stu-id="49778-223">ClearType Overview</span></span>](cleartype-overview.md)
- [<span data-ttu-id="49778-224">OpenType 字体功能</span><span class="sxs-lookup"><span data-stu-id="49778-224">OpenType Font Features</span></span>](opentype-font-features.md)
- [<span data-ttu-id="49778-225">绘制格式化文本</span><span class="sxs-lookup"><span data-stu-id="49778-225">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="49778-226">高级文本格式设置</span><span class="sxs-lookup"><span data-stu-id="49778-226">Advanced Text Formatting</span></span>](advanced-text-formatting.md)
- [<span data-ttu-id="49778-227">文本</span><span class="sxs-lookup"><span data-stu-id="49778-227">Text</span></span>](optimizing-performance-text.md)
- [<span data-ttu-id="49778-228">Microsoft 板式</span><span class="sxs-lookup"><span data-stu-id="49778-228">Microsoft Typography</span></span>](/typography/)
