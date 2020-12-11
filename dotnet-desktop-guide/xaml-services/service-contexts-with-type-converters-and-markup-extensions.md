---
title: 可供类型转换器和标记扩展使用的服务上下文
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], type converter services how-to
ms.assetid: b4dad00f-03da-4579-a4e9-d8d72d2ccbce
ms.openlocfilehash: e70b96cdea524b7558d7ed502c0b5418e929278c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972831"
---
# <a name="service-contexts-available-to-type-converters-and-markup-extensions"></a><span data-ttu-id="83015-102">可供类型转换器和标记扩展使用的服务上下文</span><span class="sxs-lookup"><span data-stu-id="83015-102">Service Contexts Available to Type Converters and Markup Extensions</span></span>
<span data-ttu-id="83015-103">支持类型转换器和标记扩展用法的类型的作者通常必须拥有用法在标记或周围对象图结构中的所在位置的相关上下文信息。</span><span class="sxs-lookup"><span data-stu-id="83015-103">Authors of the types that support type converter and markup extension usages must often have contextual information about where a usage is located in the markup, or in surrounding object graph structure.</span></span> <span data-ttu-id="83015-104">为了能正确实例化所提供的对象或者对对象图中的现有对象进行对象引用，可能需要此信息。</span><span class="sxs-lookup"><span data-stu-id="83015-104">Information might be needed so that the provided object is instantiated correctly or so that object references to existing objects in the object graph can be made.</span></span> <span data-ttu-id="83015-105">使用 .NET XAML 服务时，可能需要的上下文将作为一系列服务接口公开。</span><span class="sxs-lookup"><span data-stu-id="83015-105">When using .NET XAML Services, the context that might be required is exposed as a series of service interfaces.</span></span> <span data-ttu-id="83015-106">类型转换器或标记扩展支持代码可使用从 <xref:System.Xaml.XamlObjectWriter> 或相关类型传递且可用的服务提供程序上下文来查询服务。</span><span class="sxs-lookup"><span data-stu-id="83015-106">Type converter or markup extension support code can query for a service by using a service provider context that is available and passed through from <xref:System.Xaml.XamlObjectWriter> or related types.</span></span> <span data-ttu-id="83015-107">可通过一个这样的服务来直接获取 XAML 架构上下文。</span><span class="sxs-lookup"><span data-stu-id="83015-107">The XAML schema context is directly available through one such service.</span></span> <span data-ttu-id="83015-108">本主题介绍如何从值转换器实现访问服务上下文，并且列出了通常可用的服务及其角色。</span><span class="sxs-lookup"><span data-stu-id="83015-108">This topic describes how to access service contexts from a value converter implementation, and lists typically available services and their roles.</span></span>

## <a name="obtaining-services"></a><span data-ttu-id="83015-109">获取服务</span><span class="sxs-lookup"><span data-stu-id="83015-109">Obtaining Services</span></span>

<span data-ttu-id="83015-110">作为值转换器的实现者，你经常需要访问在其中应用了值转换器的某些类型的上下文。</span><span class="sxs-lookup"><span data-stu-id="83015-110">As an implementer of a value converter, you often need access to some type of context in which the value converter is applied.</span></span> <span data-ttu-id="83015-111">此上下文可能包括诸如活动的 XAML 架构上下文、对 XAML 架构上下文和 XAML 对象编写器提供的类型映射系统的访问权限等信息。</span><span class="sxs-lookup"><span data-stu-id="83015-111">This context might include information such as the active XAML schema context, access to the type-mapping system that the XAML schema context and XAML object writer provide, and so on.</span></span> <span data-ttu-id="83015-112">可用于标记扩展或类型转换器实现的服务通过属于每种虚方法签名的一部分的上下文参数来传递。</span><span class="sxs-lookup"><span data-stu-id="83015-112">The services available for a markup extension or type converter implementation are communicated through the context parameters that are part of the signature of each virtual method.</span></span> <span data-ttu-id="83015-113">在每种情况下，你都在上下文中实现了 <xref:System.IServiceProvider> ，并且可以调用 <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType> 来请求服务。</span><span class="sxs-lookup"><span data-stu-id="83015-113">In every case, you have <xref:System.IServiceProvider> implemented in the context, and can call <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType> to request a service.</span></span>

## <a name="services-for-a-markup-extension"></a><span data-ttu-id="83015-114">用于标记扩展的服务</span><span class="sxs-lookup"><span data-stu-id="83015-114">Services for a Markup Extension</span></span>

<span data-ttu-id="83015-115"><xref:System.Windows.Markup.MarkupExtension> 只有一个虚方法 <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>。</span><span class="sxs-lookup"><span data-stu-id="83015-115"><xref:System.Windows.Markup.MarkupExtension> has only one virtual method, <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>.</span></span> <span data-ttu-id="83015-116">输入 `serviceProvider` 参数是 XAML 处理器调用标记扩展时服务与实现的通信方式。</span><span class="sxs-lookup"><span data-stu-id="83015-116">The input `serviceProvider` parameter is how the services are communicated to implementations when the markup extension is called by a XAML processor.</span></span> <span data-ttu-id="83015-117">下面的伪代码演示了标记扩展实现可如何在其 <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>中查询服务：</span><span class="sxs-lookup"><span data-stu-id="83015-117">The following pseudocode illustrates how a markup extension implementation might query for services in its <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>:</span></span>

