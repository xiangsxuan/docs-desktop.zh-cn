---
title: 如何：使用 SystemParameters
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
ms.openlocfilehash: 1a198c9698a9cb2f56675bc953a4980cdecc3a0a
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665778"
---
# <a name="how-to-use-systemparameters"></a><span data-ttu-id="2d35c-102">如何：使用 SystemParameters</span><span class="sxs-lookup"><span data-stu-id="2d35c-102">How to: Use SystemParameters</span></span>
<span data-ttu-id="2d35c-103">此示例演示如何访问和使用的属性，以便 <xref:System.Windows.SystemParameters> 样式或自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="2d35c-103">This example shows how to access and use the properties of <xref:System.Windows.SystemParameters> in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d35c-104">示例</span><span class="sxs-lookup"><span data-stu-id="2d35c-104">Example</span></span>  
 <span data-ttu-id="2d35c-105">系统资源将多个基于系统的设置以资源的形式公开，以帮助创建与系统设置一致的视觉效果。</span><span class="sxs-lookup"><span data-stu-id="2d35c-105">System resources expose several system based settings as resources in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="2d35c-106"><xref:System.Windows.SystemParameters> 是包含系统参数值属性和绑定到值的资源键的类。</span><span class="sxs-lookup"><span data-stu-id="2d35c-106"><xref:System.Windows.SystemParameters> is a class that contains both system parameter value properties, and resource keys that bind to the values.</span></span> <span data-ttu-id="2d35c-107">例如， <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> 是 <xref:System.Windows.SystemParameters> 属性值， <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> 是对应的资源键。</span><span class="sxs-lookup"><span data-stu-id="2d35c-107">For example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> is a <xref:System.Windows.SystemParameters> property value and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> is the corresponding resource key.</span></span>  
  
 <span data-ttu-id="2d35c-108">在中 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ，你可以使用的成员 <xref:System.Windows.SystemParameters> 作为静态属性用法，或使用静态属性值 (作为键) 的动态资源引用。</span><span class="sxs-lookup"><span data-stu-id="2d35c-108">In [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemParameters> as either a static property usage, or a dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="2d35c-109">如果希望基于系统的值在应用程序运行时自动更新，请使用动态资源引用；否则，请使用静态引用。</span><span class="sxs-lookup"><span data-stu-id="2d35c-109">Use a dynamic resource reference if you want the system based value to update automatically while the application runs; otherwise, use a static reference.</span></span> <span data-ttu-id="2d35c-110">资源键将后缀 `Key` 追加到属性名称。</span><span class="sxs-lookup"><span data-stu-id="2d35c-110">Resource keys have the suffix `Key` appended to the property name.</span></span>  
  
 <span data-ttu-id="2d35c-111">下面的示例演示如何访问和使用的静态值 <xref:System.Windows.SystemParameters> 来样式或自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="2d35c-111">The following example shows how to access and use the static values of <xref:System.Windows.SystemParameters> to style or customize a button.</span></span> <span data-ttu-id="2d35c-112">此标记示例将值应用于按钮，从而调整按钮大小 <xref:System.Windows.SystemParameters> 。</span><span class="sxs-lookup"><span data-stu-id="2d35c-112">This markup example sizes a button by applying <xref:System.Windows.SystemParameters> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 <span data-ttu-id="2d35c-113">若要 <xref:System.Windows.SystemParameters> 在代码中使用的值，则不必使用静态引用或动态资源引用。</span><span class="sxs-lookup"><span data-stu-id="2d35c-113">To use the values of <xref:System.Windows.SystemParameters> in code, you do not have to use either static references or dynamic resource references.</span></span> <span data-ttu-id="2d35c-114">请改用类的值 <xref:System.Windows.SystemParameters> 。</span><span class="sxs-lookup"><span data-stu-id="2d35c-114">Instead, use the values of the <xref:System.Windows.SystemParameters> class.</span></span> <span data-ttu-id="2d35c-115">尽管非键属性已明确定义为静态属性，但是系统承载的的运行时行为 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 将会实时重新评估这些属性，并且会正确地考虑对系统值进行用户驱动的更改。</span><span class="sxs-lookup"><span data-stu-id="2d35c-115">Although the non-key properties are apparently defined as static properties, the runtime behavior of [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in realtime, and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="2d35c-116">下面的示例演示如何使用值设置按钮的宽度和高度 <xref:System.Windows.SystemParameters> 。</span><span class="sxs-lookup"><span data-stu-id="2d35c-116">The following example shows how to set the width and height of a button by using <xref:System.Windows.SystemParameters> values.</span></span>  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="2d35c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d35c-117">See also</span></span>

- <xref:System.Windows.SystemParameters>
- [<span data-ttu-id="2d35c-118">使用系统画笔绘制区域</span><span class="sxs-lookup"><span data-stu-id="2d35c-118">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="2d35c-119">使用 SystemFonts</span><span class="sxs-lookup"><span data-stu-id="2d35c-119">Use SystemFonts</span></span>](how-to-use-systemfonts.md)
- [<span data-ttu-id="2d35c-120">使用系统参数键</span><span class="sxs-lookup"><span data-stu-id="2d35c-120">Use System Parameters Keys</span></span>](how-to-use-system-parameters-keys.md)
- [<span data-ttu-id="2d35c-121">操作指南主题</span><span class="sxs-lookup"><span data-stu-id="2d35c-121">How-to Topics</span></span>](resources-how-to-topics.md)
