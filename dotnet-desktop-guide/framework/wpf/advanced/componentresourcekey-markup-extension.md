---
title: ComponentResourceKey 标记扩展
ms.date: 03/30/2017
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
ms.openlocfilehash: 1400f506789ded13ffd79640c1b10184a9322765
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666116"
---
# <a name="componentresourcekey-markup-extension"></a><span data-ttu-id="39594-102">ComponentResourceKey 标记扩展</span><span class="sxs-lookup"><span data-stu-id="39594-102">ComponentResourceKey Markup Extension</span></span>
<span data-ttu-id="39594-103">定义和引用从外部程序集加载的资源的键。</span><span class="sxs-lookup"><span data-stu-id="39594-103">Defines and references keys for resources that are loaded from external assemblies.</span></span> <span data-ttu-id="39594-104">这使得资源查找可以在程序集中指定目标类型，而不是在程序集或类中指定显式资源字典。</span><span class="sxs-lookup"><span data-stu-id="39594-104">This enables a resource lookup to specify a target type in an assembly, rather than an explicit resource dictionary in an assembly or on a class.</span></span>  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a><span data-ttu-id="39594-105">XAML 特性用法 (设置键，compact) </span><span class="sxs-lookup"><span data-stu-id="39594-105">XAML Attribute Usage (setting key, compact)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" ... />  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a><span data-ttu-id="39594-106">XAML 特性用法 (设置键，详细) </span><span class="sxs-lookup"><span data-stu-id="39594-106">XAML Attribute Usage (setting key, verbose)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" ... />  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a><span data-ttu-id="39594-107">XAML 特性用法 (请求资源，compact) </span><span class="sxs-lookup"><span data-stu-id="39594-107">XAML Attribute Usage (requesting resource, compact)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" ... />  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a><span data-ttu-id="39594-108">XAML 特性用法 (请求资源，详细) </span><span class="sxs-lookup"><span data-stu-id="39594-108">XAML Attribute Usage (requesting resource, verbose)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" ... />  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="39594-109">XAML 值</span><span class="sxs-lookup"><span data-stu-id="39594-109">XAML Values</span></span>  
  
|||  
|-|-|  
|`targetTypeName`|<span data-ttu-id="39594-110">公共公共语言运行时的名称 (CLR) 类型（在资源程序集中定义）。</span><span class="sxs-lookup"><span data-stu-id="39594-110">The name of the public common language runtime (CLR) type that is defined in the resource assembly.</span></span>|  
|`targetID`|<span data-ttu-id="39594-111">资源的键。</span><span class="sxs-lookup"><span data-stu-id="39594-111">The key for the resource.</span></span> <span data-ttu-id="39594-112">查找资源时， `targetID` 将类似于资源的 " [X：Key" 指令](/dotnet/desktop-wpf/xaml-services/xkey-directive) 。</span><span class="sxs-lookup"><span data-stu-id="39594-112">When resources are looked up, `targetID` will be analogous to the [x:Key Directive](/dotnet/desktop-wpf/xaml-services/xkey-directive) of the resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39594-113">备注</span><span class="sxs-lookup"><span data-stu-id="39594-113">Remarks</span></span>  
 <span data-ttu-id="39594-114">如以上用法中所示， `ComponentResourceKey` 可在以下两个位置找到 {} 标记扩展用法：</span><span class="sxs-lookup"><span data-stu-id="39594-114">As seen in the usages above, a {`ComponentResourceKey`} markup extension usage is found in two places:</span></span>  
  
- <span data-ttu-id="39594-115">主题资源字典中的键的定义，由控件作者提供。</span><span class="sxs-lookup"><span data-stu-id="39594-115">The definition of a key within a theme resource dictionary, as provided by a control author.</span></span>  
  
