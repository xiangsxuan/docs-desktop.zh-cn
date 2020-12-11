---
title: x:Class 指令
ms.date: 03/30/2017
f1_keywords:
- x:Class
- xClass
- Class
helpviewer_keywords:
- Class attribute in XAML [XAML Services]
- XAML [XAML Services], x:Class attribute
- x:Class attribute [XAML Services]
ms.assetid: bc4a3d8e-76e2-423e-a5d1-159a023e82ec
ms.openlocfilehash: feada5fa118f3f39170a4d269155e71a56f5b085
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973849"
---
# <a name="xclass-directive"></a><span data-ttu-id="8b2a3-102">x:Class 指令</span><span class="sxs-lookup"><span data-stu-id="8b2a3-102">x:Class Directive</span></span>

<span data-ttu-id="8b2a3-103">将 XAML 标记编译配置为在标记和代码隐藏之间加入分部类。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-103">Configures XAML markup compilation to join partial classes between markup and code-behind.</span></span> <span data-ttu-id="8b2a3-104">代码分部类以公共语言规范 (CLS) 语言在单独的代码文件中定义，而标记分部类通常在 XAML 编译过程中由代码生成创建。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-104">The code partial class is defined in a separate code file in a Common Language Specification (CLS) language, whereas the markup partial class is typically created by code generation during XAML compilation.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="8b2a3-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="8b2a3-105">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname"...>
  ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="8b2a3-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="8b2a3-106">XAML Values</span></span>

|||
|-|-|
|`namespace`|<span data-ttu-id="8b2a3-107">可选。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-107">Optional.</span></span> <span data-ttu-id="8b2a3-108">指定一个 CLR 命名空间，该命名空间包含由标识的分部类 `classname` 。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-108">Specifies a CLR namespace that contains the partial class identified by `classname`.</span></span> <span data-ttu-id="8b2a3-109">如果 `namespace` 指定了，则 ( 一个点。 ) 分隔 `namespace` 和 `classname` 。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-109">If `namespace` is specified, a dot (.) separates `namespace` and `classname`.</span></span> <span data-ttu-id="8b2a3-110">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-110">See Remarks.</span></span>|
|`classname`|<span data-ttu-id="8b2a3-111">必需。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-111">Required.</span></span> <span data-ttu-id="8b2a3-112">指定用于连接加载的 XAML 的分部类的 CLR 名称和该 XAML 的代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-112">Specifies the CLR name of the partial class that connects the loaded XAML and your code-behind for that XAML.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="8b2a3-113">依赖项</span><span class="sxs-lookup"><span data-stu-id="8b2a3-113">Dependencies</span></span>

<span data-ttu-id="8b2a3-114">`x:Class` 只能在 XAML 生产的根元素上指定。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-114">`x:Class` can only be specified on the root element of a XAML production.</span></span> <span data-ttu-id="8b2a3-115">`x:Class` 对于在 XAML 生产中具有父对象的任何对象无效。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-115">`x:Class` is invalid on any object that has a parent in the XAML production.</span></span> <span data-ttu-id="8b2a3-116">有关详细信息，请参阅[ \[ \] 4.3.1.6 部分](/previous-versions/msp-n-p/ff650760(v=pandp.10))。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-116">For more information, see [\[MS-XAML\] Section 4.3.1.6](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="remarks"></a><span data-ttu-id="8b2a3-117">备注</span><span class="sxs-lookup"><span data-stu-id="8b2a3-117">Remarks</span></span>

<span data-ttu-id="8b2a3-118">`namespace`值可能包含用于将相关命名空间组织到名称层次结构中的其他点，这是 .net 编程中的一种常用技术。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-118">The `namespace` value may contain additional dots to organize related namespaces into name hierarchies, which is a common technique in .NET programming.</span></span> <span data-ttu-id="8b2a3-119">只有值字符串中的最后一个点 `x:Class` 被解释为单独的 `namespace` ，且 `classname.` 使用的类 `x:Class` 不能为嵌套类。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-119">Only the last dot in a string of `x:Class` values is interpreted to separate `namespace` and `classname.` The class that is used as `x:Class` cannot be a nested class.</span></span> <span data-ttu-id="8b2a3-120">不允许使用嵌套类，因为 `x:Class` 如果允许嵌套类，则确定字符串点的含义不明确。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-120">Nested classes are not allowed because determining the meaning of dots for `x:Class` strings is ambiguous if nested classes are permitted.</span></span>

