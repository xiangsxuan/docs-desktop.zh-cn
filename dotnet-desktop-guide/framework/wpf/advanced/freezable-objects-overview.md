---
title: Freezable 对象概述
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], description
- unfreezing Freezable objects [WPF]
- classes [WPF], Freezable
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
ms.openlocfilehash: 8257f700f1bce8940b487a56ca58c1ea1211d58d
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665466"
---
# <a name="freezable-objects-overview"></a><span data-ttu-id="b4491-102">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="b4491-102">Freezable Objects Overview</span></span>

<span data-ttu-id="b4491-103">本主题介绍如何有效地使用和创建 <xref:System.Windows.Freezable> 对象，这些对象提供有助于提高应用程序性能的特殊功能。</span><span class="sxs-lookup"><span data-stu-id="b4491-103">This topic describes how to effectively use and create <xref:System.Windows.Freezable> objects, which provide special features that can help improve application performance.</span></span> <span data-ttu-id="b4491-104">被冻结对象的示例包括画笔、笔、转换、几何图形和动画。</span><span class="sxs-lookup"><span data-stu-id="b4491-104">Examples of freezable objects include brushes, pens, transformations, geometries, and animations.</span></span>

<a name="whatisafreezable"></a>

## <a name="what-is-a-freezable"></a><span data-ttu-id="b4491-105">什么是可冻结的？</span><span class="sxs-lookup"><span data-stu-id="b4491-105">What Is a Freezable?</span></span>

<span data-ttu-id="b4491-106"><xref:System.Windows.Freezable>是具有两种状态的特殊对象类型：解冻和冻结。</span><span class="sxs-lookup"><span data-stu-id="b4491-106">A <xref:System.Windows.Freezable> is a special type of object that has two states: unfrozen and frozen.</span></span> <span data-ttu-id="b4491-107">解冻后，的 <xref:System.Windows.Freezable> 行为与任何其他对象的行为类似。</span><span class="sxs-lookup"><span data-stu-id="b4491-107">When unfrozen, a <xref:System.Windows.Freezable> appears to behave like any other object.</span></span> <span data-ttu-id="b4491-108">冻结后，将无法 <xref:System.Windows.Freezable> 再修改。</span><span class="sxs-lookup"><span data-stu-id="b4491-108">When frozen, a <xref:System.Windows.Freezable> can no longer be modified.</span></span>

<span data-ttu-id="b4491-109"><xref:System.Windows.Freezable>提供 <xref:System.Windows.Freezable.Changed> 事件来通知观察者对对象的任何修改。</span><span class="sxs-lookup"><span data-stu-id="b4491-109">A <xref:System.Windows.Freezable> provides a <xref:System.Windows.Freezable.Changed> event to notify observers of any modifications to the object.</span></span> <span data-ttu-id="b4491-110">冻结 <xref:System.Windows.Freezable> 会提高其性能，因为它不再需要在更改通知上消耗资源。</span><span class="sxs-lookup"><span data-stu-id="b4491-110">Freezing a <xref:System.Windows.Freezable> can improve its performance, because it no longer needs to spend resources on change notifications.</span></span> <span data-ttu-id="b4491-111">冻结 <xref:System.Windows.Freezable> 还可在线程间共享，而 <xref:System.Windows.Freezable> 不能冻结。</span><span class="sxs-lookup"><span data-stu-id="b4491-111">A frozen <xref:System.Windows.Freezable> can also be shared across threads, while an unfrozen <xref:System.Windows.Freezable> cannot.</span></span>

<span data-ttu-id="b4491-112">尽管 <xref:System.Windows.Freezable> 类有许多应用程序，但 <xref:System.Windows.Freezable> 中的大多数对象 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 均与图形子系统相关。</span><span class="sxs-lookup"><span data-stu-id="b4491-112">Although the <xref:System.Windows.Freezable> class has many applications, most <xref:System.Windows.Freezable> objects in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] are related to the graphics sub-system.</span></span>

