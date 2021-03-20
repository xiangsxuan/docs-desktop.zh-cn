---
title: 演练：创建自定义的动画按钮
ms.date: 03/30/2017
helpviewer_keywords:
- custom animated buttons [WPF]
- buttons [WPF]
- animation [WPF], buttons [WPF]
ms.assetid: e9532c72-460f-4898-9332-613fa21d746a
ms.openlocfilehash: 417faf36dfd3916c4bcbf6d52dea463e54987014
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667416"
---
# <a name="walkthroughs-create-a-custom-animated-button"></a><span data-ttu-id="cf91a-102">演练：创建自定义的动画按钮</span><span class="sxs-lookup"><span data-stu-id="cf91a-102">Walkthroughs: Create a Custom Animated Button</span></span>
<span data-ttu-id="cf91a-103">顾名思义，Windows Presentation Foundation (WPF) 非常适合为客户提供丰富的演示体验。</span><span class="sxs-lookup"><span data-stu-id="cf91a-103">As its name suggests, Windows Presentation Foundation (WPF) is great for making rich presentation experiences for customers.</span></span> <span data-ttu-id="cf91a-104">这些演练说明了如何自定义按钮的外观和行为 (包括动画) 。</span><span class="sxs-lookup"><span data-stu-id="cf91a-104">These walkthroughs show you how to customize the look and behavior of a button (including animations).</span></span> <span data-ttu-id="cf91a-105">此自定义通过使用样式和模板来完成，因此你可以轻松地将此自定义按钮应用于应用程序中的任何按钮。</span><span class="sxs-lookup"><span data-stu-id="cf91a-105">This customization is done using a style and template so that you can apply this custom button easily to any buttons in your application.</span></span> <span data-ttu-id="cf91a-106">下图显示了您将创建的自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="cf91a-106">The following illustration shows the customized button that you will create.</span></span>

 <span data-ttu-id="cf91a-107">![你将创建的自定义按钮](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span><span class="sxs-lookup"><span data-stu-id="cf91a-107">![The customized button that you will create](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")</span></span>

 <span data-ttu-id="cf91a-108">构成按钮外观的矢量图形是使用创建的 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="cf91a-108">The vector graphics that make up the appearance of the button are created by using [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="cf91a-109">类似于 HTML，但它更强大且可扩展。</span><span class="sxs-lookup"><span data-stu-id="cf91a-109">is similar to HTML except it is more powerful and extensible.</span></span> [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] <span data-ttu-id="cf91a-110">可以使用 Visual Studio 或记事本手动键入，也可以使用 Blend for Visual Studio 之类的可视化设计工具。</span><span class="sxs-lookup"><span data-stu-id="cf91a-110">can be typed in manually using Visual Studio or Notepad, or you can use a visual design tool such as Blend for Visual Studio.</span></span> <span data-ttu-id="cf91a-111">通过创建基础 XAML 代码来混合工作，因此这两种方法都创建相同的图形。</span><span class="sxs-lookup"><span data-stu-id="cf91a-111">Blend works by creating underlying XAML code, so both methods create the same graphics.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="cf91a-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="cf91a-112">In This Section</span></span>
 <span data-ttu-id="cf91a-113">[使用 Microsoft Expression Blend 创建按钮](walkthrough-create-a-button-by-using-microsoft-expression-blend.md) 演示如何使用 Expression Blend 的设计器功能创建具有自定义行为的按钮。</span><span class="sxs-lookup"><span data-stu-id="cf91a-113">[Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md) Demonstrates how to create buttons with custom behavior by using the designer features of Expression Blend.</span></span>

 <span data-ttu-id="cf91a-114">[使用 XAML 创建按钮](walkthrough-create-a-button-by-using-xaml.md) 演示如何使用和 Visual Studio 创建具有自定义行为的按钮 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="cf91a-114">[Create a Button by Using XAML](walkthrough-create-a-button-by-using-xaml.md) Demonstrates how to create buttons with custom behavior by using [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] and Visual Studio.</span></span>

## <a name="related-sections"></a><span data-ttu-id="cf91a-115">相关章节</span><span class="sxs-lookup"><span data-stu-id="cf91a-115">Related Sections</span></span>
 <span data-ttu-id="cf91a-116">[样式设置和模板化](/dotnet/desktop-wpf/fundamentals/styles-templates-overview) 介绍如何使用样式和模板来确定控件的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="cf91a-116">[Styling and Templating](/dotnet/desktop-wpf/fundamentals/styles-templates-overview) Describes how styles and templates can be used to determine the appearance and behavior of controls.</span></span>

 <span data-ttu-id="cf91a-117">[动画概述](../graphics-multimedia/animation-overview.md) 介绍如何使用 WPF 动画和计时系统对对象进行动画处理。</span><span class="sxs-lookup"><span data-stu-id="cf91a-117">[Animation Overview](../graphics-multimedia/animation-overview.md) Describes how objects can be animated by using the WPF animation and timing system.</span></span>

 <span data-ttu-id="cf91a-118">[用纯色和渐变进行绘制概述](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) 介绍如何使用画笔对象绘制纯色、线性渐变和径向梯度。</span><span class="sxs-lookup"><span data-stu-id="cf91a-118">[Painting with Solid Colors and Gradients Overview](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) Describes how to use brush objects to paint with solid colors, linear gradients, and radial gradients.</span></span>

 <span data-ttu-id="cf91a-119">[位图效果概述](../graphics-multimedia/bitmap-effects-overview.md) 描述 WPF 支持的位图效果，并说明如何应用它们。</span><span class="sxs-lookup"><span data-stu-id="cf91a-119">[Bitmap Effects Overview](../graphics-multimedia/bitmap-effects-overview.md) Describes the bitmap effects supported by WPF and explains how to apply them.</span></span>
