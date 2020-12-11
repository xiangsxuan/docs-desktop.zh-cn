---
title: 如何在样式中进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: 82a1406f180de26a48808f7a094a8addab29a042
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973831"
---
# <a name="how-to-animate-in-a-style"></a><span data-ttu-id="5c47d-102">如何在样式中进行动画处理</span><span class="sxs-lookup"><span data-stu-id="5c47d-102">How to animate in a style</span></span>

<span data-ttu-id="5c47d-103">此示例演示如何在样式中对属性进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="5c47d-103">This example shows how to animate properties within a style.</span></span> <span data-ttu-id="5c47d-104">在样式中进行动画处理时，只有定义了该样式的框架元素才能直接作为目标。</span><span class="sxs-lookup"><span data-stu-id="5c47d-104">When animating within a style, only the framework element for which the style is defined can be targeted directly.</span></span> <span data-ttu-id="5c47d-105">若要以可冻结的对象为目标，必须从带样式的元素的属性 "向下"。</span><span class="sxs-lookup"><span data-stu-id="5c47d-105">To target a freezable object, you must "dot down" from a property of the styled element.</span></span>

<span data-ttu-id="5c47d-106">在下面的示例中，多个动画是在样式中定义的，并应用于 <xref:System.Windows.Controls.Button> 。</span><span class="sxs-lookup"><span data-stu-id="5c47d-106">In the following example, several animations are defined within a style and applied to a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="5c47d-107">当用户将鼠标移动到该按钮上时，它会不断地从不透明过渡到部分半透明并再次后退。</span><span class="sxs-lookup"><span data-stu-id="5c47d-107">When the user moves the mouse over the button, it fades from opaque to partially translucent and back again, repeatedly.</span></span> <span data-ttu-id="5c47d-108">当用户将鼠标移出按钮时，它将完全不透明。</span><span class="sxs-lookup"><span data-stu-id="5c47d-108">When the user moves the mouse off the button, it becomes completely opaque.</span></span> <span data-ttu-id="5c47d-109">单击该按钮时，它的背景色将从橙色变为白色，并再次返回。</span><span class="sxs-lookup"><span data-stu-id="5c47d-109">When the button is clicked, its background color changes from orange to white and back again.</span></span> <span data-ttu-id="5c47d-110">由于 <xref:System.Windows.Media.SolidColorBrush> 不能直接将用于绘制按钮的用于绘制按钮，因此可通过对从按钮的属性进行访问 <xref:System.Windows.Controls.Control.Background%2A> 。</span><span class="sxs-lookup"><span data-stu-id="5c47d-110">Because the <xref:System.Windows.Media.SolidColorBrush> used to paint the button can't be targeted directly, it is accessed by dotting down from the button's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="5c47d-111">示例</span><span class="sxs-lookup"><span data-stu-id="5c47d-111">Example</span></span>

[!code-xaml[timingbehaviors_snip#21](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]

<span data-ttu-id="5c47d-112">请注意，在样式中进行动画处理时，可以将不存在的对象设定为目标。</span><span class="sxs-lookup"><span data-stu-id="5c47d-112">Note that when animating within a style, it's possible to target objects that don't exist.</span></span> <span data-ttu-id="5c47d-113">例如，假设您的样式使用 <xref:System.Windows.Media.SolidColorBrush> 来设置按钮的背景属性，但在某些时候将重写样式，并使用设置按钮的背景 <xref:System.Windows.Media.LinearGradientBrush> 。</span><span class="sxs-lookup"><span data-stu-id="5c47d-113">For example, suppose your style uses a <xref:System.Windows.Media.SolidColorBrush> to set a Button's background property, but at some point the style is overridden and the button's background is set with a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="5c47d-114">尝试对进行动画处理 <xref:System.Windows.Media.SolidColorBrush> 不会引发异常，动画将自动失败。</span><span class="sxs-lookup"><span data-stu-id="5c47d-114">Trying to animate the <xref:System.Windows.Media.SolidColorBrush> won't throw an exception; the animation will simply fail silently.</span></span>

<span data-ttu-id="5c47d-115">有关情节提要目标语法的详细信息，请参阅 [情节提要概述](storyboards-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5c47d-115">For more information about storyboard targeting syntax, see the [Storyboards Overview](storyboards-overview.md).</span></span> <span data-ttu-id="5c47d-116">有关动画的详细信息，请参阅 [动画概述](animation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5c47d-116">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="5c47d-117">有关样式的详细信息，请参阅 [样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)。</span><span class="sxs-lookup"><span data-stu-id="5c47d-117">For more information about styles, see the [Styling and Templating](/dotnet/desktop-wpf/fundamentals/styles-templates-overview).</span></span>
