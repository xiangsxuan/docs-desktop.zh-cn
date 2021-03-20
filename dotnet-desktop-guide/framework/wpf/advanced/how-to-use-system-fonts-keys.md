---
title: 如何：使用系统字体键
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: 20df7037b439d798bdafa782811ebd46d76b4589
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665817"
---
# <a name="how-to-use-system-fonts-keys"></a><span data-ttu-id="5ed2f-102">如何：使用系统字体键</span><span class="sxs-lookup"><span data-stu-id="5ed2f-102">How to: Use System Fonts Keys</span></span>
<span data-ttu-id="5ed2f-103">系统资源将多个系统规格以资源的形式公开，以帮助开发人员创建与系统设置一致的视觉效果。</span><span class="sxs-lookup"><span data-stu-id="5ed2f-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="5ed2f-104"><xref:System.Windows.SystemFonts> 是包含系统字体值和绑定到值的系统字体资源（例如和）的类 <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5ed2f-104"><xref:System.Windows.SystemFonts> is a class that contains both system font values and system font resources that bind to the values—for example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span></span>  
  
 <span data-ttu-id="5ed2f-105">系统字体规格可用作静态或动态资源。</span><span class="sxs-lookup"><span data-stu-id="5ed2f-105">System font metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="5ed2f-106">如果希望字体规格在应用程序运行时自动更新，请使用动态资源；否则，请使用静态资源。</span><span class="sxs-lookup"><span data-stu-id="5ed2f-106">Use a dynamic resource if you want the font metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5ed2f-107">动态资源将关键字关键字 *追加到* 属性名称上。</span><span class="sxs-lookup"><span data-stu-id="5ed2f-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="5ed2f-108">以下示例演示如何访问和使用系统字体动态资源来设计按钮样式或自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="5ed2f-108">The following example shows how to access and use system font dynamic resources to style or customize a button.</span></span> <span data-ttu-id="5ed2f-109">此 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 示例创建一个按钮样式，该样式 <xref:System.Windows.SystemFonts> 为按钮赋值。</span><span class="sxs-lookup"><span data-stu-id="5ed2f-109">This [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] example creates a button style that assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ed2f-110">示例</span><span class="sxs-lookup"><span data-stu-id="5ed2f-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#FontDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="5ed2f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ed2f-111">See also</span></span>

- [<span data-ttu-id="5ed2f-112">使用系统画笔绘制区域</span><span class="sxs-lookup"><span data-stu-id="5ed2f-112">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="5ed2f-113">使用 SystemParameters</span><span class="sxs-lookup"><span data-stu-id="5ed2f-113">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
- [<span data-ttu-id="5ed2f-114">使用 SystemFonts</span><span class="sxs-lookup"><span data-stu-id="5ed2f-114">Use SystemFonts</span></span>](how-to-use-systemfonts.md)
