---
title: 结构化导航概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- structured navigation [WPF]
ms.assetid: 025d30ef-fec5-436d-ad7a-5d5483331c26
ms.openlocfilehash: 2c9635ed4e371e132639eab72d53915748603ea2
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104668185"
---
# <a name="structured-navigation-overview"></a>结构化导航概述

XAML 浏览器应用程序可以由 XAML 浏览器应用程序 (XBAP) 、或之一承载的内容由 <xref:System.Windows.Controls.Frame> <xref:System.Windows.Navigation.NavigationWindow> 可通过 pack 统一资源标识符 (uri) 并通过超链接导航到的页组成。 页面的结构以及导航页面的方式（通过超链接来定义）称为导航拓扑。 此类拓扑适合各种应用程序类型，尤其适合在文档之间导航的应用程序类型。 对于此类应用程序，用户可以从一个页面导航到另一个页面，并且其中任一页面都无需了解另一页面的任何信息。

但是，对于其他类型的应用程序，在其页面之间导航时，确实需要了解这些页面信息。 例如，假设一个人力资源应用程序，它具有一个列出组织中所有员工的页面，即“员工列表”页。 此页还允许用户通过单击超链接添加新员工。 单击超链接后，页面会导航到“添加员工”页以收集新员工的详细信息，并将其返回到“员工列表”页以创建新员工并更新列表。 这种样式的导航与调用方法来执行某些处理并返回值（称为结构化编程）类似。 同样，这种样式的导航称为 *结构化导航*。

<xref:System.Windows.Controls.Page>类不实现对结构化导航的支持。 相反， <xref:System.Windows.Navigation.PageFunction%601> 类派生自 <xref:System.Windows.Controls.Page> ，并将其与结构化导航所需的基本构造进行扩展。 本主题演示如何使用建立结构化导航 <xref:System.Windows.Navigation.PageFunction%601> 。

<a name="Structured_Navigation"></a>

## <a name="structured-navigation"></a>结构化导航

在结构化导航中，当一个页面调用另一个页面时需要以下部分或全部行为：

- 调用页导航到被调用页，并且可以选择性地传递被调用页所需的参数。

- 当用户已使用完调用页时，被调用页将专门返回到调用页，并且可以：

  - 返回描述调用页是如何完成（例如，用户按的是“确定”按钮还是“取消”按钮）的状态信息。

  - 返回从用户那里收集的数据（例如，新员工的详细信息）。

- 当调用页返回到被调用页时，被调用页会从导航历史记录中删除，以便将被调用页的一个实例与另一个实例隔离开。

下图演示了这些行为：

![屏幕截图显示调用页和被调用页之间的流。](./media/structured-navigation-overview/flow-between-calling-page-called-page.png)

您可以使用 <xref:System.Windows.Navigation.PageFunction%601> 作为被调用页来实现这些行为。

<a name="Structured_Navigation_with_PageFunction"></a>

## <a name="structured-navigation-with-pagefunction"></a>使用 PageFunction 进行结构化导航

本主题演示如何实现涉及单个的结构化导航的基本机制 <xref:System.Windows.Navigation.PageFunction%601> 。 在此示例中， <xref:System.Windows.Controls.Page> 调用 <xref:System.Windows.Navigation.PageFunction%601> 以获取用户的 <xref:System.String> 值并返回该值。

### <a name="creating-a-calling-page"></a>创建调用页

调用的页可以是 <xref:System.Windows.Navigation.PageFunction%601> <xref:System.Windows.Controls.Page> 或 <xref:System.Windows.Navigation.PageFunction%601> 。 在此示例中，它是一个 <xref:System.Windows.Controls.Page> ，如下面的代码所示。

[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup1)]
[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup2)]

[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind1)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind1)]
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind2)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind2)]
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind3)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind3)]

### <a name="creating-a-page-function-to-call"></a>创建要调用的页函数

由于调用页可以使用被调用页来从用户那里收集和返回数据，因此， <xref:System.Windows.Navigation.PageFunction%601> 将实现为泛型类，该类的类型参数指定被调用页将返回的值的类型。 下面的代码演示如何使用返回的调用页的初始实现 <xref:System.Windows.Navigation.PageFunction%601> <xref:System.String> 。

[!code-xaml[StructuredNavigationSample#CalledPageFunctionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml#calledpagefunctionmarkup)]

[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind1)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind1)]
[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind2)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind2)]

的声明类似于的 <xref:System.Windows.Navigation.PageFunction%601> 声明， <xref:System.Windows.Controls.Page> 并添加了类型参数。 从代码示语例中可以看出，在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 标记和代码隐藏中均指定了类型自变量，前者使用 `x:TypeArguments` 属性，后者使用标准的泛型类型参数语法。

不必仅使用 .NET Framework 类作为类型实参。 <xref:System.Windows.Navigation.PageFunction%601>可以调用来收集抽象为自定义类型的域特定数据。 下面的代码演示如何使用自定义类型作为的类型参数 <xref:System.Windows.Navigation.PageFunction%601> 。

[!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode1)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode1)]
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode2)]

[!code-xaml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup1)]
[!code-xaml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup2)]

[!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind1)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind1)]
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind2)]

的类型自变量为 <xref:System.Windows.Navigation.PageFunction%601> 调用页和被调用页之间的通信提供基础，以下部分对此进行了讨论。

正如您将看到的，使用的声明标识的类型在将 <xref:System.Windows.Navigation.PageFunction%601> 数据从返回到调用页时起着重要作用 <xref:System.Windows.Navigation.PageFunction%601> 。

