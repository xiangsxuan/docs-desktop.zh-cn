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
# <a name="structured-navigation-overview"></a><span data-ttu-id="6dd55-102">结构化导航概述</span><span class="sxs-lookup"><span data-stu-id="6dd55-102">Structured Navigation Overview</span></span>

<span data-ttu-id="6dd55-103">XAML 浏览器应用程序可以由 XAML 浏览器应用程序 (XBAP) 、或之一承载的内容由 <xref:System.Windows.Controls.Frame> <xref:System.Windows.Navigation.NavigationWindow> 可通过 pack 统一资源标识符 (uri) 并通过超链接导航到的页组成。</span><span class="sxs-lookup"><span data-stu-id="6dd55-103">Content that can be hosted by an XAML browser application (XBAP), a <xref:System.Windows.Controls.Frame>, or a <xref:System.Windows.Navigation.NavigationWindow> is composed of pages that can be identified by pack uniform resource identifiers (URIs) and navigated to by hyperlinks.</span></span> <span data-ttu-id="6dd55-104">页面的结构以及导航页面的方式（通过超链接来定义）称为导航拓扑。</span><span class="sxs-lookup"><span data-stu-id="6dd55-104">The structure of pages and the ways in which they can be navigated, as defined by hyperlinks, is known as a navigation topology.</span></span> <span data-ttu-id="6dd55-105">此类拓扑适合各种应用程序类型，尤其适合在文档之间导航的应用程序类型。</span><span class="sxs-lookup"><span data-stu-id="6dd55-105">Such a topology suits a variety of application types, particularly those that navigate through documents.</span></span> <span data-ttu-id="6dd55-106">对于此类应用程序，用户可以从一个页面导航到另一个页面，并且其中任一页面都无需了解另一页面的任何信息。</span><span class="sxs-lookup"><span data-stu-id="6dd55-106">For such applications, the user can navigate from one page to another page without either page needing to know anything about the other.</span></span>

<span data-ttu-id="6dd55-107">但是，对于其他类型的应用程序，在其页面之间导航时，确实需要了解这些页面信息。</span><span class="sxs-lookup"><span data-stu-id="6dd55-107">However, other types of applications have pages that do need to know when they have been navigated between.</span></span> <span data-ttu-id="6dd55-108">例如，假设一个人力资源应用程序，它具有一个列出组织中所有员工的页面，即“员工列表”页。</span><span class="sxs-lookup"><span data-stu-id="6dd55-108">For example, consider a human resources application that has one page to list all the employees in an organization—the "List Employees" page.</span></span> <span data-ttu-id="6dd55-109">此页还允许用户通过单击超链接添加新员工。</span><span class="sxs-lookup"><span data-stu-id="6dd55-109">This page could also allow users to add a new employee by clicking a hyperlink.</span></span> <span data-ttu-id="6dd55-110">单击超链接后，页面会导航到“添加员工”页以收集新员工的详细信息，并将其返回到“员工列表”页以创建新员工并更新列表。</span><span class="sxs-lookup"><span data-stu-id="6dd55-110">When clicked, the page navigates to an "Add an Employee" page to gather the new employee's details and return them to the "List Employees" page to create the new employee and update the list.</span></span> <span data-ttu-id="6dd55-111">这种样式的导航与调用方法来执行某些处理并返回值（称为结构化编程）类似。</span><span class="sxs-lookup"><span data-stu-id="6dd55-111">This style of navigation is similar to calling a method to perform some processing and return a value, which is known as structured programming.</span></span> <span data-ttu-id="6dd55-112">同样，这种样式的导航称为 *结构化导航*。</span><span class="sxs-lookup"><span data-stu-id="6dd55-112">As such, this style of navigation is known as *structured navigation*.</span></span>

