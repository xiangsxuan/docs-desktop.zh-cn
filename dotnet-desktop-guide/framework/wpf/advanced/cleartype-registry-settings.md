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
# <a name="cleartype-registry-settings"></a>ClearType 注册表设置
本主题概述了 WPF 应用程序使用的 Microsoft ClearType 注册表设置。  

<a name="overview"></a>
## <a name="technology-overview"></a>技术概述  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 向显示设备呈现文本的应用程序使用 ClearType 功能提供增强的阅读体验。 ClearType 是由 Microsoft 开发的一种软件技术，可提高现有 Lcd 上的文本可读性 (Crystal 显示屏) ，如笔记本电脑屏幕、Pocket PC 屏幕和平板显示器。 ClearType 通过访问 LCD 屏幕的每个像素中的各个垂直色带元素来工作。 有关 ClearType 的详细信息，请参阅 [Cleartype 概述](cleartype-overview.md)。  
  
 当在各种显示设备上查看时，用 ClearType 呈现的文本可能出现明显不同。 例如，少量监视器以蓝色、绿色、红色顺序而不是更常见的红色、绿色、蓝色 (RGB) 顺序来实现色带元素。  
  
 使用 ClearType 呈现的文本在由具有不同级别的颜色敏感度的个人观看时，还会显得大不相同。 某些人能够比别人更擅长发觉颜色的微小差异。  
  
 在上述每种情况下，都需要修改 ClearType 功能，以便为每个人提供最佳阅读体验。  
  
<a name="registry_settings"></a>
## <a name="registry-settings"></a>注册表设置  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 指定用于控制 ClearType 功能的四个注册表设置：  
  
|设置|说明|  
|-------------|-----------------|  
|ClearType 级别|描述 ClearType 颜色清晰度的级别。|  
|伽马级别|描述显示设备的像素颜色组件的级别。|  
|像素结构|描述显示设备的像素排列。|  
|文本对比度级别|描述显示文本的对比度级别。|  
  
 这些设置可由知道如何引用已识别 ClearType 注册表设置的外部配置实用程序来访问 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。 还可以通过使用 Windows 注册表编辑器直接访问这些值来创建或修改这些设置。  
  
 如果 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ClearType 注册表设置未设置 (这是默认状态) ，则该 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序将查询 Windows 系统参数信息以实现字体平滑设置。  
  
> [!NOTE]
> 有关枚举显示设备名称的信息，请参阅 `SystemParametersInfo` Win32 函数。  
  
<a name="ClearType_level"></a>
## <a name="cleartype-level"></a>ClearType 级别  
 ClearType 级别允许你根据颜色敏感度和个人认知度调整文本的呈现。 对于某些人而言，在其最高级别使用 ClearType 的文本呈现不会产生最佳阅读体验。  
  
 ClearType 级别为介于0到100之间的整数值。 默认级别为100，这意味着 ClearType 使用显示设备的色带元素的最大容量。 但 ClearType 级别0将文本呈现为灰色刻度。 通过将 ClearType 级别设置为介于0到100之间的某个位置，可以创建适合个人颜色敏感度的中间级别。  
  
### <a name="registry-setting"></a>注册表设置  
 ClearType 级别的注册表设置位置是对应于特定显示设备名称的单个用户设置：  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 对于用户的每个显示设备名称， `ClearTypeLevel` 会定义一个 DWORD 值。 以下屏幕截图显示 ClearType 级别的注册表编辑器设置。  
  
 ![注册表编辑器中的 ClearType 设置。](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序以两种模式之一呈现文本，但不带 ClearType。 如果呈现的文本没有 ClearType，则称为灰度呈现。  
  
<a name="gamma_level"></a>
## <a name="gamma-level"></a>伽马级别  
 伽玛级别指的是像素值和亮度之间的非线性关系。 伽玛级别设置应对应于显示设备的物理特性；否则呈现的输出中可能会出现失真。 例如，文本显示的宽度可能太大或太窄，或者标志符号的垂直词干边缘上可能出现颜色条纹。  
  
 伽马级别是一个介于 1000 到 2200 之间的整数值。 默认级别为 1900。  
  
### <a name="registry-setting"></a>注册表设置  
 伽马级别的注册表设置位置是对应于特定显示设备名称的本地计算机设置：  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 对于用户的每个显示设备名称， `GammaLevel` 会定义一个 DWORD 值。 以下屏幕快照显示了伽马级别的注册表编辑器设置。  
  
 ![注册表编辑器中的 ClearType 伽玛级别设置](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>
## <a name="pixel-structure"></a>像素结构  
 像素结构描述构成显示设备的像素的类型。 像素结构定义为三种类型之一：  
  
|类型|值|说明|  
|----------|-----------|-----------------|  
|平面|0|显示设备没有像素结构。 这意味着每种颜色的光源均匀分布在像素区域上，称为灰度呈现。 这是标准显示设备的工作方式。 ClearType 从不应用于呈现的文本。|  
|RGB|1|显示设备的像素由三种色条按以下顺序构成：红色、绿色和蓝色。 ClearType 应用于呈现的文本。|  
|BGR|2|显示设备的像素由三种色条按以下顺序构成：蓝色、绿色和红色。 ClearType 应用于呈现的文本。 注意该顺序与 RGB 类型相反。|  
  
 像素结构对应于 0 到 2 之间的一个整数值。 默认级别为 0，表示平面像素结构。  
  
> [!NOTE]
> 有关枚举显示设备名称的信息，请参阅 `EnumDisplayDevices` Win32 函数。  
  
### <a name="registry-setting"></a>注册表设置  
 像素结构的注册表设置位置是对应于特定显示设备名称的本地计算机设置：  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 对于用户的每个显示设备名称， `PixelStructure` 会定义一个 DWORD 值。 以下屏幕快照显示了像素结构的注册表编辑器设置。  
  
 ![注册表编辑器中的 ClearType 伽玛级别设置](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>
## <a name="text-contrast-level"></a>文本对比度级别  
 通过文本对比度级别可以根据字形的主体宽度来调整文本的呈现。 文本对比度级别是一个 0 到 6 之间的整数值 - 整数值越大，主体就越宽。 默认级别为 1。  
  
### <a name="registry-setting"></a>注册表设置  
 文本对比度级别的注册表设置位置是对应于特定显示设备名称的单个用户设置：  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 对于用户的每个显示设备名称， `TextContrastLevel` 会定义一个 DWORD 值。 以下屏幕快照显示了文本对比度级别的注册表编辑器设置。  
  
 ![注册表编辑器中的 ClearType 设置。](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a>请参阅

- [ClearType 概述](cleartype-overview.md)
- [ClearType 抗锯齿](/windows/desktop/gdi/cleartype-antialiasing)
