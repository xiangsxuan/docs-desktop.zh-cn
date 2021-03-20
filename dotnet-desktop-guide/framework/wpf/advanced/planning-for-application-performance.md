---
title: 规划应用程序性能
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: c91bd0c5-a193-46ff-9da1-eb7a3a76a3b3
ms.openlocfilehash: f63d54a5ab9e6c97b9f75cdf01513b80c9f63ee2
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104667208"
---
# <a name="planning-for-application-performance"></a>规划应用程序性能
实现性能目标的成功取决于你开发性能策略的程度。 规划是开发任何产品的第一阶段。 本主题介绍了几个非常简单的规则，用于开发良好的性能策略。  
  
## <a name="think-in-terms-of-scenarios"></a>考虑方案  
 方案可帮助你专注于应用程序的关键组件。 方案通常派生自你的客户和竞争产品。 请始终研究你的客户，并找出对你的产品和竞争对手的产品的真正令人兴奋的内容。 你的客户的反馈可以帮助你确定应用程序的主要方案。 例如，如果您正在设计将在启动时使用的组件，则当应用程序启动时，该组件可能只调用一次。 启动时间成为你的关键方案。 关键方案的其他示例可能是动画序列所需的帧速率，或应用程序允许的最大工作集。  
  
## <a name="define-goals"></a>定义目标  
 目标有助于确定应用程序的运行速度是否更快或更慢。 应为所有方案定义目标。 你定义的所有性能目标都应基于客户预期。 当仍有许多未解决的问题时，可能很难在应用程序开发周期中提前设置性能目标。 不过，最好设置一个初始目标，并在以后对其进行修订，使其不是一个目标。  
  
## <a name="understand-your-platform"></a>了解平台  
 在应用程序开发周期中始终维持测量、调查、优化/更正的周期。 在开发周期结束时，您需要在可靠、稳定的环境中衡量应用程序的性能。 应避免由外部因素导致的可变性。 例如，在测试性能时，您应该禁用防病毒或任何自动更新，如 SMS，以便不影响性能测试结果。 衡量应用程序的性能后，需要确定将导致最大改进的更改。 修改应用程序后，请重新启动循环。  
  
## <a name="make-performance-tuning-an-iterative-process"></a>使性能优化成为迭代过程  
 您应该知道您将使用的每项功能的相对成本。 例如，在 Microsoft .NET 框架中使用反射通常会对计算资源的性能有很大的影响，因此您需要谨慎地使用它。 这并不意味着避免使用反射，只应小心地根据你所使用的功能的性能要求来平衡应用程序的性能要求。  
  
## <a name="build-towards-graphical-richness"></a>面向图形丰富的生成  
 创建可缩放方法以实现应用程序性能的一项关键方法 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 是构建图形丰富和复杂程度。 始终使用最小的性能密集型资源来实现您的方案目标。 实现这些目标后，通过使用更多的性能密集型功能构建图形丰富的功能，始终牢记方案目标。 请记住， [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 它是一个非常丰富的平台，它提供了非常丰富的图形功能。 在不考虑的情况下使用性能密集型功能可能会对总体应用程序性能产生负面影响。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件本质上是可扩展的，因为允许跨范围自定义其外观，而不更改其控制行为。 通过利用样式、数据模板和控件模板，你可以创建并以增量方式改进可 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 适应你的性能要求的自定义。  
  
## <a name="see-also"></a>请参阅

- [优化 WPF 应用程序性能](optimizing-wpf-application-performance.md)
- [利用硬件](optimizing-performance-taking-advantage-of-hardware.md)
- [布局和示例](optimizing-performance-layout-and-design.md)
- [二维图形和图像处理](optimizing-performance-2d-graphics-and-imaging.md)
- [对象行为](optimizing-performance-object-behavior.md)
- [应用程序资源](optimizing-performance-application-resources.md)
- [文本](optimizing-performance-text.md)
- [数据绑定](optimizing-performance-data-binding.md)
- [其他性能建议](optimizing-performance-other-recommendations.md)