<span data-ttu-id="6dd55-113"><xref:System.Windows.Controls.Page>类不实现对结构化导航的支持。</span><span class="sxs-lookup"><span data-stu-id="6dd55-113">The <xref:System.Windows.Controls.Page> class doesn't implement support for structured navigation.</span></span> <span data-ttu-id="6dd55-114">相反， <xref:System.Windows.Navigation.PageFunction%601> 类派生自 <xref:System.Windows.Controls.Page> ，并将其与结构化导航所需的基本构造进行扩展。</span><span class="sxs-lookup"><span data-stu-id="6dd55-114">Instead, the <xref:System.Windows.Navigation.PageFunction%601> class derives from <xref:System.Windows.Controls.Page> and extends it with the basic constructs required for structured navigation.</span></span> <span data-ttu-id="6dd55-115">本主题演示如何使用建立结构化导航 <xref:System.Windows.Navigation.PageFunction%601> 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-115">This topic shows how to establish structured navigation using <xref:System.Windows.Navigation.PageFunction%601>.</span></span>

<a name="Structured_Navigation"></a>

## <a name="structured-navigation"></a><span data-ttu-id="6dd55-116">结构化导航</span><span class="sxs-lookup"><span data-stu-id="6dd55-116">Structured Navigation</span></span>

<span data-ttu-id="6dd55-117">在结构化导航中，当一个页面调用另一个页面时需要以下部分或全部行为：</span><span class="sxs-lookup"><span data-stu-id="6dd55-117">When one page calls another page in a structured navigation, some or all of the following behaviors are required:</span></span>

- <span data-ttu-id="6dd55-118">调用页导航到被调用页，并且可以选择性地传递被调用页所需的参数。</span><span class="sxs-lookup"><span data-stu-id="6dd55-118">The calling page navigates to the called page, optionally passing parameters required by the called page.</span></span>

- <span data-ttu-id="6dd55-119">当用户已使用完调用页时，被调用页将专门返回到调用页，并且可以：</span><span class="sxs-lookup"><span data-stu-id="6dd55-119">The called page, when a user has completed using the calling page, returns specifically to the calling page, optionally:</span></span>

  - <span data-ttu-id="6dd55-120">返回描述调用页是如何完成（例如，用户按的是“确定”按钮还是“取消”按钮）的状态信息。</span><span class="sxs-lookup"><span data-stu-id="6dd55-120">Returning state information that describes how the calling page was completed (for example, whether a user pressed an OK button or a Cancel button).</span></span>

  - <span data-ttu-id="6dd55-121">返回从用户那里收集的数据（例如，新员工的详细信息）。</span><span class="sxs-lookup"><span data-stu-id="6dd55-121">Returning that data that was collected from the user (for example, new employee details).</span></span>

- <span data-ttu-id="6dd55-122">当调用页返回到被调用页时，被调用页会从导航历史记录中删除，以便将被调用页的一个实例与另一个实例隔离开。</span><span class="sxs-lookup"><span data-stu-id="6dd55-122">When the calling page returns to the called page, the called page is removed from navigation history to isolate one instance of a called page from another.</span></span>

<span data-ttu-id="6dd55-123">下图演示了这些行为：</span><span class="sxs-lookup"><span data-stu-id="6dd55-123">These behaviors are illustrated by the following figure:</span></span>

![屏幕截图显示调用页和被调用页之间的流。](./media/structured-navigation-overview/flow-between-calling-page-called-page.png)

<span data-ttu-id="6dd55-125">您可以使用 <xref:System.Windows.Navigation.PageFunction%601> 作为被调用页来实现这些行为。</span><span class="sxs-lookup"><span data-stu-id="6dd55-125">You can implement these behaviors by using a <xref:System.Windows.Navigation.PageFunction%601> as the called page.</span></span>

<a name="Structured_Navigation_with_PageFunction"></a>

## <a name="structured-navigation-with-pagefunction"></a><span data-ttu-id="6dd55-126">使用 PageFunction 进行结构化导航</span><span class="sxs-lookup"><span data-stu-id="6dd55-126">Structured Navigation with PageFunction</span></span>

<span data-ttu-id="6dd55-127">本主题演示如何实现涉及单个的结构化导航的基本机制 <xref:System.Windows.Navigation.PageFunction%601> 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-127">This topic shows how to implement the basic mechanics of structured navigation involving a single <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="6dd55-128">在此示例中， <xref:System.Windows.Controls.Page> 调用 <xref:System.Windows.Navigation.PageFunction%601> 以获取用户的 <xref:System.String> 值并返回该值。</span><span class="sxs-lookup"><span data-stu-id="6dd55-128">In this sample, a <xref:System.Windows.Controls.Page> calls a <xref:System.Windows.Navigation.PageFunction%601> to get a <xref:System.String> value from the user and return it.</span></span>

