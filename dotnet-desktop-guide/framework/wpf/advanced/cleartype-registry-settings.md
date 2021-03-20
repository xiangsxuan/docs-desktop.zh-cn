---
title: ClearType 注册表设置
ms.date: 03/30/2017
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
ms.openlocfilehash: 193a61a498c695afaf9c734ce39b9c177e06de4f
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666183"
---
# <a name="cleartype-registry-settings"></a><span data-ttu-id="c0acd-102">ClearType 注册表设置</span><span class="sxs-lookup"><span data-stu-id="c0acd-102">ClearType Registry Settings</span></span>
<span data-ttu-id="c0acd-103">本主题概述了 WPF 应用程序使用的 Microsoft ClearType 注册表设置。</span><span class="sxs-lookup"><span data-stu-id="c0acd-103">This topic provides an overview of the Microsoft ClearType registry settings that are used by WPF applications.</span></span>  

<a name="overview"></a>
## <a name="technology-overview"></a><span data-ttu-id="c0acd-104">技术概述</span><span class="sxs-lookup"><span data-stu-id="c0acd-104">Technology Overview</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="c0acd-105">向显示设备呈现文本的应用程序使用 ClearType 功能提供增强的阅读体验。</span><span class="sxs-lookup"><span data-stu-id="c0acd-105">applications that render text to a display device use ClearType features to provide an enhanced reading experience.</span></span> <span data-ttu-id="c0acd-106">ClearType 是由 Microsoft 开发的一种软件技术，可提高现有 Lcd 上的文本可读性 (Crystal 显示屏) ，如笔记本电脑屏幕、Pocket PC 屏幕和平板显示器。</span><span class="sxs-lookup"><span data-stu-id="c0acd-106">ClearType is a software technology developed by Microsoft that improves the readability of text on existing LCDs (Liquid Crystal Displays), such as laptop screens, Pocket PC screens and flat panel monitors.</span></span> <span data-ttu-id="c0acd-107">ClearType 通过访问 LCD 屏幕的每个像素中的各个垂直色带元素来工作。</span><span class="sxs-lookup"><span data-stu-id="c0acd-107">ClearType works by accessing the individual vertical color stripe elements in every pixel of an LCD screen.</span></span> <span data-ttu-id="c0acd-108">有关 ClearType 的详细信息，请参阅 [Cleartype 概述](cleartype-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c0acd-108">For more information on ClearType, see [ClearType Overview](cleartype-overview.md).</span></span>  
  
 <span data-ttu-id="c0acd-109">当在各种显示设备上查看时，用 ClearType 呈现的文本可能出现明显不同。</span><span class="sxs-lookup"><span data-stu-id="c0acd-109">Text that is rendered with ClearType can appear significantly different when viewed on various display devices.</span></span> <span data-ttu-id="c0acd-110">例如，少量监视器以蓝色、绿色、红色顺序而不是更常见的红色、绿色、蓝色 (RGB) 顺序来实现色带元素。</span><span class="sxs-lookup"><span data-stu-id="c0acd-110">For example, a small number of monitors implement the color stripe elements in blue, green, red order rather than the more common red, green, blue (RGB) order.</span></span>  
  
 <span data-ttu-id="c0acd-111">使用 ClearType 呈现的文本在由具有不同级别的颜色敏感度的个人观看时，还会显得大不相同。</span><span class="sxs-lookup"><span data-stu-id="c0acd-111">Text that is rendered with ClearType can also appear significantly different when viewed by individuals with varying levels of color sensitivity.</span></span> <span data-ttu-id="c0acd-112">某些人能够比别人更擅长发觉颜色的微小差异。</span><span class="sxs-lookup"><span data-stu-id="c0acd-112">Some individuals can detect slight differences in color better than others.</span></span>  
  
 <span data-ttu-id="c0acd-113">在上述每种情况下，都需要修改 ClearType 功能，以便为每个人提供最佳阅读体验。</span><span class="sxs-lookup"><span data-stu-id="c0acd-113">In each of these cases, ClearType features need to be modified in order to provide the best reading experience for each individual.</span></span>  
  
<a name="registry_settings"></a>
## <a name="registry-settings"></a><span data-ttu-id="c0acd-114">注册表设置</span><span class="sxs-lookup"><span data-stu-id="c0acd-114">Registry Settings</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="c0acd-115">指定用于控制 ClearType 功能的四个注册表设置：</span><span class="sxs-lookup"><span data-stu-id="c0acd-115">specifies four registry settings for controlling ClearType features:</span></span>  
  
