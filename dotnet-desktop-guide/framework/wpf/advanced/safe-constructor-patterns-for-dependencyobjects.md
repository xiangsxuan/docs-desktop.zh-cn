---
title: DependencyObject 的安全构造函数模式
ms.date: 03/30/2017
helpviewer_keywords:
- constructor patterns for dependency objects [WPF]
- dependency objects [WPF], constructor patterns
- FXCop tool [WPF]
ms.assetid: f704b81c-449a-47a4-ace1-9332e3cc6d60
ms.openlocfilehash: 60f0cef1da362bc0d259c75509a64865f650d2f8
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104664946"
---
# <a name="safe-constructor-patterns-for-dependencyobjects"></a><span data-ttu-id="9229f-102">DependencyObject 的安全构造函数模式</span><span class="sxs-lookup"><span data-stu-id="9229f-102">Safe Constructor Patterns for DependencyObjects</span></span>
<span data-ttu-id="9229f-103">通常，类构造函数不应调用诸如虚拟方法或委托等回叫，其原因是构造函数可作为派生类的构造函数的基本初始化进行调用。</span><span class="sxs-lookup"><span data-stu-id="9229f-103">Generally, class constructors should not call callbacks such as virtual methods or delegates, because constructors can be called as base initialization of constructors for a derived class.</span></span> <span data-ttu-id="9229f-104">输入该虚拟的操作可能会在任何给定对象的不完全初始化状态下进行。</span><span class="sxs-lookup"><span data-stu-id="9229f-104">Entering the virtual might be done at an incomplete initialization state of any given object.</span></span> <span data-ttu-id="9229f-105">但是，属性系统本身在内部调用并公开回叫，作为依赖属性系统的一部分。</span><span class="sxs-lookup"><span data-stu-id="9229f-105">However, the property system itself calls and exposes callbacks internally, as part of the dependency property system.</span></span> <span data-ttu-id="9229f-106">简单的操作是使用 call 设置依赖属性值，这 <xref:System.Windows.DependencyObject.SetValue%2A> 可能会在确定的某个位置包含回调。</span><span class="sxs-lookup"><span data-stu-id="9229f-106">As simple an operation as setting a dependency property value with <xref:System.Windows.DependencyObject.SetValue%2A> call potentially includes a callback somewhere in the determination.</span></span> <span data-ttu-id="9229f-107">因此，在构造函数体内设置依赖属性值时应保持谨慎（将类型用作基类可能会导致问题）。</span><span class="sxs-lookup"><span data-stu-id="9229f-107">For this reason, you should be careful when setting dependency property values within the body of a constructor, which can become problematic if your type is used as a base class.</span></span> <span data-ttu-id="9229f-108">有一种用于实现 <xref:System.Windows.DependencyObject> 构造函数的特定模式，该模式可避免依赖属性状态和内在回调的特定问题，此处对此进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="9229f-108">There is a particular pattern for implementing <xref:System.Windows.DependencyObject> constructors that avoids specific problems with dependency property states and the inherent callbacks, which is documented here.</span></span>  

<a name="Property_System_Virtual_Methods"></a>
## <a name="property-system-virtual-methods"></a><span data-ttu-id="9229f-109">属性系统虚拟方法</span><span class="sxs-lookup"><span data-stu-id="9229f-109">Property System Virtual Methods</span></span>  
 <span data-ttu-id="9229f-110">在设置依赖属性值的调用的计算过程中，可能会调用以下虚拟方法或回调 <xref:System.Windows.DependencyObject.SetValue%2A> ： <xref:System.Windows.ValidateValueCallback> 、 <xref:System.Windows.PropertyChangedCallback> 、 <xref:System.Windows.CoerceValueCallback> 和 <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> 。</span><span class="sxs-lookup"><span data-stu-id="9229f-110">The following virtual methods or callbacks are potentially called during the computations of the <xref:System.Windows.DependencyObject.SetValue%2A> call that sets a dependency property value: <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback>, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>.</span></span> <span data-ttu-id="9229f-111">这些虚拟方法或回叫中的每一个在扩展 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 属性系统和依赖属性的多样性方面都具有特定的用途。</span><span class="sxs-lookup"><span data-stu-id="9229f-111">Each of these virtual methods or callbacks serves a particular purpose in expanding the versatility of the [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] property system and dependency properties.</span></span> <span data-ttu-id="9229f-112">有关如何使用这些虚拟方法对属性值确定进行自定义的详细信息，请参阅[依赖属性回调和验证](dependency-property-callbacks-and-validation.md)。</span><span class="sxs-lookup"><span data-stu-id="9229f-112">For more information on how to use these virtuals to customize property value determination, see [Dependency Property Callbacks and Validation](dependency-property-callbacks-and-validation.md).</span></span>  
  