### <a name="creating-a-calling-page"></a><span data-ttu-id="6dd55-129">创建调用页</span><span class="sxs-lookup"><span data-stu-id="6dd55-129">Creating a Calling Page</span></span>

<span data-ttu-id="6dd55-130">调用的页可以是 <xref:System.Windows.Navigation.PageFunction%601> <xref:System.Windows.Controls.Page> 或 <xref:System.Windows.Navigation.PageFunction%601> 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-130">The page that calls a <xref:System.Windows.Navigation.PageFunction%601> can be either a <xref:System.Windows.Controls.Page> or a <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="6dd55-131">在此示例中，它是一个 <xref:System.Windows.Controls.Page> ，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="6dd55-131">In this example, it is a <xref:System.Windows.Controls.Page>, as shown in the following code.</span></span>

[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup1)]
[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup2)]

[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind1)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind1)]
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind2)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind2)]
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind3)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind3)]

### <a name="creating-a-page-function-to-call"></a><span data-ttu-id="6dd55-132">创建要调用的页函数</span><span class="sxs-lookup"><span data-stu-id="6dd55-132">Creating a Page Function to Call</span></span>

<span data-ttu-id="6dd55-133">由于调用页可以使用被调用页来从用户那里收集和返回数据，因此， <xref:System.Windows.Navigation.PageFunction%601> 将实现为泛型类，该类的类型参数指定被调用页将返回的值的类型。</span><span class="sxs-lookup"><span data-stu-id="6dd55-133">Because the calling page can use the called page to collect and return data from the user, <xref:System.Windows.Navigation.PageFunction%601> is implemented as a generic class whose type argument specifies the type of the value that the called page will return.</span></span> <span data-ttu-id="6dd55-134">下面的代码演示如何使用返回的调用页的初始实现 <xref:System.Windows.Navigation.PageFunction%601> <xref:System.String> 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-134">The following code shows the initial implementation of the called page, using a <xref:System.Windows.Navigation.PageFunction%601>, which returns a <xref:System.String>.</span></span>

[!code-xaml[StructuredNavigationSample#CalledPageFunctionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml#calledpagefunctionmarkup)]

[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind1)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind1)]
[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind2)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind2)]

<span data-ttu-id="6dd55-135">的声明类似于的 <xref:System.Windows.Navigation.PageFunction%601> 声明， <xref:System.Windows.Controls.Page> 并添加了类型参数。</span><span class="sxs-lookup"><span data-stu-id="6dd55-135">The declaration of a <xref:System.Windows.Navigation.PageFunction%601> is similar to the declaration of a <xref:System.Windows.Controls.Page> with the addition of the type arguments.</span></span> <span data-ttu-id="6dd55-136">从代码示语例中可以看出，在 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 标记和代码隐藏中均指定了类型自变量，前者使用 `x:TypeArguments` 属性，后者使用标准的泛型类型参数语法。</span><span class="sxs-lookup"><span data-stu-id="6dd55-136">As you can see from the code example, the type arguments are specified in both [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] markup, using the `x:TypeArguments` attribute, and code-behind, using standard generic type argument syntax.</span></span>

<span data-ttu-id="6dd55-137">不必仅使用 .NET Framework 类作为类型实参。</span><span class="sxs-lookup"><span data-stu-id="6dd55-137">You don't have to use only .NET Framework classes as type arguments.</span></span> <span data-ttu-id="6dd55-138"><xref:System.Windows.Navigation.PageFunction%601>可以调用来收集抽象为自定义类型的域特定数据。</span><span class="sxs-lookup"><span data-stu-id="6dd55-138">A <xref:System.Windows.Navigation.PageFunction%601> could be called to gather domain-specific data that is abstracted as a custom type.</span></span> <span data-ttu-id="6dd55-139">下面的代码演示如何使用自定义类型作为的类型参数 <xref:System.Windows.Navigation.PageFunction%601> 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-139">The following code shows how to use a custom type as a type argument for a <xref:System.Windows.Navigation.PageFunction%601>.</span></span>

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

