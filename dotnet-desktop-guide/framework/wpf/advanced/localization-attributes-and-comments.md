---
title: 本地化特性和注释
ms.date: 03/30/2017
helpviewer_keywords:
- localization [WPF], attributes
- localization [WPF], comments
ms.assetid: ead2d9ac-b709-4ec1-a924-39927a29d02f
ms.openlocfilehash: 6b5d2a27169a2bb34bc410a8a85a6b576d36016d
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665609"
---
# <a name="localization-attributes-and-comments"></a><span data-ttu-id="2dce6-102">本地化特性和注释</span><span class="sxs-lookup"><span data-stu-id="2dce6-102">Localization Attributes and Comments</span></span>
[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="2dce6-103">本地化注释是 XAML 源代码内的属性，由开发人员提供，用于提供本地化规则和提示。</span><span class="sxs-lookup"><span data-stu-id="2dce6-103">localization comments are properties, inside XAML source code, supplied by developers to provide rules and hints for localization.</span></span> [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="2dce6-104">本地化注释包含两组信息：可本地化特性和任意形式的本地化注释。</span><span class="sxs-lookup"><span data-stu-id="2dce6-104">localization comments contain two sets of information: localizability attributes and free-form localization comments.</span></span> <span data-ttu-id="2dce6-105">可本地化特性由 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 本地化 API 用于指示哪些资源要进行本地化。</span><span class="sxs-lookup"><span data-stu-id="2dce6-105">Localizability attributes are used by the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Localization API to indicate which resources are to be localized.</span></span> <span data-ttu-id="2dce6-106">任意形式的注释是应用程序作者希望包含的任何信息。</span><span class="sxs-lookup"><span data-stu-id="2dce6-106">Free-form comments are any information that the application author wants to include.</span></span>  

<a name="Localizer_Comments_"></a>
## <a name="localization-comments"></a><span data-ttu-id="2dce6-107">本地化注释</span><span class="sxs-lookup"><span data-stu-id="2dce6-107">Localization Comments</span></span>  
 <span data-ttu-id="2dce6-108">如果标记应用程序作者对 XAML 中的特定元素（如对文本长度、字体系列或字体大小的约束）有要求，则可以将此信息传递给本地化人员，其中包含 XAML 代码中的注释。</span><span class="sxs-lookup"><span data-stu-id="2dce6-108">If markup application authors have requirements for specific elements in XAML, such as constraints on text length, font family, or font size, they can convey this information to localizers with comments in the XAML code.</span></span> <span data-ttu-id="2dce6-109">下面是用来向源代码中添加注释的过程：</span><span class="sxs-lookup"><span data-stu-id="2dce6-109">The process for adding comments to source code is as follows:</span></span>  
  
1. <span data-ttu-id="2dce6-110">应用程序开发人员将本地化注释添加到 XAML 源代码中。</span><span class="sxs-lookup"><span data-stu-id="2dce6-110">Application developer adds localization comments to XAML source code.</span></span>  
  
2. <span data-ttu-id="2dce6-111">在生成过程中，可以在 .proj 文件中指定是将任意形式的本地化注释留在程序集内、去掉部分注释还是去掉所有注释。</span><span class="sxs-lookup"><span data-stu-id="2dce6-111">During the build process, you can specify in the .proj file whether to leave the free-form localization comments in the assembly, strip out part of the comments, or strip out all the comments.</span></span> <span data-ttu-id="2dce6-112">去掉的注释放在一个单独的文件中。</span><span class="sxs-lookup"><span data-stu-id="2dce6-112">The stripped-out comments are placed in a separate file.</span></span> <span data-ttu-id="2dce6-113">可以使用 `LocalizationDirectivesToLocFile` 标记指定你的选项，例如：</span><span class="sxs-lookup"><span data-stu-id="2dce6-113">You specify your option using a `LocalizationDirectivesToLocFile` tag, eg:</span></span>  
  
     <span data-ttu-id="2dce6-114">`<LocalizationDirectivesToLocFile>`*值*`</LocalizationDirectivesToLocFile>`</span><span class="sxs-lookup"><span data-stu-id="2dce6-114">`<LocalizationDirectivesToLocFile>` *value* `</LocalizationDirectivesToLocFile>`</span></span>  
  
3. <span data-ttu-id="2dce6-115">可以分配的值包括：</span><span class="sxs-lookup"><span data-stu-id="2dce6-115">The values that can be assigned are:</span></span>  
  
    - <span data-ttu-id="2dce6-116">**None** - 注释和特性都保留在程序集中，不会生成单独的文件。</span><span class="sxs-lookup"><span data-stu-id="2dce6-116">**None** - Both comments and attributes stay inside the assembly and no separate file is generated.</span></span>  
  
    - <span data-ttu-id="2dce6-117">**CommentsOnly** - 仅从程序集中去掉注释，并将它们放在单独的 LocFile 中。</span><span class="sxs-lookup"><span data-stu-id="2dce6-117">**CommentsOnly** - Strips only the comments from the assembly and places them in the separate LocFile.</span></span>  
  
    - <span data-ttu-id="2dce6-118">**All** - 从程序集中去掉注释和特性，并将它们两者都放在单独的 LocFile 中。</span><span class="sxs-lookup"><span data-stu-id="2dce6-118">**All** - Strips both the comments and the attributes from the assembly and places them both in a separate LocFile.</span></span>  
  
4. <span data-ttu-id="2dce6-119">从 BAML 中提取可本地化的资源时，BAML 本地化 API 会考虑本地化特性。</span><span class="sxs-lookup"><span data-stu-id="2dce6-119">When localizable resources are extracted from BAML, the localizability attributes are respected by the BAML Localization API.</span></span>  
  
5. <span data-ttu-id="2dce6-120">以后可以将仅包含任意形式的注释的本地化注释文件合并到本地化过程中。</span><span class="sxs-lookup"><span data-stu-id="2dce6-120">Localization comment files, containing only free-form comments, are incorporated into the localization process at a later time.</span></span>  
  
 <span data-ttu-id="2dce6-121">下面的示例演示如何将本地化注释添加到 XAML 文件。</span><span class="sxs-lookup"><span data-stu-id="2dce6-121">The following example shows how to add localization comments to a XAML file.</span></span>  
  
 `<TextBlock x:Id = "text01"`  
  
 `FontFamily = "Microsoft Sans Serif"`  
  
 `FontSize = "12"`  
  
 `Localization.Attributes = "$Content (Unmodifiable Readable Text)`  
  
 `FontFamily (Unmodifiable Readable)"`  
  
 `Localization.Comments = "$Content (Trademark)`  
  
 `FontSize (Trademark font size)" >`  
  
 `Microsoft`  
  
 `</TextBlock>`  
  
 <span data-ttu-id="2dce6-122">在上一示例中，Localization.Attributes 部分包含本地化特性，Localization.Comments 部分包含任意形式的注释。</span><span class="sxs-lookup"><span data-stu-id="2dce6-122">In the previous sample the Localization.Attributes section contains the localization attributes and the Localization.Comments section the free-form comments.</span></span> <span data-ttu-id="2dce6-123">下表显示了特性和注释及其对于本地化人员的含义。</span><span class="sxs-lookup"><span data-stu-id="2dce6-123">The following tables show the attributes and comments and their meaning to the localizer.</span></span>  
  
|<span data-ttu-id="2dce6-124">本地化特性</span><span class="sxs-lookup"><span data-stu-id="2dce6-124">Localization attributes</span></span>|<span data-ttu-id="2dce6-125">含义</span><span class="sxs-lookup"><span data-stu-id="2dce6-125">Meaning</span></span>|  
|-----------------------------|-------------|  
|<span data-ttu-id="2dce6-126">$Content（不可修改的可读文本）</span><span class="sxs-lookup"><span data-stu-id="2dce6-126">$Content (Unmodifiable Readable Text)</span></span>|<span data-ttu-id="2dce6-127">无法修改 TextBlock 元素的内容。</span><span class="sxs-lookup"><span data-stu-id="2dce6-127">Contents of the TextBlock element cannot be modified.</span></span> <span data-ttu-id="2dce6-128">本地化人员不能更改单词“Microsoft”。</span><span class="sxs-lookup"><span data-stu-id="2dce6-128">Localizers cannot change the word "Microsoft".</span></span> <span data-ttu-id="2dce6-129">内容对本地化人员可见（可读）。</span><span class="sxs-lookup"><span data-stu-id="2dce6-129">The content is visible (Readable) to the localizer.</span></span> <span data-ttu-id="2dce6-130">内容为文本类别。</span><span class="sxs-lookup"><span data-stu-id="2dce6-130">The category of the content is text.</span></span>|  
|<span data-ttu-id="2dce6-131">FontFamily（不可修改但可读）</span><span class="sxs-lookup"><span data-stu-id="2dce6-131">FontFamily (Unmodifiable Readable)</span></span>|<span data-ttu-id="2dce6-132">无法更改 TextBlock 元素的字体系列属性，但该属性对本地化人员可见。</span><span class="sxs-lookup"><span data-stu-id="2dce6-132">The font family property of the TextBlock element cannot be changed but it is visible to the localizer.</span></span>|  
  
|<span data-ttu-id="2dce6-133">本地化任意形式的注释</span><span class="sxs-lookup"><span data-stu-id="2dce6-133">Localization free-form comments</span></span>|<span data-ttu-id="2dce6-134">含义</span><span class="sxs-lookup"><span data-stu-id="2dce6-134">Meaning</span></span>|  
|--------------------------------------|-------------|  
|<span data-ttu-id="2dce6-135">$Content（商标）</span><span class="sxs-lookup"><span data-stu-id="2dce6-135">$Content (Trademark)</span></span>|<span data-ttu-id="2dce6-136">应用程序作者告知本地化人员 TextBlock 元素中的内容是商标。</span><span class="sxs-lookup"><span data-stu-id="2dce6-136">The application author tells the localizer that the content in the TextBlock element is a trademark.</span></span>|  
|<span data-ttu-id="2dce6-137">FontSize（商标字号）</span><span class="sxs-lookup"><span data-stu-id="2dce6-137">FontSize (Trademark font size)</span></span>|<span data-ttu-id="2dce6-138">应用程序作者指示字号属性应遵循标准商标大小。</span><span class="sxs-lookup"><span data-stu-id="2dce6-138">The application author indicates that the font size property should follow the standard trademark size.</span></span>|  
  
### <a name="localizability-attributes"></a><span data-ttu-id="2dce6-139">可本地化特性</span><span class="sxs-lookup"><span data-stu-id="2dce6-139">Localizability Attributes</span></span>  
 <span data-ttu-id="2dce6-140">Localization.Attributes 中的信息包含对的列表：目标值名称和关联的可本地化值。</span><span class="sxs-lookup"><span data-stu-id="2dce6-140">The information in Localization.Attributes contains a list of pairs: the targeted value name and the associated localizability values.</span></span> <span data-ttu-id="2dce6-141">目标名称可以是属性名称或特殊 $Content 名称。</span><span class="sxs-lookup"><span data-stu-id="2dce6-141">The target name can be a property name or the special $Content name.</span></span> <span data-ttu-id="2dce6-142">如果是属性名称，则目标值为属性的值。</span><span class="sxs-lookup"><span data-stu-id="2dce6-142">If it is a property name, the targeted value is the value of the property.</span></span> <span data-ttu-id="2dce6-143">如果是 $Content，则目标值为元素的内容。</span><span class="sxs-lookup"><span data-stu-id="2dce6-143">If it is $Content, the target value is the content of the element.</span></span>  
  
 <span data-ttu-id="2dce6-144">有三种类型的属性：</span><span class="sxs-lookup"><span data-stu-id="2dce6-144">There are three types of attributes:</span></span>  
  
- <span data-ttu-id="2dce6-145">**类别**。</span><span class="sxs-lookup"><span data-stu-id="2dce6-145">**Category**.</span></span> <span data-ttu-id="2dce6-146">它指定是否可以从本地化工具修改值。</span><span class="sxs-lookup"><span data-stu-id="2dce6-146">This specifies whether a value should be modifiable from a localizer tool.</span></span> <span data-ttu-id="2dce6-147">请参阅 <xref:System.Windows.LocalizabilityAttribute.Category%2A>。</span><span class="sxs-lookup"><span data-stu-id="2dce6-147">See <xref:System.Windows.LocalizabilityAttribute.Category%2A>.</span></span>  
  
- <span data-ttu-id="2dce6-148">**可读性**。</span><span class="sxs-lookup"><span data-stu-id="2dce6-148">**Readability**.</span></span> <span data-ttu-id="2dce6-149">它指定本地化工具是否可读取（和显示）值。</span><span class="sxs-lookup"><span data-stu-id="2dce6-149">This specifies whether a localizer tool should read (and display) a value.</span></span> <span data-ttu-id="2dce6-150">请参阅 <xref:System.Windows.LocalizabilityAttribute.Readability%2A>。</span><span class="sxs-lookup"><span data-stu-id="2dce6-150">See <xref:System.Windows.LocalizabilityAttribute.Readability%2A>.</span></span>  
  
- <span data-ttu-id="2dce6-151">**Modifiability**。</span><span class="sxs-lookup"><span data-stu-id="2dce6-151">**Modifiability**.</span></span> <span data-ttu-id="2dce6-152">它指定本地化工具是否允许修改值。</span><span class="sxs-lookup"><span data-stu-id="2dce6-152">This specifies whether a localizer tool allows a value to be modified.</span></span> <span data-ttu-id="2dce6-153">请参阅 <xref:System.Windows.LocalizabilityAttribute.Modifiability%2A>。</span><span class="sxs-lookup"><span data-stu-id="2dce6-153">See <xref:System.Windows.LocalizabilityAttribute.Modifiability%2A>.</span></span>  
  
 <span data-ttu-id="2dce6-154">这些特性可以按照由空格分开的任何顺序进行指定。</span><span class="sxs-lookup"><span data-stu-id="2dce6-154">These attributes can be specified in any order delimited by a space.</span></span> <span data-ttu-id="2dce6-155">如果指定了重复特性，则最后一个特性将替代前面的特性。</span><span class="sxs-lookup"><span data-stu-id="2dce6-155">In case duplicate attributes are specified, the last attribute will override former ones.</span></span> <span data-ttu-id="2dce6-156">例如，Localization.Attributes = "Unmodifiable Modifiable" 会将 Modifiability 设置为 Modifiable，因为最后一个值是 Modifiable。</span><span class="sxs-lookup"><span data-stu-id="2dce6-156">For example, Localization.Attributes = "Unmodifiable Modifiable" sets Modifiability to Modifiable because it is the last value.</span></span>  
  
 <span data-ttu-id="2dce6-157">Modifiability 和 Readability 的名称已经揭示了自身的含义。</span><span class="sxs-lookup"><span data-stu-id="2dce6-157">Modifiability and Readability are self-explanatory.</span></span> <span data-ttu-id="2dce6-158">“Category”特性提供的预定义类别可帮助本地化人员翻译文本。</span><span class="sxs-lookup"><span data-stu-id="2dce6-158">The Category attribute provides predefined categories that help the localizer when translating text.</span></span> <span data-ttu-id="2dce6-159">类别（如 Text、Label 和 Title）为本地化人员提供了有关如何翻译文本的信息。</span><span class="sxs-lookup"><span data-stu-id="2dce6-159">Categories, such as, Text, Label, and Title give the localizer information about how to translate the text.</span></span> <span data-ttu-id="2dce6-160">另外，还有一些特殊类别：None、Inherit、Ignore 和 NeverLocalize。</span><span class="sxs-lookup"><span data-stu-id="2dce6-160">There are also special categories: None, Inherit, Ignore, and NeverLocalize.</span></span>  
  
 <span data-ttu-id="2dce6-161">下表显示了这些特殊类别的含义。</span><span class="sxs-lookup"><span data-stu-id="2dce6-161">The following table shows the meaning of the special categories.</span></span>  
  
|<span data-ttu-id="2dce6-162">类别</span><span class="sxs-lookup"><span data-stu-id="2dce6-162">Category</span></span>|<span data-ttu-id="2dce6-163">含义</span><span class="sxs-lookup"><span data-stu-id="2dce6-163">Meaning</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="2dce6-164">无</span><span class="sxs-lookup"><span data-stu-id="2dce6-164">None</span></span>|<span data-ttu-id="2dce6-165">没有为目标值定义类别。</span><span class="sxs-lookup"><span data-stu-id="2dce6-165">Targeted value has no defined category.</span></span>|  
|<span data-ttu-id="2dce6-166">继承</span><span class="sxs-lookup"><span data-stu-id="2dce6-166">Inherit</span></span>|<span data-ttu-id="2dce6-167">目标值从其父级继承其类别。</span><span class="sxs-lookup"><span data-stu-id="2dce6-167">Targeted value inherits its category from its parent.</span></span>|  
|<span data-ttu-id="2dce6-168">忽略</span><span class="sxs-lookup"><span data-stu-id="2dce6-168">Ignore</span></span>|<span data-ttu-id="2dce6-169">在本地化过程中将忽略目标值。</span><span class="sxs-lookup"><span data-stu-id="2dce6-169">Targeted value is ignored in the localization process.</span></span> <span data-ttu-id="2dce6-170">Ignore 仅影响当前值。</span><span class="sxs-lookup"><span data-stu-id="2dce6-170">Ignore affects only the current value.</span></span> <span data-ttu-id="2dce6-171">它不会影响子节点。</span><span class="sxs-lookup"><span data-stu-id="2dce6-171">It will not affect child nodes.</span></span>|  
|<span data-ttu-id="2dce6-172">NeverLocalize</span><span class="sxs-lookup"><span data-stu-id="2dce6-172">NeverLocalize</span></span>|<span data-ttu-id="2dce6-173">无法对当前值进行本地化。</span><span class="sxs-lookup"><span data-stu-id="2dce6-173">Current value cannot be localized.</span></span> <span data-ttu-id="2dce6-174">此类别由元素的子级继承。</span><span class="sxs-lookup"><span data-stu-id="2dce6-174">This category is inherited by the children of an element.</span></span>|  
  
<a name="Localization_Comments"></a>
## <a name="localization-comments"></a><span data-ttu-id="2dce6-175">本地化注释</span><span class="sxs-lookup"><span data-stu-id="2dce6-175">Localization Comments</span></span>  
 <span data-ttu-id="2dce6-176">Localization.Comments 包含与目标值有关的任意形式的字符串。</span><span class="sxs-lookup"><span data-stu-id="2dce6-176">Localization.Comments contains free-form strings concerning the targeted value.</span></span> <span data-ttu-id="2dce6-177">应用程序开发人员可以添加一些信息，以便为本地化人员提供有关如何翻译应用程序文本的提示。</span><span class="sxs-lookup"><span data-stu-id="2dce6-177">Application developers can add information to give localizers hints about how the applications text should be translated.</span></span> <span data-ttu-id="2dce6-178">注释格式可以是由“()”括起来的任何字符串。</span><span class="sxs-lookup"><span data-stu-id="2dce6-178">The format of the comments can be any string surrounded by "()".</span></span> <span data-ttu-id="2dce6-179">可以使用“\\”对字符进行转义。</span><span class="sxs-lookup"><span data-stu-id="2dce6-179">Use '\\' to escape characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dce6-180">请参阅</span><span class="sxs-lookup"><span data-stu-id="2dce6-180">See also</span></span>

- [<span data-ttu-id="2dce6-181">WPF 的全球化</span><span class="sxs-lookup"><span data-stu-id="2dce6-181">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="2dce6-182">使用自动布局创建按钮</span><span class="sxs-lookup"><span data-stu-id="2dce6-182">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
- [<span data-ttu-id="2dce6-183">使用网格进行自动布局</span><span class="sxs-lookup"><span data-stu-id="2dce6-183">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
- [<span data-ttu-id="2dce6-184">对应用程序进行本地化</span><span class="sxs-lookup"><span data-stu-id="2dce6-184">Localize an Application</span></span>](how-to-localize-an-application.md)