```csharp
public override object ProvideValue(IServiceProvider serviceProvider)
{
...
    // Get the IXamlTypeResolver from the service provider
    if (serviceProvider == null)
    {
        throw new ArgumentNullException("serviceProvider");
    }
    IXamlTypeResolver xamlTypeResolver = serviceProvider.GetService(typeof(IXamlTypeResolver)) as IXamlTypeResolver;
    if (xamlTypeResolver == null)
   {
        throw new ArgumentException("IXamlTypeResolver"));
    }
...
}
```

## <a name="services-for-a-type-converter"></a><span data-ttu-id="83015-118">用于类型转换器的服务</span><span class="sxs-lookup"><span data-stu-id="83015-118">Services for a Type Converter</span></span>

<span data-ttu-id="83015-119"><xref:System.ComponentModel.TypeConverter> 有四个虚方法，它们使用一个服务上下文并且都支持 XAML 用法。</span><span class="sxs-lookup"><span data-stu-id="83015-119"><xref:System.ComponentModel.TypeConverter> has four virtual methods that use a service context and that support XAML usages.</span></span> <span data-ttu-id="83015-120">每个方法都传递一个输入 `context` 参数。</span><span class="sxs-lookup"><span data-stu-id="83015-120">Each of these methods passes an input `context` parameter.</span></span> <span data-ttu-id="83015-121">此参数的类型为 <xref:System.ComponentModel.ITypeDescriptorContext>，但该接口继承 <xref:System.IServiceProvider>，因此具有一个可用于类型转换器实现的 <xref:System.IServiceProvider.GetService%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="83015-121">This parameter is of type <xref:System.ComponentModel.ITypeDescriptorContext>, but that interface inherits <xref:System.IServiceProvider>, and therefore, there is a <xref:System.IServiceProvider.GetService%2A> method available to type converter implementations.</span></span>

<span data-ttu-id="83015-122">下面的伪代码演示了 XAML 用法的类型转换器实现可如何在它的一个替代（在本示例中为 <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>）中查询服务：</span><span class="sxs-lookup"><span data-stu-id="83015-122">The following pseudocode illustrates how a type converter implementation for XAML usages might query for services in one of its overrides, in this case <xref:System.ComponentModel.TypeConverter.ConvertFrom%2A>:</span></span>

```csharp
public override object ConvertFrom(ITypeDescriptorContext typeDescriptorContext,
  CultureInfo cultureInfo,
  object source)
{
    IRootObjectProvider rootProvider = typeDescriptorContext.GetService(typeof(IRootObjectProvider)) as IRootObjectProvider;
    if (rootProvider != null && source is String)
    {
        //return something, else ...
    }
    throw GetConvertFromException(source);
}
```

## <a name="services-for-a-value-serializer"></a><span data-ttu-id="83015-123">用于值序列化程序的服务</span><span class="sxs-lookup"><span data-stu-id="83015-123">Services for a Value Serializer</span></span>

<span data-ttu-id="83015-124">对于值序列化程序上下文，使用特定于 <xref:System.Windows.Markup.ValueSerializer> 类 <xref:System.Windows.Markup.IValueSerializerContext>的服务提供程序类型。</span><span class="sxs-lookup"><span data-stu-id="83015-124">For value serializer context, you use a service provider type that is specific to the <xref:System.Windows.Markup.ValueSerializer> class, <xref:System.Windows.Markup.IValueSerializerContext>.</span></span> <span data-ttu-id="83015-125">该上下文传递给四个 <xref:System.Windows.Markup.ValueSerializer> 虚方法的替代。</span><span class="sxs-lookup"><span data-stu-id="83015-125">That context is passed to overrides of the four <xref:System.Windows.Markup.ValueSerializer> virtual methods.</span></span> <span data-ttu-id="83015-126">从上下文调用 <xref:System.IServiceProvider.GetService%2A> 以获取服务。</span><span class="sxs-lookup"><span data-stu-id="83015-126">Call <xref:System.IServiceProvider.GetService%2A> from the context to obtain services.</span></span>

## <a name="using-the-xaml-service-provider-contexts"></a><span data-ttu-id="83015-127">使用 XAML 服务提供程序上下文</span><span class="sxs-lookup"><span data-stu-id="83015-127">Using the XAML Service Provider Contexts</span></span>