<span data-ttu-id="6dd55-140">的类型自变量为 <xref:System.Windows.Navigation.PageFunction%601> 调用页和被调用页之间的通信提供基础，以下部分对此进行了讨论。</span><span class="sxs-lookup"><span data-stu-id="6dd55-140">The type arguments for the <xref:System.Windows.Navigation.PageFunction%601> provide the foundation for the communication between a calling page and the called page, which are discussed in the following sections.</span></span>

<span data-ttu-id="6dd55-141">正如您将看到的，使用的声明标识的类型在将 <xref:System.Windows.Navigation.PageFunction%601> 数据从返回到调用页时起着重要作用 <xref:System.Windows.Navigation.PageFunction%601> 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-141">As you'll see, the type that is identified with the declaration of a <xref:System.Windows.Navigation.PageFunction%601> plays an important role in returning data from a <xref:System.Windows.Navigation.PageFunction%601> to the calling page.</span></span>

### <a name="calling-a-pagefunction-and-passing-parameters"></a><span data-ttu-id="6dd55-142">调用 PageFunction 和传递参数</span><span class="sxs-lookup"><span data-stu-id="6dd55-142">Calling a PageFunction and Passing Parameters</span></span>

<span data-ttu-id="6dd55-143">若要调用页，调用页必须实例化被调用的页，并使用方法导航到它 <xref:System.Windows.Navigation.NavigationService.Navigate%2A> 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-143">To call a page, the calling page must instantiate the called page and navigate to it using the <xref:System.Windows.Navigation.NavigationService.Navigate%2A> method.</span></span> <span data-ttu-id="6dd55-144">这使得调用页可以将初始数据传递给被调用页，例如，被调用页收集的数据的默认值。</span><span class="sxs-lookup"><span data-stu-id="6dd55-144">This allows the calling page to pass initial data to the called page, such as default values for the data being gathered by the called page.</span></span>

<span data-ttu-id="6dd55-145">下面的代码显示了使用非参数构造函数的被调用页，以接受来自调用页的参数。</span><span class="sxs-lookup"><span data-stu-id="6dd55-145">The following code shows the called page with a non-parameterless constructor to accept parameters from the calling page.</span></span>

[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind1)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind1)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind2)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind2)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind3)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind3)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind4)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind4)]

<span data-ttu-id="6dd55-146">下面的代码演示了用于处理的事件的调用页， <xref:System.Windows.Documents.Hyperlink.Click> <xref:System.Windows.Documents.Hyperlink> 用于实例化被调用的页并向其传递初始字符串值。</span><span class="sxs-lookup"><span data-stu-id="6dd55-146">The following code shows the calling page handling the <xref:System.Windows.Documents.Hyperlink.Click> event of the <xref:System.Windows.Documents.Hyperlink> to instantiate the called page and pass it an initial string value.</span></span>

