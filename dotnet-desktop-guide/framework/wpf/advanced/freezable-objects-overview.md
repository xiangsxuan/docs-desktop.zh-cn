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
# <a name="freezable-objects-overview"></a>Freezable 对象概述

本主题介绍如何有效地使用和创建 <xref:System.Windows.Freezable> 对象，这些对象提供有助于提高应用程序性能的特殊功能。 被冻结对象的示例包括画笔、笔、转换、几何图形和动画。

<a name="whatisafreezable"></a>

## <a name="what-is-a-freezable"></a>什么是可冻结的？

<xref:System.Windows.Freezable>是具有两种状态的特殊对象类型：解冻和冻结。 解冻后，的 <xref:System.Windows.Freezable> 行为与任何其他对象的行为类似。 冻结后，将无法 <xref:System.Windows.Freezable> 再修改。

<xref:System.Windows.Freezable>提供 <xref:System.Windows.Freezable.Changed> 事件来通知观察者对对象的任何修改。 冻结 <xref:System.Windows.Freezable> 会提高其性能，因为它不再需要在更改通知上消耗资源。 冻结 <xref:System.Windows.Freezable> 还可在线程间共享，而 <xref:System.Windows.Freezable> 不能冻结。

尽管 <xref:System.Windows.Freezable> 类有许多应用程序，但 <xref:System.Windows.Freezable> 中的大多数对象 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 均与图形子系统相关。

<xref:System.Windows.Freezable>使用类可以更轻松地使用某些图形系统对象，并且可以帮助提高应用程序性能。 继承自的类型的示例 <xref:System.Windows.Freezable> 包括 <xref:System.Windows.Media.Brush> 、 <xref:System.Windows.Media.Transform> 和 <xref:System.Windows.Media.Geometry> 类。 由于它们包含非托管资源，因此，系统必须监视这些对象进行修改，然后在对原始对象进行更改时更新其相应的非托管资源。 即使您不实际修改图形系统对象，系统仍必须将它的一些资源用于监视对象，以防您这样做更改。

例如，假设您创建了一个 <xref:System.Windows.Media.SolidColorBrush> 画笔，并使用它来绘制按钮的背景。