### <a name="fxcop-rule-enforcement-vs-property-system-virtuals"></a><span data-ttu-id="9229f-113">FXCop 规则强制与属性系统虚方法</span><span class="sxs-lookup"><span data-stu-id="9229f-113">FXCop Rule Enforcement vs. Property System Virtuals</span></span>  
 <span data-ttu-id="9229f-114">如果将 Microsoft 工具 FXCop 用作生成过程的一部分，并从某些调用基构造函数的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 框架类派生，或在派生的类上实现自己的依赖属性，则可能会违反某个 FXCop 规则。</span><span class="sxs-lookup"><span data-stu-id="9229f-114">If you use the Microsoft tool FXCop as part of your build process, and you either derive from certain [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] framework classes calling the base constructor, or implement your own dependency properties on derived classes, you might encounter a particular FXCop rule violation.</span></span> <span data-ttu-id="9229f-115">此违反事件的名称字符串为：</span><span class="sxs-lookup"><span data-stu-id="9229f-115">The name string for this violation is:</span></span>  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 <span data-ttu-id="9229f-116">此规则是为 FXCop 设置的默认公共规则的一部分。</span><span class="sxs-lookup"><span data-stu-id="9229f-116">This is a rule that is part of the default public rule set for FXCop.</span></span> <span data-ttu-id="9229f-117">此规则所报告的内容可能为通过依赖属性系统实现的跟踪情况，该系统会最终调用依赖属性系统虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="9229f-117">What this rule might be reporting is a trace through the dependency property system that eventually calls a dependency property system virtual method.</span></span> <span data-ttu-id="9229f-118">即使遵循本主题中介绍并建议使用的构造函数模式，仍可能存在此规则冲突，因此可能需要在 FXCop 规则设置配置中禁用或取消该规则。</span><span class="sxs-lookup"><span data-stu-id="9229f-118">This rule violation might continue to appear even after following the recommended constructor patterns documented in this topic, so you might need to disable or suppress that rule in your FXCop rule set configuration.</span></span>  
  
### <a name="most-issues-come-from-deriving-classes-not-using-existing-classes"></a><span data-ttu-id="9229f-119">大多数问题是因派生类导致的，而不是因为使用现有类所致</span><span class="sxs-lookup"><span data-stu-id="9229f-119">Most Issues Come From Deriving Classes, Not Using Existing Classes</span></span>  
 <span data-ttu-id="9229f-120">当按构造顺序使用虚拟方法实现一个类后从该类进行派生时，便会发生此规则所报告的问题。</span><span class="sxs-lookup"><span data-stu-id="9229f-120">The issues reported by this rule occur when a class that you implement with virtual methods in its construction sequence is then derived from.</span></span> <span data-ttu-id="9229f-121">如果密封了类，或者确信不会派生自此类或强制不得派生自此类，则此处介绍的注意事项和触发 FXCop 规则的问题将不适用。</span><span class="sxs-lookup"><span data-stu-id="9229f-121">If you seal your class, or otherwise know or enforce that your class will not be derived from, the considerations explained here and the issues that motivated the FXCop rule do not apply to you.</span></span> <span data-ttu-id="9229f-122">但是，如果出于将类用作基类的目的来创作类，例如，如果正创建模板或可扩展的控件库集，则应遵循此处建议的用于构造函数的模式。</span><span class="sxs-lookup"><span data-stu-id="9229f-122">However, if you are authoring classes in such a way that they are intended to be used as base classes, for instance if you are creating templates, or an expandable control library set, you should follow the patterns recommended here for constructors.</span></span>  
  
