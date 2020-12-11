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
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970962"
---
# <a name="opentype-font-features"></a>OpenType 字体功能

本主题概述了中的 OpenType 字体技术的一些重要功能 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。  
  
<a name="overview"></a>

## <a name="opentype-font-format"></a>OpenType 字体格式  

 OpenType 字体格式是 TrueType®字体格式的扩展，添加了对 PostScript 字体数据的支持。 OpenType 字体格式由 Microsoft 和 Adobe Corporation 共同开发。 OpenType 字体和支持 OpenType 字体的操作系统服务为用户提供了一种简单的方法来安装和使用字体，无论字体是否包含 TrueType 大纲或 CFF (PostScript) 大纲。  
  
 OpenType 字体格式解决了以下开发人员难题：  
  
- 更广泛的多平台支持。  
  
- 更出色的国际字符集支持。  
  
- 更优的字体数据保护。  
  
- 更小的文件大小，让字体发布更加高效。  
  
- 更广泛的高级版式控件支持。  
  
> [!NOTE]
> Windows SDK 包含一组可用于应用程序的示例 OpenType 字体 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。 这些字体提供本主题余下部分所述的大多数功能。 有关详细信息，请参阅[示例 OpenType 字体包](sample-opentype-font-pack.md)。  
  
有关 OpenType 字体格式的详细信息，请参阅 [opentype 规范](/typography/opentype/spec/)。  
  
### <a name="advanced-typographic-extensions"></a>高级版式扩展  

  (OpenType 布局表格的高级版式表格) 通过 TrueType 或 CFF 轮廓扩展字体功能。 OpenType 布局字体包含扩展字体功能的其他信息，以支持高质量的国际版式。 大多数 OpenType 字体只公开了可用的全部 OpenType 功能的子集。 OpenType 字体提供以下功能。  
  
- 字符与字形之间的丰富映射，可支持连字、定位格式、备用项以及其他字体替换功能。  
  
- 支持二维定位和字形附加。  
  
