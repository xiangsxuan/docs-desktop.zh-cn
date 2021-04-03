---
title: 如何：在渐变中使用系统颜色
ms.date: 03/30/2017
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
ms.openlocfilehash: 55c99640907a0c372f8c7bbc50b9b45c9f15ef3c
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96972827"
---
# <a name="how-to-use-system-colors-in-a-gradient"></a><span data-ttu-id="e5b9a-102">如何：在渐变中使用系统颜色</span><span class="sxs-lookup"><span data-stu-id="e5b9a-102">How to: Use System Colors in a Gradient</span></span>
<span data-ttu-id="e5b9a-103">若要在渐变中使用系统颜色，可以使用 *\<SystemColor>* 类的 color 和 *\<SystemColor>* ColorKey 静态属性 <xref:System.Windows.SystemColors> 来获取对颜色的引用，其中 *\<SystemColor>* 是所需系统颜色的名称。</span><span class="sxs-lookup"><span data-stu-id="e5b9a-103">To use a system color in a gradient, you use the *\<SystemColor>* Color and *\<SystemColor>* ColorKey static properties of the <xref:System.Windows.SystemColors> class to obtain a reference to the color, where *\<SystemColor>* is the name of the desired system color.</span></span> <span data-ttu-id="e5b9a-104">*\<SystemColor>* 如果要创建在系统主题发生更改时自动更新的动态引用，请使用 ColorKey 属性。</span><span class="sxs-lookup"><span data-stu-id="e5b9a-104">Use the *\<SystemColor>* ColorKey properties when you want to create a dynamic reference that updates automatically as the system theme changes.</span></span> <span data-ttu-id="e5b9a-105">否则，请使用 *\<SystemColor>* 颜色属性。</span><span class="sxs-lookup"><span data-stu-id="e5b9a-105">Otherwise, use the *\<SystemColor>* Color properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5b9a-106">示例</span><span class="sxs-lookup"><span data-stu-id="e5b9a-106">Example</span></span>  
 <span data-ttu-id="e5b9a-107">以下示例使用动态系统颜色资源创建渐变。</span><span class="sxs-lookup"><span data-stu-id="e5b9a-107">The following example uses dynamic system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 <span data-ttu-id="e5b9a-108">下一个示例使用静态系统颜色资源创建渐变。</span><span class="sxs-lookup"><span data-stu-id="e5b9a-108">The next example uses static system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e5b9a-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5b9a-109">See also</span></span>

- <xref:System.Windows.SystemColors>
- [<span data-ttu-id="e5b9a-110">使用系统画笔绘制区域</span><span class="sxs-lookup"><span data-stu-id="e5b9a-110">Paint an Area with a System Brush</span></span>](how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="e5b9a-111">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="e5b9a-111">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