[!code-xaml[StructuredNavigationSample#PassingDataMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#passingdatamarkup2)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind1)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind1)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind2)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind2)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind3)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind3)]

<span data-ttu-id="6dd55-147">不必向被调用页传递参数。</span><span class="sxs-lookup"><span data-stu-id="6dd55-147">You are not required to pass parameters to the called page.</span></span> <span data-ttu-id="6dd55-148">可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6dd55-148">Instead, you could do the following:</span></span>

- <span data-ttu-id="6dd55-149">从调用页：</span><span class="sxs-lookup"><span data-stu-id="6dd55-149">From the calling page:</span></span>

  1. <span data-ttu-id="6dd55-150"><xref:System.Windows.Navigation.PageFunction%601>使用无参数构造函数实例化调用的。</span><span class="sxs-lookup"><span data-stu-id="6dd55-150">Instantiate the called <xref:System.Windows.Navigation.PageFunction%601> using the parameterless constructor.</span></span>

  2. <span data-ttu-id="6dd55-151">将参数存储在中 <xref:System.Windows.Application.Properties%2A> 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-151">Store the parameters in <xref:System.Windows.Application.Properties%2A>.</span></span>

  3. <span data-ttu-id="6dd55-152">导航到调用的 <xref:System.Windows.Navigation.PageFunction%601> 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-152">Navigate to the called <xref:System.Windows.Navigation.PageFunction%601>.</span></span>

- <span data-ttu-id="6dd55-153">从调用的 <xref:System.Windows.Navigation.PageFunction%601> ：</span><span class="sxs-lookup"><span data-stu-id="6dd55-153">From the called <xref:System.Windows.Navigation.PageFunction%601>:</span></span>

  - <span data-ttu-id="6dd55-154">检索并使用中存储的参数 <xref:System.Windows.Application.Properties%2A> 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-154">Retrieve and use the parameters stored in <xref:System.Windows.Application.Properties%2A>.</span></span>

<span data-ttu-id="6dd55-155">但是，你不久就会看到，你仍然需要使用代码来实例化并导航到被调用页，以收集被调用页返回的数据。</span><span class="sxs-lookup"><span data-stu-id="6dd55-155">But, as you'll see shortly, you'll still need use code to instantiate and navigate to the called page to collect the data returned by the called page.</span></span> <span data-ttu-id="6dd55-156">出于此原因， <xref:System.Windows.Navigation.PageFunction%601> 需要保持活动状态; 否则，下一次导航到时 <xref:System.Windows.Navigation.PageFunction%601> ，WPF 将 <xref:System.Windows.Navigation.PageFunction%601> 使用无参数构造函数实例化。</span><span class="sxs-lookup"><span data-stu-id="6dd55-156">For this reason, the <xref:System.Windows.Navigation.PageFunction%601> needs to be kept alive; otherwise, the next time you navigate to the <xref:System.Windows.Navigation.PageFunction%601>, WPF instantiates the <xref:System.Windows.Navigation.PageFunction%601> using the parameterless constructor.</span></span>

<span data-ttu-id="6dd55-157">但是，在被调用页返回前，需要返回可以由调用页检索的数据。</span><span class="sxs-lookup"><span data-stu-id="6dd55-157">Before the called page can return, however, it needs to return data that can be retrieved by the calling page.</span></span>

### <a name="returning-task-result-and-task-data-from-a-task-to-a-calling-page"></a><span data-ttu-id="6dd55-158">将任务的任务结果和任务数据返回到调用页</span><span class="sxs-lookup"><span data-stu-id="6dd55-158">Returning Task Result and Task Data from a Task to a Calling Page</span></span>

<span data-ttu-id="6dd55-159">在用户使用完被调用页后（在本示例中通过按“确定”或“取消”按钮来表示），被调用页需要返回。</span><span class="sxs-lookup"><span data-stu-id="6dd55-159">Once the user has finished using the called page, signified in this example by pressing either the OK or Cancel buttons, the called page needs to return.</span></span> <span data-ttu-id="6dd55-160">因为调用页已使用被调用页来从用户那里收集数据，所以调用页需要两种类型的信息：</span><span class="sxs-lookup"><span data-stu-id="6dd55-160">Since the calling page used the called page to collect data from the user, the calling page requires two types of information:</span></span>

1. <span data-ttu-id="6dd55-161">用户是否取消了被调用页（在此示例中通过按“确定”或“取消”按钮）。</span><span class="sxs-lookup"><span data-stu-id="6dd55-161">Whether the user canceled the called page (by pressing either the OK button or the Cancel button in this example).</span></span> <span data-ttu-id="6dd55-162">这使得调用页可以确定是否处理调用页从用户那里收集的数据。</span><span class="sxs-lookup"><span data-stu-id="6dd55-162">This allows the calling page to determine whether to process the data that the calling page gathered from the user.</span></span>

2. <span data-ttu-id="6dd55-163">用户提供的数据。</span><span class="sxs-lookup"><span data-stu-id="6dd55-163">The data that was provided by the user.</span></span>

<span data-ttu-id="6dd55-164">若要返回信息，请 <xref:System.Windows.Navigation.PageFunction%601> 实现 <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="6dd55-164">To return information, <xref:System.Windows.Navigation.PageFunction%601> implements the <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> method.</span></span> <span data-ttu-id="6dd55-165">下面的代码演示如何调用它。</span><span class="sxs-lookup"><span data-stu-id="6dd55-165">The following code shows how to call it.</span></span>

[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind1)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind1)]
[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind2)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind2)]