<span data-ttu-id="83015-128">用于 <xref:System.IServiceProvider.GetService%2A> 访问可用于标记扩展或类型转换器的 XAML 服务的服务提供程序作为内部类实现，并且仅通过接口以及将其传递到相关上下文中的方式公开。</span><span class="sxs-lookup"><span data-stu-id="83015-128">The service provider for <xref:System.IServiceProvider.GetService%2A> access to XAML services available to markup extensions or type converters is implemented as an internal class, with exposure only through the interface and how it is passed into the relevant context.</span></span> <span data-ttu-id="83015-129">只要加载路径或保存路径的默认 .NET XAML 服务实现中的 XAML 处理操作调用需要服务上下文的相关标记扩展或类型转换器方法，就会传递此内部对象。</span><span class="sxs-lookup"><span data-stu-id="83015-129">Whenever a XAML processing operation in the default .NET XAML Services implementations of load path or save path invokes the relevant markup extension or type converter methods that require a service context, this internal object is passed.</span></span> <span data-ttu-id="83015-130">根据具体情况，系统服务上下文提供 `MarkupExtensionContext` 或 `TextSyntaxContext`，但这两个特定类都是内部类。</span><span class="sxs-lookup"><span data-stu-id="83015-130">Depending on the circumstance, the system service context provides either `MarkupExtensionContext` or `TextSyntaxContext`, but the specifics of both of these classes are internal.</span></span> <span data-ttu-id="83015-131">你与这些类的交互仅限于通过 <xref:System.IServiceProvider.GetService%2A>从中请求服务。</span><span class="sxs-lookup"><span data-stu-id="83015-131">Your interaction with these classes is limited to requesting services from them, through <xref:System.IServiceProvider.GetService%2A>.</span></span>

## <a name="available-services-from-the-net-xaml-service-context"></a><span data-ttu-id="83015-132">.NET XAML 服务上下文中可用的服务</span><span class="sxs-lookup"><span data-stu-id="83015-132">Available Services from the .NET XAML Service Context</span></span>

<span data-ttu-id="83015-133">.NET XAML 服务为标记扩展、类型转换器、值序列化程序和可能的其他用法定义服务。</span><span class="sxs-lookup"><span data-stu-id="83015-133">.NET XAML Services defines services for markup extensions, type converters, value serializers, and potentially other usages.</span></span> <span data-ttu-id="83015-134">以下各节介绍每种服务，并提供有关可如何在实现中使用服务的指导。</span><span class="sxs-lookup"><span data-stu-id="83015-134">The following sections describe each of these services and provide guidance about how the service might be used in an implementation.</span></span>

### <a name="iserviceprovider"></a><span data-ttu-id="83015-135">IServiceProvider</span><span class="sxs-lookup"><span data-stu-id="83015-135">IServiceProvider</span></span>

<span data-ttu-id="83015-136">**参考文档**： <xref:System.IServiceProvider></span><span class="sxs-lookup"><span data-stu-id="83015-136">**Reference documentation**: <xref:System.IServiceProvider></span></span>

<span data-ttu-id="83015-137">**相关内容：** .NET 中基于服务的基础结构的基本操作，以便你可以调用 <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="83015-137">**Relevant to:** Basic operation of a service-based infrastructure in .NET so that you can call <xref:System.IServiceProvider.GetService%2A?displayProperty=nameWithType>.</span></span>

### <a name="itypedescriptorcontext"></a><span data-ttu-id="83015-138">ITypeDescriptorContext</span><span class="sxs-lookup"><span data-stu-id="83015-138">ITypeDescriptorContext</span></span>

<span data-ttu-id="83015-139">**参考文档**： <xref:System.ComponentModel.ITypeDescriptorContext></span><span class="sxs-lookup"><span data-stu-id="83015-139">**Reference documentation**: <xref:System.ComponentModel.ITypeDescriptorContext></span></span>