### <a name="calling-a-pagefunction-and-passing-parameters"></a>调用 PageFunction 和传递参数

若要调用页，调用页必须实例化被调用的页，并使用方法导航到它 <xref:System.Windows.Navigation.NavigationService.Navigate%2A> 。 这使得调用页可以将初始数据传递给被调用页，例如，被调用页收集的数据的默认值。

下面的代码显示了使用非参数构造函数的被调用页，以接受来自调用页的参数。

[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind1)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind1)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind2)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind2)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind3)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind3)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind4)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind4)]

下面的代码演示了用于处理的事件的调用页， <xref:System.Windows.Documents.Hyperlink.Click> <xref:System.Windows.Documents.Hyperlink> 用于实例化被调用的页并向其传递初始字符串值。

[!code-xaml[StructuredNavigationSample#PassingDataMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#passingdatamarkup2)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind1)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind1)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind2)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind2)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind3)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind3)]

不必向被调用页传递参数。 可以执行以下操作：

- 从调用页：

  1. <xref:System.Windows.Navigation.PageFunction%601>使用无参数构造函数实例化调用的。

  2. 将参数存储在中 <xref:System.Windows.Application.Properties%2A> 。

  3. 导航到调用的 <xref:System.Windows.Navigation.PageFunction%601> 。

- 从调用的 <xref:System.Windows.Navigation.PageFunction%601> ：

  - 检索并使用中存储的参数 <xref:System.Windows.Application.Properties%2A> 。

但是，你不久就会看到，你仍然需要使用代码来实例化并导航到被调用页，以收集被调用页返回的数据。 出于此原因， <xref:System.Windows.Navigation.PageFunction%601> 需要保持活动状态; 否则，下一次导航到时 <xref:System.Windows.Navigation.PageFunction%601> ，WPF 将 <xref:System.Windows.Navigation.PageFunction%601> 使用无参数构造函数实例化。

但是，在被调用页返回前，需要返回可以由调用页检索的数据。

### <a name="returning-task-result-and-task-data-from-a-task-to-a-calling-page"></a>将任务的任务结果和任务数据返回到调用页

在用户使用完被调用页后（在本示例中通过按“确定”或“取消”按钮来表示），被调用页需要返回。 因为调用页已使用被调用页来从用户那里收集数据，所以调用页需要两种类型的信息：

1. 用户是否取消了被调用页（在此示例中通过按“确定”或“取消”按钮）。 这使得调用页可以确定是否处理调用页从用户那里收集的数据。

2. 用户提供的数据。

若要返回信息，请 <xref:System.Windows.Navigation.PageFunction%601> 实现 <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 方法。 下面的代码演示如何调用它。

[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind1)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind1)]
[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind2)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind2)]

在此示例中，如果用户按“取消”按钮，则会向调用页返回 `null` 值。 如果按“确定”按钮，则返回用户提供的字符串值。 <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 是 `protected virtual` 调用以将数据返回到调用页的方法。 需要将你的数据打包到泛型类型的实例中 <xref:System.Windows.Navigation.ReturnEventArgs%601> ，其类型参数指定返回的值的类型 <xref:System.Windows.Navigation.ReturnEventArgs%601.Result%2A> 。 这样，当你 <xref:System.Windows.Navigation.PageFunction%601> 使用特定类型参数声明时，你将会声明， <xref:System.Windows.Navigation.PageFunction%601> 将返回类型参数指定的类型的实例。 在此示例中，类型参数和，因此，返回值的类型为 <xref:System.String> 。

<xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>调用时，调用页需要某种方法来接收的返回值 <xref:System.Windows.Navigation.PageFunction%601> 。 出于此原因， <xref:System.Windows.Navigation.PageFunction%601> 实现了 <xref:System.Windows.Navigation.PageFunction%601.Return> 用于调用要处理的页的事件。 调用时， <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> <xref:System.Windows.Navigation.PageFunction%601.Return> 将引发，因此调用页可以向注册 <xref:System.Windows.Navigation.PageFunction%601.Return> 以接收通知。

[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind1)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind1)]
[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind2)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind2)]

### <a name="removing-task-pages-when-a-task-completes"></a>当任务完成时删除任务页

当被调用页返回，并且用户未取消被调用页时，调用页将处理由用户提供并且从被调用页返回的数据。 这种方式的数据采集通常是独立的活动；当被调用页返回时，调用页需要创建并导航到新的调用页来捕获更多数据。

不过，除非已从日志中删除被调用页，否则用户将能够向后导航到调用页的上一个实例。 是否 <xref:System.Windows.Navigation.PageFunction%601> 在日记中保留是由属性确定的 <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> 。 默认情况下，当调用时，将自动删除页面函数， <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 因为 <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> 设置为 `true` 。 若要在调用后在导航历史记录中保留页面函数 <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> ，请将设置 <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> 为 `false` 。

<a name="Other_Types_of_Structured_Navigation"></a>

## <a name="other-types-of-structured-navigation"></a>其他类型的结构化导航

本主题说明了对的最基本使用 <xref:System.Windows.Navigation.PageFunction%601> 来支持调用/返回结构化导航。 这一基础使你能够创建更复杂的结构化导航类型。

例如，有时调用页需要多个页面来从用户那里收集足够的数据或者执行任务。 多个页面的使用称为“向导”。

在其他情况下，应用程序可能具有依赖于结构化导航来有效操作的复杂导航拓扑。 有关详细信息，请参阅[导航拓扑概述](navigation-topologies-overview.md)。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [导航拓扑概述](navigation-topologies-overview.md)
