---
title: x:Arguments 指令
description: X:Arguments 指令为 XAML 中的非参数构造函数对象元素打包构造参数。
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 21b7b2b13c0255445f9b838b3b115a42d5af119a
ms.sourcegitcommit: 32616f61a7b001efcc8567fee5fdf01f83da76cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "107560239"
---
# <a name="xarguments-directive"></a><span data-ttu-id="a0ff1-103">x:Arguments 指令</span><span class="sxs-lookup"><span data-stu-id="a0ff1-103">x:Arguments Directive</span></span>

<span data-ttu-id="a0ff1-104">为 XAML 中的非参数构造函数对象元素声明或工厂方法对象声明包构造参数。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-104">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>

## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="a0ff1-105">XAML 元素用法 (Nonparameterless 构造函数) </span><span class="sxs-lookup"><span data-stu-id="a0ff1-105">XAML Element Usage (Nonparameterless constructor)</span></span>

```xaml
<object ...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="a0ff1-106">XAML 元素用法 (工厂方法) </span><span class="sxs-lookup"><span data-stu-id="a0ff1-106">XAML Element Usage (factory method)</span></span>

```xaml
<object x:FactoryMethod="methodName"...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="a0ff1-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="a0ff1-107">XAML Values</span></span>

| <span data-ttu-id="a0ff1-108">值</span><span class="sxs-lookup"><span data-stu-id="a0ff1-108">Value</span></span> | <span data-ttu-id="a0ff1-109">说明</span><span class="sxs-lookup"><span data-stu-id="a0ff1-109">Description</span></span> |
|-|-|
|`oneOrMoreObjectElements`|<span data-ttu-id="a0ff1-110">一个或多个对象元素，用于指定要传递给支持的非参数构造函数或工厂方法的参数。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-110">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="a0ff1-111">典型用法是使用对象元素中的初始化文本来指定实际参数值。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-111">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="a0ff1-112">请参阅“示例”部分。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-112">See Examples section.</span></span><br /><br /> <span data-ttu-id="a0ff1-113">元素的顺序非常重要。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-113">The order of the elements is significant.</span></span> <span data-ttu-id="a0ff1-114">按顺序排列的 XAML 类型必须与后备构造函数或工厂方法重载的类型和类型顺序相匹配。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-114">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|
|`methodName`|<span data-ttu-id="a0ff1-115">应处理任何参数的工厂方法的名称 `x:Arguments` 。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-115">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="a0ff1-116">依赖关系</span><span class="sxs-lookup"><span data-stu-id="a0ff1-116">Dependencies</span></span>

<span data-ttu-id="a0ff1-117">`x:FactoryMethod` 可以修改应用的作用域和行为 `x:Arguments` 。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-117">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>

<span data-ttu-id="a0ff1-118">如果未 `x:FactoryMethod` 指定，则 `x:Arguments` 应用于后备构造函数的备用 (非默认) 签名。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-118">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>

<span data-ttu-id="a0ff1-119">如果 `x:FactoryMethod` 指定，则 `x:Arguments` 应用于命名方法的重载。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-119">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>

## <a name="remarks"></a><span data-ttu-id="a0ff1-120">注解</span><span class="sxs-lookup"><span data-stu-id="a0ff1-120">Remarks</span></span>

<span data-ttu-id="a0ff1-121">XAML 2006 可以通过初始化文本支持非默认初始化。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-121">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="a0ff1-122">但是，初始化文本构造技术的实际应用程序是有限的。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-122">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="a0ff1-123">初始化文本被视为单个文本字符串;因此，它仅添加单个参数初始化的功能，除非为构造行为定义了一个类型转换器，此构造行为可分析自定义信息项和字符串中的自定义分隔符。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-123">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="a0ff1-124">此外，文本字符串到对象逻辑可能是给定的 XAML 分析器用于处理除 true 字符串以外的基元的本机默认类型转换器。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-124">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>

<span data-ttu-id="a0ff1-125">`x:Arguments`XAML 用法不是典型意义上的属性元素用法，因为指令标记不引用包含对象元素的类型。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-125">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="a0ff1-126">它更类似于其他指令，例如 `x:Code` 元素 demarks 的范围，其中的标记应被解释为除子内容的默认值以外的其他指令。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-126">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="a0ff1-127">在这种情况下，每个对象元素的 XAML 类型会传达有关参数类型的信息，XAML 分析器使用这些信息来确定 `x:Arguments` 使用情况正在尝试引用的特定构造函数工厂方法签名。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-127">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>