<span data-ttu-id="6dd55-166">在此示例中，如果用户按“取消”按钮，则会向调用页返回 `null` 值。</span><span class="sxs-lookup"><span data-stu-id="6dd55-166">In this example, if a user presses the Cancel button, a value of `null` is returned to the calling page.</span></span> <span data-ttu-id="6dd55-167">如果按“确定”按钮，则返回用户提供的字符串值。</span><span class="sxs-lookup"><span data-stu-id="6dd55-167">If the OK button is pressed instead, the string value provided by the user is returned.</span></span> <span data-ttu-id="6dd55-168"><xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 是 `protected virtual` 调用以将数据返回到调用页的方法。</span><span class="sxs-lookup"><span data-stu-id="6dd55-168"><xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> is a `protected virtual` method that you call to return your data to the calling page.</span></span> <span data-ttu-id="6dd55-169">需要将你的数据打包到泛型类型的实例中 <xref:System.Windows.Navigation.ReturnEventArgs%601> ，其类型参数指定返回的值的类型 <xref:System.Windows.Navigation.ReturnEventArgs%601.Result%2A> 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-169">Your data needs to be packaged in an instance of the generic <xref:System.Windows.Navigation.ReturnEventArgs%601> type, whose type argument specifies the type of value that <xref:System.Windows.Navigation.ReturnEventArgs%601.Result%2A> returns.</span></span> <span data-ttu-id="6dd55-170">这样，当你 <xref:System.Windows.Navigation.PageFunction%601> 使用特定类型参数声明时，你将会声明， <xref:System.Windows.Navigation.PageFunction%601> 将返回类型参数指定的类型的实例。</span><span class="sxs-lookup"><span data-stu-id="6dd55-170">In this way, when you declare a <xref:System.Windows.Navigation.PageFunction%601> with a particular type argument, you are stating that a <xref:System.Windows.Navigation.PageFunction%601> will return an instance of the type that is specified by the type argument.</span></span> <span data-ttu-id="6dd55-171">在此示例中，类型参数和，因此，返回值的类型为 <xref:System.String> 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-171">In this example, the type argument and, consequently, the return value is of type <xref:System.String>.</span></span>

<span data-ttu-id="6dd55-172"><xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>调用时，调用页需要某种方法来接收的返回值 <xref:System.Windows.Navigation.PageFunction%601> 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-172">When <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> is called, the calling page needs some way of receiving the return value of the <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="6dd55-173">出于此原因， <xref:System.Windows.Navigation.PageFunction%601> 实现了 <xref:System.Windows.Navigation.PageFunction%601.Return> 用于调用要处理的页的事件。</span><span class="sxs-lookup"><span data-stu-id="6dd55-173">For this reason, <xref:System.Windows.Navigation.PageFunction%601> implements the <xref:System.Windows.Navigation.PageFunction%601.Return> event for calling pages to handle.</span></span> <span data-ttu-id="6dd55-174">调用时， <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> <xref:System.Windows.Navigation.PageFunction%601.Return> 将引发，因此调用页可以向注册 <xref:System.Windows.Navigation.PageFunction%601.Return> 以接收通知。</span><span class="sxs-lookup"><span data-stu-id="6dd55-174">When <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> is called, <xref:System.Windows.Navigation.PageFunction%601.Return> is raised, so the calling page can register with <xref:System.Windows.Navigation.PageFunction%601.Return> to receive the notification.</span></span>

[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind1)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind1)]
[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind2)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind2)]

### <a name="removing-task-pages-when-a-task-completes"></a><span data-ttu-id="6dd55-175">当任务完成时删除任务页</span><span class="sxs-lookup"><span data-stu-id="6dd55-175">Removing Task Pages When a Task Completes</span></span>

