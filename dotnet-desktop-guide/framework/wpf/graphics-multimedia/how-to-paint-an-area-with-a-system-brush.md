---
title: 如何：使用系统画笔绘制区域
ms.date: 03/30/2017
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
ms.openlocfilehash: 26511c577bf06b016dfc69cedc7fce2bafb35f32
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972775"
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a><span data-ttu-id="0026f-102">如何：使用系统画笔绘制区域</span><span class="sxs-lookup"><span data-stu-id="0026f-102">How to: Paint an Area with a System Brush</span></span>
<span data-ttu-id="0026f-103"><xref:System.Windows.SystemColors>类提供对系统画笔和颜色（如、和）的访问 <xref:System.Windows.SystemColors.ControlBrush%2A> <xref:System.Windows.SystemColors.ControlBrushKey%2A> <xref:System.Windows.SystemColors.DesktopBrush%2A> 。</span><span class="sxs-lookup"><span data-stu-id="0026f-103">The <xref:System.Windows.SystemColors> class provides access to system brushes and colors, such as <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, and <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span></span> <span data-ttu-id="0026f-104">系统画笔是一个 <xref:System.Windows.Media.SolidColorBrush> 对象，它使用指定的系统颜色绘制区域。</span><span class="sxs-lookup"><span data-stu-id="0026f-104">A system brush is a <xref:System.Windows.Media.SolidColorBrush> object that paints an area with the specified system color.</span></span> <span data-ttu-id="0026f-105">系统画笔总是生成纯色填充，它不能用于创建渐变。</span><span class="sxs-lookup"><span data-stu-id="0026f-105">A system brush always produces a solid fill; it can't be used to create a gradient.</span></span>  
  
 <span data-ttu-id="0026f-106">可以将系统画笔用作静态资源，也可以用作动态资源。</span><span class="sxs-lookup"><span data-stu-id="0026f-106">You can use system brushes as either a static or a dynamic resource.</span></span> <span data-ttu-id="0026f-107">如果希望在应用程序运行期间画笔自动进行更新（当用户更改系统画笔时），请使用动态资源；否则请使用静态资源。</span><span class="sxs-lookup"><span data-stu-id="0026f-107">Use a dynamic resource if you want the brush to update automatically if the user changes the system brush as the application is running; otherwise, use a static resource.</span></span> <span data-ttu-id="0026f-108">SystemColors 类包含大量静态属性，这些属性严格遵循命名约定：</span><span class="sxs-lookup"><span data-stu-id="0026f-108">The SystemColors class contains a variety of static properties that follow a strict naming convention:</span></span>  
  
- <span data-ttu-id="0026f-109">*\<SystemColor>* 画笔</span><span class="sxs-lookup"><span data-stu-id="0026f-109">*\<SystemColor>* Brush</span></span>  
  
     <span data-ttu-id="0026f-110">获取对 <xref:System.Windows.Media.SolidColorBrush> 指定系统颜色的的静态引用。</span><span class="sxs-lookup"><span data-stu-id="0026f-110">Gets a static reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
- <span data-ttu-id="0026f-111">*\<SystemColor>* BrushKey</span><span class="sxs-lookup"><span data-stu-id="0026f-111">*\<SystemColor>* BrushKey</span></span>  
  
     <span data-ttu-id="0026f-112">获取对指定系统颜色的的动态引用 <xref:System.Windows.Media.SolidColorBrush> 。</span><span class="sxs-lookup"><span data-stu-id="0026f-112">Gets a dynamic reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
- <span data-ttu-id="0026f-113">*\<SystemColor>* 颜色</span><span class="sxs-lookup"><span data-stu-id="0026f-113">*\<SystemColor>* Color</span></span>  
  
     <span data-ttu-id="0026f-114">获取对 <xref:System.Windows.Media.Color> 指定系统颜色的结构的静态引用。</span><span class="sxs-lookup"><span data-stu-id="0026f-114">Gets a static reference to a <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
- <span data-ttu-id="0026f-115">*\<SystemColor>* ColorKey</span><span class="sxs-lookup"><span data-stu-id="0026f-115">*\<SystemColor>* ColorKey</span></span>  
  
     <span data-ttu-id="0026f-116">获取对 <xref:System.Windows.Media.Color> 指定系统颜色的结构的动态引用。</span><span class="sxs-lookup"><span data-stu-id="0026f-116">Gets a dynamic reference to the <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
 <span data-ttu-id="0026f-117">系统颜色是 <xref:System.Windows.Media.Color> 可用于配置画笔的结构。</span><span class="sxs-lookup"><span data-stu-id="0026f-117">A system color is a <xref:System.Windows.Media.Color> structure that can be used to configure a brush.</span></span> <span data-ttu-id="0026f-118">例如，您可以通过使用系统颜色设置 <xref:System.Windows.Media.GradientStop.Color%2A> <xref:System.Windows.Media.LinearGradientBrush> 对象的渐变停止点的属性来创建使用系统颜色的渐变。</span><span class="sxs-lookup"><span data-stu-id="0026f-118">For example, you can create a gradient using system colors by setting the <xref:System.Windows.Media.GradientStop.Color%2A> properties of a <xref:System.Windows.Media.LinearGradientBrush> object's gradient stops with system colors.</span></span> <span data-ttu-id="0026f-119">有关示例，请参阅 [在渐变中使用系统颜色](how-to-use-system-colors-in-a-gradient.md)。</span><span class="sxs-lookup"><span data-stu-id="0026f-119">For an example, see [Use System Colors in a Gradient](how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0026f-120">示例</span><span class="sxs-lookup"><span data-stu-id="0026f-120">Example</span></span>  
 <span data-ttu-id="0026f-121">以下示例使用动态系统画笔引用来设置按钮的背景。</span><span class="sxs-lookup"><span data-stu-id="0026f-121">The following example uses a dynamic system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 <span data-ttu-id="0026f-122">下一个示例使用静态系统画笔引用来设置按钮的背景。</span><span class="sxs-lookup"><span data-stu-id="0026f-122">The next example uses a static system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 <span data-ttu-id="0026f-123">有关演示如何在渐变中使用系统颜色的示例，请参阅 [在渐变中使用系统颜色](how-to-use-system-colors-in-a-gradient.md)。</span><span class="sxs-lookup"><span data-stu-id="0026f-123">For an example showing how to use a system color in a gradient, see [Use System Colors in a Gradient](how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0026f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0026f-124">See also</span></span>

- [<span data-ttu-id="0026f-125">在渐变中使用系统颜色</span><span class="sxs-lookup"><span data-stu-id="0026f-125">Use System Colors in a Gradient</span></span>](how-to-use-system-colors-in-a-gradient.md)
- [<span data-ttu-id="0026f-126">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="0026f-126">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