[!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
[!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]

呈现按钮时， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 图形子系统将使用您提供的信息来绘制一组像素来创建按钮的外观。 虽然您使用纯色画笔来说明如何绘制按钮，但您的纯色画笔实际上不会执行绘制操作。 图形系统会为按钮和画笔生成快速、低级别的对象，并且这些对象确实出现在屏幕上。

如果要修改画笔，则必须重新生成这些低级别对象。 可冻结的类可让画笔查找其相应的已生成低级别对象并在更改时更新这些对象。 启用此功能后，画笔会被视为 "解冻"。

可冻结的 <xref:System.Windows.Freezable.Freeze%2A> 方法使您能够禁用此自我更新功能。 您可以使用此方法使画笔变为 "冻结" 或不可修改。

> [!NOTE]
> 并非每个可冻结的对象都可以冻结。 若要避免引发 <xref:System.InvalidOperationException> ，请检查可冻结对象的属性的值， <xref:System.Windows.Freezable.CanFreeze%2A> 以确定它是否可以冻结，然后再尝试将其冻结。

[!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
[!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]

当你不再需要修改可冻结的时，冻结它可提供性能优势。 如果在此示例中冻结了画笔，则图形系统将不再需要监视其更改。 图形系统还可以进行其他优化，因为它知道画笔不会改变。

> [!NOTE]
> 为方便起见，可冻结对象保持解冻，除非你显式冻结它们。

<a name="frozenfreezables"></a>

## <a name="using-freezables"></a>使用可冻结对象

使用未冻结的可冻结对象与使用任何其他类型的对象类似。 在下面的示例中，在 <xref:System.Windows.Media.SolidColorBrush> 用于绘制按钮背景后，的颜色将从黄色更改为红色。 图形系统在幕后工作，在下次刷新屏幕时，自动将按钮从黄色更改为红色。

[!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
[!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]

### <a name="freezing-a-freezable"></a>冻结冻结

若要使 <xref:System.Windows.Freezable> 其成为不可修改的，请调用其 <xref:System.Windows.Freezable.Freeze%2A> 方法。 冻结包含可冻结对象的对象时，这些对象也会被冻结。 例如，如果冻结 <xref:System.Windows.Media.PathGeometry> ，则它包含的图形和段也将被冻结。

如果满足以下任一条件，则 **无法** 冻结可冻结的：

- 它具有动画或数据绑定属性。

- 它包含动态资源设置的属性。  (有关动态资源的详细信息，请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define) 。 ) 

- 它包含 <xref:System.Windows.Freezable> 无法冻结的子对象。

如果这些条件为 false，并且你不打算修改，则 <xref:System.Windows.Freezable> 应该冻结它以获得前面所述的性能优势。

调用可冻结的方法后 <xref:System.Windows.Freezable.Freeze%2A> ，将无法再对其进行修改。 尝试修改冻结对象将导致 <xref:System.InvalidOperationException> 引发。 下面的代码引发异常，因为我们尝试在冻结画笔之后修改画笔。

[!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
[!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]

若要避免引发此异常，可以使用 <xref:System.Windows.Freezable.IsFrozen%2A> 方法来确定是否 <xref:System.Windows.Freezable> 已冻结。

[!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
[!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]

在上面的代码示例中，使用方法对冻结的对象创建了一个可修改的副本 <xref:System.Windows.Freezable.Clone%2A> 。 下一部分更详细地讨论了克隆。

> [!NOTE]
> 由于不能对冻结的可冻结对象进行动画处理，因此 <xref:System.Windows.Freezable> 当你尝试使用对它们进行动画处理时，动画系统将自动创建冻结对象的可修改复本 <xref:System.Windows.Media.Animation.Storyboard> 。 若要消除克隆导致的性能开销，请在要对对象进行动画处理时使对象保持解冻。 有关利用情节提要进行动画处理的详细信息，请参阅 [情节提要概述](../graphics-multimedia/storyboards-overview.md)。

### <a name="freezing-from-markup"></a>从标记冻结

若要冻结 <xref:System.Windows.Freezable> 在标记中声明的对象，请使用 `PresentationOptions:Freeze` 特性。 在下面的示例中，将 <xref:System.Windows.Media.SolidColorBrush> 声明为页资源并冻结。 然后，将使用它来设置按钮的背景。

[!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]

若要使用 `Freeze` 属性，必须映射到表示选项命名空间： `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` 。 `PresentationOptions` 建议用于映射此命名空间的前缀：

```xaml
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"
```

由于并非所有 XAML 读取器都能识别此特性，因此建议使用 [mc：可忽略属性](mc-ignorable-attribute.md) 将属性标记 `Presentation:Freeze` 为可忽略：

```xaml
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
mc:Ignorable="PresentationOptions"
```

有关详细信息，请参阅 [mc：忽略属性](mc-ignorable-attribute.md) 页。

### <a name="unfreezing-a-freezable"></a>"解冻"

一旦冻结，就 <xref:System.Windows.Freezable> 永远不能对其进行修改或取消冻结; 不过，可以使用或方法创建未冻结的克隆 <xref:System.Windows.Freezable.Clone%2A> <xref:System.Windows.Freezable.CloneCurrentValue%2A> 。

在下面的示例中，按钮的背景是使用画笔设置的，然后该画笔会被冻结。 使用方法对画笔生成了未冻结的副本 <xref:System.Windows.Freezable.Clone%2A> 。 将修改克隆，并使用它将按钮的背景从黄色更改为红色。

[!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
[!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]

> [!NOTE]
> 不管使用哪种克隆方法，动画永远都不会复制到新的 <xref:System.Windows.Freezable> 。

<xref:System.Windows.Freezable.Clone%2A>和 <xref:System.Windows.Freezable.CloneCurrentValue%2A> 方法会生成一个已冻结的深层副本。 如果可冻结的包含其他冻结的可冻结对象，则它们也会被克隆，并可进行修改。 例如，如果克隆冻结的 <xref:System.Windows.Media.PathGeometry> 以使其可修改，则还会复制其包含的图形和线段，并使其成为可修改的。

<a name="createyourownfreezableclass"></a>

## <a name="creating-your-own-freezable-class"></a>创建自己的有冻结类

派生自的类具有 <xref:System.Windows.Freezable> 以下功能。

- 特殊状态：只读 (冻结) 和可写状态。

- 线程安全：冻结 <xref:System.Windows.Freezable> 可以在线程之间共享。

- 详细更改通知：与其他不同 <xref:System.Windows.DependencyObject> ，可冻结对象会在子属性值更改时提供更改通知。

- 轻松克隆：可冻结的类已经实现了几种生成深层克隆的方法。

<xref:System.Windows.Freezable>是的一种类型 <xref:System.Windows.DependencyObject> ，因此使用了依赖属性系统。 类属性不一定是依赖属性，但使用依赖属性将减少您必须编写的代码量，因为 <xref:System.Windows.Freezable> 该类是使用依赖属性设计的。 有关依赖属性系统的详细信息，请参阅 [依赖属性概述](dependency-properties-overview.md)。

每个 <xref:System.Windows.Freezable> 子类必须重写 <xref:System.Windows.Freezable.CreateInstanceCore%2A> 方法。 如果你的类对所有数据使用依赖属性，则你已完成。

如果类包含非依赖属性数据成员，还必须重写以下方法：

- <xref:System.Windows.Freezable.CloneCore%2A>

- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>

- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>

- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>

- <xref:System.Windows.Freezable.FreezeCore%2A>

还必须遵守以下规则，以便访问和写入不是依赖属性的数据成员：

- 在读取非依赖属性数据成员的任何 API 的开头，调用 <xref:System.Windows.Freezable.ReadPreamble%2A> 方法。

- 在写入非依赖属性数据成员的任何 API 的开头，请调用 <xref:System.Windows.Freezable.WritePreamble%2A> 方法。  (<xref:System.Windows.Freezable.WritePreamble%2A> 在 API 中调用后， <xref:System.Windows.Freezable.ReadPreamble%2A> 如果还读取非依赖属性数据成员，则无需额外调用。 ) 

- <xref:System.Windows.Freezable.WritePostscript%2A>在退出写入非依赖属性数据成员的方法之前调用方法。

如果类包含非依赖属性数据成员 <xref:System.Windows.DependencyObject> （这些对象是对象），则在 <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> 每次更改其值时，您还必须调用方法，即使您要将成员设置为 `null` 。

> [!NOTE]
> <xref:System.Windows.Freezable>使用对基实现的调用来开始重写的每个方法非常重要。

有关自定义类的示例 <xref:System.Windows.Freezable> ，请参阅 [自定义动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Freezable>
- [自定义动画示例](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)
- [依赖项属性概述](dependency-properties-overview.md)
- [自定义依赖项属性](custom-dependency-properties.md)
