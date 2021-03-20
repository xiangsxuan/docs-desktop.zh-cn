---
title: 如何：定义和引用资源
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: b7c7c7a06837750e77c313f50a6dd4f61029f892
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665934"
---
# <a name="how-to-define-and-reference-a-resource"></a><span data-ttu-id="f9f8d-102">如何：定义和引用资源</span><span class="sxs-lookup"><span data-stu-id="f9f8d-102">How to: Define and Reference a Resource</span></span>

<span data-ttu-id="f9f8d-103">此示例演示如何使用中的属性定义资源并对其进行引用 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="f9f8d-103">This example shows how to define a resource and reference it by using an attribute in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)].</span></span>

## <a name="example"></a><span data-ttu-id="f9f8d-104">示例</span><span class="sxs-lookup"><span data-stu-id="f9f8d-104">Example</span></span>

<span data-ttu-id="f9f8d-105">下面的示例定义了两种类型的资源： <xref:System.Windows.Media.SolidColorBrush> 资源和多个 <xref:System.Windows.Style> 资源。</span><span class="sxs-lookup"><span data-stu-id="f9f8d-105">The following example defines two types of resources: a <xref:System.Windows.Media.SolidColorBrush> resource, and several <xref:System.Windows.Style> resources.</span></span> <span data-ttu-id="f9f8d-106"><xref:System.Windows.Media.SolidColorBrush>资源 `MyBrush` 用于提供多个属性的值，每个属性都采用 <xref:System.Windows.Media.Brush> 类型值。</span><span class="sxs-lookup"><span data-stu-id="f9f8d-106">The <xref:System.Windows.Media.SolidColorBrush> resource `MyBrush` is used to provide the value of several properties that each take a <xref:System.Windows.Media.Brush> type value.</span></span> <span data-ttu-id="f9f8d-107"><xref:System.Windows.Style>资源 `PageBackground` ， `TitleText` `Label` 每个目标为特定的控件类型。</span><span class="sxs-lookup"><span data-stu-id="f9f8d-107">The <xref:System.Windows.Style> resources `PageBackground`, `TitleText` and `Label` each target a particular control type.</span></span> <span data-ttu-id="f9f8d-108">样式在目标控件上设置各种不同的属性，当该样式资源由资源键引用并用于设置 <xref:System.Windows.FrameworkElement.Style%2A> 中定义的多个特定控件元素的属性时 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="f9f8d-108">The styles set a variety of different properties on the targeted controls, when that style resource is referenced by resource key and is used to set the <xref:System.Windows.FrameworkElement.Style%2A> property of several specific control elements defined in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)].</span></span>

<span data-ttu-id="f9f8d-109">请注意，样式的资源库中的一个属性 `Label` 也引用 `MyBrush` 前面定义的资源。</span><span class="sxs-lookup"><span data-stu-id="f9f8d-109">Note that one of the properties within the setters of the `Label` style also references the `MyBrush` resource defined earlier.</span></span> <span data-ttu-id="f9f8d-110">这是一种常见的技术，但请务必记住，按给定顺序对资源进行分析并将其输入到资源字典中。</span><span class="sxs-lookup"><span data-stu-id="f9f8d-110">This is a common technique, but it is important to remember that resources are parsed and entered into a resource dictionary in the order that they are given.</span></span> <span data-ttu-id="f9f8d-111">如果使用 [StaticResource 标记扩展](staticresource-markup-extension.md) 在其他资源内引用资源，则还会按字典中找到的顺序请求资源。</span><span class="sxs-lookup"><span data-stu-id="f9f8d-111">Resources are also requested by the order found within the dictionary if you use the [StaticResource Markup Extension](staticresource-markup-extension.md) to reference them from within another resource.</span></span> <span data-ttu-id="f9f8d-112">请确保所引用的任何资源先前在资源集合中定义的资源超出了该资源的请求位置。</span><span class="sxs-lookup"><span data-stu-id="f9f8d-112">Make sure that any resource that you reference is defined earlier within the resources collection than where that resource is then requested.</span></span> <span data-ttu-id="f9f8d-113">如有必要，可以通过使用 [DynamicResource 标记扩展](dynamicresource-markup-extension.md) 在运行时引用资源来解决资源引用的严格创建顺序，但应注意，这种 DynamicResource 方法会产生性能后果。</span><span class="sxs-lookup"><span data-stu-id="f9f8d-113">If necessary, you can work around the strict creation order of resource references by using a [DynamicResource Markup Extension](dynamicresource-markup-extension.md) to reference the resource at runtime instead, but you should be aware that this DynamicResource technique has performance consequences.</span></span> <span data-ttu-id="f9f8d-114">有关详细信息，请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)。</span><span class="sxs-lookup"><span data-stu-id="f9f8d-114">For details, see [XAML Resources](/dotnet/desktop-wpf/fundamentals/xaml-resources-define).</span></span>

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a><span data-ttu-id="f9f8d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9f8d-115">See also</span></span>

- [<span data-ttu-id="f9f8d-116">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="f9f8d-116">XAML Resources</span></span>](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [<span data-ttu-id="f9f8d-117">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="f9f8d-117">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
