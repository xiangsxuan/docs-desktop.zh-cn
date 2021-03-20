---
title: 优化性能：应用程序资源
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
ms.openlocfilehash: f5e99e1566f254c83b7562592690c9c1f334516e
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666857"
---
# <a name="optimizing-performance-application-resources"></a><span data-ttu-id="3f82c-102">优化性能：应用程序资源</span><span class="sxs-lookup"><span data-stu-id="3f82c-102">Optimizing Performance: Application Resources</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="3f82c-103">允许共享应用程序资源，使你能够跨相似类型的元素支持一致的外观或行为。</span><span class="sxs-lookup"><span data-stu-id="3f82c-103">allows you to share application resources so that you can support a consistent look or behavior across similar-typed elements.</span></span> <span data-ttu-id="3f82c-104">本主题提供了此方面的几项建议，可帮助您提高应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="3f82c-104">This topic provides a few recommendations in this area that can help you improve the performance of your applications.</span></span>  
  
 <span data-ttu-id="3f82c-105">有关资源的详细信息，请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)。</span><span class="sxs-lookup"><span data-stu-id="3f82c-105">For more information on resources, see [XAML Resources](/dotnet/desktop-wpf/fundamentals/xaml-resources-define).</span></span>  
  
## <a name="sharing-resources"></a><span data-ttu-id="3f82c-106">共享资源</span><span class="sxs-lookup"><span data-stu-id="3f82c-106">Sharing resources</span></span>  
 <span data-ttu-id="3f82c-107">如果你的应用程序使用自定义控件并在 <xref:System.Windows.ResourceDictionary> (或 XAML 资源节点) 中定义资源，则建议你在 <xref:System.Windows.Application> 或对象级别定义资源 <xref:System.Windows.Window> ，或者在自定义控件的默认主题中定义这些资源。</span><span class="sxs-lookup"><span data-stu-id="3f82c-107">If your application uses custom controls and defines resources in a <xref:System.Windows.ResourceDictionary> (or XAML Resources node), it is recommended that you either define the resources at the <xref:System.Windows.Application> or <xref:System.Windows.Window> object level, or define them in the default theme for the custom controls.</span></span> <span data-ttu-id="3f82c-108">在自定义控件中定义资源 <xref:System.Windows.ResourceDictionary> 会对该控件的每个实例产生性能影响。</span><span class="sxs-lookup"><span data-stu-id="3f82c-108">Defining resources in a custom control's <xref:System.Windows.ResourceDictionary> imposes a performance impact for every instance of that control.</span></span> <span data-ttu-id="3f82c-109">例如，如果您有一些在自定义控件的资源定义和自定义控件实例的资源定义中定义的性能密集型画笔操作，则应用程序的工作集会显著增加。</span><span class="sxs-lookup"><span data-stu-id="3f82c-109">For example, if you have performance-intensive brush operations defined as part of the resource definition of a custom control and many instances of the custom control, the application's working set will increase significantly.</span></span>  
  
 <span data-ttu-id="3f82c-110">为了说明这一点，请考虑以下事项。</span><span class="sxs-lookup"><span data-stu-id="3f82c-110">To illustrate this point, consider the following.</span></span> <span data-ttu-id="3f82c-111">假设您正在使用开发纸牌游戏 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="3f82c-111">Let's say you are developing a card game using [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="3f82c-112">对于大多数纸牌游戏，需要52个包含52个不同表面的卡。</span><span class="sxs-lookup"><span data-stu-id="3f82c-112">For most card games, you need 52 cards with 52 different faces.</span></span> <span data-ttu-id="3f82c-113">您决定实现卡片自定义控件，并定义52画笔 (每个画笔表示卡片自定义控件的资源) 。</span><span class="sxs-lookup"><span data-stu-id="3f82c-113">You decide to implement a card custom control and you define 52 brushes (each representing a card face) in the resources of your card custom control.</span></span> <span data-ttu-id="3f82c-114">在主应用程序中，最初创建此卡自定义控件的52实例。</span><span class="sxs-lookup"><span data-stu-id="3f82c-114">In your main application, you initially create 52 instances of this card custom control.</span></span> <span data-ttu-id="3f82c-115">卡自定义控件的每个实例都会生成52个 <xref:System.Windows.Media.Brush> 对象实例，这为您的应用程序提供了总共 52 \* 52 <xref:System.Windows.Media.Brush> 对象。</span><span class="sxs-lookup"><span data-stu-id="3f82c-115">Each instance of the card custom control generates 52 instances of <xref:System.Windows.Media.Brush> objects, which gives you a total of 52 \* 52 <xref:System.Windows.Media.Brush> objects in your application.</span></span> <span data-ttu-id="3f82c-116">通过将画笔从卡片自定义控件资源移出到 <xref:System.Windows.Application> 或 <xref:System.Windows.Window> 对象级别，或在自定义控件的默认主题中进行定义，可以减少应用程序的工作集，因为现在可以在卡片控件的52实例之间共享52画笔。</span><span class="sxs-lookup"><span data-stu-id="3f82c-116">By moving the brushes out of the card custom control resources to the <xref:System.Windows.Application> or <xref:System.Windows.Window> object level, or defining them in the default theme for the custom control, you reduce the working set of the application, since you are now sharing the 52 brushes among 52 instances of the card control.</span></span>  
  