<span data-ttu-id="a0ff1-128">`x:Arguments` 对于正在构造的对象元素，必须在该对象元素的任何其他属性元素、内容、内部文本或初始化字符串之前。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-128">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="a0ff1-129">中的对象元素 `x:Arguments` 可以包括属性和初始化字符串，这是该 XAML 类型及其后备构造函数或工厂方法所允许的。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-129">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="a0ff1-130">对于对象或参数，可以通过引用已建立的前缀映射来指定默认 XAML 命名空间之外的自定义 XAML 类型或 XAML 类型。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-130">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>

<span data-ttu-id="a0ff1-131">XAML 处理器使用以下准则来确定应如何使用中指定的参数 `x:Arguments` 来构造对象。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-131">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="a0ff1-132">如果 `x:FactoryMethod` 指定了，则会将信息与指定 (进行比较， `x:FactoryMethod` 请注意，的值 `x:FactoryMethod` 为方法名称，并且命名方法可以具有重载。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-132">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="a0ff1-133">如果 `x:FactoryMethod` 未指定，则会将信息与对象的所有公共构造函数重载集进行比较。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-133">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="a0ff1-134">然后，XAML 处理逻辑会比较参数的数目，并选择具有匹配 arity 的重载。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-134">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="a0ff1-135">如果有多个匹配项，则 XAML 处理器应根据提供的对象元素的 XAML 类型来比较参数的类型。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-135">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="a0ff1-136">如果仍有多个匹配项，则 XAML 处理器行为是不确定的。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-136">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="a0ff1-137">如果 `x:FactoryMethod` 指定了，但无法解析方法，则 XAML 处理器应引发异常。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-137">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>

<span data-ttu-id="a0ff1-138">`<x:Arguments>string</x:Arguments>`从技术上讲，可以使用 XAML 属性。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-138">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="a0ff1-139">但是，这不会提供除通过初始化文本和类型转换器以外的任何功能，并且使用此语法不是 XAML 2009 工厂方法功能的设计意图。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-139">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>

## <a name="examples"></a><span data-ttu-id="a0ff1-140">示例</span><span class="sxs-lookup"><span data-stu-id="a0ff1-140">Examples</span></span>

<span data-ttu-id="a0ff1-141">下面的示例演示一个无参数的构造函数签名，然后是 `x:Arguments` 用于访问该签名的的 XAML 用法。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-141">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public class Food {
  private string _name;
  private Int32 _calories;
  public Food(string name, Int32 calories) {
      _name=name;
      _calories=calories;
  }
}
```

```xaml
<my:Food>
  <x:Arguments>
      <x:String>Apple</x:String>
      <x:Int32>150</x:Int32>
  </x:Arguments>
</my:Food>
```

<span data-ttu-id="a0ff1-142">下面的示例演示了一个目标工厂方法签名，然后是 `x:Arguments` 用于访问该签名的的 XAML 用法。</span><span class="sxs-lookup"><span data-stu-id="a0ff1-142">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public Food TryLookupFood(string name)
{
switch (name) {
  case "Apple": return new Food("Apple",150);
  case "Chocolate": return new Food("Chocolate",200);
  case "Cheese": return new Food("Cheese", 450);
  default: {return new Food(name,0);
}
}
```

```xaml
<my:Food x:FactoryMethod="TryLookupFood">
  <x:Arguments>
      <x:String>Apple</x:String>
  </x:Arguments>
</my:Food>
```

## <a name="see-also"></a><span data-ttu-id="a0ff1-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0ff1-143">See also</span></span>

- [<span data-ttu-id="a0ff1-144">定义与 .NET XAML 服务一起使用的自定义类型</span><span class="sxs-lookup"><span data-stu-id="a0ff1-144">Defining Custom Types for Use with .NET XAML Services</span></span>](define-custom-types.md)
- [<span data-ttu-id="a0ff1-145">XAML 概述 (WPF .NET)</span><span class="sxs-lookup"><span data-stu-id="a0ff1-145">XAML overview (WPF .NET)</span></span>](../net/wpf/xaml/index.md)
