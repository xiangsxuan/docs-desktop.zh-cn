---
title: OpenType 字体功能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], OpenType
- typography [WPF], OpenType font technology
- OpenType font technology [WPF]
ms.assetid: 4061a9d1-fe8b-4921-9e17-18ec7d2e3ea2
ms.openlocfilehash: 5f9f5b14400962af2da94dd60f5170cb2f3d2f51
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96970962"
---
# <a name="opentype-font-features"></a><span data-ttu-id="aa9cc-102">OpenType 字体功能</span><span class="sxs-lookup"><span data-stu-id="aa9cc-102">OpenType Font Features</span></span>

<span data-ttu-id="aa9cc-103">本主题概述了中的 OpenType 字体技术的一些重要功能 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-103">This topic provides an overview of some of the key features of OpenType font technology in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
<a name="overview"></a>

## <a name="opentype-font-format"></a><span data-ttu-id="aa9cc-104">OpenType 字体格式</span><span class="sxs-lookup"><span data-stu-id="aa9cc-104">OpenType Font Format</span></span>  

 <span data-ttu-id="aa9cc-105">OpenType 字体格式是 TrueType®字体格式的扩展，添加了对 PostScript 字体数据的支持。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-105">The OpenType font format is an extension of the TrueType® font format, adding support for PostScript font data.</span></span> <span data-ttu-id="aa9cc-106">OpenType 字体格式由 Microsoft 和 Adobe Corporation 共同开发。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-106">The OpenType font format was developed jointly by Microsoft and Adobe Corporation.</span></span> <span data-ttu-id="aa9cc-107">OpenType 字体和支持 OpenType 字体的操作系统服务为用户提供了一种简单的方法来安装和使用字体，无论字体是否包含 TrueType 大纲或 CFF (PostScript) 大纲。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-107">OpenType fonts and the operating system services which support OpenType fonts provide users with a simple way to install and use fonts, whether the fonts contain TrueType outlines or CFF (PostScript) outlines.</span></span>  
  
 <span data-ttu-id="aa9cc-108">OpenType 字体格式解决了以下开发人员难题：</span><span class="sxs-lookup"><span data-stu-id="aa9cc-108">The OpenType font format addresses the following developer challenges:</span></span>  
  
- <span data-ttu-id="aa9cc-109">更广泛的多平台支持。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-109">Broader multi-platform support.</span></span>  
  
- <span data-ttu-id="aa9cc-110">更出色的国际字符集支持。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-110">Better support for international character sets.</span></span>  
  
- <span data-ttu-id="aa9cc-111">更优的字体数据保护。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-111">Better protection for font data.</span></span>  
  
- <span data-ttu-id="aa9cc-112">更小的文件大小，让字体发布更加高效。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-112">Smaller file sizes to make font distribution more efficient.</span></span>  
  
- <span data-ttu-id="aa9cc-113">更广泛的高级版式控件支持。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-113">Broader support for advanced typographic control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aa9cc-114">Windows SDK 包含一组可用于应用程序的示例 OpenType 字体 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-114">The Windows SDK contains a set of sample OpenType fonts that you can use with [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="aa9cc-115">这些字体提供本主题余下部分所述的大多数功能。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-115">These fonts provide most of the features illustrated in the rest of this topic.</span></span> <span data-ttu-id="aa9cc-116">有关详细信息，请参阅[示例 OpenType 字体包](sample-opentype-font-pack.md)。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-116">For more information, see [Sample OpenType Font Pack](sample-opentype-font-pack.md).</span></span>  
  
<span data-ttu-id="aa9cc-117">有关 OpenType 字体格式的详细信息，请参阅 [opentype 规范](/typography/opentype/spec/)。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-117">For details of the OpenType font format, see the [OpenType specification](/typography/opentype/spec/).</span></span>  
  
### <a name="advanced-typographic-extensions"></a><span data-ttu-id="aa9cc-118">高级版式扩展</span><span class="sxs-lookup"><span data-stu-id="aa9cc-118">Advanced Typographic Extensions</span></span>  

 <span data-ttu-id="aa9cc-119"> (OpenType 布局表格的高级版式表格) 通过 TrueType 或 CFF 轮廓扩展字体功能。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-119">The Advanced Typographic tables (OpenType Layout tables) extend the functionality of fonts with either TrueType or CFF outlines.</span></span> <span data-ttu-id="aa9cc-120">OpenType 布局字体包含扩展字体功能的其他信息，以支持高质量的国际版式。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-120">OpenType Layout fonts contain additional information that extends the capabilities of the fonts to support high-quality international typography.</span></span> <span data-ttu-id="aa9cc-121">大多数 OpenType 字体只公开了可用的全部 OpenType 功能的子集。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-121">Most OpenType fonts expose only a subset of the total OpenType features available.</span></span> <span data-ttu-id="aa9cc-122">OpenType 字体提供以下功能。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-122">OpenType fonts provide the following features.</span></span>  
  
- <span data-ttu-id="aa9cc-123">字符与字形之间的丰富映射，可支持连字、定位格式、备用项以及其他字体替换功能。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-123">Rich mapping between characters and glyphs that support ligatures, positional forms, alternates, and other font substitutions.</span></span>  
  
- <span data-ttu-id="aa9cc-124">支持二维定位和字形附加。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-124">Support for two-dimensional positioning and glyph attachment.</span></span>  
  