<span data-ttu-id="83015-140">派生自 <xref:System.IServiceProvider>。</span><span class="sxs-lookup"><span data-stu-id="83015-140">Derives from <xref:System.IServiceProvider>.</span></span> <span data-ttu-id="83015-141">此类表示标准 <xref:System.ComponentModel.TypeConverter> 签名中的上下文； <xref:System.ComponentModel.TypeConverter> 是自 .NET Framework 1.0 起就已存在的类。</span><span class="sxs-lookup"><span data-stu-id="83015-141">This class represents context in the standard <xref:System.ComponentModel.TypeConverter> signatures; <xref:System.ComponentModel.TypeConverter> is a class that has existed since .NET Framework 1.0.</span></span> <span data-ttu-id="83015-142">它早于用于字符串到值类型转换的 XAML 和 XAML <xref:System.ComponentModel.TypeConverter> 方案。</span><span class="sxs-lookup"><span data-stu-id="83015-142">It predates XAML and the XAML <xref:System.ComponentModel.TypeConverter> scenario for string-value type conversion.</span></span> <span data-ttu-id="83015-143">在 .NET XAML 服务上下文中，的方法 <xref:System.ComponentModel.TypeConverter> 是显式实现的。</span><span class="sxs-lookup"><span data-stu-id="83015-143">In .NET XAML Services context, methods of <xref:System.ComponentModel.TypeConverter> are implemented explicitly.</span></span> <span data-ttu-id="83015-144">显式实现的行为向调用方指示 <xref:System.ComponentModel.ITypeDescriptorContext> API 与 XAML 类型系统无关，或者与 XAML 中的读取或写入对象无关。</span><span class="sxs-lookup"><span data-stu-id="83015-144">The explicit implementation's behavior indicates to callers that the <xref:System.ComponentModel.ITypeDescriptorContext> API is not relevant for XAML type systems, or for reading or writing objects from XAML.</span></span> <span data-ttu-id="83015-145"><xref:System.ComponentModel.ITypeDescriptorContext.Container%2A>、 <xref:System.ComponentModel.ITypeDescriptorContext.Instance%2A> 和 <xref:System.ComponentModel.ITypeDescriptorContext.PropertyDescriptor%2A> 通常 `null` 从 .net XAML 服务上下文返回。</span><span class="sxs-lookup"><span data-stu-id="83015-145"><xref:System.ComponentModel.ITypeDescriptorContext.Container%2A>, <xref:System.ComponentModel.ITypeDescriptorContext.Instance%2A>, and <xref:System.ComponentModel.ITypeDescriptorContext.PropertyDescriptor%2A> generally return `null` from .NET XAML Services contexts.</span></span>

### <a name="ivalueserializercontext"></a><span data-ttu-id="83015-146">IValueSerializerContext</span><span class="sxs-lookup"><span data-stu-id="83015-146">IValueSerializerContext</span></span>

<span data-ttu-id="83015-147">**参考文档**： <xref:System.Windows.Markup.IValueSerializerContext></span><span class="sxs-lookup"><span data-stu-id="83015-147">**Reference documentation**: <xref:System.Windows.Markup.IValueSerializerContext></span></span>

<span data-ttu-id="83015-148">派生自 <xref:System.ComponentModel.ITypeDescriptorContext> ，并且还依赖于显式实现以抑制有关 XAML 类型系统的错误含义。</span><span class="sxs-lookup"><span data-stu-id="83015-148">Derives from <xref:System.ComponentModel.ITypeDescriptorContext> and also relies on explicit implementations to suppress false implications about the XAML type system.</span></span> <span data-ttu-id="83015-149">支持 <xref:System.Windows.Markup.ValueSerializer>上的静态查找帮助器方法。</span><span class="sxs-lookup"><span data-stu-id="83015-149">Supports the static lookup helper methods on <xref:System.Windows.Markup.ValueSerializer>.</span></span>

### <a name="ixamltyperesolver"></a><span data-ttu-id="83015-150">IXamlTypeResolver</span><span class="sxs-lookup"><span data-stu-id="83015-150">IXamlTypeResolver</span></span>

<span data-ttu-id="83015-151">**参考文档**： <xref:System.Windows.Markup.IXamlTypeResolver></span><span class="sxs-lookup"><span data-stu-id="83015-151">**Reference documentation**: <xref:System.Windows.Markup.IXamlTypeResolver></span></span>

<span data-ttu-id="83015-152">**由以下内容定义：**  <xref:System.Windows.Markup> 命名空间、System.Xaml 程序集</span><span class="sxs-lookup"><span data-stu-id="83015-152">**Defined by:**  <xref:System.Windows.Markup> namespace, System.Xaml assembly</span></span>

<span data-ttu-id="83015-153">**相关内容：** 加载路径方案以及与 XAML 架构上下文的交互</span><span class="sxs-lookup"><span data-stu-id="83015-153">**Relevant to:** Load path scenarios, and interaction with XAML schema context</span></span>

<span data-ttu-id="83015-154">**服务 API：**  <xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A></span><span class="sxs-lookup"><span data-stu-id="83015-154">**Service API:**  <xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A></span></span>

<span data-ttu-id="83015-155">可能会影响 XAML 到 CLR 类型映射，当 XAML 编写器在对象图中构造 CLR 对象时，此映射是必需的。</span><span class="sxs-lookup"><span data-stu-id="83015-155">Can influence the XAML-to-CLR type mapping that is necessary when the XAML writer constructs a CLR object in an object graph.</span></span> <span data-ttu-id="83015-156"><xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A> 处理对应于 XAML 类型名称 (<xref:System.Xaml.XamlType.Name%2A?displayProperty=nameWithType>) 的可能由前缀限定的字符串，并返回一个 CLR <xref:System.Type>。</span><span class="sxs-lookup"><span data-stu-id="83015-156"><xref:System.Windows.Markup.IXamlTypeResolver.Resolve%2A> processes a potentially prefix-qualified string that corresponds to a XAML type name (<xref:System.Xaml.XamlType.Name%2A?displayProperty=nameWithType>), and returns a CLR <xref:System.Type>.</span></span> <span data-ttu-id="83015-157">解析类型通常很大程度上取决于 XAML 架构上下文。</span><span class="sxs-lookup"><span data-stu-id="83015-157">Resolving types is typically heavily dependent on XAML schema context.</span></span> <span data-ttu-id="83015-158">只有 XAML 架构上下文了解注意事项，如加载哪些程序集以及可以或应访问其中哪些程序集以进行类型解析。</span><span class="sxs-lookup"><span data-stu-id="83015-158">Only the XAML schema context is aware of considerations such as which assemblies are loaded, and which of these assemblies can or should be accessed for type resolution.</span></span>

