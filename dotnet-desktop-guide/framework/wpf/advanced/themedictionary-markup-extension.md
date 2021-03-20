---
title: ThemeDictionary 标记扩展
ms.date: 03/30/2017
f1_keywords:
- ThemeDictionaryExtension
- ThemeDictionary
helpviewer_keywords:
- ThemeDictionary markup extension [WPF]
- XAML [WPF], ThemeDictionary markup extension
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
ms.openlocfilehash: 5e9b4b4013f026bf6612b6ba70ae705c0b2dca3e
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664673"
---
# <a name="themedictionary-markup-extension"></a><span data-ttu-id="1e92c-102">ThemeDictionary 标记扩展</span><span class="sxs-lookup"><span data-stu-id="1e92c-102">ThemeDictionary Markup Extension</span></span>
<span data-ttu-id="1e92c-103">为集成第三方控件的自定义控件创作者或应用程序提供一种方法，用于加载要在设置控件样式时使用的特定于主题的资源字典。</span><span class="sxs-lookup"><span data-stu-id="1e92c-103">Provides a way for custom control authors or applications that integrate third-party controls to load theme-specific resource dictionaries to use in styling the control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="1e92c-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="1e92c-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" ... />  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="1e92c-105">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="1e92c-105">XAML Object Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="1e92c-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="1e92c-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`assemblyUri`|<span data-ttu-id="1e92c-107">包含主题信息的程序集 (URI) 的统一资源标识符。</span><span class="sxs-lookup"><span data-stu-id="1e92c-107">The uniform resource identifier (URI) of the assembly that contains theme information.</span></span> <span data-ttu-id="1e92c-108">通常，这是一个引用较大包中程序集的 Pack URI。</span><span class="sxs-lookup"><span data-stu-id="1e92c-108">Typically, this is a pack URI that references an assembly in the larger package.</span></span> <span data-ttu-id="1e92c-109">程序集资源和 Pack URI 可以简化部署问题。</span><span class="sxs-lookup"><span data-stu-id="1e92c-109">Assembly resources and pack URIs simplify deployment issues.</span></span> <span data-ttu-id="1e92c-110">有关详细信息，请参阅 [WPF 中的 Pack uri](../app-development/pack-uris-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="1e92c-110">For more information see [Pack URIs in WPF](../app-development/pack-uris-in-wpf.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e92c-111">备注</span><span class="sxs-lookup"><span data-stu-id="1e92c-111">Remarks</span></span>  
 <span data-ttu-id="1e92c-112">此扩展仅用于填充一个特定的属性值：值 <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="1e92c-112">This extension is intended to fill only one specific property value: a value for <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="1e92c-113">通过使用此扩展，你可以指定仅限单个资源的程序集，该程序集包含的某些样式仅在将 Windows Aero 主题应用于用户系统时使用，其他样式仅在 Luna 主题处于活动状态时如此。</span><span class="sxs-lookup"><span data-stu-id="1e92c-113">By using this extension, you can specify a single resources-only assembly that contains some styles to use only when the Windows Aero theme is applied to the user's system, other styles only when the Luna theme is active, and so on.</span></span> <span data-ttu-id="1e92c-114">通过使用此扩展，可以自动让特定于控件的资源字典的内容失效，并在需要时重新将其加载为特定于其他主题的内容。</span><span class="sxs-lookup"><span data-stu-id="1e92c-114">By using this extension, the contents of a control-specific resource dictionary can be automatically invalidated and reloaded to be specific for another theme when required.</span></span>  
  
 <span data-ttu-id="1e92c-115">`assemblyUri`String (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> 属性值) 构成命名约定的基础，该约定标识哪个字典适用于特定主题。</span><span class="sxs-lookup"><span data-stu-id="1e92c-115">The `assemblyUri` string (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> property value) forms the basis of a naming convention that identifies which dictionary applies for a particular theme.</span></span> <span data-ttu-id="1e92c-116"><xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>用于 `ThemeDictionary` 完成该约定的逻辑， (URI) 生成一个统一资源标识符，该标识符指向特定主题字典变体（包含在预编译的资源程序集中）。</span><span class="sxs-lookup"><span data-stu-id="1e92c-116">The <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> logic for `ThemeDictionary` completes the convention by generating a uniform resource identifier (URI) that points to a particular theme dictionary variant, as contained within a precompiled resource assembly.</span></span> <span data-ttu-id="1e92c-117">本文并未将该约定（即主题与一般控件样式设置和页/应用程序级样式设置之间的交互）作为一个概念进行详细介绍。</span><span class="sxs-lookup"><span data-stu-id="1e92c-117">Describing this convention, or theme interactions with general control styling and page/application level styling as a concept, is not covered fully here.</span></span> <span data-ttu-id="1e92c-118">使用的基本方案 `ThemeDictionary` 是指定 <xref:System.Windows.ResourceDictionary.Source%2A> `ResourceDictionary` 在应用程序级别声明的的属性。</span><span class="sxs-lookup"><span data-stu-id="1e92c-118">The basic scenario for using `ThemeDictionary` is to specify the <xref:System.Windows.ResourceDictionary.Source%2A> property of a `ResourceDictionary` declared at the application level.</span></span> <span data-ttu-id="1e92c-119">当通过扩展而不是直接 URI 为程序集提供 URI 时 `ThemeDictionary` ，扩展逻辑将提供在系统主题发生更改时应用的失效逻辑。</span><span class="sxs-lookup"><span data-stu-id="1e92c-119">When you provide a URI for the assembly through a `ThemeDictionary` extension rather than as a direct URI, the extension logic will provide invalidation logic that applies whenever the system theme changes.</span></span>  
  
 <span data-ttu-id="1e92c-120">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="1e92c-120">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="1e92c-121">在 `ThemeDictionary` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> 扩展类的 <xref:System.Windows.ThemeDictionaryExtension> 值。</span><span class="sxs-lookup"><span data-stu-id="1e92c-121">The string token provided after the `ThemeDictionary` identifier string is assigned as the <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> value of the underlying <xref:System.Windows.ThemeDictionaryExtension> extension class.</span></span>  
  
 <span data-ttu-id="1e92c-122">`ThemeDictionary` 还可以在对象元素语法中使用。</span><span class="sxs-lookup"><span data-stu-id="1e92c-122">`ThemeDictionary` may also be used in object element syntax.</span></span> <span data-ttu-id="1e92c-123">在这种情况下，需要指定属性的值 <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> 。</span><span class="sxs-lookup"><span data-stu-id="1e92c-123">In this case, specifying the value of the <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> property is required.</span></span>  
  
 <span data-ttu-id="1e92c-124">`ThemeDictionary` 还可以在详细特性用法中使用，以便将 <xref:System.Windows.Markup.StaticExtension.Member%2A> 属性指定为一个 property=value 对：</span><span class="sxs-lookup"><span data-stu-id="1e92c-124">`ThemeDictionary` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.Markup.StaticExtension.Member%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" ... />  
