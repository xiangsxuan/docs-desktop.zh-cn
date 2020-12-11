---
title: x:FactoryMethod 指令
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 5e864b6f5d664b079036a5d915e2f6f81b83639f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970929"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="c907a-102">x:FactoryMethod 指令</span><span class="sxs-lookup"><span data-stu-id="c907a-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="c907a-103">指定一个方法，该方法不是 XAML 处理器在解析其支持类型后用于初始化对象的构造函数。</span><span class="sxs-lookup"><span data-stu-id="c907a-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="c907a-104">XAML 特性用法，无 x:Arguments</span><span class="sxs-lookup"><span data-stu-id="c907a-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="c907a-105">XAML 特性用法，x:Arguments 作为元素 (s) </span><span class="sxs-lookup"><span data-stu-id="c907a-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c907a-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="c907a-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="c907a-107">XAML 处理器调用以初始化指定为的实例的方法的字符串方法名称 `object` 。</span><span class="sxs-lookup"><span data-stu-id="c907a-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="c907a-108">请参阅“备注”。</span><span class="sxs-lookup"><span data-stu-id="c907a-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="c907a-109">用于指定工厂方法参数的对象的一个或多个对象元素。</span><span class="sxs-lookup"><span data-stu-id="c907a-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="c907a-110">顺序非常重要;它表示应将参数传递给工厂方法的顺序。</span><span class="sxs-lookup"><span data-stu-id="c907a-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c907a-111">备注</span><span class="sxs-lookup"><span data-stu-id="c907a-111">Remarks</span></span>  
 <span data-ttu-id="c907a-112">如果 `methodname` 是实例方法，则不能对其进行限定。</span><span class="sxs-lookup"><span data-stu-id="c907a-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="c907a-113">支持静态方法作为工厂方法。</span><span class="sxs-lookup"><span data-stu-id="c907a-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="c907a-114">如果 `methodname` 是静态方法， `methodname` 则以组合形式提供 `typeName.methodName` ，其中 `typeName` 命名定义静态工厂方法的类。</span><span class="sxs-lookup"><span data-stu-id="c907a-114">If `methodname` is a static method, `methodname` is provided as a `typeName.methodName` combination, where `typeName` names the class that defines the static factory method.</span></span> <span data-ttu-id="c907a-115">`typeName` 如果引用映射的 xmlns 中的类型，则可以是前缀限定的。</span><span class="sxs-lookup"><span data-stu-id="c907a-115">`typeName` can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="c907a-116">`typeName` 可以是不同于的类型 `typeof(object)` 。</span><span class="sxs-lookup"><span data-stu-id="c907a-116">`typeName` can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="c907a-117">工厂方法必须是该类型的声明的公共方法，该方法支持相关的对象元素。</span><span class="sxs-lookup"><span data-stu-id="c907a-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="c907a-118">工厂方法必须返回可分配给相关对象的实例。</span><span class="sxs-lookup"><span data-stu-id="c907a-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="c907a-119">工厂方法绝不应返回 null。</span><span class="sxs-lookup"><span data-stu-id="c907a-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="c907a-120">`x:Arguments` 对工厂方法签名的最佳匹配原则进行操作。</span><span class="sxs-lookup"><span data-stu-id="c907a-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="c907a-121">匹配首先计算参数计数。</span><span class="sxs-lookup"><span data-stu-id="c907a-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="c907a-122">如果某个参数计数有多个可能的匹配项，则将计算参数类型并确定最佳匹配项。</span><span class="sxs-lookup"><span data-stu-id="c907a-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="c907a-123">如果在此计算阶段后仍然存在歧义，则 XAML 处理器行为是不确定的。</span><span class="sxs-lookup"><span data-stu-id="c907a-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="c907a-124">`x:FactoryMethod`由于指令标记不引用包含对象元素的类型，因此元素用法不是属性元素的用法。</span><span class="sxs-lookup"><span data-stu-id="c907a-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="c907a-125">预期元素用法不如属性用法常见。</span><span class="sxs-lookup"><span data-stu-id="c907a-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="c907a-126">`x:Arguments` (特性或元素使用情况) 可以与 `x:FactoryMethod` 元素使用一起使用，但不会在用法部分中明确显示。</span><span class="sxs-lookup"><span data-stu-id="c907a-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="c907a-127">`x:FactoryMethod` 作为元素必须位于任何其他属性元素之前，必须 `x:Arguments` 在提供的任何元素前面作为元素，并且必须位于任何内容/内部文本/初始化文本之前。</span><span class="sxs-lookup"><span data-stu-id="c907a-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c907a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c907a-128">See also</span></span>

- [<span data-ttu-id="c907a-129">x:Arguments 指令</span><span class="sxs-lookup"><span data-stu-id="c907a-129">x:Arguments Directive</span></span>](xarguments-directive.md)