## <a name="sharing-a-brush-without-copying"></a><span data-ttu-id="3f82c-117">共享画笔而不复制</span><span class="sxs-lookup"><span data-stu-id="3f82c-117">Sharing a Brush without Copying</span></span>  
 <span data-ttu-id="3f82c-118">如果有多个使用同一对象的元素 <xref:System.Windows.Media.Brush> ，请将画笔定义为资源并对其进行引用，而不是在 XAML 中以内联方式定义画笔。</span><span class="sxs-lookup"><span data-stu-id="3f82c-118">If you have multiple elements using the same <xref:System.Windows.Media.Brush> object, define the brush as a resource and reference it, rather than defining the brush inline in XAML.</span></span> <span data-ttu-id="3f82c-119">此方法将创建一个实例并重复使用它，而在 XAML 中以内联方式定义将为每个元素创建一个新的实例。</span><span class="sxs-lookup"><span data-stu-id="3f82c-119">This method will create one instance and reuse it, whereas defining brushes inline in XAML creates a new instance for each element.</span></span>  
  
 <span data-ttu-id="3f82c-120">以下标记示例说明了这一点：</span><span class="sxs-lookup"><span data-stu-id="3f82c-120">The following markup sample illustrates this point:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a><span data-ttu-id="3f82c-121">尽可能使用静态资源</span><span class="sxs-lookup"><span data-stu-id="3f82c-121">Use Static Resources when Possible</span></span>  
 <span data-ttu-id="3f82c-122">静态资源通过查找对已定义资源的引用来为任何 XAML 属性特性提供一个值。</span><span class="sxs-lookup"><span data-stu-id="3f82c-122">A static resource provides a value for any XAML property attribute by looking up a reference to an already defined resource.</span></span> <span data-ttu-id="3f82c-123">该资源的查找行为类似于编译时查找。</span><span class="sxs-lookup"><span data-stu-id="3f82c-123">Lookup behavior for that resource is analogous to compile-time lookup.</span></span>  
  
 <span data-ttu-id="3f82c-124">另一方面，动态资源将在初始编译期间创建一个临时表达式，从而推迟资源的查找，直到实际需要请求的资源值才能构造对象。</span><span class="sxs-lookup"><span data-stu-id="3f82c-124">A dynamic resource, on the other hand, will create a temporary expression during the initial compilation and thus defer lookup for resources until the requested resource value is actually required in order to construct an object.</span></span> <span data-ttu-id="3f82c-125">该资源的查找行为类似于运行时查找，这会影响性能。</span><span class="sxs-lookup"><span data-stu-id="3f82c-125">Lookup behavior for that resource is analogous to run-time lookup, which imposes a performance impact.</span></span> <span data-ttu-id="3f82c-126">在应用程序中尽可能使用静态资源，仅在必要时使用动态资源。</span><span class="sxs-lookup"><span data-stu-id="3f82c-126">Use static resources whenever possible in your application, using dynamic resources only when necessary.</span></span>  
  
 <span data-ttu-id="3f82c-127">以下标记示例演示如何使用两种类型的资源：</span><span class="sxs-lookup"><span data-stu-id="3f82c-127">The following markup sample shows the use of both types of resources:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a><span data-ttu-id="3f82c-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f82c-128">See also</span></span>

- [<span data-ttu-id="3f82c-129">优化 WPF 应用程序性能</span><span class="sxs-lookup"><span data-stu-id="3f82c-129">Optimizing WPF Application Performance</span></span>](optimizing-wpf-application-performance.md)
- [<span data-ttu-id="3f82c-130">规划应用程序性能</span><span class="sxs-lookup"><span data-stu-id="3f82c-130">Planning for Application Performance</span></span>](planning-for-application-performance.md)
- [<span data-ttu-id="3f82c-131">利用硬件</span><span class="sxs-lookup"><span data-stu-id="3f82c-131">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)
- [<span data-ttu-id="3f82c-132">布局和示例</span><span class="sxs-lookup"><span data-stu-id="3f82c-132">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)
- [<span data-ttu-id="3f82c-133">二维图形和图像处理</span><span class="sxs-lookup"><span data-stu-id="3f82c-133">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="3f82c-134">对象行为</span><span class="sxs-lookup"><span data-stu-id="3f82c-134">Object Behavior</span></span>](optimizing-performance-object-behavior.md)
- [<span data-ttu-id="3f82c-135">文本</span><span class="sxs-lookup"><span data-stu-id="3f82c-135">Text</span></span>](optimizing-performance-text.md)
- [<span data-ttu-id="3f82c-136">数据绑定</span><span class="sxs-lookup"><span data-stu-id="3f82c-136">Data Binding</span></span>](optimizing-performance-data-binding.md)
- [<span data-ttu-id="3f82c-137">其他性能建议</span><span class="sxs-lookup"><span data-stu-id="3f82c-137">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)
