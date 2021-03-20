---
title: 如何：使用 SystemFonts
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: c81b37def3f1a7a95be2a855b773d00b502a37c1
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665765"
---
# <a name="how-to-use-systemfonts"></a><span data-ttu-id="e90d7-102">如何：使用 SystemFonts</span><span class="sxs-lookup"><span data-stu-id="e90d7-102">How to: Use SystemFonts</span></span>
<span data-ttu-id="e90d7-103">此示例演示如何使用类的静态资源 <xref:System.Windows.SystemFonts> 来样式或自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="e90d7-103">This example shows how to use the static resources of the <xref:System.Windows.SystemFonts> class in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e90d7-104">示例</span><span class="sxs-lookup"><span data-stu-id="e90d7-104">Example</span></span>  
 <span data-ttu-id="e90d7-105">系统资源将系统确定的许多值以资源和属性的形式公开，以帮助创建与系统设置一致的视觉效果。</span><span class="sxs-lookup"><span data-stu-id="e90d7-105">System resources expose several system-determined values as both resources and properties in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="e90d7-106"><xref:System.Windows.SystemFonts> 是一个类，其中包含作为静态属性的系统字体值和引用资源键的属性，这些属性可用于在运行时动态访问这些值。</span><span class="sxs-lookup"><span data-stu-id="e90d7-106"><xref:System.Windows.SystemFonts> is a class that contains both system font values as static properties, and properties that reference resource keys that can be used to access those values dynamically at run time.</span></span> <span data-ttu-id="e90d7-107">例如， <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> 是一个 <xref:System.Windows.SystemFonts> 值，并且 <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> 是对应的资源键。</span><span class="sxs-lookup"><span data-stu-id="e90d7-107">For example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> is a <xref:System.Windows.SystemFonts> value, and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> is a corresponding resource key.</span></span>  
  
 <span data-ttu-id="e90d7-108">在中 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，你可以将的成员 <xref:System.Windows.SystemFonts> 作为静态属性或动态资源引用 (，并将静态属性值用作键) 。</span><span class="sxs-lookup"><span data-stu-id="e90d7-108">In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemFonts> as either static properties or dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="e90d7-109">如果希望字体规格在应用程序运行时自动更新，请使用动态资源引用；否则，请使用静态值引用。</span><span class="sxs-lookup"><span data-stu-id="e90d7-109">Use a dynamic resource reference if you want the font metric to automatically update while the application runs; otherwise, use a static value reference.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e90d7-110">资源键属性名称后面附有“Key”后缀。</span><span class="sxs-lookup"><span data-stu-id="e90d7-110">The resource keys have the suffix "Key" appended to the property name.</span></span>  
  
 <span data-ttu-id="e90d7-111">下面的示例演示如何访问并将的属性 <xref:System.Windows.SystemFonts> 用作静态值，以便样式或自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="e90d7-111">The following example shows how to access and use the properties of <xref:System.Windows.SystemFonts> as static values in order to style or customize a button.</span></span> <span data-ttu-id="e90d7-112">此标记示例 <xref:System.Windows.SystemFonts> 为按钮赋值。</span><span class="sxs-lookup"><span data-stu-id="e90d7-112">This markup example assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 <span data-ttu-id="e90d7-113">若要 <xref:System.Windows.SystemFonts> 在代码中使用的值，则不必使用静态值或动态资源引用。</span><span class="sxs-lookup"><span data-stu-id="e90d7-113">To use the values of <xref:System.Windows.SystemFonts> in code, you do not have to use either a static value or a dynamic resource reference.</span></span> <span data-ttu-id="e90d7-114">请改用类的非键属性 <xref:System.Windows.SystemFonts> 。</span><span class="sxs-lookup"><span data-stu-id="e90d7-114">Instead, use the non-key properties of the <xref:System.Windows.SystemFonts> class.</span></span> <span data-ttu-id="e90d7-115">尽管非键属性已明确定义为静态属性，但是系统承载的的运行时行为 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 将会实时重新评估这些属性，并且将正确地考虑对系统值进行用户驱动的更改。</span><span class="sxs-lookup"><span data-stu-id="e90d7-115">Although the non-key properties are apparently defined as static properties, the run-time behavior of [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in real time and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="e90d7-116">以下示例演示如何指定按钮的字体设置。</span><span class="sxs-lookup"><span data-stu-id="e90d7-116">The following example shows how to specify the font settings of a button.</span></span>  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="e90d7-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e90d7-117">See also</span></span>

- <xref:System.Windows.SystemFonts>
- [<span data-ttu-id="e90d7-118">使用系统画笔绘制区域</span><span class="sxs-lookup"><span data-stu-id="e90d7-118">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="e90d7-119">使用 SystemParameters</span><span class="sxs-lookup"><span data-stu-id="e90d7-119">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
- [<span data-ttu-id="e90d7-120">使用系统字体键</span><span class="sxs-lookup"><span data-stu-id="e90d7-120">Use System Fonts Keys</span></span>](how-to-use-system-fonts-keys.md)
- [<span data-ttu-id="e90d7-121">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="e90d7-121">How-to Topics</span></span>](resources-how-to-topics.md)
- [<span data-ttu-id="e90d7-122">x:Static 标记扩展</span><span class="sxs-lookup"><span data-stu-id="e90d7-122">x:Static Markup Extension</span></span>](/dotnet/desktop-wpf/xaml-services/xstatic-markup-extension)
- [<span data-ttu-id="e90d7-123">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="e90d7-123">XAML Resources</span></span>](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [<span data-ttu-id="e90d7-124">DynamicResource 标记扩展</span><span class="sxs-lookup"><span data-stu-id="e90d7-124">DynamicResource Markup Extension</span></span>](dynamicresource-markup-extension.md)