- 字体中包含的显式脚本和语言信息，使文本处理应用程序可相应调整其行为。  
  
 Opentype 规范的 ["字体文件表"](https://www.microsoft.com/typography/otspec/otff.htm) 部分中更详细地介绍了 opentype 布局表。  
  
 本概述的其余部分介绍了由对象的属性公开的一些视觉对象 OpenType 功能的广度和灵活性 <xref:System.Windows.Documents.Typography> 。 有关此对象的详细信息，请参阅[版式类](#typography_class)。  
  
<a name="variants"></a>

## <a name="variants"></a>变量  

 变量用于呈现不同的版式风格，例如上标和下标。  
  
### <a name="superscripts-and-subscripts"></a>上标和下标  

 <xref:System.Windows.Documents.Typography.Variants%2A>属性允许您设置 OpenType 字体的上标和下标值。  
  
 以下文本显示 Palatino Linotype 字体的上标。  
  
 ![使用 OpenType 上标的文本](./media/opentype-font-features/opentype-superscripts.gif "使用 OpenType 上标的文本")  
  
 以下标记示例演示如何使用对象的属性定义 Palatino Linotype 字体的上标 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 以下文本显示 Palatino Linotype 字体的下标。  
  
 ![使用 OpenType 下标的文本](./media/opentype-font-features/opentype-subscripts.gif "使用 OpenType 下标的文本")  
  
 以下标记示例演示如何使用对象的属性定义 Palatino Linotype 字体的下标 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a>上标和下标的修饰用法  

 也可使用上标和下标来营造混合大小写文本的修饰效果。 以下文本显示 Palatino Linotype 字体的上标和下标文本。 注意，大写字母不受影响。  
  
 ![使用 OpenType 上标和下标的文本](./media/opentype-font-features/opentype-superscripts-subscripts.gif "使用 OpenType 上标和下标的文本")  

 以下标记示例演示如何使用对象的属性为字体定义上标和下标 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>

## <a name="capitals"></a>大写字母  

 大写字母是一组以大写样式字形呈现文本的版式形式。 通常情况下，当以全大写呈现文本时，字母之间的间距可能看起来很小，字母的权重和比例看起来会很大。 对于大写字母，OpenType 支持多种样式格式，其中包括小型大写字母、小号大写字母、标题和大写字母间距。 通过这些样式格式可控制大写字母的外观。  
  
 以下文本显示 Pescadero 字体的标准大写字母，其后接样式为“SmallCaps”和“AllSmallCaps”的字母。 本例中，对所有三个单词均使用相同的字体大小。  
  
 ![使用 OpenType 大写字母的文本](./media/opentype-font-features/opentype-capitals.gif "使用 OpenType 大写字母的文本")  
  
 以下标记示例演示如何使用对象的属性定义 Pescadero 字体的大写字母 <xref:System.Windows.Documents.Typography> 。 使用“SmallCaps”格式时会忽略任何前导大写字母。  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a>标题大写字母  

 标题大写字母权重和比例更小，外观比普通大写字母更加雅致。 标题大写字母通常用于作为标题的大号字体中。 以下文本显示 Pescadero 字体的普通大写字母和标题大写字母。 请注意第二行文本的宽度更窄。  
  
 ![使用 OpenType 标题大写字母的文本](./media/opentype-font-features/opentype-titling-capitals.gif "使用 OpenType 标题大写字母的文本")  
  
 以下标记示例演示如何使用对象的属性定义 Pescadero 字体的标题大写字母 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet17](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a>大写字母间距  

 大写字母间距功能让你可以在使用全大写字母文本时提供更宽的间距。 大写字母通常设计为与小写字母混合使用。 大写字母和小写字母之间看起来比较美观的间距在使用全大写字母时可能会显得过紧。 以下文本显示 Pescadero 字体的普通间距和大写字母间距。  
  
 ![使用 OpenType 大写字母间距的文本](./media/opentype-font-features/opentype-capital-spacing.gif "使用 OpenType 大写字母间距的文本")  

 以下标记示例演示如何使用对象的属性定义 Pescadero 字体的大写字母间距 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet18](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>

## <a name="ligatures"></a>连字  

 连子是为使文本更具可读性或更加美观而由两个或更多字形形成的一个单一字形。 OpenType 字体支持四种类型的连字：  
  
- **标准连字**。 旨在增强可读性。 标准连字包括“fi”、“fl”和“ff”。  
  
- **上下文连字**。 旨在通过在组成连字的字符之间提供更好的联结行为来增强可读性。  
  
- **自由连字**。 重在修饰性，并非专为可读性而设计。  
  
- **历史连字**。 重在历史性，并非专为可读性而设计。  
  
 以下文本显示 Pericles 字体的标准连字字形。  
  
 ![使用 OpenType 标准连字的文本](./media/opentype-font-features/opentype-standard-ligatures.gif "使用 OpenType 标准连字的文本")  
  
 以下标记示例演示如何使用对象的属性定义 Pericles 字体的标准连字字形 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 以下文本显示 Pericles 字体的自由连字字形。  
  
 ![使用 OpenType 自由连字的文本](./media/opentype-font-features/opentype-discretionary-ligatures.gif "使用 OpenType 自由连字的文本")  
  
 以下标记示例演示如何使用对象的属性定义 Pericles 字体的自由连字字形 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 默认情况下，OpenType 字体会 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 启用标准连字。 例如，如果使用 Palatino Linotype 字体，则标准连字“fi”、“ff”和“fl”显示为组合字符字形。 请注意，每个标准连字的字符对之间彼此相连。  
  
 ![使用 OpenType 标准连字与 Palatino Linotype 的文本](./media/opentype-font-features/opentype-standard-ligatures-palatino.gif "使用 OpenType 标准连字与 Palatino Linotype 的文本")

 但是，可禁用标准连字功能，从而使“ff”等标准连字显示为两个单独的字形，而不显示为一个组合字符字形。  
  
 ![使用禁用的 OpenType 标准连字的文本](./media/opentype-font-features/disabled-opentype-standard-ligatures.gif "使用禁用的 OpenType 标准连字的文本")  

 以下标记示例演示如何使用对象的属性来禁用 Palatino Linotype 字体的标准连字字形 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>

## <a name="swashes"></a>花体  

 花体是使用精美修饰的装饰性字形，通常与书法相关。 以下文本显示 Pescadero 字体的标准和花体字形。  
  
 ![使用 OpenType 标准字形和花体连字的文本](./media/opentype-font-features/opentype-standard-swash-glyphs.gif "使用 OpenType 标准和花体连字的文本")  

 花体通常用作事件公告等简短文章中的修饰元素。 以下文本使用花体强调事件名称的大写字母。  
  
 ![使用 OpenType 花体的文本](./media/opentype-font-features/opentype-swashes.gif "使用 OpenType 花体的文本")  
  
 以下标记示例演示如何使用对象的属性为字体定义花体 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a>连接形式花体  

 花体字形的某些组合可能导致文本外观欠佳，例如相邻字母的下行处出现重叠。 通过连接形式花体，可使用能生成更佳外观的替代花体字形。 以下文本显示同一单词应用连接形式花体前后的外观。  
  
 ![使用 OpenType 连接形式花体的文本](./media/opentype-font-features/opentype-contextual-swashes.gif "使用 OpenType 连接形式花体的文本")  
  
 以下标记示例演示如何使用对象的属性定义 Pescadero 字体的上下文花体 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet16](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>

## <a name="alternates"></a>备用项  

 备用项是可替代标准字形的字形。 OpenType 字体（如以下示例中使用的 Pericles 字体）可以包含可用于创建不同文本外观的备用标志符号。 以下文本显示 Pericles 字体的标准字形。  
  
 ![使用 OpenType 标准字形的文本](./media/opentype-font-features/opentype-standard-glyphs.gif "使用 OpenType 标准字形的文本")  

 Pericles OpenType 字体包含其他一些标志符号，它们提供标准字形集的样式备用项。 以下文本显示样式备用字形。  
  
 ![使用 OpenType 样式备用标志符号的文本](./media/opentype-font-features/opentype-stylistic-alternate-glyphs.gif "使用 OpenType 样式备用标志符号的文本")  
  
 以下标记示例演示如何使用对象的属性定义 Pericles 字体的样式备用标志符号 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 以下文本显示 Pericles 字体的几种其他样式备用字形。  
  
 ![使用 Pericles 字体的 OpenType 样式备用标志符号的文本](./media/opentype-font-features/opentype-stylistic-alternate-glyphs-pericles.gif "使用 Pericles 字体的 OpenType 样式备用标志符号的文本")

 以下标记示例演示如何定义其他样式备用字形。  
  
 [!code-xaml[OpenTypeFontSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a>随机备用连接形式  

 随机备用连接形式为单个字符提供多种备用字形。 实现脚本类型字体时，此功能可通过使用一组随机选择的外观稍有差异的字形来模拟手写内容。 以下文本使用 Lindsey 字体的随机备用连接形式。 请注意字母“a”外观稍有变化  
  
 ![使用 OpenType 随机备用连接形式的文本](./media/opentype-font-features/opentype-random-contextual-alternates.gif "使用 OpenType 随机备用连接形式的文本")  
  
 以下标记示例演示如何使用对象的属性定义 Lindsey 字体的随机上下文备用项 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet20](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a>历史形式  

 历史形式指过去常见的版式约定。 以下文本使用 Palatino Linotype 字体的一种历史字形形式显示短语“Boston, Massachusetts”。  
  
 ![使用 OpenType 历史形式的文本](./media/opentype-font-features/opentype-historical-forms.gif "使用 OpenType 历史形式的文本")  

 以下标记示例演示如何使用对象的属性定义 Palatino Linotype 字体的历史窗体 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>

## <a name="numerical-styles"></a>数字样式  

 OpenType 字体支持多种可用于文本中数值的功能。  
  
### <a name="fractions"></a>分数  

 OpenType 字体支持分数样式，包括斜杠和堆积样式。  
  
 以下文本显示 Palatino Linotype 字体的分数样式。  
  
 ![使用 OpenType 横式分数和竖式分数的文本](./media/opentype-font-features/opentype-slashed-stacked-fractions.gif "使用 OpenType 横式分数和竖式分数的文本")  

 以下标记示例演示如何使用对象的属性定义 Palatino Linotype 字体的分数样式 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a>旧样式数字  

 OpenType 字体支持旧样式数字格式。 此格式对于显示不再是标准样式的数字非常有用。 以下文本以 Palatino Linotype 字体的标准和旧样式数字格式显示 18 世纪日期。  
  
 ![使用 OpenType 旧样式数字的文本](./media/opentype-font-features/opentype-old-style-numerals.gif "使用 OpenType 旧样式数字的文本")  

 以下文本显示 Palatino Linotype 字体的标准数字，后跟旧样式数字。  
  
 ![使用 OpenType 旧样式数字集的文本](./media/opentype-font-features/opentype-old-style-numeral-sets.gif "使用 OpenType 旧样式数字集的文本")  
  
 以下标记示例演示如何使用对象的属性定义 Palatino Linotype 字体的旧样式数字 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a>比例数字和表格式数字  

 OpenType 字体支持比例和表格格式的功能，可在使用数字时控制宽度的对齐方式。 比例数字将每个数字视为具有不同的宽度—“1”窄于“5”。 表格式数字被视为宽度相等的数字，因此它们可垂直对齐，从而增强财务类型信息的可读性。  
  
 以下文本使用 Miramonte 字体显示第一列中的两个表格式数字。 请注意数字“5”和“1”之间的宽度差异。 第二列显示相同的两个数值，并通过使用表格式数字功能调整其宽度。  
  
 ![使用 OpenType 比例数字和表格式数字的文本](./media/opentype-font-features/opentype-proportional-tabular-figures.gif "使用 OpenType 比例数字和表格式数字的文本")  

 以下标记示例演示如何使用对象的属性定义 Miramonte 字体的比例和表格数字 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet19](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a>斜线零  

 OpenType 字体支持斜杠零数字格式，以强调字母 "O" 和数字 "0" 之间的差异。 斜线零数字通常用于财务和商务信息中的标识符。  
  
 以下文本显示使用 Miramonte 字体的订单标识符。 第一行使用标准数字。 第二行使用斜线零数字，以便更易于与大写字母“O”进行区分。  
  
 ![使用 OpenType 斜线零数字的文本](./media/opentype-font-features/opentype-slashed-zero-numerals.gif "使用 OpenType 斜线零数字的文本")  

 以下标记示例演示如何使用对象的属性定义 Miramonte 字体的斜杠零数字 <xref:System.Windows.Documents.Typography> 。  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>

## <a name="typography-class"></a>版式类  

 <xref:System.Windows.Documents.Typography>对象公开 OpenType 字体支持的一组功能。 通过 <xref:System.Windows.Documents.Typography> 在标记中设置的属性，可轻松创作利用 OpenType 功能的文档。  
  
 以下文本显示 Pescadero 字体的标准大写字母，其后接样式为“SmallCaps”和“AllSmallCaps”的字母。 本例中，对所有三个单词均使用相同的字体大小。  
  
 ![使用 OpenType 大写字母的文本](./media/opentype-font-features/opentype-capitals.gif "使用 OpenType 大写字母的文本")  

 以下标记示例演示如何使用对象的属性定义 Pescadero 字体的大写字母 <xref:System.Windows.Documents.Typography> 。 使用“SmallCaps”格式时会忽略任何前导大写字母。  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 以下代码示例完成与先前的标记事例相同的任务。  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a>版式类属性  

 下表列出了对象的属性、值和默认设置 <xref:System.Windows.Documents.Typography> 。  
  
|properties|值|默认值|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|数值 - 字节|0|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<xref:System.Windows.FontCapitals.AllPetiteCaps> &#124; <xref:System.Windows.FontCapitals.AllSmallCaps> &#124; <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> &#124; <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; <xref:System.Windows.FontCapitals.Unicase>|<xref:System.Windows.FontCapitals.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|数值 - 字节|0|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<xref:System.Windows.FontEastAsianLanguage.HojoKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; &#124; <xref:System.Windows.FontEastAsianLanguage.TraditionalNames>|<xref:System.Windows.FontEastAsianLanguage.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<xref:System.Windows.FontEastAsianWidths.Full> &#124; <xref:System.Windows.FontEastAsianWidths.Half> &#124; <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> &#124; <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; <xref:System.Windows.FontEastAsianWidths.Third>|<xref:System.Windows.FontEastAsianWidths.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.Fraction%2A>|<xref:System.Windows.FontFraction.Normal> &#124; <xref:System.Windows.FontFraction.Slashed> &#124; <xref:System.Windows.FontFraction.Stacked>|<xref:System.Windows.FontFraction.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.HistoricalForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.HistoricalLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Kerning%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.MathematicalGreek%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.NumeralAlignment%2A>|<xref:System.Windows.FontNumeralAlignment.Normal> &#124; <xref:System.Windows.FontNumeralAlignment.Proportional> &#124; <xref:System.Windows.FontNumeralAlignment.Tabular>|<xref:System.Windows.FontNumeralAlignment.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.NumeralStyle%2A>|<xref:System.Boolean>|<xref:System.Windows.FontNumeralStyle.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.SlashedZero%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StandardLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.StandardSwashes%2A>|数值 - 字节|0|  
|<xref:System.Windows.Documents.Typography.StylisticAlternates%2A>|数值 - 字节|0|  
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
|<xref:System.Windows.Documents.Typography.Variants%2A>|<xref:System.Windows.FontVariants.Inferior> &#124; <xref:System.Windows.FontVariants.Normal> &#124; <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> &#124; <xref:System.Windows.FontVariants.Subscript> &#124; <xref:System.Windows.FontVariants.Superscript>|<xref:System.Windows.FontVariants.Normal?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Documents.Typography>
- [OpenType 规范](/typography/opentype/spec/)
- [WPF 中的版式](typography-in-wpf.md)
- [示例 OpenType 字体包](sample-opentype-font-pack.md)
- [将字体与应用程序一起打包](packaging-fonts-with-applications.md)