### <a name="default-constructors-must-initialize-all-values-requested-by-callbacks"></a><span data-ttu-id="9229f-123">默认构造函数必须初始化由回叫请求的所有值</span><span class="sxs-lookup"><span data-stu-id="9229f-123">Default Constructors Must Initialize All Values Requested By Callbacks</span></span>  
 <span data-ttu-id="9229f-124">您的类所使用的任何实例成员都将重写或回调 (从属性系统虚方法部分的列表中的回调) 必须在您的类参数构造函数中进行初始化，即使其中一些值通过 nonparameterless 构造函数的参数使用 "真实" 值填充。</span><span class="sxs-lookup"><span data-stu-id="9229f-124">Any instance members that are used by your class overrides or callbacks (the callbacks from the list in the Property System Virtuals section) must be initialized in your class parameterless constructor, even if some of those values are filled by "real" values through parameters of the nonparameterless constructors.</span></span>  
  
 <span data-ttu-id="9229f-125">以下代码示例（和后面的示例）是一个与此规则冲突的伪 C# 示例，其中对问题进行了说明：</span><span class="sxs-lookup"><span data-stu-id="9229f-125">The following example code (and subsequent examples) is a pseudo-C# example that violates this rule and explains the problem:</span></span>  
  
```csharp  
public class MyClass : DependencyObject  
{  
    public MyClass() {}  
    public MyClass(object toSetWobble)  
        : this()  
    {  
        Wobble = toSetWobble; //this is backed by a DependencyProperty  
        _myList = new ArrayList();    // this line should be in the default ctor  
    }  
    public static readonly DependencyProperty WobbleProperty =
        DependencyProperty.Register("Wobble", typeof(object), typeof(MyClass));  
    public object Wobble  
    {  
        get { return GetValue(WobbleProperty); }  
        set { SetValue(WobbleProperty, value); }  
    }  
    protected override void OnPropertyChanged(DependencyPropertyChangedEventArgs e)  
    {  
        int count = _myList.Count;    // null-reference exception  
    }  
    private ArrayList _myList;  
}  
```  
  
 <span data-ttu-id="9229f-126">当应用程序代码调用时 `new MyClass(objectvalue)` ，这将调用无参数的构造函数和基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="9229f-126">When application code calls `new MyClass(objectvalue)`, this calls the parameterless constructor and base class constructors.</span></span> <span data-ttu-id="9229f-127">然后，它会设置，它对 `Property1 = object1` 拥有的调用虚拟方法 `OnPropertyChanged` `MyClass` <xref:System.Windows.DependencyObject> 。</span><span class="sxs-lookup"><span data-stu-id="9229f-127">Then it sets `Property1 = object1`, which calls the virtual method `OnPropertyChanged` on the owning `MyClass` <xref:System.Windows.DependencyObject>.</span></span>  <span data-ttu-id="9229f-128">重写引用尚未初始化的 `_myList`。</span><span class="sxs-lookup"><span data-stu-id="9229f-128">The override refers to `_myList`, which has not been initialized yet.</span></span>  
  
 <span data-ttu-id="9229f-129">避免这些问题的一个方法是：确保回叫仅使用其他依赖属性，并且每个这样的依赖属性都有一个确立的默认值作为其注册元数据的一部分。</span><span class="sxs-lookup"><span data-stu-id="9229f-129">One way to avoid these issues is to make sure that callbacks use only other dependency properties, and that each such dependency property has an established default value as part of its registered metadata.</span></span>  
  
<a name="Safe_Constructor_Patterns"></a>
## <a name="safe-constructor-patterns"></a><span data-ttu-id="9229f-130">安全构造函数模式</span><span class="sxs-lookup"><span data-stu-id="9229f-130">Safe Constructor Patterns</span></span>  
 <span data-ttu-id="9229f-131">若要在将类用作基类的情况下规避未完全实现初始化的风险，请遵循以下模式：</span><span class="sxs-lookup"><span data-stu-id="9229f-131">To avoid the risks of incomplete initialization if your class is used as a base class, follow these patterns:</span></span>  
  