### <a name="iuricontext"></a><span data-ttu-id="83015-159">IUriContext</span><span class="sxs-lookup"><span data-stu-id="83015-159">IUriContext</span></span>

<span data-ttu-id="83015-160">**参考文档**： <xref:System.Windows.Markup.IUriContext></span><span class="sxs-lookup"><span data-stu-id="83015-160">**Reference documentation**: <xref:System.Windows.Markup.IUriContext></span></span>

<span data-ttu-id="83015-161">**由以下内容定义：**  <xref:System.Windows.Markup> 命名空间、System.Xaml 程序集</span><span class="sxs-lookup"><span data-stu-id="83015-161">**Defined by:**  <xref:System.Windows.Markup> namespace, System.Xaml assembly</span></span>

<span data-ttu-id="83015-162">**相关内容：** 是 URI 或 `x:Uri` 值的成员值的加载路径和保存路径处理。</span><span class="sxs-lookup"><span data-stu-id="83015-162">**Relevant to:** Load path and save path handling of member values that are URIs or `x:Uri` values.</span></span>

<span data-ttu-id="83015-163">**服务 API：**  <xref:System.Windows.Markup.IUriContext.BaseUri%2A></span><span class="sxs-lookup"><span data-stu-id="83015-163">**Service API:**  <xref:System.Windows.Markup.IUriContext.BaseUri%2A></span></span>

<span data-ttu-id="83015-164">此服务报告一个全局可用的 URI 根（如果有）。</span><span class="sxs-lookup"><span data-stu-id="83015-164">This service reports a globally available URI root, if any.</span></span> <span data-ttu-id="83015-165">可使用此 URI 根将相对 URI 解析为绝对 URI，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="83015-165">The URI root can be used to resolve relative URIs to absolute URIs or vice versa.</span></span> <span data-ttu-id="83015-166">此方案主要与由特定框架或框架中常用根元素类的功能公开的应用程序服务相关。</span><span class="sxs-lookup"><span data-stu-id="83015-166">This scenario is mainly relevant to application services that are exposed by a particular framework, or capabilities of a frequently used root element class in a framework.</span></span> <span data-ttu-id="83015-167">可以采用 XAML 读取器设置的形式建立基 URI，然后传递给 XAML 对象编写器并由此服务进行报告。</span><span class="sxs-lookup"><span data-stu-id="83015-167">The base URI can be established as a XAML reader setting, which is then passed through to the XAML object writer and reported by this service.</span></span>

### <a name="iambientprovider"></a><span data-ttu-id="83015-168">IAmbientProvider</span><span class="sxs-lookup"><span data-stu-id="83015-168">IAmbientProvider</span></span>

<span data-ttu-id="83015-169">**参考文档**： <xref:System.Xaml.IAmbientProvider></span><span class="sxs-lookup"><span data-stu-id="83015-169">**Reference documentation**: <xref:System.Xaml.IAmbientProvider></span></span>

<span data-ttu-id="83015-170">**由以下内容定义：**  <xref:System.Xaml> 命名空间、System.Xaml 程序集</span><span class="sxs-lookup"><span data-stu-id="83015-170">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>

<span data-ttu-id="83015-171">**相关内容：** 加载路径处理以及类型查找延迟或优化。</span><span class="sxs-lookup"><span data-stu-id="83015-171">**Relevant to:** Load path handling and type lookup deferrals or optimizations.</span></span>

<span data-ttu-id="83015-172">**服务 api：** <xref:System.Xaml.IAmbientProvider.GetAllAmbientValues%2A> 、其他三个。  </span><span class="sxs-lookup"><span data-stu-id="83015-172">**Service APIs:**  <xref:System.Xaml.IAmbientProvider.GetAllAmbientValues%2A>, three others.</span></span>

