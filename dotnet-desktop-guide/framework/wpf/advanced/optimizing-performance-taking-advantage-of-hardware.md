---
title: 优化性能：利用硬件
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], performance
- hardware rendering pipeline [WPF]
- rendering tiers [WPF]
- graphics rendering tiers [WPF]
- graphics [WPF], rendering tiers
- software rendering pipeline [WPF]
ms.assetid: bfb89bae-7aab-4cac-a26c-a956eda8fce2
ms.openlocfilehash: 3cc63b69848024bd6c18dc0de48ae3a1e4b4134f
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665310"
---
# <a name="optimizing-performance-taking-advantage-of-hardware"></a>优化性能：利用硬件
的内部体系结构 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 有两个渲染管道：硬件和软件。 本主题提供有关这些渲染管道的信息，以帮助您确定应用程序的性能优化。  
  
## <a name="hardware-rendering-pipeline"></a>硬件呈现管道  
 确定性能的最重要因素之一 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 在于它是呈现绑定的（需要呈现的像素越多），性能开销就越大。 但是，可以卸载到图形处理单元 (GPU) 的渲染越多，可获得的性能优势就越多。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]应用程序硬件呈现管道充分利用了 Microsoft directx 功能，这些功能支持最少的 Microsoft directx 7.0 版硬件。 可以通过支持 Microsoft DirectX 7.0 版和 PixelShader 2.0 + 功能的硬件来获得进一步的优化。  
  
## <a name="software-rendering-pipeline"></a>软件呈现管道  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]软件呈现管道完全受 CPU 限制。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 利用 CPU 中的 SSE 和 SSE2 指令集来实现经过优化且功能完备的软件光栅。 当应用程序功能不能使用硬件呈现管道进行呈现时，无缝回退到软件。  
  
 在软件模式下呈现时遇到的最大性能问题与填充率相关，填充率定义为要呈现的像素数。 如果你担心软件呈现模式的性能，请尝试最大程度地减少重绘像素的次数。 例如，如果应用程序具有蓝色背景，然后在其上呈现略微透明的图像，则会在应用程序中呈现两次所有像素。 因此，使用图像呈现应用程序需要两次，而不是只有蓝色背景。  
  
### <a name="graphics-rendering-tiers"></a>图形呈现层  
 预测应用程序将在其上运行的硬件配置可能非常困难。 但是，你可能需要考虑允许应用程序在不同硬件上运行时无缝切换功能的设计，使其能够充分利用各种不同的硬件配置。  
  
 为实现此目的， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 提供了在运行时确定系统的图形功能的功能。 图形功能通过将视频卡分类为三个呈现功能层之一来确定。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 公开一个 API，该 API 允许应用程序查询呈现功能层。 然后，应用程序可以在运行时采用不同的代码路径，具体取决于硬件支持的呈现层。  
  
 对呈现层级别影响最大的图形硬件功能包括：  
  
- **视频 RAM** - 图形硬件中的视频内存量决定了可用于合成图形的缓冲区大小和数量。  
  
- **像素着色器** - 像素着色器是基于像素计算效果的图形处理功能。 每个显示帧可能有数百万像素需要处理，具体取决于显示图形的分辨率。  
  
- **顶点着色器** - 顶点着色器是对对象的顶点数据执行数学运算的图形处理功能。  
  
- **多纹理支持** - 多纹理支持是指对 3D 图形对象执行混合操作期间应用两个或更多个不同纹理的功能。 多纹理支持的程度取决于图形硬件中的多纹理单元数。  
  
 "像素着色器"、"顶点着色器" 和 "多纹理" 功能用于定义特定的 DirectX 版本级别，后者反过来用于定义中的不同呈现层 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。  
  
 图形硬件的功能决定了 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 应用程序的呈现功能。 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 系统定义了 3 个呈现层：  
  
- **呈现层 0** - 无图形硬件加速。 DirectX 版本级别低于版本7.0。  
  
- **呈现层 1** 部分图形硬件加速。 DirectX 版本级别大于或等于版本 7.0 **，并且低于** 版本9.0。  
  
- **呈现层 2** - 大多数图形功能都使用图形硬件加速。 DirectX 版本级别大于或等于版本9.0。  
  
 有关呈现层的详细信息 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] ，请参阅 [图形呈现层](graphics-rendering-tiers.md)。  
  
## <a name="see-also"></a>请参阅

- [优化 WPF 应用程序性能](optimizing-wpf-application-performance.md)
- [规划应用程序性能](planning-for-application-performance.md)
- [布局和示例](optimizing-performance-layout-and-design.md)
- [二维图形和图像处理](optimizing-performance-2d-graphics-and-imaging.md)
- [对象行为](optimizing-performance-object-behavior.md)
- [应用程序资源](optimizing-performance-application-resources.md)
- [文本](optimizing-performance-text.md)
- [数据绑定](optimizing-performance-data-binding.md)
- [其他性能建议](optimizing-performance-other-recommendations.md)