#### <a name="parameterless-constructors-calling-base-initialization"></a><span data-ttu-id="9229f-132">调用基初始化的无参数构造函数</span><span class="sxs-lookup"><span data-stu-id="9229f-132">Parameterless constructors calling base initialization</span></span>  
 <span data-ttu-id="9229f-133">实现以下用于调用基本默认值的构造函数：</span><span class="sxs-lookup"><span data-stu-id="9229f-133">Implement these constructors calling the base default:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-not-matching-any-base-signatures"></a><span data-ttu-id="9229f-134">非默认（方便）构造函数，不与任何基本签名匹配</span><span class="sxs-lookup"><span data-stu-id="9229f-134">Non-default (convenience) constructors, not matching any base signatures</span></span>  
 <span data-ttu-id="9229f-135">如果这些构造函数使用参数设置初始化中的依赖项属性，请首先调用自己的类参数构造函数进行初始化，然后使用参数设置依赖属性。</span><span class="sxs-lookup"><span data-stu-id="9229f-135">If these constructors use the parameters to set dependency properties in the initialization, first call your own class parameterless constructor for initialization, and then use the parameters to set dependency properties.</span></span> <span data-ttu-id="9229f-136">这些可能是类所定义的依赖属性，也可能是从基类继承的依赖属性，但在这两种情况下都使用以下模式：</span><span class="sxs-lookup"><span data-stu-id="9229f-136">These could either be dependency properties defined by your class, or dependency properties inherited from base classes, but in either case use the following pattern:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-which-do-match-base-signatures"></a><span data-ttu-id="9229f-137">非默认（方便）构造函数，确实与基本签名匹配</span><span class="sxs-lookup"><span data-stu-id="9229f-137">Non-default (convenience) constructors, which do match base signatures</span></span>  
 <span data-ttu-id="9229f-138">不要用相同的参数化调用基构造函数，而应再次调用自己的类的无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="9229f-138">Instead of calling the base constructor with the same parameterization, again call your own class' parameterless constructor.</span></span> <span data-ttu-id="9229f-139">请勿调用基本初始值设定项，而应调用 `this()`。</span><span class="sxs-lookup"><span data-stu-id="9229f-139">Do not call the base initializer; instead you should call `this()`.</span></span> <span data-ttu-id="9229f-140">然后使用传递的参数作为用于设置相关属性的值来重现原始构造函数行为。</span><span class="sxs-lookup"><span data-stu-id="9229f-140">Then reproduce the original constructor behavior by using the passed parameters as values for setting the relevant properties.</span></span> <span data-ttu-id="9229f-141">将原始基本构造函数文档用作指导依据，确定要对特定参数设置的属性：</span><span class="sxs-lookup"><span data-stu-id="9229f-141">Use the original base constructor documentation for guidance in determining the properties that the particular parameters are intended to set:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="must-match-all-signatures"></a><span data-ttu-id="9229f-142">必须匹配所有签名</span><span class="sxs-lookup"><span data-stu-id="9229f-142">Must match all signatures</span></span>  
 <span data-ttu-id="9229f-143">如果基类型具有多个签名，则必须在设置更多属性之前，将所有可能的签名与你自己的构造函数实现进行了匹配，并使用调用类无参数构造函数的建议模式。</span><span class="sxs-lookup"><span data-stu-id="9229f-143">For cases where the base type has multiple signatures, you must deliberately match all possible signatures with a constructor implementation of your own that uses the recommended pattern of calling the class parameterless constructor before setting further properties.</span></span>  
  
#### <a name="setting-dependency-properties-with-setvalue"></a><span data-ttu-id="9229f-144">使用 SetValue 设置依赖属性</span><span class="sxs-lookup"><span data-stu-id="9229f-144">Setting dependency properties with SetValue</span></span>  
 <span data-ttu-id="9229f-145">如果要设置的属性没有属性设置的包装，并且使用设置值，则这些相同的模式适用 <xref:System.Windows.DependencyObject.SetValue%2A> 。</span><span class="sxs-lookup"><span data-stu-id="9229f-145">These same patterns apply if you are setting a property that does not have a wrapper for property setting convenience, and set values with <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="9229f-146">对 <xref:System.Windows.DependencyObject.SetValue%2A> 通过构造函数参数的的调用还应调用类的无参数构造函数以进行初始化。</span><span class="sxs-lookup"><span data-stu-id="9229f-146">Your calls to <xref:System.Windows.DependencyObject.SetValue%2A> that pass through constructor parameters should also call the class' parameterless constructor for initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9229f-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="9229f-147">See also</span></span>

- [<span data-ttu-id="9229f-148">自定义依赖项属性</span><span class="sxs-lookup"><span data-stu-id="9229f-148">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="9229f-149">依赖项属性概述</span><span class="sxs-lookup"><span data-stu-id="9229f-149">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="9229f-150">依赖项属性的安全性</span><span class="sxs-lookup"><span data-stu-id="9229f-150">Dependency Property Security</span></span>](dependency-property-security.md)