<span data-ttu-id="83015-173">XAML 中的环境概念是一种将类型的特定成员标记为环境的方法。</span><span class="sxs-lookup"><span data-stu-id="83015-173">The ambience concept in XAML is a technique for marking a particular member of a type as ambient.</span></span> <span data-ttu-id="83015-174">或者，某种类型也可以是环境，以便保留该类型实例的所有属性值都应视为环境属性。</span><span class="sxs-lookup"><span data-stu-id="83015-174">Alternatively, a type can be ambient so that all property values that hold an instance of the type should be considered ambient properties.</span></span> <span data-ttu-id="83015-175">沿 XAML 节点流前进或作为对象图中的后代的标记扩展或类型转换器可以在加载时访问环境属性或类型实例；也可以在保存时使用环境结构的知识。</span><span class="sxs-lookup"><span data-stu-id="83015-175">Markup extensions or type converters that are further along the XAML node stream and that are descendants in the object graph can access the ambient property or type instance at load time; or they can use knowledge of the ambient structure at save time.</span></span> <span data-ttu-id="83015-176">这可能会影响其他服务（例如， <xref:System.Windows.Markup.IXamlTypeResolver> 或 `x:Type`）的类型解析所需的限定程度。</span><span class="sxs-lookup"><span data-stu-id="83015-176">This can affect the degree of qualification that is needed to resolve types for other services, such as for <xref:System.Windows.Markup.IXamlTypeResolver> or for `x:Type`.</span></span> <span data-ttu-id="83015-177">另请参阅 <xref:System.Xaml.AmbientPropertyValue>。</span><span class="sxs-lookup"><span data-stu-id="83015-177">See also <xref:System.Xaml.AmbientPropertyValue>.</span></span>

### <a name="ixamlschemacontextprovider"></a><span data-ttu-id="83015-178">IXamlSchemaContextProvider</span><span class="sxs-lookup"><span data-stu-id="83015-178">IXamlSchemaContextProvider</span></span>

<span data-ttu-id="83015-179">**参考文档**： <xref:System.Xaml.IXamlSchemaContextProvider></span><span class="sxs-lookup"><span data-stu-id="83015-179">**Reference documentation**: <xref:System.Xaml.IXamlSchemaContextProvider></span></span>

<span data-ttu-id="83015-180">**由以下内容定义：**  <xref:System.Xaml> 命名空间、System.Xaml 程序集</span><span class="sxs-lookup"><span data-stu-id="83015-180">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>

<span data-ttu-id="83015-181">**相关内容：** 加载路径以及必须将 XAML 类型解析为后备类型的任何操作。</span><span class="sxs-lookup"><span data-stu-id="83015-181">**Relevant to:** Load path, and any operation that must resolve a XAML type to a backing type.</span></span>

<span data-ttu-id="83015-182">**服务 API：**  <xref:System.Xaml.IXamlSchemaContextProvider.SchemaContext%2A></span><span class="sxs-lookup"><span data-stu-id="83015-182">**Service API:**  <xref:System.Xaml.IXamlSchemaContextProvider.SchemaContext%2A></span></span>

<span data-ttu-id="83015-183">对于任何推迟加载操作，XAML 架构上下文都是必需的，因为同一架构上下文必须作用于推迟的区域才能集成推迟的内容。</span><span class="sxs-lookup"><span data-stu-id="83015-183">XAML schema context is necessary for any defer load operations, because the same schema context must act on the deferred area in order to integrate the deferred content.</span></span> <span data-ttu-id="83015-184">有关 XAML 架构上下文的角色的详细信息，请参阅 [XAML Services](/dotnet/api/)。</span><span class="sxs-lookup"><span data-stu-id="83015-184">For more information about the role of the XAML schema context, see [XAML Services](/dotnet/api/).</span></span>

### <a name="irootobjectprovider"></a><span data-ttu-id="83015-185">IRootObjectProvider</span><span class="sxs-lookup"><span data-stu-id="83015-185">IRootObjectProvider</span></span>

<span data-ttu-id="83015-186">**参考文档**： <xref:System.Xaml.IRootObjectProvider></span><span class="sxs-lookup"><span data-stu-id="83015-186">**Reference documentation**: <xref:System.Xaml.IRootObjectProvider></span></span>

<span data-ttu-id="83015-187">**由以下内容定义：**  <xref:System.Xaml> 命名空间、System.Xaml 程序集</span><span class="sxs-lookup"><span data-stu-id="83015-187">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>

<span data-ttu-id="83015-188">**相关内容：** 加载路径。</span><span class="sxs-lookup"><span data-stu-id="83015-188">**Relevant to:** Load path.</span></span>

<span data-ttu-id="83015-189">**服务 API：**  <xref:System.Xaml.IRootObjectProvider.RootObject%2A></span><span class="sxs-lookup"><span data-stu-id="83015-189">**Service API:**  <xref:System.Xaml.IRootObjectProvider.RootObject%2A></span></span>

<span data-ttu-id="83015-190">该服务与由特定框架或框架中常用根元素类的功能公开的应用程序服务相关。</span><span class="sxs-lookup"><span data-stu-id="83015-190">The service is relevant to application services that are exposed by a particular framework or by capabilities of a frequently used root element class in a framework.</span></span> <span data-ttu-id="83015-191">一种获取根对象的情况是连接代码隐藏和事件连结。</span><span class="sxs-lookup"><span data-stu-id="83015-191">One scenario for obtaining the root object is connecting code-behind and event wiring.</span></span> <span data-ttu-id="83015-192">例如， `x:Class` 的 WPF 实现用于 XAML 标记中任何其他位置处的任何事件处理程序特性的标记编译和连结。</span><span class="sxs-lookup"><span data-stu-id="83015-192">For example, the WPF implementation of `x:Class` is used for markup compile and wiring of any event handler attribute that is found at any other position in the XAML markup.</span></span> <span data-ttu-id="83015-193">标记与为标记编译定义分部类的代码隐藏的连接点在根元素处。</span><span class="sxs-lookup"><span data-stu-id="83015-193">The connection point of markup and code-behind defined partial classes for markup compile is at the root element.</span></span>

