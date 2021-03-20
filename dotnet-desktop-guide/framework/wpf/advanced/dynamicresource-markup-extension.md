---
title: DynamicResource 标记扩展
ms.date: 03/30/2017
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
ms.openlocfilehash: 56acc3f205424f9d0eb21fbc193534a16939c7cd
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666025"
---
# <a name="dynamicresource-markup-extension"></a><span data-ttu-id="93b75-102">DynamicResource 标记扩展</span><span class="sxs-lookup"><span data-stu-id="93b75-102">DynamicResource Markup Extension</span></span>
<span data-ttu-id="93b75-103">[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]通过将值推迟为对已定义资源的引用来为任何属性属性提供值。</span><span class="sxs-lookup"><span data-stu-id="93b75-103">Provides a value for any [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] property attribute by deferring that value to be a reference to a defined resource.</span></span> <span data-ttu-id="93b75-104">该资源的查找行为类似于运行时查找。</span><span class="sxs-lookup"><span data-stu-id="93b75-104">Lookup behavior for that resource is analogous to run-time lookup.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="93b75-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="93b75-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{DynamicResource key}" ... />  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="93b75-106">XAML 属性元素用法</span><span class="sxs-lookup"><span data-stu-id="93b75-106">XAML Property Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" ... />  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="93b75-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="93b75-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`key`|<span data-ttu-id="93b75-108">所请求资源的密钥。</span><span class="sxs-lookup"><span data-stu-id="93b75-108">The key for the requested resource.</span></span> <span data-ttu-id="93b75-109">如果在标记中创建了资源，则此密钥最初由 [X：Key 指令](/dotnet/desktop-wpf/xaml-services/xkey-directive) 分配，或在 `key` 调用时作为参数提供（ <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> 如果资源是在代码中创建的）。</span><span class="sxs-lookup"><span data-stu-id="93b75-109">This key was initially assigned by the [x:Key Directive](/dotnet/desktop-wpf/xaml-services/xkey-directive) if a resource was created in markup, or was provided as the `key` parameter when calling <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> if the resource was created in code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93b75-110">备注</span><span class="sxs-lookup"><span data-stu-id="93b75-110">Remarks</span></span>  
 <span data-ttu-id="93b75-111">在 `DynamicResource` 初始编译过程中，将创建一个临时表达式，从而推迟资源的查找，直到实际需要请求的资源值才能构造对象。</span><span class="sxs-lookup"><span data-stu-id="93b75-111">A `DynamicResource` will create a temporary expression during the initial compilation and thus defer lookup for resources until the requested resource value is actually required in order to construct an object.</span></span> <span data-ttu-id="93b75-112">这可能是在加载页面后进行的 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="93b75-112">This may potentially be after the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] page is loaded.</span></span> <span data-ttu-id="93b75-113">将基于从当前页范围开始的所有活动资源字典的键搜索来找到资源值，并将其替换为编译中的占位符表达式。</span><span class="sxs-lookup"><span data-stu-id="93b75-113">The resource value will be found based on key search against all active resource dictionaries starting from the current page scope, and is substituted for the placeholder expression from compilation.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="93b75-114">就依赖属性优先级而言， `DynamicResource` 表达式等效于应用动态资源引用的位置。</span><span class="sxs-lookup"><span data-stu-id="93b75-114">In terms of dependency property precedence, a `DynamicResource` expression is equivalent to the position where the dynamic resource reference is applied.</span></span> <span data-ttu-id="93b75-115">如果为之前将表达式作为本地值的属性设置本地值 `DynamicResource` ，则将 `DynamicResource` 完全删除。</span><span class="sxs-lookup"><span data-stu-id="93b75-115">If you set a local value for a property that previously had a `DynamicResource` expression as the local value, the `DynamicResource` is completely removed.</span></span> <span data-ttu-id="93b75-116">有关详细信息，请参阅[依赖属性值优先级](dependency-property-value-precedence.md)。</span><span class="sxs-lookup"><span data-stu-id="93b75-116">For details, see [Dependency Property Value Precedence](dependency-property-value-precedence.md).</span></span>  
  
 <span data-ttu-id="93b75-117">某些资源访问方案特别适用于 `DynamicResource` 与 [StaticResource 标记扩展](staticresource-markup-extension.md)相对的。</span><span class="sxs-lookup"><span data-stu-id="93b75-117">Certain resource access scenarios are particularly appropriate for `DynamicResource` as opposed to a [StaticResource Markup Extension](staticresource-markup-extension.md).</span></span> <span data-ttu-id="93b75-118">请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define) ，详细了解和的相对优点和性能影响 `DynamicResource` `StaticResource` 。</span><span class="sxs-lookup"><span data-stu-id="93b75-118">See [XAML Resources](/dotnet/desktop-wpf/fundamentals/xaml-resources-define) for a discussion about the relative merits and performance implications of `DynamicResource` and `StaticResource`.</span></span>  
  
 <span data-ttu-id="93b75-119">指定的 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 应对应于页面、应用程序、可用控件主题和外部资源或系统资源的某个级别由 [x：Key 指令](/dotnet/desktop-wpf/xaml-services/xkey-directive) 确定的现有资源，并按该顺序进行资源查找。</span><span class="sxs-lookup"><span data-stu-id="93b75-119">The specified <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> should correspond to an existing resource determined by [x:Key Directive](/dotnet/desktop-wpf/xaml-services/xkey-directive) at some level in your page, application, the available control themes and external resources, or system resources, and the resource lookup will happen in that order.</span></span> <span data-ttu-id="93b75-120">有关静态和动态资源的资源查找的详细信息，请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)。</span><span class="sxs-lookup"><span data-stu-id="93b75-120">For more information about resource lookup for static and dynamic resources, see [XAML Resources](/dotnet/desktop-wpf/fundamentals/xaml-resources-define).</span></span>  
  
 <span data-ttu-id="93b75-121">资源键可以是 [XamlName 语法](/dotnet/desktop-wpf/xaml-services/xamlname-grammar)中定义的任何字符串。</span><span class="sxs-lookup"><span data-stu-id="93b75-121">A resource key may be any string defined in the [XamlName Grammar](/dotnet/desktop-wpf/xaml-services/xamlname-grammar).</span></span> <span data-ttu-id="93b75-122">资源键还可以是其他对象类型，如 <xref:System.Type> 。</span><span class="sxs-lookup"><span data-stu-id="93b75-122">A resource key may also be other object types, such as a <xref:System.Type>.</span></span> <span data-ttu-id="93b75-123"><xref:System.Type>关键是主题如何对控件进行样式设计。</span><span class="sxs-lookup"><span data-stu-id="93b75-123">A <xref:System.Type> key is fundamental to how controls can be styled by themes.</span></span> <span data-ttu-id="93b75-124">有关详细信息，请参阅[控件创作概述](../controls/control-authoring-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="93b75-124">For more information, see [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="93b75-125">用于查找资源值的 Api （例如 <xref:System.Windows.FrameworkElement.FindResource%2A> ）按照使用的相同资源查找逻辑 `DynamicResource` 。</span><span class="sxs-lookup"><span data-stu-id="93b75-125">APIs for lookup of resource values, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, follow the same resource lookup logic as used by `DynamicResource`.</span></span>  
  
 <span data-ttu-id="93b75-126">引用资源的替代声明方法是作为 [StaticResource 标记扩展](staticresource-markup-extension.md)。</span><span class="sxs-lookup"><span data-stu-id="93b75-126">The alternative declarative means of referencing a resource is as a [StaticResource Markup Extension](staticresource-markup-extension.md).</span></span>  
  
 <span data-ttu-id="93b75-127">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="93b75-127">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="93b75-128">在 `DynamicResource` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 扩展类的 <xref:System.Windows.DynamicResourceExtension> 值。</span><span class="sxs-lookup"><span data-stu-id="93b75-128">The string token provided after the `DynamicResource` identifier string is assigned as the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> value of the underlying <xref:System.Windows.DynamicResourceExtension> extension class.</span></span>  
  
 <span data-ttu-id="93b75-129">`DynamicResource` 可以在对象元素语法中使用。</span><span class="sxs-lookup"><span data-stu-id="93b75-129">`DynamicResource` can be used in object element syntax.</span></span> <span data-ttu-id="93b75-130">在这种情况下，需要指定属性的值 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 。</span><span class="sxs-lookup"><span data-stu-id="93b75-130">In this case, specifying the value of the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property is required.</span></span>  
  
 <span data-ttu-id="93b75-131">`DynamicResource` 还可以在详细特性用法中使用，以便将 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 属性指定为一个 property=value 对：</span><span class="sxs-lookup"><span data-stu-id="93b75-131">`DynamicResource` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" ... />  
```  
  
 <span data-ttu-id="93b75-132">如果扩展具有一个以上的可设置属性，或者某些属性是可选的，则详细用法通常会很有用。</span><span class="sxs-lookup"><span data-stu-id="93b75-132">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="93b75-133">由于 `DynamicResource` 仅有一个可设置的属性，并且此属性是必需的，因此该详细用法不具有典型性。</span><span class="sxs-lookup"><span data-stu-id="93b75-133">Because `DynamicResource` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="93b75-134">在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器实现中，对此标记扩展的处理由 <xref:System.Windows.DynamicResourceExtension> 类定义。</span><span class="sxs-lookup"><span data-stu-id="93b75-134">In the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.DynamicResourceExtension> class.</span></span>  
  
 <span data-ttu-id="93b75-135">`DynamicResource` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="93b75-135">`DynamicResource` is a markup extension.</span></span> <span data-ttu-id="93b75-136">当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。</span><span class="sxs-lookup"><span data-stu-id="93b75-136">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="93b75-137">[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。</span><span class="sxs-lookup"><span data-stu-id="93b75-137">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="93b75-138">有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="93b75-138">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93b75-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="93b75-139">See also</span></span>

- [<span data-ttu-id="93b75-140">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="93b75-140">XAML Resources</span></span>](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [<span data-ttu-id="93b75-141">资源和代码</span><span class="sxs-lookup"><span data-stu-id="93b75-141">Resources and Code</span></span>](resources-and-code.md)
- [<span data-ttu-id="93b75-142">x:Key 指令</span><span class="sxs-lookup"><span data-stu-id="93b75-142">x:Key Directive</span></span>](/dotnet/desktop-wpf/xaml-services/xkey-directive)
- [<span data-ttu-id="93b75-143">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="93b75-143">XAML Overview (WPF)</span></span>](/dotnet/desktop-wpf/fundamentals/xaml)
- [<span data-ttu-id="93b75-144">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="93b75-144">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="93b75-145">StaticResource 标记扩展</span><span class="sxs-lookup"><span data-stu-id="93b75-145">StaticResource Markup Extension</span></span>](staticresource-markup-extension.md)
- [<span data-ttu-id="93b75-146">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="93b75-146">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