<span data-ttu-id="b4491-113"><xref:System.Windows.Freezable>使用类可以更轻松地使用某些图形系统对象，并且可以帮助提高应用程序性能。</span><span class="sxs-lookup"><span data-stu-id="b4491-113">The <xref:System.Windows.Freezable> class makes it easier to use certain graphics system objects and can help improve application performance.</span></span> <span data-ttu-id="b4491-114">继承自的类型的示例 <xref:System.Windows.Freezable> 包括 <xref:System.Windows.Media.Brush> 、 <xref:System.Windows.Media.Transform> 和 <xref:System.Windows.Media.Geometry> 类。</span><span class="sxs-lookup"><span data-stu-id="b4491-114">Examples of types that inherit from <xref:System.Windows.Freezable> include the <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, and <xref:System.Windows.Media.Geometry> classes.</span></span> <span data-ttu-id="b4491-115">由于它们包含非托管资源，因此，系统必须监视这些对象进行修改，然后在对原始对象进行更改时更新其相应的非托管资源。</span><span class="sxs-lookup"><span data-stu-id="b4491-115">Because they contain unmanaged resources, the system must monitor these objects for modifications, and then update their corresponding unmanaged resources when there is a change to the original object.</span></span> <span data-ttu-id="b4491-116">即使您不实际修改图形系统对象，系统仍必须将它的一些资源用于监视对象，以防您这样做更改。</span><span class="sxs-lookup"><span data-stu-id="b4491-116">Even if you don't actually modify a graphics system object, the system must still spend some of its resources monitoring the object, in case you do change it.</span></span>

<span data-ttu-id="b4491-117">例如，假设您创建了一个 <xref:System.Windows.Media.SolidColorBrush> 画笔，并使用它来绘制按钮的背景。</span><span class="sxs-lookup"><span data-stu-id="b4491-117">For example, suppose you create a <xref:System.Windows.Media.SolidColorBrush> brush and use it to paint the background of a button.</span></span>

[!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
[!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]

<span data-ttu-id="b4491-118">呈现按钮时， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 图形子系统将使用您提供的信息来绘制一组像素来创建按钮的外观。</span><span class="sxs-lookup"><span data-stu-id="b4491-118">When the button is rendered, the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] graphics sub-system uses the information you provided to paint a group of pixels to create the appearance of a button.</span></span> <span data-ttu-id="b4491-119">虽然您使用纯色画笔来说明如何绘制按钮，但您的纯色画笔实际上不会执行绘制操作。</span><span class="sxs-lookup"><span data-stu-id="b4491-119">Although you used a solid color brush to describe how the button should be painted, your solid color brush doesn't actually do the painting.</span></span> <span data-ttu-id="b4491-120">图形系统会为按钮和画笔生成快速、低级别的对象，并且这些对象确实出现在屏幕上。</span><span class="sxs-lookup"><span data-stu-id="b4491-120">The graphics system generates fast, low-level objects for the button and the brush, and it is those objects that actually appear on the screen.</span></span>

<span data-ttu-id="b4491-121">如果要修改画笔，则必须重新生成这些低级别对象。</span><span class="sxs-lookup"><span data-stu-id="b4491-121">If you were to modify the brush, those low-level objects would have to be regenerated.</span></span> <span data-ttu-id="b4491-122">可冻结的类可让画笔查找其相应的已生成低级别对象并在更改时更新这些对象。</span><span class="sxs-lookup"><span data-stu-id="b4491-122">The freezable class is what gives a brush the ability to find its corresponding generated, low-level objects and to update them when it changes.</span></span> <span data-ttu-id="b4491-123">启用此功能后，画笔会被视为 "解冻"。</span><span class="sxs-lookup"><span data-stu-id="b4491-123">When this ability is enabled, the brush is said to be "unfrozen."</span></span>

<span data-ttu-id="b4491-124">可冻结的 <xref:System.Windows.Freezable.Freeze%2A> 方法使您能够禁用此自我更新功能。</span><span class="sxs-lookup"><span data-stu-id="b4491-124">A freezable's <xref:System.Windows.Freezable.Freeze%2A> method enables you to disable this self-updating ability.</span></span> <span data-ttu-id="b4491-125">您可以使用此方法使画笔变为 "冻结" 或不可修改。</span><span class="sxs-lookup"><span data-stu-id="b4491-125">You can use this method to make the brush become "frozen," or unmodifiable.</span></span>