<span data-ttu-id="8b2a3-121">在使用的现有编程模型中 `x:Class` ， `x:Class` 是可选的，因为有一个 XAML 页没有代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-121">In existing programming models that use `x:Class`, `x:Class` is optional in the sense that it is entirely valid to have a XAML page that has no code-behind.</span></span> <span data-ttu-id="8b2a3-122">但是，该功能与使用 XAML 的框架实现的生成操作交互。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-122">However, that capability interacts with the build actions as implemented by frameworks that use XAML.</span></span> <span data-ttu-id="8b2a3-123">`x:Class` 功能还受 XAML 指定内容的各种分类在应用程序模型中以及对应的生成操作中的作用。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-123">`x:Class` capability is also influenced by the roles that various classifications of XAML-specified content have in an application model and in the corresponding build actions.</span></span> <span data-ttu-id="8b2a3-124">如果 XAML 声明事件处理特性值或实例化自定义元素（其中定义类在代码隐藏类中），则必须为 `x:Class` 代码隐藏提供 (或 [x:Subclass](xsubclass-directive.md)) 的指令引用到适当的类。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-124">If your XAML declares event-handling attribute values or instantiates custom elements where the defining classes are in the code-behind class, you have to provide the `x:Class` directive reference (or [x:Subclass](xsubclass-directive.md)) to the appropriate class for code-behind.</span></span>

<span data-ttu-id="8b2a3-125">指令的值 `x:Class` 必须是一个字符串，该字符串指定类的完全限定名，但不 (等效于) 的任何程序集信息 <xref:System.Type.FullName%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-125">The value of the `x:Class` directive must be a string that specifies the fully qualified name of a class but without any assembly information (equivalent to the <xref:System.Type.FullName%2A?displayProperty=nameWithType>).</span></span> <span data-ttu-id="8b2a3-126">对于简单的应用程序，如果代码隐藏也是以这种方式构造的，则可以省略 CLR 命名空间信息， (代码定义从类级别) 。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-126">For simple applications, you can omit CLR namespace information if the code-behind is also structured in that manner (code definition starts at the class level).</span></span>

<span data-ttu-id="8b2a3-127">页面或应用程序定义的代码隐藏文件必须位于代码文件中，该代码文件包含在生成已编译的应用程序并涉及标记编译的项目中。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-127">The code-behind file for a page or application definition must be within a code file that is included as part of the project that produces a compiled application and involves markup compilation.</span></span> <span data-ttu-id="8b2a3-128">必须遵循 CLR 类的名称规则。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-128">You must follow name rules for CLR classes.</span></span> <span data-ttu-id="8b2a3-129">有关详细信息，请参阅 [框架设计准则](/dotnet/api/)。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-129">For more information, see [Framework Design Guidelines](/dotnet/api/).</span></span> <span data-ttu-id="8b2a3-130">默认情况下，代码隐藏类必须是 `public` ; 但是，您可以使用 [x:ClassModifier 指令](xclassmodifier-directive.md)在不同的访问级别定义它。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-130">By default, the code-behind class must be `public`; however, you can define it at a different access level by using the [x:ClassModifier Directive](xclassmodifier-directive.md).</span></span>

<span data-ttu-id="8b2a3-131">此属性的解释 `x:Class` 仅适用于基于 CLR 的 xaml 实现，尤其是 .NET Xaml 服务。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-131">This interpretation of the `x:Class` attribute applies only to a CLR-based XAML implementation, in particular to .NET XAML Services.</span></span> <span data-ttu-id="8b2a3-132">其他不基于 CLR 并且不使用 .NET XAML 服务的 XAML 实现可能会使用不同的解析公式来连接 XAML 标记和支持运行时代码。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-132">Other XAML implementations that are not based on CLR and that do not use .NET XAML Services might use a different resolution formula for connecting XAML markup and backing run-time code.</span></span> <span data-ttu-id="8b2a3-133">有关的更多一般解释的详细信息 `x:Class` ，请参阅 " [ \[ MS-XAML \] ](/previous-versions/msp-n-p/ff650760(v=pandp.10))"。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-133">For more information about more general interpretations of `x:Class`, see [\[MS-XAML\]](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

<span data-ttu-id="8b2a3-134">在特定的体系结构级别， `x:Class` .NET XAML 服务中没有定义的含义。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-134">At a certain level of architecture, the meaning of `x:Class` is undefined in .NET XAML Services.</span></span> <span data-ttu-id="8b2a3-135">这是因为，.NET XAML 服务不会指定用于连接 XAML 标记和支持代码的编程模型。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-135">This is because .NET XAML Services does not specify the programming model by which XAML markup and backing code are connected.</span></span> <span data-ttu-id="8b2a3-136">指令的其他用法 `x:Class` 可能由使用编程模型或应用程序模型的特定框架实现，以定义如何连接 XAML 标记和基于 CLR 的代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-136">Additional uses of the `x:Class` directive might be implemented by specific frameworks that use programming models or application models to define how to connect XAML markup and CLR-based code-behind.</span></span> <span data-ttu-id="8b2a3-137">每个框架都可以有自己的生成操作，这些操作可实现某些必须包括在生成环境中的行为或特定组件。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-137">Each framework can have its own build actions that enable some of the behavior or specific components that must be included in the build environment.</span></span> <span data-ttu-id="8b2a3-138">在框架中，生成操作也可能根据用于代码隐藏的特定 CLR 语言而有所不同。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-138">Within a framework, build actions can also vary depending on the specific CLR language that is used for the code-behind.</span></span>