- <span data-ttu-id="aa9cc-125">字体中包含的显式脚本和语言信息，使文本处理应用程序可相应调整其行为。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-125">Explicit script and language information contained in font, so a text-processing application can adjust its behavior accordingly.</span></span>  
  
 <span data-ttu-id="aa9cc-126">Opentype 规范的 ["字体文件表"](https://www.microsoft.com/typography/otspec/otff.htm) 部分中更详细地介绍了 opentype 布局表。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-126">The OpenType Layout tables are described in more detail in the ["Font File Tables"](https://www.microsoft.com/typography/otspec/otff.htm) section of the OpenType specification.</span></span>  
  
 <span data-ttu-id="aa9cc-127">本概述的其余部分介绍了由对象的属性公开的一些视觉对象 OpenType 功能的广度和灵活性 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-127">The remainder of this overview introduces the breadth and flexibility of some of the visually-interesting OpenType features that are exposed by the properties of the <xref:System.Windows.Documents.Typography> object.</span></span> <span data-ttu-id="aa9cc-128">有关此对象的详细信息，请参阅[版式类](#typography_class)。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-128">For more information on this object, see [Typography Class](#typography_class).</span></span>  
  
<a name="variants"></a>

## <a name="variants"></a><span data-ttu-id="aa9cc-129">变量</span><span class="sxs-lookup"><span data-stu-id="aa9cc-129">Variants</span></span>  

 <span data-ttu-id="aa9cc-130">变量用于呈现不同的版式风格，例如上标和下标。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-130">Variants are used to render different typographic styles, such as superscripts and subscripts.</span></span>  
  
### <a name="superscripts-and-subscripts"></a><span data-ttu-id="aa9cc-131">上标和下标</span><span class="sxs-lookup"><span data-stu-id="aa9cc-131">Superscripts and Subscripts</span></span>  

 <span data-ttu-id="aa9cc-132"><xref:System.Windows.Documents.Typography.Variants%2A>属性允许您设置 OpenType 字体的上标和下标值。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-132">The <xref:System.Windows.Documents.Typography.Variants%2A> property allows you to set superscript and subscript values for an OpenType font.</span></span>  
  
 <span data-ttu-id="aa9cc-133">以下文本显示 Palatino Linotype 字体的上标。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-133">The following text displays superscripts for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="aa9cc-134">![使用 OpenType 上标的文本](./media/opentype-font-features/opentype-superscripts.gif "使用 OpenType 上标的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-134">![Text using OpenType superscripts](./media/opentype-font-features/opentype-superscripts.gif "Text using OpenType superscripts")</span></span>  
  
 <span data-ttu-id="aa9cc-135">以下标记示例演示如何使用对象的属性定义 Palatino Linotype 字体的上标 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-135">The following markup example shows how to define superscripts for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 <span data-ttu-id="aa9cc-136">以下文本显示 Palatino Linotype 字体的下标。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-136">The following text displays subscripts for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="aa9cc-137">![使用 OpenType 下标的文本](./media/opentype-font-features/opentype-subscripts.gif "使用 OpenType 下标的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-137">![Text using OpenType subscripts](./media/opentype-font-features/opentype-subscripts.gif "Text using OpenType subscripts")</span></span>  
  
 <span data-ttu-id="aa9cc-138">以下标记示例演示如何使用对象的属性定义 Palatino Linotype 字体的下标 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-138">The following markup example shows how to define subscripts for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a><span data-ttu-id="aa9cc-139">上标和下标的修饰用法</span><span class="sxs-lookup"><span data-stu-id="aa9cc-139">Decorative Uses of Superscripts and Subscripts</span></span>  

 <span data-ttu-id="aa9cc-140">也可使用上标和下标来营造混合大小写文本的修饰效果。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-140">You can also use superscripts and subscripts to create decorative effects of mixed case text.</span></span> <span data-ttu-id="aa9cc-141">以下文本显示 Palatino Linotype 字体的上标和下标文本。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-141">The following text displays superscript and subscript text for the Palatino Linotype font.</span></span> <span data-ttu-id="aa9cc-142">注意，大写字母不受影响。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-142">Note that the capitals are not affected.</span></span>  
  
 <span data-ttu-id="aa9cc-143">![使用 OpenType 上标和下标的文本](./media/opentype-font-features/opentype-superscripts-subscripts.gif "使用 OpenType 上标和下标的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-143">![Text using OpenType superscripts and subscripts](./media/opentype-font-features/opentype-superscripts-subscripts.gif "Text using OpenType superscripts and subscripts")</span></span>  

 <span data-ttu-id="aa9cc-144">以下标记示例演示如何使用对象的属性为字体定义上标和下标 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-144">The following markup example shows how to define superscripts and subscripts for a font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>

## <a name="capitals"></a><span data-ttu-id="aa9cc-145">大写字母</span><span class="sxs-lookup"><span data-stu-id="aa9cc-145">Capitals</span></span>  

 <span data-ttu-id="aa9cc-146">大写字母是一组以大写样式字形呈现文本的版式形式。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-146">Capitals are a set of typographical forms that render text in capital-styled glyphs.</span></span> <span data-ttu-id="aa9cc-147">通常情况下，当以全大写呈现文本时，字母之间的间距可能看起来很小，字母的权重和比例看起来会很大。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-147">Typically, when text is rendered as all capitals, the spacing between letters can appear too tight, and the weight and proportion of the letters too heavy.</span></span> <span data-ttu-id="aa9cc-148">对于大写字母，OpenType 支持多种样式格式，其中包括小型大写字母、小号大写字母、标题和大写字母间距。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-148">OpenType supports a number of styling formats for capitals, including small capitals, petite capitals, titling, and capital spacing.</span></span> <span data-ttu-id="aa9cc-149">通过这些样式格式可控制大写字母的外观。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-149">These styling formats allow you to control the appearance of capitals.</span></span>  
  
 <span data-ttu-id="aa9cc-150">以下文本显示 Pescadero 字体的标准大写字母，其后接样式为“SmallCaps”和“AllSmallCaps”的字母。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-150">The following text displays standard capital letters for the Pescadero font, followed by the letters styled as "SmallCaps" and "AllSmallCaps".</span></span> <span data-ttu-id="aa9cc-151">本例中，对所有三个单词均使用相同的字体大小。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-151">In this case, the same font size is used for all three words.</span></span>  
  
 <span data-ttu-id="aa9cc-152">![使用 OpenType 大写字母的文本](./media/opentype-font-features/opentype-capitals.gif "使用 OpenType 大写字母的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-152">![Text using OpenType capitals](./media/opentype-font-features/opentype-capitals.gif "Text using OpenType capitals")</span></span>  
  
 <span data-ttu-id="aa9cc-153">以下标记示例演示如何使用对象的属性定义 Pescadero 字体的大写字母 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-153">The following markup example shows how to define capitals for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span> <span data-ttu-id="aa9cc-154">使用“SmallCaps”格式时会忽略任何前导大写字母。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-154">When the "SmallCaps" format is used, any leading capital letter is ignored.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a><span data-ttu-id="aa9cc-155">标题大写字母</span><span class="sxs-lookup"><span data-stu-id="aa9cc-155">Titling Capitals</span></span>  

 <span data-ttu-id="aa9cc-156">标题大写字母权重和比例更小，外观比普通大写字母更加雅致。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-156">Titling capitals are lighter in weight and proportion and designed to give a more elegant look than normal capitals.</span></span> <span data-ttu-id="aa9cc-157">标题大写字母通常用于作为标题的大号字体中。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-157">Titling capitals are typically used in larger font sizes as headings.</span></span> <span data-ttu-id="aa9cc-158">以下文本显示 Pescadero 字体的普通大写字母和标题大写字母。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-158">The following text displays normal and titling capitals for the Pescadero font.</span></span> <span data-ttu-id="aa9cc-159">请注意第二行文本的宽度更窄。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-159">Notice the narrower stem widths of the text on the second line.</span></span>  
  
 <span data-ttu-id="aa9cc-160">![使用 OpenType 标题大写字母的文本](./media/opentype-font-features/opentype-titling-capitals.gif "使用 OpenType 标题大写字母的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-160">![Text using OpenType titling capitals](./media/opentype-font-features/opentype-titling-capitals.gif "Text using OpenType titling capitals")</span></span>  
  
 <span data-ttu-id="aa9cc-161">以下标记示例演示如何使用对象的属性定义 Pescadero 字体的标题大写字母 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-161">The following markup example shows how to define titling capitals for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet17](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a><span data-ttu-id="aa9cc-162">大写字母间距</span><span class="sxs-lookup"><span data-stu-id="aa9cc-162">Capital Spacing</span></span>  

 <span data-ttu-id="aa9cc-163">大写字母间距功能让你可以在使用全大写字母文本时提供更宽的间距。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-163">Capital spacing is a feature that allows you to provide more spacing when using all capitals in text.</span></span> <span data-ttu-id="aa9cc-164">大写字母通常设计为与小写字母混合使用。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-164">Capital letters are typically designed to blend with lowercase letters.</span></span> <span data-ttu-id="aa9cc-165">大写字母和小写字母之间看起来比较美观的间距在使用全大写字母时可能会显得过紧。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-165">Spacing that appears attractive between and a capital letter and a lowercase letter may look too tight when all capital letters are used.</span></span> <span data-ttu-id="aa9cc-166">以下文本显示 Pescadero 字体的普通间距和大写字母间距。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-166">The following text displays normal and capital spacing for the Pescadero font.</span></span>  
  
 <span data-ttu-id="aa9cc-167">![使用 OpenType 大写字母间距的文本](./media/opentype-font-features/opentype-capital-spacing.gif "使用 OpenType 大写字母间距的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-167">![Text using OpenType capital spacing](./media/opentype-font-features/opentype-capital-spacing.gif "Text using OpenType capital spacing")</span></span>  

 <span data-ttu-id="aa9cc-168">以下标记示例演示如何使用对象的属性定义 Pescadero 字体的大写字母间距 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-168">The following markup example shows how to define capital spacing for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet18](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>

## <a name="ligatures"></a><span data-ttu-id="aa9cc-169">连字</span><span class="sxs-lookup"><span data-stu-id="aa9cc-169">Ligatures</span></span>  

 <span data-ttu-id="aa9cc-170">连子是为使文本更具可读性或更加美观而由两个或更多字形形成的一个单一字形。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-170">Ligatures are two or more glyphs that are formed into a single glyph in order to create more readable or attractive text.</span></span> <span data-ttu-id="aa9cc-171">OpenType 字体支持四种类型的连字：</span><span class="sxs-lookup"><span data-stu-id="aa9cc-171">OpenType fonts support four types of ligatures:</span></span>  
  
- <span data-ttu-id="aa9cc-172">**标准连字**。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-172">**Standard ligatures**.</span></span> <span data-ttu-id="aa9cc-173">旨在增强可读性。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-173">Designed to enhance readability.</span></span> <span data-ttu-id="aa9cc-174">标准连字包括“fi”、“fl”和“ff”。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-174">Standard ligatures include "fi", "fl", and "ff".</span></span>  
  
- <span data-ttu-id="aa9cc-175">**上下文连字**。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-175">**Contextual ligatures**.</span></span> <span data-ttu-id="aa9cc-176">旨在通过在组成连字的字符之间提供更好的联结行为来增强可读性。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-176">Designed to enhance readability by providing better joining behavior between the characters that make up the ligature.</span></span>  
  
- <span data-ttu-id="aa9cc-177">**自由连字**。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-177">**Discretionary ligatures**.</span></span> <span data-ttu-id="aa9cc-178">重在修饰性，并非专为可读性而设计。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-178">Designed to be ornamental, and not specifically designed for readability.</span></span>  
  
- <span data-ttu-id="aa9cc-179">**历史连字**。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-179">**Historical ligatures**.</span></span> <span data-ttu-id="aa9cc-180">重在历史性，并非专为可读性而设计。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-180">Designed to be historical, and not specifically designed for readability.</span></span>  
  
 <span data-ttu-id="aa9cc-181">以下文本显示 Pericles 字体的标准连字字形。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-181">The following text displays standard ligature glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="aa9cc-182">![使用 OpenType 标准连字的文本](./media/opentype-font-features/opentype-standard-ligatures.gif "使用 OpenType 标准连字的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-182">![Text using OpenType standard ligatures](./media/opentype-font-features/opentype-standard-ligatures.gif "Text using OpenType standard ligatures")</span></span>  
  
 <span data-ttu-id="aa9cc-183">以下标记示例演示如何使用对象的属性定义 Pericles 字体的标准连字字形 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-183">The following markup example shows how to define standard ligature glyphs for the Pericles font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 <span data-ttu-id="aa9cc-184">以下文本显示 Pericles 字体的自由连字字形。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-184">The following text displays discretionary ligature glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="aa9cc-185">![使用 OpenType 自由连字的文本](./media/opentype-font-features/opentype-discretionary-ligatures.gif "使用 OpenType 自由连字的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-185">![Text using OpenType discretionary ligatures](./media/opentype-font-features/opentype-discretionary-ligatures.gif "Text using OpenType discretionary ligatures")</span></span>  
  
 <span data-ttu-id="aa9cc-186">以下标记示例演示如何使用对象的属性定义 Pericles 字体的自由连字字形 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-186">The following markup example shows how to define discretionary ligature glyphs for the Pericles font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 <span data-ttu-id="aa9cc-187">默认情况下，OpenType 字体会 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 启用标准连字。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-187">By default, OpenType fonts in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] enable standard ligatures.</span></span> <span data-ttu-id="aa9cc-188">例如，如果使用 Palatino Linotype 字体，则标准连字“fi”、“ff”和“fl”显示为组合字符字形。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-188">For example, if you use the Palatino Linotype font, the standard ligatures "fi", "ff", and "fl" appear as a combined character glyph.</span></span> <span data-ttu-id="aa9cc-189">请注意，每个标准连字的字符对之间彼此相连。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-189">Notice that the pair of characters for each standard ligature touch each other.</span></span>  
  
 <span data-ttu-id="aa9cc-190">![使用 OpenType 标准连字与 Palatino Linotype 的文本](./media/opentype-font-features/opentype-standard-ligatures-palatino.gif "使用 OpenType 标准连字与 Palatino Linotype 的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-190">![Text using OpenType standard ligatures with Palatino Linotype](./media/opentype-font-features/opentype-standard-ligatures-palatino.gif "Text using OpenType standard ligatures with Palatino Linotype")</span></span>

 <span data-ttu-id="aa9cc-191">但是，可禁用标准连字功能，从而使“ff”等标准连字显示为两个单独的字形，而不显示为一个组合字符字形。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-191">However, you can disable standard ligature features so that a standard ligature such as "ff" displays as two separate glyphs, rather than as a combined character glyph.</span></span>  
  
 <span data-ttu-id="aa9cc-192">![使用禁用的 OpenType 标准连字的文本](./media/opentype-font-features/disabled-opentype-standard-ligatures.gif "使用禁用的 OpenType 标准连字的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-192">![Text using disabled OpenType standard ligatures](./media/opentype-font-features/disabled-opentype-standard-ligatures.gif "Text using disabled OpenType standard ligatures")</span></span>  

 <span data-ttu-id="aa9cc-193">以下标记示例演示如何使用对象的属性来禁用 Palatino Linotype 字体的标准连字字形 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-193">The following markup example shows how to disable standard ligature glyphs for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>

## <a name="swashes"></a><span data-ttu-id="aa9cc-194">花体</span><span class="sxs-lookup"><span data-stu-id="aa9cc-194">Swashes</span></span>  

 <span data-ttu-id="aa9cc-195">花体是使用精美修饰的装饰性字形，通常与书法相关。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-195">Swashes are decorative glyphs that use elaborate ornamentation often associated with calligraphy.</span></span> <span data-ttu-id="aa9cc-196">以下文本显示 Pescadero 字体的标准和花体字形。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-196">The following text displays standard and swash glyphs for the Pescadero font.</span></span>  
  
 <span data-ttu-id="aa9cc-197">![使用 OpenType 标准字形和花体连字的文本](./media/opentype-font-features/opentype-standard-swash-glyphs.gif "使用 OpenType 标准和花体连字的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-197">![Text using OpenType standard and swash glyphs](./media/opentype-font-features/opentype-standard-swash-glyphs.gif "Text using OpenType standard and swash glyphs")</span></span>  

 <span data-ttu-id="aa9cc-198">花体通常用作事件公告等简短文章中的修饰元素。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-198">Swashes are often used as decorative elements in short phrases such as event announcements.</span></span> <span data-ttu-id="aa9cc-199">以下文本使用花体强调事件名称的大写字母。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-199">The following text uses swashes to emphasize the capital letters of the name of the event.</span></span>  
  
 <span data-ttu-id="aa9cc-200">![使用 OpenType 花体的文本](./media/opentype-font-features/opentype-swashes.gif "使用 OpenType 花体的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-200">![Text using OpenType swashes](./media/opentype-font-features/opentype-swashes.gif "Text using OpenType swashes")</span></span>  
  
 <span data-ttu-id="aa9cc-201">以下标记示例演示如何使用对象的属性为字体定义花体 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-201">The following markup example shows how to define swashes for a font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a><span data-ttu-id="aa9cc-202">连接形式花体</span><span class="sxs-lookup"><span data-stu-id="aa9cc-202">Contextual Swashes</span></span>  

 <span data-ttu-id="aa9cc-203">花体字形的某些组合可能导致文本外观欠佳，例如相邻字母的下行处出现重叠。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-203">Certain combinations of swash glyphs can cause an unattractive appearance, such as overlapping descenders on adjacent letters.</span></span> <span data-ttu-id="aa9cc-204">通过连接形式花体，可使用能生成更佳外观的替代花体字形。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-204">Using a contextual swash allows you to use a substitute swash glyph that produces a better appearance.</span></span> <span data-ttu-id="aa9cc-205">以下文本显示同一单词应用连接形式花体前后的外观。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-205">The following text shows the same word before and after a contextual swash is applied.</span></span>  
  
 <span data-ttu-id="aa9cc-206">![使用 OpenType 连接形式花体的文本](./media/opentype-font-features/opentype-contextual-swashes.gif "使用 OpenType 连接形式花体的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-206">![Text using OpenType contextual swashes](./media/opentype-font-features/opentype-contextual-swashes.gif "Text using OpenType contextual swashes")</span></span>  
  
 <span data-ttu-id="aa9cc-207">以下标记示例演示如何使用对象的属性定义 Pescadero 字体的上下文花体 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-207">The following markup example shows how to define a contextual swash for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet16](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>

## <a name="alternates"></a><span data-ttu-id="aa9cc-208">备用项</span><span class="sxs-lookup"><span data-stu-id="aa9cc-208">Alternates</span></span>  

 <span data-ttu-id="aa9cc-209">备用项是可替代标准字形的字形。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-209">Alternates are glyphs that can be substituted for a standard glyph.</span></span> <span data-ttu-id="aa9cc-210">OpenType 字体（如以下示例中使用的 Pericles 字体）可以包含可用于创建不同文本外观的备用标志符号。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-210">OpenType fonts, such as the Pericles font used in the following examples, can contain alternate glyphs that you can use to create different appearances for text.</span></span> <span data-ttu-id="aa9cc-211">以下文本显示 Pericles 字体的标准字形。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-211">The following text displays standard glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="aa9cc-212">![使用 OpenType 标准字形的文本](./media/opentype-font-features/opentype-standard-glyphs.gif "使用 OpenType 标准字形的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-212">![Text using OpenType standard glyphs](./media/opentype-font-features/opentype-standard-glyphs.gif "Text using OpenType standard glyphs")</span></span>  

 <span data-ttu-id="aa9cc-213">Pericles OpenType 字体包含其他一些标志符号，它们提供标准字形集的样式备用项。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-213">The Pericles OpenType font contains additional glyphs that provide stylistic alternates to the standard set of glyphs.</span></span> <span data-ttu-id="aa9cc-214">以下文本显示样式备用字形。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-214">The following text displays stylistic alternate glyphs.</span></span>  
  
 <span data-ttu-id="aa9cc-215">![使用 OpenType 样式备用标志符号的文本](./media/opentype-font-features/opentype-stylistic-alternate-glyphs.gif "使用 OpenType 样式备用标志符号的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-215">![Text using OpenType stylistic alternate glyphs](./media/opentype-font-features/opentype-stylistic-alternate-glyphs.gif "Text using OpenType stylistic alternate glyphs")</span></span>  
  
 <span data-ttu-id="aa9cc-216">以下标记示例演示如何使用对象的属性定义 Pericles 字体的样式备用标志符号 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-216">The following markup example shows how to define stylistic alternate glyphs for the Pericles font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 <span data-ttu-id="aa9cc-217">以下文本显示 Pericles 字体的几种其他样式备用字形。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-217">The following text displays several other stylistic alternate glyphs for the Pericles font.</span></span>  
  
 <span data-ttu-id="aa9cc-218">![使用 Pericles 字体的 OpenType 样式备用标志符号的文本](./media/opentype-font-features/opentype-stylistic-alternate-glyphs-pericles.gif "使用 Pericles 字体的 OpenType 样式备用标志符号的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-218">![Text using OpenType stylistic alternate glyphs  for the Pericles font](./media/opentype-font-features/opentype-stylistic-alternate-glyphs-pericles.gif "Text using OpenType stylistic alternate glyphs  for the Pericles font")</span></span>

 <span data-ttu-id="aa9cc-219">以下标记示例演示如何定义其他样式备用字形。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-219">The following markup example shows how to define these other stylistic alternate glyphs.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a><span data-ttu-id="aa9cc-220">随机备用连接形式</span><span class="sxs-lookup"><span data-stu-id="aa9cc-220">Random Contextual Alternates</span></span>  

 <span data-ttu-id="aa9cc-221">随机备用连接形式为单个字符提供多种备用字形。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-221">Random contextual alternates provide multiple substitute glyphs for a single character.</span></span> <span data-ttu-id="aa9cc-222">实现脚本类型字体时，此功能可通过使用一组随机选择的外观稍有差异的字形来模拟手写内容。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-222">When implemented with script-type fonts, this feature can simulate handwriting by using of a set of randomly chosen glyphs with slight differences in appearance.</span></span> <span data-ttu-id="aa9cc-223">以下文本使用 Lindsey 字体的随机备用连接形式。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-223">The following text uses random contextual alternates for the Lindsey font.</span></span> <span data-ttu-id="aa9cc-224">请注意字母“a”外观稍有变化</span><span class="sxs-lookup"><span data-stu-id="aa9cc-224">Notice that the letter "a" varies slightly in appearance</span></span>  
  
 <span data-ttu-id="aa9cc-225">![使用 OpenType 随机备用连接形式的文本](./media/opentype-font-features/opentype-random-contextual-alternates.gif "使用 OpenType 随机备用连接形式的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-225">![Text using OpenType random contextual alternates](./media/opentype-font-features/opentype-random-contextual-alternates.gif "Text using OpenType random contextual alternates")</span></span>  
  
 <span data-ttu-id="aa9cc-226">以下标记示例演示如何使用对象的属性定义 Lindsey 字体的随机上下文备用项 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-226">The following markup example shows how to define random contextual alternates for the Lindsey font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet20](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a><span data-ttu-id="aa9cc-227">历史形式</span><span class="sxs-lookup"><span data-stu-id="aa9cc-227">Historical Forms</span></span>  

 <span data-ttu-id="aa9cc-228">历史形式指过去常见的版式约定。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-228">Historical forms are typographic conventions that were common in the past.</span></span> <span data-ttu-id="aa9cc-229">以下文本使用 Palatino Linotype 字体的一种历史字形形式显示短语“Boston, Massachusetts”。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-229">The following text displays the phrase, "Boston, Massachusetts", using an historical form of glyphs for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="aa9cc-230">![使用 OpenType 历史形式的文本](./media/opentype-font-features/opentype-historical-forms.gif "使用 OpenType 历史形式的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-230">![Text using OpenType historical forms](./media/opentype-font-features/opentype-historical-forms.gif "Text using OpenType historical forms")</span></span>  

 <span data-ttu-id="aa9cc-231">以下标记示例演示如何使用对象的属性定义 Palatino Linotype 字体的历史窗体 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-231">The following markup example shows how to define historical forms for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>

## <a name="numerical-styles"></a><span data-ttu-id="aa9cc-232">数字样式</span><span class="sxs-lookup"><span data-stu-id="aa9cc-232">Numerical Styles</span></span>  

 <span data-ttu-id="aa9cc-233">OpenType 字体支持多种可用于文本中数值的功能。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-233">OpenType fonts support a large number of features that can be used with numerical values in text.</span></span>  
  
### <a name="fractions"></a><span data-ttu-id="aa9cc-234">分数</span><span class="sxs-lookup"><span data-stu-id="aa9cc-234">Fractions</span></span>  

 <span data-ttu-id="aa9cc-235">OpenType 字体支持分数样式，包括斜杠和堆积样式。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-235">OpenType fonts support styles for fractions, including slashed and stacked.</span></span>  
  
 <span data-ttu-id="aa9cc-236">以下文本显示 Palatino Linotype 字体的分数样式。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-236">The following text displays fraction styles for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="aa9cc-237">![使用 OpenType 横式分数和竖式分数的文本](./media/opentype-font-features/opentype-slashed-stacked-fractions.gif "使用 OpenType 横式分数和竖式分数的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-237">![Text using OpenType slashed and stacked fractions](./media/opentype-font-features/opentype-slashed-stacked-fractions.gif "Text using OpenType slashed and stacked fractions")</span></span>  

 <span data-ttu-id="aa9cc-238">以下标记示例演示如何使用对象的属性定义 Palatino Linotype 字体的分数样式 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-238">The following markup example shows how to define fraction styles for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a><span data-ttu-id="aa9cc-239">旧样式数字</span><span class="sxs-lookup"><span data-stu-id="aa9cc-239">Old Style Numerals</span></span>  

 <span data-ttu-id="aa9cc-240">OpenType 字体支持旧样式数字格式。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-240">OpenType fonts support an old style numeral format.</span></span> <span data-ttu-id="aa9cc-241">此格式对于显示不再是标准样式的数字非常有用。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-241">This format is useful for displaying numerals in styles that are no longer standard.</span></span> <span data-ttu-id="aa9cc-242">以下文本以 Palatino Linotype 字体的标准和旧样式数字格式显示 18 世纪日期。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-242">The following text displays an 18th century date in standard and old style numeral formats for the Palatino Linotype font.</span></span>  
  
 <span data-ttu-id="aa9cc-243">![使用 OpenType 旧样式数字的文本](./media/opentype-font-features/opentype-old-style-numerals.gif "使用 OpenType 旧样式数字的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-243">![Text using OpenType old style numerals](./media/opentype-font-features/opentype-old-style-numerals.gif "Text using OpenType old style numerals")</span></span>  

 <span data-ttu-id="aa9cc-244">以下文本显示 Palatino Linotype 字体的标准数字，后跟旧样式数字。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-244">The following text displays standard numerals for the Palatino Linotype font, followed by old style numerals.</span></span>  
  
 <span data-ttu-id="aa9cc-245">![使用 OpenType 旧样式数字集的文本](./media/opentype-font-features/opentype-old-style-numeral-sets.gif "使用 OpenType 旧样式数字集的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-245">![Text using OpenType old style numeral sets](./media/opentype-font-features/opentype-old-style-numeral-sets.gif "Text using OpenType old style numeral sets")</span></span>  
  
 <span data-ttu-id="aa9cc-246">以下标记示例演示如何使用对象的属性定义 Palatino Linotype 字体的旧样式数字 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-246">The following markup example shows how to define old style numerals for the Palatino Linotype font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a><span data-ttu-id="aa9cc-247">比例数字和表格式数字</span><span class="sxs-lookup"><span data-stu-id="aa9cc-247">Proportional and Tabular Figures</span></span>  

 <span data-ttu-id="aa9cc-248">OpenType 字体支持比例和表格格式的功能，可在使用数字时控制宽度的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-248">OpenType fonts support a proportional and tabular figure feature to control the alignment of widths when using numerals.</span></span> <span data-ttu-id="aa9cc-249">比例数字将每个数字视为具有不同的宽度—“1”窄于“5”。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-249">Proportional figures treat each numeral as having a different width—"1" is narrower than "5".</span></span> <span data-ttu-id="aa9cc-250">表格式数字被视为宽度相等的数字，因此它们可垂直对齐，从而增强财务类型信息的可读性。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-250">Tabular figures are treated as equal-width numerals so that they align vertically, which increases the readability of financial type information.</span></span>  
  
 <span data-ttu-id="aa9cc-251">以下文本使用 Miramonte 字体显示第一列中的两个表格式数字。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-251">The following text displays two proportional figures in the first column using the Miramonte font.</span></span> <span data-ttu-id="aa9cc-252">请注意数字“5”和“1”之间的宽度差异。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-252">Note the difference in width between the numerals "5" and "1".</span></span> <span data-ttu-id="aa9cc-253">第二列显示相同的两个数值，并通过使用表格式数字功能调整其宽度。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-253">The second column shows the same two numeric values with the widths adjusted by using the tabular figure feature.</span></span>  
  
 <span data-ttu-id="aa9cc-254">![使用 OpenType 比例数字和表格式数字的文本](./media/opentype-font-features/opentype-proportional-tabular-figures.gif "使用 OpenType 比例数字和表格式数字的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-254">![Text using OpenType proportional & tabular figures](./media/opentype-font-features/opentype-proportional-tabular-figures.gif "Text using OpenType proportional and tabular figures")</span></span>  

 <span data-ttu-id="aa9cc-255">以下标记示例演示如何使用对象的属性定义 Miramonte 字体的比例和表格数字 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-255">The following markup example shows how to define proportional and tabular figures for the Miramonte font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet19](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a><span data-ttu-id="aa9cc-256">斜线零</span><span class="sxs-lookup"><span data-stu-id="aa9cc-256">Slashed Zero</span></span>  

 <span data-ttu-id="aa9cc-257">OpenType 字体支持斜杠零数字格式，以强调字母 "O" 和数字 "0" 之间的差异。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-257">OpenType fonts support a slashed zero numeral format to emphasize the difference between the letter "O" and the numeral "0".</span></span> <span data-ttu-id="aa9cc-258">斜线零数字通常用于财务和商务信息中的标识符。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-258">The slashed zero numeral is often used for identifiers in financial and business information.</span></span>  
  
 <span data-ttu-id="aa9cc-259">以下文本显示使用 Miramonte 字体的订单标识符。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-259">The following text displays a sample order identifier using the Miramonte font.</span></span> <span data-ttu-id="aa9cc-260">第一行使用标准数字。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-260">The first line uses standard numerals.</span></span> <span data-ttu-id="aa9cc-261">第二行使用斜线零数字，以便更易于与大写字母“O”进行区分。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-261">The second line used slashed zero numerals to provide better contrast with the uppercase "O" letter.</span></span>  
  
 <span data-ttu-id="aa9cc-262">![使用 OpenType 斜线零数字的文本](./media/opentype-font-features/opentype-slashed-zero-numerals.gif "使用 OpenType 斜线零数字的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-262">![Text using OpenType slashed zero numerals](./media/opentype-font-features/opentype-slashed-zero-numerals.gif "Text using OpenType slashed zero numerals")</span></span>  

 <span data-ttu-id="aa9cc-263">以下标记示例演示如何使用对象的属性定义 Miramonte 字体的斜杠零数字 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-263">The following markup example shows how to define slashed zero numerals for the Miramonte font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>

## <a name="typography-class"></a><span data-ttu-id="aa9cc-264">版式类</span><span class="sxs-lookup"><span data-stu-id="aa9cc-264">Typography Class</span></span>  

 <span data-ttu-id="aa9cc-265"><xref:System.Windows.Documents.Typography>对象公开 OpenType 字体支持的一组功能。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-265">The <xref:System.Windows.Documents.Typography> object exposes the set of features that an OpenType font supports.</span></span> <span data-ttu-id="aa9cc-266">通过 <xref:System.Windows.Documents.Typography> 在标记中设置的属性，可轻松创作利用 OpenType 功能的文档。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-266">By setting the properties of <xref:System.Windows.Documents.Typography> in markup, you can easily author documents that take advantage of OpenType features.</span></span>  
  
 <span data-ttu-id="aa9cc-267">以下文本显示 Pescadero 字体的标准大写字母，其后接样式为“SmallCaps”和“AllSmallCaps”的字母。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-267">The following text displays standard capital letters for the Pescadero font, followed by the letters styled as "SmallCaps" and "AllSmallCaps".</span></span> <span data-ttu-id="aa9cc-268">本例中，对所有三个单词均使用相同的字体大小。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-268">In this case, the same font size is used for all three words.</span></span>  
  
 <span data-ttu-id="aa9cc-269">![使用 OpenType 大写字母的文本](./media/opentype-font-features/opentype-capitals.gif "使用 OpenType 大写字母的文本")</span><span class="sxs-lookup"><span data-stu-id="aa9cc-269">![Text using OpenType capitals](./media/opentype-font-features/opentype-capitals.gif "Text using OpenType capitals")</span></span>  

 <span data-ttu-id="aa9cc-270">以下标记示例演示如何使用对象的属性定义 Pescadero 字体的大写字母 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-270">The following markup example shows how to define capitals for the Pescadero font, using properties of the <xref:System.Windows.Documents.Typography> object.</span></span> <span data-ttu-id="aa9cc-271">使用“SmallCaps”格式时会忽略任何前导大写字母。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-271">When the "SmallCaps" format is used, any leading capital letter is ignored.</span></span>  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 <span data-ttu-id="aa9cc-272">以下代码示例完成与先前的标记事例相同的任务。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-272">The following code example accomplishes the same task as the previous markup example.</span></span>  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a><span data-ttu-id="aa9cc-273">版式类属性</span><span class="sxs-lookup"><span data-stu-id="aa9cc-273">Typography Class Properties</span></span>  

 <span data-ttu-id="aa9cc-274">下表列出了对象的属性、值和默认设置 <xref:System.Windows.Documents.Typography> 。</span><span class="sxs-lookup"><span data-stu-id="aa9cc-274">The following table lists the properties, values, and default settings of the <xref:System.Windows.Documents.Typography> object.</span></span>  
  
|<span data-ttu-id="aa9cc-275">properties</span><span class="sxs-lookup"><span data-stu-id="aa9cc-275">Property</span></span>|<span data-ttu-id="aa9cc-276">值</span><span class="sxs-lookup"><span data-stu-id="aa9cc-276">Value(s)</span></span>|<span data-ttu-id="aa9cc-277">默认值</span><span class="sxs-lookup"><span data-stu-id="aa9cc-277">Default Value</span></span>|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|<span data-ttu-id="aa9cc-278">数值 - 字节</span><span class="sxs-lookup"><span data-stu-id="aa9cc-278">Numeric value - byte</span></span>|<span data-ttu-id="aa9cc-279">0</span><span class="sxs-lookup"><span data-stu-id="aa9cc-279">0</span></span>|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<span data-ttu-id="aa9cc-280"><xref:System.Windows.FontCapitals.AllPetiteCaps> &#124; <xref:System.Windows.FontCapitals.AllSmallCaps> &#124; <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> &#124; <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; <xref:System.Windows.FontCapitals.Unicase></span><span class="sxs-lookup"><span data-stu-id="aa9cc-280"><xref:System.Windows.FontCapitals.AllPetiteCaps> &#124; <xref:System.Windows.FontCapitals.AllSmallCaps> &#124; <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> &#124; <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; <xref:System.Windows.FontCapitals.Unicase></span></span>|<xref:System.Windows.FontCapitals.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|<span data-ttu-id="aa9cc-281">数值 - 字节</span><span class="sxs-lookup"><span data-stu-id="aa9cc-281">Numeric value - byte</span></span>|<span data-ttu-id="aa9cc-282">0</span><span class="sxs-lookup"><span data-stu-id="aa9cc-282">0</span></span>|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<span data-ttu-id="aa9cc-283"><xref:System.Windows.FontEastAsianLanguage.HojoKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; &#124; <xref:System.Windows.FontEastAsianLanguage.TraditionalNames></span><span class="sxs-lookup"><span data-stu-id="aa9cc-283"><xref:System.Windows.FontEastAsianLanguage.HojoKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> &#124; <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; <xref:System.Windows.FontEastAsianLanguage.TraditionalNames></span></span>|<xref:System.Windows.FontEastAsianLanguage.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<span data-ttu-id="aa9cc-284"><xref:System.Windows.FontEastAsianWidths.Full> &#124; <xref:System.Windows.FontEastAsianWidths.Half> &#124; <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> &#124; <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; <xref:System.Windows.FontEastAsianWidths.Third></span><span class="sxs-lookup"><span data-stu-id="aa9cc-284"><xref:System.Windows.FontEastAsianWidths.Full> &#124; <xref:System.Windows.FontEastAsianWidths.Half> &#124; <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> &#124; <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; <xref:System.Windows.FontEastAsianWidths.Third></span></span>|<xref:System.Windows.FontEastAsianWidths.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.Fraction%2A>|<span data-ttu-id="aa9cc-285"><xref:System.Windows.FontFraction.Normal> &#124; <xref:System.Windows.FontFraction.Slashed> &#124; <xref:System.Windows.FontFraction.Stacked></span><span class="sxs-lookup"><span data-stu-id="aa9cc-285"><xref:System.Windows.FontFraction.Normal> &#124; <xref:System.Windows.FontFraction.Slashed> &#124; <xref:System.Windows.FontFraction.Stacked></span></span>|<xref:System.Windows.FontFraction.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.HistoricalForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.HistoricalLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Kerning%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.MathematicalGreek%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.NumeralAlignment%2A>|<span data-ttu-id="aa9cc-286"><xref:System.Windows.FontNumeralAlignment.Normal> &#124; <xref:System.Windows.FontNumeralAlignment.Proportional> &#124; <xref:System.Windows.FontNumeralAlignment.Tabular></span><span class="sxs-lookup"><span data-stu-id="aa9cc-286"><xref:System.Windows.FontNumeralAlignment.Normal> &#124; <xref:System.Windows.FontNumeralAlignment.Proportional> &#124; <xref:System.Windows.FontNumeralAlignment.Tabular></span></span>|<xref:System.Windows.FontNumeralAlignment.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.NumeralStyle%2A>|<xref:System.Boolean>|<xref:System.Windows.FontNumeralStyle.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.SlashedZero%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StandardLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.StandardSwashes%2A>|<span data-ttu-id="aa9cc-287">数值 - 字节</span><span class="sxs-lookup"><span data-stu-id="aa9cc-287">numeric value – byte</span></span>|<span data-ttu-id="aa9cc-288">0</span><span class="sxs-lookup"><span data-stu-id="aa9cc-288">0</span></span>|  
|<xref:System.Windows.Documents.Typography.StylisticAlternates%2A>|<span data-ttu-id="aa9cc-289">数值 - 字节</span><span class="sxs-lookup"><span data-stu-id="aa9cc-289">numeric value – byte</span></span>|<span data-ttu-id="aa9cc-290">0</span><span class="sxs-lookup"><span data-stu-id="aa9cc-290">0</span></span>|  
|<xref:System.Windows.Documents.Typography.StylisticSet1%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet2%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet3%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet4%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet5%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet6%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet7%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet8%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet9%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet10%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet11%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet12%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet13%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet14%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet15%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet16%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet17%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet18%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet19%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet20%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Variants%2A>|<span data-ttu-id="aa9cc-291"><xref:System.Windows.FontVariants.Inferior> &#124; <xref:System.Windows.FontVariants.Normal> &#124; <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> &#124; <xref:System.Windows.FontVariants.Subscript> &#124; <xref:System.Windows.FontVariants.Superscript></span><span class="sxs-lookup"><span data-stu-id="aa9cc-291"><xref:System.Windows.FontVariants.Inferior> &#124; <xref:System.Windows.FontVariants.Normal> &#124; <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> &#124; <xref:System.Windows.FontVariants.Subscript> &#124; <xref:System.Windows.FontVariants.Superscript></span></span>|<xref:System.Windows.FontVariants.Normal?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="aa9cc-292">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa9cc-292">See also</span></span>

- <xref:System.Windows.Documents.Typography>
- [<span data-ttu-id="aa9cc-293">OpenType 规范</span><span class="sxs-lookup"><span data-stu-id="aa9cc-293">OpenType specification</span></span>](/typography/opentype/spec/)
- [<span data-ttu-id="aa9cc-294">WPF 中的版式</span><span class="sxs-lookup"><span data-stu-id="aa9cc-294">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="aa9cc-295">示例 OpenType 字体包</span><span class="sxs-lookup"><span data-stu-id="aa9cc-295">Sample OpenType Font Pack</span></span>](sample-opentype-font-pack.md)
- [<span data-ttu-id="aa9cc-296">将字体与应用程序一起打包</span><span class="sxs-lookup"><span data-stu-id="aa9cc-296">Packaging Fonts with Applications</span></span>](packaging-fonts-with-applications.md)