> [!NOTE]
> <span data-ttu-id="b4491-126">并非每个可冻结的对象都可以冻结。</span><span class="sxs-lookup"><span data-stu-id="b4491-126">Not every Freezable object can be frozen.</span></span> <span data-ttu-id="b4491-127">若要避免引发 <xref:System.InvalidOperationException> ，请检查可冻结对象的属性的值， <xref:System.Windows.Freezable.CanFreeze%2A> 以确定它是否可以冻结，然后再尝试将其冻结。</span><span class="sxs-lookup"><span data-stu-id="b4491-127">To avoid throwing an <xref:System.InvalidOperationException>, check the value of the Freezable object's <xref:System.Windows.Freezable.CanFreeze%2A> property to determine whether it can be frozen before attempting to freeze it.</span></span>

[!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
[!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]

<span data-ttu-id="b4491-128">当你不再需要修改可冻结的时，冻结它可提供性能优势。</span><span class="sxs-lookup"><span data-stu-id="b4491-128">When you no longer need to modify a freezable, freezing it provides performance benefits.</span></span> <span data-ttu-id="b4491-129">如果在此示例中冻结了画笔，则图形系统将不再需要监视其更改。</span><span class="sxs-lookup"><span data-stu-id="b4491-129">If you were to freeze the brush in this example, the graphics system would no longer need to monitor it for changes.</span></span> <span data-ttu-id="b4491-130">图形系统还可以进行其他优化，因为它知道画笔不会改变。</span><span class="sxs-lookup"><span data-stu-id="b4491-130">The graphics system can also make other optimizations, because it knows the brush won't change.</span></span>

> [!NOTE]
> <span data-ttu-id="b4491-131">为方便起见，可冻结对象保持解冻，除非你显式冻结它们。</span><span class="sxs-lookup"><span data-stu-id="b4491-131">For convenience, freezable objects remain unfrozen unless you explicitly freeze them.</span></span>

<a name="frozenfreezables"></a>

## <a name="using-freezables"></a><span data-ttu-id="b4491-132">使用可冻结对象</span><span class="sxs-lookup"><span data-stu-id="b4491-132">Using Freezables</span></span>

<span data-ttu-id="b4491-133">使用未冻结的可冻结对象与使用任何其他类型的对象类似。</span><span class="sxs-lookup"><span data-stu-id="b4491-133">Using an unfrozen freezable is like using any other type of object.</span></span> <span data-ttu-id="b4491-134">在下面的示例中，在 <xref:System.Windows.Media.SolidColorBrush> 用于绘制按钮背景后，的颜色将从黄色更改为红色。</span><span class="sxs-lookup"><span data-stu-id="b4491-134">In the following example, the color of a <xref:System.Windows.Media.SolidColorBrush> is changed from yellow to red after it's used to paint the background of a button.</span></span> <span data-ttu-id="b4491-135">图形系统在幕后工作，在下次刷新屏幕时，自动将按钮从黄色更改为红色。</span><span class="sxs-lookup"><span data-stu-id="b4491-135">The graphics system works behind the scenes to automatically change the button from yellow to red the next time the screen is refreshed.</span></span>

[!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
[!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]

### <a name="freezing-a-freezable"></a><span data-ttu-id="b4491-136">冻结冻结</span><span class="sxs-lookup"><span data-stu-id="b4491-136">Freezing a Freezable</span></span>

<span data-ttu-id="b4491-137">若要使 <xref:System.Windows.Freezable> 其成为不可修改的，请调用其 <xref:System.Windows.Freezable.Freeze%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="b4491-137">To make a <xref:System.Windows.Freezable> unmodifiable, you call its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span> <span data-ttu-id="b4491-138">冻结包含可冻结对象的对象时，这些对象也会被冻结。</span><span class="sxs-lookup"><span data-stu-id="b4491-138">When you freeze an object that contains freezable objects, those objects are frozen as well.</span></span> <span data-ttu-id="b4491-139">例如，如果冻结 <xref:System.Windows.Media.PathGeometry> ，则它包含的图形和段也将被冻结。</span><span class="sxs-lookup"><span data-stu-id="b4491-139">For example, if you freeze a <xref:System.Windows.Media.PathGeometry>, the figures and segments it contains would be frozen too.</span></span>

<span data-ttu-id="b4491-140">如果满足以下任一条件，则 **无法** 冻结可冻结的：</span><span class="sxs-lookup"><span data-stu-id="b4491-140">A Freezable **can't** be frozen if any of the following are true:</span></span>

- <span data-ttu-id="b4491-141">它具有动画或数据绑定属性。</span><span class="sxs-lookup"><span data-stu-id="b4491-141">It has animated or data bound properties.</span></span>

- <span data-ttu-id="b4491-142">它包含动态资源设置的属性。</span><span class="sxs-lookup"><span data-stu-id="b4491-142">It has properties set by a dynamic resource.</span></span> <span data-ttu-id="b4491-143"> (有关动态资源的详细信息，请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define) 。 ) </span><span class="sxs-lookup"><span data-stu-id="b4491-143">(See the [XAML Resources](/dotnet/desktop-wpf/fundamentals/xaml-resources-define) for more information about dynamic resources.)</span></span>

- <span data-ttu-id="b4491-144">它包含 <xref:System.Windows.Freezable> 无法冻结的子对象。</span><span class="sxs-lookup"><span data-stu-id="b4491-144">It contains <xref:System.Windows.Freezable> sub-objects that can't be frozen.</span></span>

<span data-ttu-id="b4491-145">如果这些条件为 false，并且你不打算修改，则 <xref:System.Windows.Freezable> 应该冻结它以获得前面所述的性能优势。</span><span class="sxs-lookup"><span data-stu-id="b4491-145">If these conditions are false, and you don't intend to modify the <xref:System.Windows.Freezable>, then you should freeze it to gain the performance benefits described earlier.</span></span>

<span data-ttu-id="b4491-146">调用可冻结的方法后 <xref:System.Windows.Freezable.Freeze%2A> ，将无法再对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="b4491-146">Once you call a freezable's <xref:System.Windows.Freezable.Freeze%2A> method, it can no longer be modified.</span></span> <span data-ttu-id="b4491-147">尝试修改冻结对象将导致 <xref:System.InvalidOperationException> 引发。</span><span class="sxs-lookup"><span data-stu-id="b4491-147">Attempting to modify a frozen object causes an <xref:System.InvalidOperationException> to be thrown.</span></span> <span data-ttu-id="b4491-148">下面的代码引发异常，因为我们尝试在冻结画笔之后修改画笔。</span><span class="sxs-lookup"><span data-stu-id="b4491-148">The following code throws an exception, because we attempt to modify the brush after it's been frozen.</span></span>

[!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
[!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]

<span data-ttu-id="b4491-149">若要避免引发此异常，可以使用 <xref:System.Windows.Freezable.IsFrozen%2A> 方法来确定是否 <xref:System.Windows.Freezable> 已冻结。</span><span class="sxs-lookup"><span data-stu-id="b4491-149">To avoid throwing this exception, you can use the <xref:System.Windows.Freezable.IsFrozen%2A> method to determine whether a <xref:System.Windows.Freezable> is frozen.</span></span>

[!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
[!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]

<span data-ttu-id="b4491-150">在上面的代码示例中，使用方法对冻结的对象创建了一个可修改的副本 <xref:System.Windows.Freezable.Clone%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b4491-150">In the preceding code example, a modifiable copy was made of a frozen object using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="b4491-151">下一部分更详细地讨论了克隆。</span><span class="sxs-lookup"><span data-stu-id="b4491-151">The next section discusses cloning in more detail.</span></span>

> [!NOTE]
> <span data-ttu-id="b4491-152">由于不能对冻结的可冻结对象进行动画处理，因此 <xref:System.Windows.Freezable> 当你尝试使用对它们进行动画处理时，动画系统将自动创建冻结对象的可修改复本 <xref:System.Windows.Media.Animation.Storyboard> 。</span><span class="sxs-lookup"><span data-stu-id="b4491-152">Because a frozen freezable cannot be animated, the animation system will automatically create modifiable clones of frozen <xref:System.Windows.Freezable> objects when you try to animate them with a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="b4491-153">若要消除克隆导致的性能开销，请在要对对象进行动画处理时使对象保持解冻。</span><span class="sxs-lookup"><span data-stu-id="b4491-153">To eliminate the performance overhead caused by cloning, leave an object unfrozen if you intend to animate it.</span></span> <span data-ttu-id="b4491-154">有关利用情节提要进行动画处理的详细信息，请参阅 [情节提要概述](../graphics-multimedia/storyboards-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b4491-154">For more information about animating with storyboards, see the [Storyboards Overview](../graphics-multimedia/storyboards-overview.md).</span></span>

### <a name="freezing-from-markup"></a><span data-ttu-id="b4491-155">从标记冻结</span><span class="sxs-lookup"><span data-stu-id="b4491-155">Freezing from Markup</span></span>

<span data-ttu-id="b4491-156">若要冻结 <xref:System.Windows.Freezable> 在标记中声明的对象，请使用 `PresentationOptions:Freeze` 特性。</span><span class="sxs-lookup"><span data-stu-id="b4491-156">To freeze a <xref:System.Windows.Freezable> object declared in markup, you use the `PresentationOptions:Freeze` attribute.</span></span> <span data-ttu-id="b4491-157">在下面的示例中，将 <xref:System.Windows.Media.SolidColorBrush> 声明为页资源并冻结。</span><span class="sxs-lookup"><span data-stu-id="b4491-157">In the following example, a <xref:System.Windows.Media.SolidColorBrush> is declared as a page resource and frozen.</span></span> <span data-ttu-id="b4491-158">然后，将使用它来设置按钮的背景。</span><span class="sxs-lookup"><span data-stu-id="b4491-158">It is then used to set the background of a button.</span></span>

[!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]

<span data-ttu-id="b4491-159">若要使用 `Freeze` 属性，必须映射到表示选项命名空间： `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` 。</span><span class="sxs-lookup"><span data-stu-id="b4491-159">To use the `Freeze` attribute, you must map to the presentation options namespace: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`.</span></span> <span data-ttu-id="b4491-160">`PresentationOptions` 建议用于映射此命名空间的前缀：</span><span class="sxs-lookup"><span data-stu-id="b4491-160">`PresentationOptions` is the recommended prefix for mapping this namespace:</span></span>

```xaml
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"
```

<span data-ttu-id="b4491-161">由于并非所有 XAML 读取器都能识别此特性，因此建议使用 [mc：可忽略属性](mc-ignorable-attribute.md) 将属性标记 `Presentation:Freeze` 为可忽略：</span><span class="sxs-lookup"><span data-stu-id="b4491-161">Because not all XAML readers recognize this attribute, it's recommended that you use the [mc:Ignorable Attribute](mc-ignorable-attribute.md) to mark the `Presentation:Freeze` attribute as ignorable:</span></span>

```xaml
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
mc:Ignorable="PresentationOptions"
```

<span data-ttu-id="b4491-162">有关详细信息，请参阅 [mc：忽略属性](mc-ignorable-attribute.md) 页。</span><span class="sxs-lookup"><span data-stu-id="b4491-162">For more information, see the [mc:Ignorable Attribute](mc-ignorable-attribute.md) page.</span></span>

### <a name="unfreezing-a-freezable"></a><span data-ttu-id="b4491-163">"解冻"</span><span class="sxs-lookup"><span data-stu-id="b4491-163">"Unfreezing" a Freezable</span></span>

<span data-ttu-id="b4491-164">一旦冻结，就 <xref:System.Windows.Freezable> 永远不能对其进行修改或取消冻结; 不过，可以使用或方法创建未冻结的克隆 <xref:System.Windows.Freezable.Clone%2A> <xref:System.Windows.Freezable.CloneCurrentValue%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b4491-164">Once frozen, a <xref:System.Windows.Freezable> can never be modified or unfrozen; however, you can create an unfrozen clone using the <xref:System.Windows.Freezable.Clone%2A> or <xref:System.Windows.Freezable.CloneCurrentValue%2A> method.</span></span>

<span data-ttu-id="b4491-165">在下面的示例中，按钮的背景是使用画笔设置的，然后该画笔会被冻结。</span><span class="sxs-lookup"><span data-stu-id="b4491-165">In the following example, the button's background is set with a brush and that brush is then frozen.</span></span> <span data-ttu-id="b4491-166">使用方法对画笔生成了未冻结的副本 <xref:System.Windows.Freezable.Clone%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b4491-166">An unfrozen copy is made of the brush using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="b4491-167">将修改克隆，并使用它将按钮的背景从黄色更改为红色。</span><span class="sxs-lookup"><span data-stu-id="b4491-167">The clone is modified and used to change the button's background from yellow to red.</span></span>

[!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
[!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]

> [!NOTE]
> <span data-ttu-id="b4491-168">不管使用哪种克隆方法，动画永远都不会复制到新的 <xref:System.Windows.Freezable> 。</span><span class="sxs-lookup"><span data-stu-id="b4491-168">Regardless of which clone method you use, animations are never copied to the new <xref:System.Windows.Freezable>.</span></span>

<span data-ttu-id="b4491-169"><xref:System.Windows.Freezable.Clone%2A>和 <xref:System.Windows.Freezable.CloneCurrentValue%2A> 方法会生成一个已冻结的深层副本。</span><span class="sxs-lookup"><span data-stu-id="b4491-169">The <xref:System.Windows.Freezable.Clone%2A> and <xref:System.Windows.Freezable.CloneCurrentValue%2A> methods produce deep copies of the freezable.</span></span> <span data-ttu-id="b4491-170">如果可冻结的包含其他冻结的可冻结对象，则它们也会被克隆，并可进行修改。</span><span class="sxs-lookup"><span data-stu-id="b4491-170">If the freezable contains other frozen freezable objects, they are also cloned and made modifiable.</span></span> <span data-ttu-id="b4491-171">例如，如果克隆冻结的 <xref:System.Windows.Media.PathGeometry> 以使其可修改，则还会复制其包含的图形和线段，并使其成为可修改的。</span><span class="sxs-lookup"><span data-stu-id="b4491-171">For example, if you clone a frozen <xref:System.Windows.Media.PathGeometry> to make it modifiable, the figures and segments it contains are also copied and made modifiable.</span></span>

<a name="createyourownfreezableclass"></a>

## <a name="creating-your-own-freezable-class"></a><span data-ttu-id="b4491-172">创建自己的有冻结类</span><span class="sxs-lookup"><span data-stu-id="b4491-172">Creating Your Own Freezable Class</span></span>

<span data-ttu-id="b4491-173">派生自的类具有 <xref:System.Windows.Freezable> 以下功能。</span><span class="sxs-lookup"><span data-stu-id="b4491-173">A class that derives from <xref:System.Windows.Freezable> gains the following features.</span></span>

- <span data-ttu-id="b4491-174">特殊状态：只读 (冻结) 和可写状态。</span><span class="sxs-lookup"><span data-stu-id="b4491-174">Special states: a read-only (frozen) and a writable state.</span></span>

- <span data-ttu-id="b4491-175">线程安全：冻结 <xref:System.Windows.Freezable> 可以在线程之间共享。</span><span class="sxs-lookup"><span data-stu-id="b4491-175">Thread safety: a frozen <xref:System.Windows.Freezable> can be shared across threads.</span></span>

- <span data-ttu-id="b4491-176">详细更改通知：与其他不同 <xref:System.Windows.DependencyObject> ，可冻结对象会在子属性值更改时提供更改通知。</span><span class="sxs-lookup"><span data-stu-id="b4491-176">Detailed change notification: Unlike other <xref:System.Windows.DependencyObject>s, Freezable objects provide change notifications when sub-property values change.</span></span>

- <span data-ttu-id="b4491-177">轻松克隆：可冻结的类已经实现了几种生成深层克隆的方法。</span><span class="sxs-lookup"><span data-stu-id="b4491-177">Easy cloning: the Freezable class has already implemented several methods that produce deep clones.</span></span>

<span data-ttu-id="b4491-178"><xref:System.Windows.Freezable>是的一种类型 <xref:System.Windows.DependencyObject> ，因此使用了依赖属性系统。</span><span class="sxs-lookup"><span data-stu-id="b4491-178">A <xref:System.Windows.Freezable> is a type of <xref:System.Windows.DependencyObject>, and therefore uses the dependency property system.</span></span> <span data-ttu-id="b4491-179">类属性不一定是依赖属性，但使用依赖属性将减少您必须编写的代码量，因为 <xref:System.Windows.Freezable> 该类是使用依赖属性设计的。</span><span class="sxs-lookup"><span data-stu-id="b4491-179">Your class properties don't have to be dependency properties, but using dependency properties will reduce the amount of code you have to write, because the <xref:System.Windows.Freezable> class was designed with dependency properties in mind.</span></span> <span data-ttu-id="b4491-180">有关依赖属性系统的详细信息，请参阅 [依赖属性概述](dependency-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b4491-180">For more information about the dependency property system, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span>

<span data-ttu-id="b4491-181">每个 <xref:System.Windows.Freezable> 子类必须重写 <xref:System.Windows.Freezable.CreateInstanceCore%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="b4491-181">Every <xref:System.Windows.Freezable> subclass must override the <xref:System.Windows.Freezable.CreateInstanceCore%2A> method.</span></span> <span data-ttu-id="b4491-182">如果你的类对所有数据使用依赖属性，则你已完成。</span><span class="sxs-lookup"><span data-stu-id="b4491-182">If your class uses dependency properties for all its data, you're finished.</span></span>

<span data-ttu-id="b4491-183">如果类包含非依赖属性数据成员，还必须重写以下方法：</span><span class="sxs-lookup"><span data-stu-id="b4491-183">If your class contains non-dependency property data members, you must also override the following methods:</span></span>

- <xref:System.Windows.Freezable.CloneCore%2A>

- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>

- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>

- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>

- <xref:System.Windows.Freezable.FreezeCore%2A>

<span data-ttu-id="b4491-184">还必须遵守以下规则，以便访问和写入不是依赖属性的数据成员：</span><span class="sxs-lookup"><span data-stu-id="b4491-184">You must also observe the following rules for accessing and writing to data members that are not dependency properties:</span></span>

- <span data-ttu-id="b4491-185">在读取非依赖属性数据成员的任何 API 的开头，调用 <xref:System.Windows.Freezable.ReadPreamble%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="b4491-185">At the beginning of any API that reads non-dependency property data members, call the <xref:System.Windows.Freezable.ReadPreamble%2A> method.</span></span>

- <span data-ttu-id="b4491-186">在写入非依赖属性数据成员的任何 API 的开头，请调用 <xref:System.Windows.Freezable.WritePreamble%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="b4491-186">At the beginning of any API that writes non-dependency property data members, call the <xref:System.Windows.Freezable.WritePreamble%2A> method.</span></span> <span data-ttu-id="b4491-187"> (<xref:System.Windows.Freezable.WritePreamble%2A> 在 API 中调用后， <xref:System.Windows.Freezable.ReadPreamble%2A> 如果还读取非依赖属性数据成员，则无需额外调用。 ) </span><span class="sxs-lookup"><span data-stu-id="b4491-187">(Once you've called <xref:System.Windows.Freezable.WritePreamble%2A> in an API, you don't need to make an additional call to <xref:System.Windows.Freezable.ReadPreamble%2A> if you also read non-dependency property data members.)</span></span>

- <span data-ttu-id="b4491-188"><xref:System.Windows.Freezable.WritePostscript%2A>在退出写入非依赖属性数据成员的方法之前调用方法。</span><span class="sxs-lookup"><span data-stu-id="b4491-188">Call the <xref:System.Windows.Freezable.WritePostscript%2A> method before exiting methods that write to non-dependency property data members.</span></span>

<span data-ttu-id="b4491-189">如果类包含非依赖属性数据成员 <xref:System.Windows.DependencyObject> （这些对象是对象），则在 <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> 每次更改其值时，您还必须调用方法，即使您要将成员设置为 `null` 。</span><span class="sxs-lookup"><span data-stu-id="b4491-189">If your class contains non-dependency-property data members that are <xref:System.Windows.DependencyObject> objects, you must also call the <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> method each time you change one of their values, even if you're setting the member to `null`.</span></span>

> [!NOTE]
> <span data-ttu-id="b4491-190"><xref:System.Windows.Freezable>使用对基实现的调用来开始重写的每个方法非常重要。</span><span class="sxs-lookup"><span data-stu-id="b4491-190">It's very important that you begin each <xref:System.Windows.Freezable> method you override with a call to the base implementation.</span></span>

<span data-ttu-id="b4491-191">有关自定义类的示例 <xref:System.Windows.Freezable> ，请参阅 [自定义动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)。</span><span class="sxs-lookup"><span data-stu-id="b4491-191">For an example of a custom <xref:System.Windows.Freezable> class, see the [Custom Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation).</span></span>

## <a name="see-also"></a><span data-ttu-id="b4491-192">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4491-192">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="b4491-193">自定义动画示例</span><span class="sxs-lookup"><span data-stu-id="b4491-193">Custom Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)
- [<span data-ttu-id="b4491-194">依赖项属性概述</span><span class="sxs-lookup"><span data-stu-id="b4491-194">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="b4491-195">自定义依赖项属性</span><span class="sxs-lookup"><span data-stu-id="b4491-195">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
