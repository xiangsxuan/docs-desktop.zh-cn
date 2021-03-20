---
title: 优化应用程序性能
description: 使用这些资源提高 Windows Presentation Foundation 应用程序的性能，例如规划性能和充分利用硬件。
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 8e040825867a0c7fc27f030cfd07c6582f65b432
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665271"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="95382-103">优化 WPF 应用程序性能</span><span class="sxs-lookup"><span data-stu-id="95382-103">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="95382-104">本部分旨在作为 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 正在寻找提高应用程序性能的方法的应用程序开发人员的参考。</span><span class="sxs-lookup"><span data-stu-id="95382-104">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="95382-105">如果你是 Microsoft .NET 框架的新手的开发人员 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，则应首先熟悉这两个平台。</span><span class="sxs-lookup"><span data-stu-id="95382-105">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="95382-106">本部分假设同时了解这两种情况，并为已知道足以启动并运行应用程序的程序员编写这些内容。</span><span class="sxs-lookup"><span data-stu-id="95382-106">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95382-107">本部分中提供的性能数据基于 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 2.8 GHZ 电脑上运行的应用程序，其中包含 512 RAM 和 ATI Radeon 9700 图形卡。</span><span class="sxs-lookup"><span data-stu-id="95382-107">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95382-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="95382-108">In This Section</span></span>  
 [<span data-ttu-id="95382-109">规划应用程序性能</span><span class="sxs-lookup"><span data-stu-id="95382-109">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="95382-110">利用硬件</span><span class="sxs-lookup"><span data-stu-id="95382-110">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="95382-111">布局和示例</span><span class="sxs-lookup"><span data-stu-id="95382-111">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="95382-112">二维图形和图像处理</span><span class="sxs-lookup"><span data-stu-id="95382-112">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="95382-113">对象行为</span><span class="sxs-lookup"><span data-stu-id="95382-113">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="95382-114">应用程序资源</span><span class="sxs-lookup"><span data-stu-id="95382-114">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="95382-115">文本</span><span class="sxs-lookup"><span data-stu-id="95382-115">Text</span></span>](optimizing-performance-text.md)  
  
 [<span data-ttu-id="95382-116">数据绑定</span><span class="sxs-lookup"><span data-stu-id="95382-116">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="95382-117">控件</span><span class="sxs-lookup"><span data-stu-id="95382-117">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="95382-118">其他性能建议</span><span class="sxs-lookup"><span data-stu-id="95382-118">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="95382-119">应用程序启动时间</span><span class="sxs-lookup"><span data-stu-id="95382-119">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="95382-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="95382-120">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="95382-121">图形呈现层</span><span class="sxs-lookup"><span data-stu-id="95382-121">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="95382-122">WPF 图形呈现疑难解答</span><span class="sxs-lookup"><span data-stu-id="95382-122">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="95382-123">布局</span><span class="sxs-lookup"><span data-stu-id="95382-123">Layout</span></span>](layout.md)
- [<span data-ttu-id="95382-124">WPF 中的树</span><span class="sxs-lookup"><span data-stu-id="95382-124">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="95382-125">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="95382-125">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="95382-126">使用 DrawingVisual 对象</span><span class="sxs-lookup"><span data-stu-id="95382-126">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="95382-127">依赖项属性概述</span><span class="sxs-lookup"><span data-stu-id="95382-127">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="95382-128">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="95382-128">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="95382-129">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="95382-129">XAML Resources</span></span>](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [<span data-ttu-id="95382-130">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="95382-130">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="95382-131">绘制格式化文本</span><span class="sxs-lookup"><span data-stu-id="95382-131">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="95382-132">WPF 中的版式</span><span class="sxs-lookup"><span data-stu-id="95382-132">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="95382-133">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="95382-133">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="95382-134">导航概述</span><span class="sxs-lookup"><span data-stu-id="95382-134">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="95382-135">动画提示和技巧</span><span class="sxs-lookup"><span data-stu-id="95382-135">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="95382-136">演练：在 WPF 应用程序中缓存应用程序数据</span><span class="sxs-lookup"><span data-stu-id="95382-136">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