|<span data-ttu-id="c0acd-116">设置</span><span class="sxs-lookup"><span data-stu-id="c0acd-116">Setting</span></span>|<span data-ttu-id="c0acd-117">说明</span><span class="sxs-lookup"><span data-stu-id="c0acd-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c0acd-118">ClearType 级别</span><span class="sxs-lookup"><span data-stu-id="c0acd-118">ClearType level</span></span>|<span data-ttu-id="c0acd-119">描述 ClearType 颜色清晰度的级别。</span><span class="sxs-lookup"><span data-stu-id="c0acd-119">Describes the level of ClearType color clarity.</span></span>|  
|<span data-ttu-id="c0acd-120">伽马级别</span><span class="sxs-lookup"><span data-stu-id="c0acd-120">Gamma level</span></span>|<span data-ttu-id="c0acd-121">描述显示设备的像素颜色组件的级别。</span><span class="sxs-lookup"><span data-stu-id="c0acd-121">Describes the level of the pixel color component for a display device.</span></span>|  
|<span data-ttu-id="c0acd-122">像素结构</span><span class="sxs-lookup"><span data-stu-id="c0acd-122">Pixel structure</span></span>|<span data-ttu-id="c0acd-123">描述显示设备的像素排列。</span><span class="sxs-lookup"><span data-stu-id="c0acd-123">Describes the arrangement of pixels for a display device.</span></span>|  
|<span data-ttu-id="c0acd-124">文本对比度级别</span><span class="sxs-lookup"><span data-stu-id="c0acd-124">Text contrast level</span></span>|<span data-ttu-id="c0acd-125">描述显示文本的对比度级别。</span><span class="sxs-lookup"><span data-stu-id="c0acd-125">Describes the level of contrast for displayed text.</span></span>|  
  
 <span data-ttu-id="c0acd-126">这些设置可由知道如何引用已识别 ClearType 注册表设置的外部配置实用程序来访问 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="c0acd-126">These settings can be accessed by an external configuration utility that knows how to reference the identified [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ClearType registry settings.</span></span> <span data-ttu-id="c0acd-127">还可以通过使用 Windows 注册表编辑器直接访问这些值来创建或修改这些设置。</span><span class="sxs-lookup"><span data-stu-id="c0acd-127">These settings can also be created or modified by accessing the values directly by using the Windows Registry Editor.</span></span>  
  
 <span data-ttu-id="c0acd-128">如果 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ClearType 注册表设置未设置 (这是默认状态) ，则该 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序将查询 Windows 系统参数信息以实现字体平滑设置。</span><span class="sxs-lookup"><span data-stu-id="c0acd-128">If the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ClearType registry settings are not set (which is the default state), the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] application queries the Windows system parameters information for font smoothing settings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c0acd-129">有关枚举显示设备名称的信息，请参阅 `SystemParametersInfo` Win32 函数。</span><span class="sxs-lookup"><span data-stu-id="c0acd-129">For information on enumerating display device names, see the `SystemParametersInfo`Win32 function.</span></span>  
  