- <span data-ttu-id="39594-116">在重新模板化控件时访问程序集中的主题资源，但需要使用由控件主题提供的资源提供的属性值。</span><span class="sxs-lookup"><span data-stu-id="39594-116">Accessing a theme resource from the assembly, when you are retemplating the control but want to use property values that come from resources provided by the control's themes.</span></span>  
  
 <span data-ttu-id="39594-117">对于引用来自主题的组件资源，通常建议使用 `{DynamicResource}` 而不是 `{StaticResource}` 。</span><span class="sxs-lookup"><span data-stu-id="39594-117">For referencing component resources that come from themes, it is generally recommended that you use `{DynamicResource}` rather than `{StaticResource}`.</span></span> <span data-ttu-id="39594-118">用法中显示了这种情况。</span><span class="sxs-lookup"><span data-stu-id="39594-118">This is shown in the usages.</span></span> <span data-ttu-id="39594-119">`{DynamicResource}` 建议使用，因为用户可以更改主题本身。</span><span class="sxs-lookup"><span data-stu-id="39594-119">`{DynamicResource}` is recommended because the theme itself can be changed by the user.</span></span> <span data-ttu-id="39594-120">如果希望组件资源与控件作者为支持主题最匹配，则应使组件资源引用也是动态的。</span><span class="sxs-lookup"><span data-stu-id="39594-120">If you want the component resource that most closely matches the control author's intent for supporting a theme, you should enable your component resource reference to be dynamic also.</span></span>  
  
 <span data-ttu-id="39594-121"><xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>标识在实际定义资源的目标程序集中存在的类型。</span><span class="sxs-lookup"><span data-stu-id="39594-121">The <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifies a type that exists in the target assembly where the resource is actually defined.</span></span> <span data-ttu-id="39594-122">`ComponentResourceKey`可以定义和使用独立于确切了解定义的位置 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> ，但最终必须通过引用的程序集解析类型。</span><span class="sxs-lookup"><span data-stu-id="39594-122">A `ComponentResourceKey` can be defined and used independently of knowing exactly where the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> is defined, but eventually must resolve the type through referenced assemblies.</span></span>  
  
 <span data-ttu-id="39594-123">的一个常见用途 <xref:System.Windows.ComponentResourceKey> 是定义随后作为类的成员公开的键。</span><span class="sxs-lookup"><span data-stu-id="39594-123">A common usage for <xref:System.Windows.ComponentResourceKey> is to define keys that are then exposed as members of a class.</span></span> <span data-ttu-id="39594-124">对于此用法，使用 <xref:System.Windows.ComponentResourceKey> 类构造函数，而不是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="39594-124">For this usage, you use the <xref:System.Windows.ComponentResourceKey> class constructor, not the markup extension.</span></span> <span data-ttu-id="39594-125">有关详细信息，请参阅 <xref:System.Windows.ComponentResourceKey> 或主题 [控件创作概述](../controls/control-authoring-overview.md)的 "定义和引用主题资源的键" 一节。</span><span class="sxs-lookup"><span data-stu-id="39594-125">For more information, see <xref:System.Windows.ComponentResourceKey>, or the "Defining and Referencing Keys for Theme Resources" section of the topic [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="39594-126">对于建立密钥和引用键控资源，特性语法通常用于 `ComponentResourceKey` 标记扩展。</span><span class="sxs-lookup"><span data-stu-id="39594-126">For both establishing keys and referencing keyed resources, attribute syntax is commonly used for the `ComponentResourceKey` markup extension.</span></span>  
  
 <span data-ttu-id="39594-127">所示的压缩语法依赖于 <xref:System.Windows.ComponentResourceKey.%23ctor%2A> 标记扩展的构造函数签名和位置参数用法。</span><span class="sxs-lookup"><span data-stu-id="39594-127">The compact syntax shown relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A> constructor signature and positional parameter usage of a markup extension.</span></span> <span data-ttu-id="39594-128">给定和的顺序非常 `targetTypeName` `targetID` 重要。</span><span class="sxs-lookup"><span data-stu-id="39594-128">The order in which the `targetTypeName` and `targetID` are given is important.</span></span> <span data-ttu-id="39594-129">详细语法依赖于 <xref:System.Windows.ComponentResourceKey.%23ctor%2A> 无参数的构造函数，然后以与 <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> <xref:System.Windows.ComponentResourceKey.ResourceId%2A> object 元素上的 true 特性语法类似的方式来设置和。</span><span class="sxs-lookup"><span data-stu-id="39594-129">The verbose syntax relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A> parameterless constructor, and then sets the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> in a way that is analogous to a true attribute syntax on an object element.</span></span> <span data-ttu-id="39594-130">在详细语法中，设置属性的顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="39594-130">In the verbose syntax, the order in which the properties are set is not important.</span></span> <span data-ttu-id="39594-131">主题 [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)中更详细地介绍了这两种备选方法的关系和机制 (简洁和详细) 。</span><span class="sxs-lookup"><span data-stu-id="39594-131">The relationship and mechanisms of these two alternatives (compact and verbose) is described in more detail in the topic [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="39594-132">从技术上来说，的值 `targetID` 可以是任何对象，不一定是字符串。</span><span class="sxs-lookup"><span data-stu-id="39594-132">Technically, the value for `targetID` can be any object, it does not have to be a string.</span></span> <span data-ttu-id="39594-133">不过，WPF 最常见的用法是将 `targetID` 值与字符串形式的窗体进行对齐，在 [XamlName 语法](/dotnet/desktop-wpf/xaml-services/xamlname-grammar)中，此类字符串有效。</span><span class="sxs-lookup"><span data-stu-id="39594-133">However, the most common usage in WPF is to align the `targetID` value with forms that are strings, and where such strings are valid in the [XamlName Grammar](/dotnet/desktop-wpf/xaml-services/xamlname-grammar).</span></span>  
  
 <span data-ttu-id="39594-134">`ComponentResourceKey` 可以在对象元素语法中使用。</span><span class="sxs-lookup"><span data-stu-id="39594-134">`ComponentResourceKey` can be used in object element syntax.</span></span> <span data-ttu-id="39594-135">在这种情况下， <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> 需要指定和属性的值 <xref:System.Windows.ComponentResourceKey.ResourceId%2A> 才能正确地初始化扩展。</span><span class="sxs-lookup"><span data-stu-id="39594-135">In this case, specifying the value of both the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> properties is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="39594-136">在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 读取器实现中，对此标记扩展的处理由类定义 <xref:System.Windows.ComponentResourceKey> 。</span><span class="sxs-lookup"><span data-stu-id="39594-136">In the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] reader implementation, the handling for this markup extension is defined by the <xref:System.Windows.ComponentResourceKey> class.</span></span>  
  
 <span data-ttu-id="39594-137">`ComponentResourceKey` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="39594-137">`ComponentResourceKey` is a markup extension.</span></span> <span data-ttu-id="39594-138">当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。</span><span class="sxs-lookup"><span data-stu-id="39594-138">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="39594-139">[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。</span><span class="sxs-lookup"><span data-stu-id="39594-139">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="39594-140">有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="39594-140">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39594-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="39594-141">See also</span></span>

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="39594-142">控件创作概述</span><span class="sxs-lookup"><span data-stu-id="39594-142">Control Authoring Overview</span></span>](../controls/control-authoring-overview.md)
- [<span data-ttu-id="39594-143">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="39594-143">XAML Overview (WPF)</span></span>](/dotnet/desktop-wpf/fundamentals/xaml)
- [<span data-ttu-id="39594-144">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="39594-144">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