### <a name="ixamlnamespaceresolver"></a><span data-ttu-id="83015-194">IXamlNamespaceResolver</span><span class="sxs-lookup"><span data-stu-id="83015-194">IXamlNamespaceResolver</span></span>

<span data-ttu-id="83015-195">**参考文档**： <xref:System.Xaml.IXamlNamespaceResolver></span><span class="sxs-lookup"><span data-stu-id="83015-195">**Reference documentation**: <xref:System.Xaml.IXamlNamespaceResolver></span></span>

<span data-ttu-id="83015-196">**由以下内容定义：**  <xref:System.Xaml> 命名空间、System.Xaml 程序集</span><span class="sxs-lookup"><span data-stu-id="83015-196">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>

<span data-ttu-id="83015-197">**相关内容：** 加载路径、保存路径。</span><span class="sxs-lookup"><span data-stu-id="83015-197">**Relevant to:** Load path, save path.</span></span>

<span data-ttu-id="83015-198">**服务 API：** <xref:System.Xaml.IXamlNamespaceResolver.GetNamespace%2A> 对于 "保存路径"，则为 <xref:System.Xaml.IXamlNamespaceResolver.GetNamespacePrefixes%2A> 。</span><span class="sxs-lookup"><span data-stu-id="83015-198">**Service API:** <xref:System.Xaml.IXamlNamespaceResolver.GetNamespace%2A> for load path, <xref:System.Xaml.IXamlNamespaceResolver.GetNamespacePrefixes%2A> for save path.</span></span>

<span data-ttu-id="83015-199"><xref:System.Xaml.IXamlNamespaceResolver> 是一项服务，该服务可按照原始 XAML 标记中映射的方式基于 XAML 命名空间的前缀返回 XAML 命名空间标识符/URI。</span><span class="sxs-lookup"><span data-stu-id="83015-199"><xref:System.Xaml.IXamlNamespaceResolver> is a service that can return a XAML namespace identifier / URI based on its prefix as mapped in the originating XAML markup.</span></span>

### <a name="iprovidevaluetarget"></a><span data-ttu-id="83015-200">IProvideValueTarget</span><span class="sxs-lookup"><span data-stu-id="83015-200">IProvideValueTarget</span></span>

<span data-ttu-id="83015-201">**参考文档**： <xref:System.Windows.Markup.IProvideValueTarget></span><span class="sxs-lookup"><span data-stu-id="83015-201">**Reference documentation**: <xref:System.Windows.Markup.IProvideValueTarget></span></span>

<span data-ttu-id="83015-202">**由以下内容定义：**  <xref:System.Windows.Markup> 命名空间、System.Xaml 程序集</span><span class="sxs-lookup"><span data-stu-id="83015-202">**Defined by:**  <xref:System.Windows.Markup> namespace, System.Xaml assembly</span></span>

<span data-ttu-id="83015-203">**相关内容：** 加载路径和保存路径。</span><span class="sxs-lookup"><span data-stu-id="83015-203">**Relevant to:** Load path and save path.</span></span>

<span data-ttu-id="83015-204">**服务 api：** <xref:System.Windows.Markup.IProvideValueTarget.TargetObject%2A> 、 <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A> 。  </span><span class="sxs-lookup"><span data-stu-id="83015-204">**Service APIs:**  <xref:System.Windows.Markup.IProvideValueTarget.TargetObject%2A>, <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A>.</span></span>

<span data-ttu-id="83015-205"><xref:System.Windows.Markup.IProvideValueTarget> 可使类型转换器或标记扩展能够获取有关加载时作用位置的上下文。</span><span class="sxs-lookup"><span data-stu-id="83015-205"><xref:System.Windows.Markup.IProvideValueTarget> enables a type converter or markup extension to obtain context about where it is acting at load time.</span></span> <span data-ttu-id="83015-206">实现可能使用此上下文来使某个用法失效。</span><span class="sxs-lookup"><span data-stu-id="83015-206">Implementations might use this context to invalidate a usage.</span></span> <span data-ttu-id="83015-207">例如，WPF 在其某些标记扩展（例如 <xref:System.Windows.DynamicResourceExtension>）中具有逻辑。</span><span class="sxs-lookup"><span data-stu-id="83015-207">For example, WPF has logic inside some of its markup extensions such as <xref:System.Windows.DynamicResourceExtension>.</span></span> <span data-ttu-id="83015-208">该逻辑检查 <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A> 以确保该扩展仅用于设置依赖项属性（或其他非依赖项属性的简短列表）。</span><span class="sxs-lookup"><span data-stu-id="83015-208">The logic checks the <xref:System.Windows.Markup.IProvideValueTarget.TargetProperty%2A> to make sure that the extension is only used to set dependency properties (or a short list of other non-dependency properties).</span></span>