```  
  
 <span data-ttu-id="1e92c-125">如果扩展具有一个以上的可设置属性，或者某些属性是可选的，则详细用法通常会很有用。</span><span class="sxs-lookup"><span data-stu-id="1e92c-125">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="1e92c-126">由于 `ThemeDictionary` 仅有一个可设置的属性，并且此属性是必需的，因此该详细用法不具有典型性。</span><span class="sxs-lookup"><span data-stu-id="1e92c-126">Because `ThemeDictionary` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="1e92c-127">在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器实现中，对此标记扩展的处理由 <xref:System.Windows.ThemeDictionaryExtension> 类定义。</span><span class="sxs-lookup"><span data-stu-id="1e92c-127">In the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.ThemeDictionaryExtension> class.</span></span>  
  
 <span data-ttu-id="1e92c-128">`ThemeDictionary` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="1e92c-128">`ThemeDictionary` is a markup extension.</span></span> <span data-ttu-id="1e92c-129">当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。</span><span class="sxs-lookup"><span data-stu-id="1e92c-129">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="1e92c-130">[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。</span><span class="sxs-lookup"><span data-stu-id="1e92c-130">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="1e92c-131">有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="1e92c-131">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e92c-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e92c-132">See also</span></span>

- [<span data-ttu-id="1e92c-133">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="1e92c-133">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="1e92c-134">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="1e92c-134">XAML Overview (WPF)</span></span>](/dotnet/desktop-wpf/fundamentals/xaml)
- [<span data-ttu-id="1e92c-135">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="1e92c-135">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="1e92c-136">WPF 应用程序资源、内容和数据文件</span><span class="sxs-lookup"><span data-stu-id="1e92c-136">WPF Application Resource, Content, and Data Files</span></span>](../app-development/wpf-application-resource-content-and-data-files.md)
