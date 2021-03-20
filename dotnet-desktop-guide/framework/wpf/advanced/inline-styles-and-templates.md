---
title: 内联样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: bc28c25aa7acfa93ddd2b095762093ad9378744a
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665700"
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="7ec3a-102">内联样式和模板</span><span class="sxs-lookup"><span data-stu-id="7ec3a-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="7ec3a-103">提供 <xref:System.Windows.Style> (子类) 的对象和模板对象，以便在 <xref:System.Windows.FrameworkTemplate> 资源中定义元素的可视外观，使其可多次使用。</span><span class="sxs-lookup"><span data-stu-id="7ec3a-103">provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="7ec3a-104">出于此原因，中的特性 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 采用类型 <xref:System.Windows.Style> ， <xref:System.Windows.FrameworkTemplate> 几乎总是对现有样式和模板进行资源引用，而不是以内联方式定义新样式和模板。</span><span class="sxs-lookup"><span data-stu-id="7ec3a-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="7ec3a-105">内联样式和模板的限制</span><span class="sxs-lookup"><span data-stu-id="7ec3a-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="7ec3a-106">在中 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ，样式和模板属性在技术上可以通过以下两种方式之一进行设置。</span><span class="sxs-lookup"><span data-stu-id="7ec3a-106">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="7ec3a-107">您可以使用特性语法来引用资源中定义的样式，例如 `<` *对象* `Style="{StaticResource` *myResourceKey* `}" .../>` 。</span><span class="sxs-lookup"><span data-stu-id="7ec3a-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="7ec3a-108">或者，可以使用属性元素语法来定义内联样式，例如：</span><span class="sxs-lookup"><span data-stu-id="7ec3a-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 <span data-ttu-id="7ec3a-109">`<`*对象*`>`</span><span class="sxs-lookup"><span data-stu-id="7ec3a-109">`<` *object* `>`</span></span>  
  
 <span data-ttu-id="7ec3a-110">`<`*对象*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="7ec3a-110">`<` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="7ec3a-111">`<` `Style`  `.../>`</span><span class="sxs-lookup"><span data-stu-id="7ec3a-111">`<` `Style`  `.../>`</span></span>  
  
 <span data-ttu-id="7ec3a-112">`</`*对象*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="7ec3a-112">`</` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="7ec3a-113">`</`*对象*`>`</span><span class="sxs-lookup"><span data-stu-id="7ec3a-113">`</` *object* `>`</span></span>  
  
 <span data-ttu-id="7ec3a-114">特性用法更常见。</span><span class="sxs-lookup"><span data-stu-id="7ec3a-114">The attribute usage is much more common.</span></span> <span data-ttu-id="7ec3a-115">在资源中以内联方式定义且未在资源中定义的样式必须仅限于包含元素，因为它没有资源键，所以不能轻易地重新使用。</span><span class="sxs-lookup"><span data-stu-id="7ec3a-115">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="7ec3a-116">通常，资源定义的样式更通用并且有用，更多的是将 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 程序逻辑与代码中的程序逻辑分离在标记中的常规编程模型原则。</span><span class="sxs-lookup"><span data-stu-id="7ec3a-116">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="7ec3a-117">通常，即使只是要在该位置使用该样式或模板，也没有理由设置样式或模板。</span><span class="sxs-lookup"><span data-stu-id="7ec3a-117">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="7ec3a-118">大多数可以采用样式或模板的元素也支持 content 属性和内容模型。</span><span class="sxs-lookup"><span data-stu-id="7ec3a-118">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="7ec3a-119">如果只使用通过样式设置或模板化一次创建的任何逻辑树，只需在直接标记中使用等效的子元素填充该内容属性即可。</span><span class="sxs-lookup"><span data-stu-id="7ec3a-119">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="7ec3a-120">这会完全跳过样式和模板机制。</span><span class="sxs-lookup"><span data-stu-id="7ec3a-120">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="7ec3a-121">对于样式和模板，也可以通过返回对象的标记扩展启用其他语法。</span><span class="sxs-lookup"><span data-stu-id="7ec3a-121">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="7ec3a-122">可能的两种扩展插件都包含 [TemplateBinding](templatebinding-markup-extension.md) 和 <xref:System.Windows.Data.Binding> 。</span><span class="sxs-lookup"><span data-stu-id="7ec3a-122">Two such extensions that have possible scenarios include [TemplateBinding](templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec3a-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ec3a-123">See also</span></span>

- [<span data-ttu-id="7ec3a-124">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="7ec3a-124">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