### <a name="ixamlnameresolver"></a><span data-ttu-id="83015-209">IXamlNameResolver</span><span class="sxs-lookup"><span data-stu-id="83015-209">IXamlNameResolver</span></span>

<span data-ttu-id="83015-210">**参考文档**： <xref:System.Xaml.IXamlNameResolver></span><span class="sxs-lookup"><span data-stu-id="83015-210">**Reference documentation**: <xref:System.Xaml.IXamlNameResolver></span></span>

<span data-ttu-id="83015-211">**由以下内容定义：**  <xref:System.Xaml> 命名空间、System.Xaml 程序集</span><span class="sxs-lookup"><span data-stu-id="83015-211">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>

<span data-ttu-id="83015-212">**相关内容：** 加载路径对象关系图定义，解析由 `x:Name` 、 `x:Reference` 或特定于框架的技术标识的对象。</span><span class="sxs-lookup"><span data-stu-id="83015-212">**Relevant to:** Load path object graph definition, resolving objects identified by `x:Name`, `x:Reference`, or framework-specific techniques.</span></span>

<span data-ttu-id="83015-213">**服务 API：**  <xref:System.Xaml.IXamlNameResolver.Resolve%2A>；用于更高级方案（如处理前向引用）的其他 API。</span><span class="sxs-lookup"><span data-stu-id="83015-213">**Service APIs:**  <xref:System.Xaml.IXamlNameResolver.Resolve%2A>; other APIs for more advanced scenarios such as dealing with forward references.</span></span>

<span data-ttu-id="83015-214">处理的 .NET XAML 服务实现 `x:Reference` 依赖于此服务。</span><span class="sxs-lookup"><span data-stu-id="83015-214">.NET XAML Services implementation of `x:Reference` handling relies on this service.</span></span> <span data-ttu-id="83015-215">特定框架或支持框架的工具使用此服务进行 `x:Name` 处理或等效的（<xref:System.Windows.Markup.RuntimeNamePropertyAttribute> 特性化）属性处理。</span><span class="sxs-lookup"><span data-stu-id="83015-215">Specific frameworks or tools that support the framework use this service for `x:Name` handling or equivalent (<xref:System.Windows.Markup.RuntimeNamePropertyAttribute> attributed) property handling.</span></span>

### <a name="idestinationtypeprovider"></a><span data-ttu-id="83015-216">IDestinationTypeProvider</span><span class="sxs-lookup"><span data-stu-id="83015-216">IDestinationTypeProvider</span></span>

<span data-ttu-id="83015-217">**参考文档**： <xref:System.Xaml.IDestinationTypeProvider></span><span class="sxs-lookup"><span data-stu-id="83015-217">**Reference documentation**: <xref:System.Xaml.IDestinationTypeProvider></span></span>

<span data-ttu-id="83015-218">**由以下内容定义：**  <xref:System.Xaml> 命名空间、System.Xaml 程序集</span><span class="sxs-lookup"><span data-stu-id="83015-218">**Defined by:**  <xref:System.Xaml> namespace, System.Xaml assembly</span></span>

<span data-ttu-id="83015-219">**相关内容：** 间接 CLR 类型信息的加载路径解析。</span><span class="sxs-lookup"><span data-stu-id="83015-219">**Relevant to:** Load path resolution of indirect CLR type information.</span></span>

<span data-ttu-id="83015-220">**服务 API：**<xref:System.Xaml.IDestinationTypeProvider.GetDestinationType%2A></span><span class="sxs-lookup"><span data-stu-id="83015-220">**Service API:** <xref:System.Xaml.IDestinationTypeProvider.GetDestinationType%2A></span></span>

<span data-ttu-id="83015-221">有关详细信息，请参阅 <xref:System.Xaml.IDestinationTypeProvider>。</span><span class="sxs-lookup"><span data-stu-id="83015-221">For more information, see <xref:System.Xaml.IDestinationTypeProvider>.</span></span>

## <a name="see-also"></a><span data-ttu-id="83015-222">请参阅</span><span class="sxs-lookup"><span data-stu-id="83015-222">See also</span></span>

- <xref:System.Windows.Markup.MarkupExtension>
- <xref:System.Xaml.XamlObjectWriter>
- [<span data-ttu-id="83015-223">XAML 的标记扩展概述</span><span class="sxs-lookup"><span data-stu-id="83015-223">Markup Extensions for XAML Overview</span></span>](markup-extensions-overview.md)
- [<span data-ttu-id="83015-224">XAML 的类型转换器概述</span><span class="sxs-lookup"><span data-stu-id="83015-224">Type Converters for XAML Overview</span></span>](type-converters-overview.md)