<a name="ClearType_level"></a>
## <a name="cleartype-level"></a><span data-ttu-id="c0acd-130">ClearType 级别</span><span class="sxs-lookup"><span data-stu-id="c0acd-130">ClearType Level</span></span>  
 <span data-ttu-id="c0acd-131">ClearType 级别允许你根据颜色敏感度和个人认知度调整文本的呈现。</span><span class="sxs-lookup"><span data-stu-id="c0acd-131">The ClearType level allows you to adjust the rendering of text based on the color sensitivity and perception of an individual.</span></span> <span data-ttu-id="c0acd-132">对于某些人而言，在其最高级别使用 ClearType 的文本呈现不会产生最佳阅读体验。</span><span class="sxs-lookup"><span data-stu-id="c0acd-132">For some individuals, the rendering of text that uses ClearType at its highest level does not produce the best reading experience.</span></span>  
  
 <span data-ttu-id="c0acd-133">ClearType 级别为介于0到100之间的整数值。</span><span class="sxs-lookup"><span data-stu-id="c0acd-133">The ClearType level is an integer value that ranges from 0 to 100.</span></span> <span data-ttu-id="c0acd-134">默认级别为100，这意味着 ClearType 使用显示设备的色带元素的最大容量。</span><span class="sxs-lookup"><span data-stu-id="c0acd-134">The default level is 100, which means ClearType uses the maximum capability of the color stripe elements of the display device.</span></span> <span data-ttu-id="c0acd-135">但 ClearType 级别0将文本呈现为灰色刻度。</span><span class="sxs-lookup"><span data-stu-id="c0acd-135">However, a ClearType level of 0 renders text as gray scale.</span></span> <span data-ttu-id="c0acd-136">通过将 ClearType 级别设置为介于0到100之间的某个位置，可以创建适合个人颜色敏感度的中间级别。</span><span class="sxs-lookup"><span data-stu-id="c0acd-136">By setting the ClearType level somewhere between 0 and 100, you can create an intermediate level that is suitable to an individual's color sensitivity.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="c0acd-137">注册表设置</span><span class="sxs-lookup"><span data-stu-id="c0acd-137">Registry Setting</span></span>  
 <span data-ttu-id="c0acd-138">ClearType 级别的注册表设置位置是对应于特定显示设备名称的单个用户设置：</span><span class="sxs-lookup"><span data-stu-id="c0acd-138">The registry setting location for the ClearType level is an individual user setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="c0acd-139">对于用户的每个显示设备名称， `ClearTypeLevel` 会定义一个 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="c0acd-139">For each display device name for a user, a `ClearTypeLevel` DWORD value is defined.</span></span> <span data-ttu-id="c0acd-140">以下屏幕截图显示 ClearType 级别的注册表编辑器设置。</span><span class="sxs-lookup"><span data-stu-id="c0acd-140">The following screenshot shows the Registry Editor setting for the ClearType level.</span></span>  
  
 ![注册表编辑器中的 ClearType 设置。](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="c0acd-142">应用程序以两种模式之一呈现文本，但不带 ClearType。</span><span class="sxs-lookup"><span data-stu-id="c0acd-142">applications render text in one of either two modes, with and without ClearType.</span></span> <span data-ttu-id="c0acd-143">如果呈现的文本没有 ClearType，则称为灰度呈现。</span><span class="sxs-lookup"><span data-stu-id="c0acd-143">When text is rendered without ClearType, it is referred to as gray scale rendering.</span></span>  
  
<a name="gamma_level"></a>
## <a name="gamma-level"></a><span data-ttu-id="c0acd-144">伽马级别</span><span class="sxs-lookup"><span data-stu-id="c0acd-144">Gamma Level</span></span>  
 <span data-ttu-id="c0acd-145">伽玛级别指的是像素值和亮度之间的非线性关系。</span><span class="sxs-lookup"><span data-stu-id="c0acd-145">The gamma level refers to the nonlinear relationship between a pixel value and luminance.</span></span> <span data-ttu-id="c0acd-146">伽玛级别设置应对应于显示设备的物理特性；否则呈现的输出中可能会出现失真。</span><span class="sxs-lookup"><span data-stu-id="c0acd-146">The gamma level setting should correspond to the physical characteristics of the display device; otherwise, distortions in rendered output may occur.</span></span> <span data-ttu-id="c0acd-147">例如，文本显示的宽度可能太大或太窄，或者标志符号的垂直词干边缘上可能出现颜色条纹。</span><span class="sxs-lookup"><span data-stu-id="c0acd-147">For example, text may appear too wide or too narrow, or color fringes may appear on the edges of vertical stems of glyphs.</span></span>  
  
 <span data-ttu-id="c0acd-148">伽马级别是一个介于 1000 到 2200 之间的整数值。</span><span class="sxs-lookup"><span data-stu-id="c0acd-148">The gamma level is an integer value that ranges from 1000 to 2200.</span></span> <span data-ttu-id="c0acd-149">默认级别为 1900。</span><span class="sxs-lookup"><span data-stu-id="c0acd-149">The default level is 1900.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="c0acd-150">注册表设置</span><span class="sxs-lookup"><span data-stu-id="c0acd-150">Registry Setting</span></span>  
 <span data-ttu-id="c0acd-151">伽马级别的注册表设置位置是对应于特定显示设备名称的本地计算机设置：</span><span class="sxs-lookup"><span data-stu-id="c0acd-151">The registry setting location for the gamma level is a local machine setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="c0acd-152">对于用户的每个显示设备名称， `GammaLevel` 会定义一个 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="c0acd-152">For each display device name for a user, a `GammaLevel` DWORD value is defined.</span></span> <span data-ttu-id="c0acd-153">以下屏幕快照显示了伽马级别的注册表编辑器设置。</span><span class="sxs-lookup"><span data-stu-id="c0acd-153">The following screenshot shows the Registry Editor setting for the gamma level.</span></span>  
  
 ![注册表编辑器中的 ClearType 伽玛级别设置](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>
## <a name="pixel-structure"></a><span data-ttu-id="c0acd-155">像素结构</span><span class="sxs-lookup"><span data-stu-id="c0acd-155">Pixel Structure</span></span>  
 <span data-ttu-id="c0acd-156">像素结构描述构成显示设备的像素的类型。</span><span class="sxs-lookup"><span data-stu-id="c0acd-156">The pixel structure describes the type of pixels that make up a display device.</span></span> <span data-ttu-id="c0acd-157">像素结构定义为三种类型之一：</span><span class="sxs-lookup"><span data-stu-id="c0acd-157">The pixel structure is defined as one of three types:</span></span>  
  
|<span data-ttu-id="c0acd-158">类型</span><span class="sxs-lookup"><span data-stu-id="c0acd-158">Type</span></span>|<span data-ttu-id="c0acd-159">值</span><span class="sxs-lookup"><span data-stu-id="c0acd-159">Value</span></span>|<span data-ttu-id="c0acd-160">说明</span><span class="sxs-lookup"><span data-stu-id="c0acd-160">Description</span></span>|  
|----------|-----------|-----------------|  
|<span data-ttu-id="c0acd-161">平面</span><span class="sxs-lookup"><span data-stu-id="c0acd-161">Flat</span></span>|<span data-ttu-id="c0acd-162">0</span><span class="sxs-lookup"><span data-stu-id="c0acd-162">0</span></span>|<span data-ttu-id="c0acd-163">显示设备没有像素结构。</span><span class="sxs-lookup"><span data-stu-id="c0acd-163">The display device has no pixel structure.</span></span> <span data-ttu-id="c0acd-164">这意味着每种颜色的光源均匀分布在像素区域上，称为灰度呈现。</span><span class="sxs-lookup"><span data-stu-id="c0acd-164">This means that light sources for each color are spread equally on the pixel area—this is referred to as gray scale rendering.</span></span> <span data-ttu-id="c0acd-165">这是标准显示设备的工作方式。</span><span class="sxs-lookup"><span data-stu-id="c0acd-165">This is how a standard display device works.</span></span> <span data-ttu-id="c0acd-166">ClearType 从不应用于呈现的文本。</span><span class="sxs-lookup"><span data-stu-id="c0acd-166">ClearType is never applied to the rendered text.</span></span>|  
|<span data-ttu-id="c0acd-167">RGB</span><span class="sxs-lookup"><span data-stu-id="c0acd-167">RGB</span></span>|<span data-ttu-id="c0acd-168">1</span><span class="sxs-lookup"><span data-stu-id="c0acd-168">1</span></span>|<span data-ttu-id="c0acd-169">显示设备的像素由三种色条按以下顺序构成：红色、绿色和蓝色。</span><span class="sxs-lookup"><span data-stu-id="c0acd-169">The display device has pixels that consist of three stripes in the following order: red, green, and blue.</span></span> <span data-ttu-id="c0acd-170">ClearType 应用于呈现的文本。</span><span class="sxs-lookup"><span data-stu-id="c0acd-170">ClearType is applied to the rendered text.</span></span>|  
|<span data-ttu-id="c0acd-171">BGR</span><span class="sxs-lookup"><span data-stu-id="c0acd-171">BGR</span></span>|<span data-ttu-id="c0acd-172">2</span><span class="sxs-lookup"><span data-stu-id="c0acd-172">2</span></span>|<span data-ttu-id="c0acd-173">显示设备的像素由三种色条按以下顺序构成：蓝色、绿色和红色。</span><span class="sxs-lookup"><span data-stu-id="c0acd-173">The display device has pixels that consist of three stripes in the following order: blue, green, and red.</span></span> <span data-ttu-id="c0acd-174">ClearType 应用于呈现的文本。</span><span class="sxs-lookup"><span data-stu-id="c0acd-174">ClearType is applied to the rendered text.</span></span> <span data-ttu-id="c0acd-175">注意该顺序与 RGB 类型相反。</span><span class="sxs-lookup"><span data-stu-id="c0acd-175">Notice how the order is inverted from the RGB type.</span></span>|  
  
 <span data-ttu-id="c0acd-176">像素结构对应于 0 到 2 之间的一个整数值。</span><span class="sxs-lookup"><span data-stu-id="c0acd-176">The pixel structure corresponds to an integer value that ranges from 0 to 2.</span></span> <span data-ttu-id="c0acd-177">默认级别为 0，表示平面像素结构。</span><span class="sxs-lookup"><span data-stu-id="c0acd-177">The default level is 0, which represents a flat pixel structure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c0acd-178">有关枚举显示设备名称的信息，请参阅 `EnumDisplayDevices` Win32 函数。</span><span class="sxs-lookup"><span data-stu-id="c0acd-178">For information on enumerating display device names, see the `EnumDisplayDevices`Win32 function.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="c0acd-179">注册表设置</span><span class="sxs-lookup"><span data-stu-id="c0acd-179">Registry Setting</span></span>  
 <span data-ttu-id="c0acd-180">像素结构的注册表设置位置是对应于特定显示设备名称的本地计算机设置：</span><span class="sxs-lookup"><span data-stu-id="c0acd-180">The registry setting location for the pixel structure is a local machine setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="c0acd-181">对于用户的每个显示设备名称， `PixelStructure` 会定义一个 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="c0acd-181">For each display device name for a user, a `PixelStructure` DWORD value is defined.</span></span> <span data-ttu-id="c0acd-182">以下屏幕快照显示了像素结构的注册表编辑器设置。</span><span class="sxs-lookup"><span data-stu-id="c0acd-182">The following screenshot shows the Registry Editor setting for the pixel structure.</span></span>  
  
 ![注册表编辑器中的 ClearType 伽玛级别设置](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>
## <a name="text-contrast-level"></a><span data-ttu-id="c0acd-184">文本对比度级别</span><span class="sxs-lookup"><span data-stu-id="c0acd-184">Text Contrast Level</span></span>  
 <span data-ttu-id="c0acd-185">通过文本对比度级别可以根据字形的主体宽度来调整文本的呈现。</span><span class="sxs-lookup"><span data-stu-id="c0acd-185">The text contrast level allows you to adjust the rendering of text based on the stem widths of glyphs.</span></span> <span data-ttu-id="c0acd-186">文本对比度级别是一个 0 到 6 之间的整数值 - 整数值越大，主体就越宽。</span><span class="sxs-lookup"><span data-stu-id="c0acd-186">The text contrast level is an integer value that ranges from 0 to 6—the larger the integer value, the wider the stem.</span></span> <span data-ttu-id="c0acd-187">默认级别为 1。</span><span class="sxs-lookup"><span data-stu-id="c0acd-187">The default level is 1.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="c0acd-188">注册表设置</span><span class="sxs-lookup"><span data-stu-id="c0acd-188">Registry Setting</span></span>  
 <span data-ttu-id="c0acd-189">文本对比度级别的注册表设置位置是对应于特定显示设备名称的单个用户设置：</span><span class="sxs-lookup"><span data-stu-id="c0acd-189">The registry setting location for the text contrast level is an individual user setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="c0acd-190">对于用户的每个显示设备名称， `TextContrastLevel` 会定义一个 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="c0acd-190">For each display device name for a user, a `TextContrastLevel` DWORD value is defined.</span></span> <span data-ttu-id="c0acd-191">以下屏幕快照显示了文本对比度级别的注册表编辑器设置。</span><span class="sxs-lookup"><span data-stu-id="c0acd-191">The following screenshot shows the Registry Editor setting for the text contrast level.</span></span>  
  
 ![注册表编辑器中的 ClearType 设置。](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a><span data-ttu-id="c0acd-193">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0acd-193">See also</span></span>

- [<span data-ttu-id="c0acd-194">ClearType 概述</span><span class="sxs-lookup"><span data-stu-id="c0acd-194">ClearType Overview</span></span>](cleartype-overview.md)
- [<span data-ttu-id="c0acd-195">ClearType 抗锯齿</span><span class="sxs-lookup"><span data-stu-id="c0acd-195">ClearType Antialiasing</span></span>](/windows/desktop/gdi/cleartype-antialiasing)
