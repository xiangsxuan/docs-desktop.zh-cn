---
title: 如何：使用系统参数键
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: dda2d174421818005bcc3d4493f08918cb49b9e1
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665804"
---
# <a name="how-to-use-system-parameters-keys"></a><span data-ttu-id="e608b-102">如何：使用系统参数键</span><span class="sxs-lookup"><span data-stu-id="e608b-102">How to: Use System Parameters Keys</span></span>
<span data-ttu-id="e608b-103">系统资源将多个系统规格以资源的形式公开，以帮助开发人员创建与系统设置一致的视觉效果。</span><span class="sxs-lookup"><span data-stu-id="e608b-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="e608b-104"><xref:System.Windows.SystemParameters> 是包含系统参数值和绑定到值的资源键（例如和）的类 <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> 。</span><span class="sxs-lookup"><span data-stu-id="e608b-104"><xref:System.Windows.SystemParameters> is a class that contains both system parameter values and resource keys that bind to the values—for example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.</span></span> <span data-ttu-id="e608b-105">系统参数规格可用作静态或动态资源。</span><span class="sxs-lookup"><span data-stu-id="e608b-105">System parameter metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="e608b-106">如果希望参数规格在应用程序运行时自动更新，请使用动态资源；否则，请使用静态资源。</span><span class="sxs-lookup"><span data-stu-id="e608b-106">Use a dynamic resource if you want the parameter metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e608b-107">动态资源将关键字关键字 *追加到* 属性名称上。</span><span class="sxs-lookup"><span data-stu-id="e608b-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="e608b-108">以下示例演示如何访问和使用系统参数动态资源来设计按钮样式或自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="e608b-108">The following example shows how to access and use system parameter dynamic resources to style or customize a button.</span></span> <span data-ttu-id="e608b-109">此 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 示例通过将 <xref:System.Windows.SystemParameters> 值分配给按钮的宽度和高度来调整按钮的大小。</span><span class="sxs-lookup"><span data-stu-id="e608b-109">This [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] example sizes a button by assigning <xref:System.Windows.SystemParameters> values to the button's width and height.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e608b-110">示例</span><span class="sxs-lookup"><span data-stu-id="e608b-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="e608b-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="e608b-111">See also</span></span>

- [<span data-ttu-id="e608b-112">使用系统画笔绘制区域</span><span class="sxs-lookup"><span data-stu-id="e608b-112">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="e608b-113">使用 SystemFonts</span><span class="sxs-lookup"><span data-stu-id="e608b-113">Use SystemFonts</span></span>](how-to-use-systemfonts.md)
- [<span data-ttu-id="e608b-114">使用 SystemParameters</span><span class="sxs-lookup"><span data-stu-id="e608b-114">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
