---
title: ClearType 概述
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], ClearType technology
- ClearType [WPF], technology
ms.assetid: 7e2392e0-75dc-463d-a716-908772782431
ms.openlocfilehash: 51808ea2c48b2d56709dea4c4ff5124af3eb9fac
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971961"
---
# <a name="cleartype-overview"></a>ClearType 概述
本主题概述了中的 Microsoft ClearType 技术 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。  

<a name="overview"></a>
## <a name="technology-overview"></a>技术概述  
 ClearType 是由 Microsoft 开发的一种软件技术，可提高现有 Lcd 上的文本可读性 (Crystal 显示屏) ，如笔记本电脑屏幕、Pocket PC 屏幕和平板显示器。  ClearType 通过访问 LCD 屏幕的每个像素中的各个垂直色带元素来工作。 在 ClearType 之前，计算机可以显示的最小细节级别为单个像素，但在 LCD 监视器上运行 ClearType 时，我们现在可以将文本的功能显示为小到宽度的一小部分。 超高的分辨率增加了文本显示中细节的清晰度，使其更便于长时间阅读。  
  
 中可用的 ClearType [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 是最新一代的 cleartype，它对 Microsoft Windows 图形设备接口 (GDI) 中的版本进行了多项改进。  
  
<a name="sub-pixel_positioning"></a>
## <a name="sub-pixel-positioning"></a>子像素定位  
 对以前版本的 ClearType 的重大改进是使用子像素定位。 与在 GDI 中找到的 ClearType 实现不同，中找到的 ClearType [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 允许标志符号在像素内开始，而不仅仅是像素的开始边界。 由于在定位字形时的这种超高的分辨率，字形的间距和比例更加精确和一致。  
  
 以下两个示例演示了使用子像素定位时，字形如何从任意子像素边界处开始。 左侧的示例使用较早版本的 ClearType 呈现器呈现，该版本不采用子像素定位。 右侧的示例使用新版本的 ClearType 呈现器呈现，使用了子像素定位。 请注意右侧图像中的每个 **e** 和 **l** 的呈现方式稍有不同，因为每一个字母都开始于一个不同的子像素。 在屏幕上以正常尺寸查看文本时，由于字形图像的高对比度，这种差异并不明显。 这种情况只能由 ClearType 中包含的复杂颜色筛选来实现。  
  
 ![使用两个版本的 ClearType 显示的文本](./media/wcpsdk-mmgraphics-text-cleartype-overview-01.png "wcpsdk_mmgraphics_text_cleartype_overview_01")  
使用较早和较晚版本的 ClearType 显示的文本  
  
 以下两个示例将早期 ClearType 呈现器的输出与 ClearType 呈现器的新版本进行比较。 右侧显示的子像素定位显著改善了屏幕上的字体间距，尤其是在较小尺寸处，子像素与整个像素之间的差异在很大程度上代表了字形宽度。 请注意，第二张图中字母之间的间距更均匀。 子像素定位到文本屏幕整体外观的累积收益大大增加，并代表 ClearType 技术的重大演变。  
  
 ![使用较早的 ClearType 版本显示的文本](./media/wcpsdk-mmgraphics-text-cleartype-overview-02.png "wcpsdk_mmgraphics_text_cleartype_overview_02")  
使用较早和较晚版本的 ClearType 显示的文本  
  
<a name="y-direction_antialiasing"></a>
## <a name="y-direction-antialiasing"></a>Y 方向抗锯齿功能  
 中 ClearType 的另一个改进 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 是 y 方向抗锯齿。 无 y 方向抗锯齿的 GDI 中的 ClearType 在 x 轴上提供更好的分辨率，而不是 y 轴。 在平缓曲线的顶部和底部，锯齿状边缘会降低其可读性。  
  
 以下示例演示了没有 y 方向抗锯齿功能的效果。 在这个示例中，字母顶部和底部的锯齿状边缘非常明显。  
  
 ![平缓曲线上有粗糙边缘的文本](./media/wcpsdk-mmgraphics-text-cleartype-overview-03.png "wcpsdk_mmgraphics_text_cleartype_overview_03")  
平缓曲线上有粗糙边缘的文本  
  
 ClearType in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 提供 y 方向的抗锯齿功能，以平滑任何交错边缘。 这对于提高东亚语言的可读性特别重要，在东亚语言中，表意文字的水平和垂直平缓曲线几乎同样多。  
  
 以下示例演示了 y 方向抗锯齿功能的效果。 在这个示例中，字母顶部和底部对曲线较为平滑。  
  
 ![采用 ClearType y 向抗锯齿的文本](./media/wcpsdk-mmgraphics-text-cleartype-overview-04.png "wcpsdk_mmgraphics_text_cleartype_overview_04")  
采用 ClearType y 向抗锯齿的文本  
  
<a name="hardware_acceleration"></a>
## <a name="hardware-acceleration"></a>硬件加速  
 中 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 的 ClearType 可以利用硬件加速来提高性能，并减少 CPU 负载和系统内存要求。 通过使用图形卡的像素着色器和视频内存，ClearType 可以更快地呈现文本，尤其是使用动画时。  
  
 ClearType in 不 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 会修改系统范围内的 cleartype 设置。 在 Windows 中禁用 ClearType 会将 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 抗锯齿设置为灰度模式。 此外，中的 ClearType 不 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 会修改 [Cleartype 调谐器 PowerToy](https://www.microsoft.com/typography/ClearTypePowerToy.mspx)的设置。  
  
 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 体系结构设计决策之一是让不依赖于分辨率的布局更好地支持较高分辨率的 DPI 显示器，这种显示器正在日益普及。 此决策的后果是 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 不支持某些东亚字体中抗锯齿的文本呈现或位图，因为它们都依赖于分辨率。  
  
<a name="further_information"></a>
## <a name="further-information"></a>其他信息  
 [ClearType 信息](https://www.microsoft.com/typography/ClearTypeInfo.mspx)  
  
 [ClearType 调谐器 PowerToy](https://www.microsoft.com/typography/ClearTypePowerToy.mspx)  
  
## <a name="see-also"></a>另请参阅

- [ClearType 注册表设置](cleartype-registry-settings.md)