<span data-ttu-id="6dd55-176">当被调用页返回，并且用户未取消被调用页时，调用页将处理由用户提供并且从被调用页返回的数据。</span><span class="sxs-lookup"><span data-stu-id="6dd55-176">When a called page returns, and the user didn't cancel the called page, the calling page will process the data that was provided by the user and also returned from the called page.</span></span> <span data-ttu-id="6dd55-177">这种方式的数据采集通常是独立的活动；当被调用页返回时，调用页需要创建并导航到新的调用页来捕获更多数据。</span><span class="sxs-lookup"><span data-stu-id="6dd55-177">Data acquisition in this way is usually an isolated activity; when the called page returns, the calling page needs to create and navigate to a new calling page to capture more data.</span></span>

<span data-ttu-id="6dd55-178">不过，除非已从日志中删除被调用页，否则用户将能够向后导航到调用页的上一个实例。</span><span class="sxs-lookup"><span data-stu-id="6dd55-178">However, unless a called page is removed from the journal, a user will be able to navigate back to a previous instance of the calling page.</span></span> <span data-ttu-id="6dd55-179">是否 <xref:System.Windows.Navigation.PageFunction%601> 在日记中保留是由属性确定的 <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-179">Whether a <xref:System.Windows.Navigation.PageFunction%601> is retained in the journal is determined by the <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> property.</span></span> <span data-ttu-id="6dd55-180">默认情况下，当调用时，将自动删除页面函数， <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> 因为 <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> 设置为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-180">By default, a page function is automatically removed when <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> is called because <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> is set to `true`.</span></span> <span data-ttu-id="6dd55-181">若要在调用后在导航历史记录中保留页面函数 <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> ，请将设置 <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> 为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="6dd55-181">To keep a page function in navigation history after <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> is called, set <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> to `false`.</span></span>

<a name="Other_Types_of_Structured_Navigation"></a>

## <a name="other-types-of-structured-navigation"></a><span data-ttu-id="6dd55-182">其他类型的结构化导航</span><span class="sxs-lookup"><span data-stu-id="6dd55-182">Other Types of Structured Navigation</span></span>

<span data-ttu-id="6dd55-183">本主题说明了对的最基本使用 <xref:System.Windows.Navigation.PageFunction%601> 来支持调用/返回结构化导航。</span><span class="sxs-lookup"><span data-stu-id="6dd55-183">This topic illustrates the most basic use of a <xref:System.Windows.Navigation.PageFunction%601> to support call/return structured navigation.</span></span> <span data-ttu-id="6dd55-184">这一基础使你能够创建更复杂的结构化导航类型。</span><span class="sxs-lookup"><span data-stu-id="6dd55-184">This foundation provides you with the ability to create more complex types of structured navigation.</span></span>

<span data-ttu-id="6dd55-185">例如，有时调用页需要多个页面来从用户那里收集足够的数据或者执行任务。</span><span class="sxs-lookup"><span data-stu-id="6dd55-185">For example, sometimes multiple pages are required by a calling page to gather enough data from a user or to perform a task.</span></span> <span data-ttu-id="6dd55-186">多个页面的使用称为“向导”。</span><span class="sxs-lookup"><span data-stu-id="6dd55-186">The use of multiple pages is referred to as a "wizard".</span></span>

<span data-ttu-id="6dd55-187">在其他情况下，应用程序可能具有依赖于结构化导航来有效操作的复杂导航拓扑。</span><span class="sxs-lookup"><span data-stu-id="6dd55-187">In other cases, applications may have complex navigation topologies that depend on structured navigation to operate effectively.</span></span> <span data-ttu-id="6dd55-188">有关详细信息，请参阅[导航拓扑概述](navigation-topologies-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6dd55-188">For more information, see [Navigation Topologies Overview](navigation-topologies-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6dd55-189">请参阅</span><span class="sxs-lookup"><span data-stu-id="6dd55-189">See also</span></span>

- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [<span data-ttu-id="6dd55-190">导航拓扑概述</span><span class="sxs-lookup"><span data-stu-id="6dd55-190">Navigation Topologies Overview</span></span>](navigation-topologies-overview.md)