## <a name="xclass-in-the-wpf-programming-model"></a><span data-ttu-id="8b2a3-139">WPF 编程模型中的 X：Class</span><span class="sxs-lookup"><span data-stu-id="8b2a3-139">x:Class in the WPF Programming Model</span></span>

<span data-ttu-id="8b2a3-140">在 WPF 应用程序和 WPF 应用程序模型中， `x:Class` 可以将作为 xaml 文件的根的任何元素的属性声明为，并将其编译 (其中，xaml 包含在具有生成操作) 的 WPF 应用程序项目中 `Page` ，或用于 <xref:System.Windows.Application> 编译的 wpf 应用程序的应用程序定义中的根。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-140">In WPF applications and the WPF application model, `x:Class` can be declared as an attribute for any element that is the root of a XAML file and is being compiled (where the XAML is included in a WPF application project with `Page` build action), or for the <xref:System.Windows.Application> root in the application definition of a compiled WPF application.</span></span> <span data-ttu-id="8b2a3-141">`x:Class`在页根或应用程序根以外的元素或未编译的 WPF xaml 文件上声明会导致 .NET Framework 3.0 和 .NET Framework 3.5 WPF xaml 编译器下出现编译时错误。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-141">Declaring `x:Class` on an element other than a page root or application root, or on a WPF XAML file that is not compiled, causes a compile-time error under the .NET Framework 3.0 and .NET Framework 3.5 WPF XAML compiler.</span></span> <span data-ttu-id="8b2a3-142">有关 WPF 中的其他处理方面的信息 `x:Class` ，请参阅 [wpf 中的代码隐藏和 XAML](../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-142">For information about other aspects of `x:Class` handling in WPF, see [Code-Behind and XAML in WPF](../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).</span></span>

## <a name="xclass-for-windows-workflow-foundation"></a><span data-ttu-id="8b2a3-143">适用于 Windows Workflow Foundation 的 X：Class</span><span class="sxs-lookup"><span data-stu-id="8b2a3-143">x:Class for Windows Workflow Foundation</span></span>

<span data-ttu-id="8b2a3-144">对于 "Windows Workflow Foundation"，请对 `x:Class` 完全在 XAML 中组成的自定义活动的类进行命名，或使用代码隐藏为活动设计器命名 XAML 页的分部类。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-144">For Windows Workflow Foundation, `x:Class` names the class of a custom activity composed entirely in XAML, or names the partial class of the XAML page for  an activity designer with code-behind.</span></span>

## <a name="silverlight-usage-notes"></a><span data-ttu-id="8b2a3-145">Silverlight 使用说明</span><span class="sxs-lookup"><span data-stu-id="8b2a3-145">Silverlight Usage Notes</span></span>

<span data-ttu-id="8b2a3-146">`x:Class` 对于 Silverlight，单独记录。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-146">`x:Class` for Silverlight is documented separately.</span></span> <span data-ttu-id="8b2a3-147">有关详细信息，请参阅 [XAML 命名空间 (x： ) 语言功能 (Silverlight) ](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95))。</span><span class="sxs-lookup"><span data-stu-id="8b2a3-147">For more information, see [XAML Namespace (x:) Language Features (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).</span></span>

## <a name="see-also"></a><span data-ttu-id="8b2a3-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b2a3-148">See also</span></span>

- [<span data-ttu-id="8b2a3-149">x:Subclass 指令</span><span class="sxs-lookup"><span data-stu-id="8b2a3-149">x:Subclass Directive</span></span>](xsubclass-directive.md)
- [<span data-ttu-id="8b2a3-150">XAML 及 WPF 的自定义类</span><span class="sxs-lookup"><span data-stu-id="8b2a3-150">XAML and Custom Classes for WPF</span></span>](../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [<span data-ttu-id="8b2a3-151">x:ClassModifier 指令</span><span class="sxs-lookup"><span data-stu-id="8b2a3-151">x:ClassModifier Directive</span></span>](xclassmodifier-directive.md)
- [<span data-ttu-id="8b2a3-152">从 WPF 迁移到 System.Xaml 的类型</span><span class="sxs-lookup"><span data-stu-id="8b2a3-152">Types Migrated from WPF to System.Xaml</span></span>](../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
