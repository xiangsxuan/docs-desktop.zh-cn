---
title: 最大化三维性能
ms.date: 03/30/2017
helpviewer_keywords:
- 3D graphics [WPF]
ms.assetid: 4bcf949d-d92f-4d8d-8a9b-1e4c61b25bf6
ms.openlocfilehash: 0cc7ce1d62fd9a21abc3130c0a799e1d3a049ca6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973171"
---
# <a name="maximize-wpf-3d-performance"></a>最大程度地提高 WPF 三维性能
当你使用 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 生成3d 控件并在应用程序中包括三维场景时，考虑性能优化很重要。 本主题提供了对应用程序性能产生影响的3D 类和属性的列表，以及在使用这些类和属性时优化性能的建议。  
  
 本主题假定你已了解 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 3d 功能。 本文档中的建议适用于 "呈现层 2"，其大致定义为支持像素着色器版本2.0 和顶点着色器版本2.0 的硬件。 有关更多详细信息，请参阅 [图形呈现层](../advanced/graphics-rendering-tiers.md)。  
  
## <a name="performance-impact-high"></a>性能影响：高  
  
|属性|建议|  
|-|-|  
|<xref:System.Windows.Media.Brush>|画笔速度 (最快到最慢) ：<br /><br /> <xref:System.Windows.Media.SolidColorBrush><br /><br /> <xref:System.Windows.Media.LinearGradientBrush><br /><br /> <xref:System.Windows.Media.ImageBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> (缓存) <br /><br /> <xref:System.Windows.Media.VisualBrush> (缓存) <br /><br /> <xref:System.Windows.Media.RadialGradientBrush><br /><br /> <xref:System.Windows.Media.DrawingBrush> (未缓存) <br /><br /> <xref:System.Windows.Media.VisualBrush> (未缓存) |  
|<xref:System.Windows.UIElement.ClipToBoundsProperty>|`Viewport3D.ClipToBounds`每当不需要将的 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 内容显式剪裁到 Viewport3D's 矩形时，将设置为 false <xref:System.Windows.Controls.Viewport3D> 。 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 消除锯齿剪辑可能非常慢，并且 `ClipToBounds` 默认情况下 (慢速) 启用 <xref:System.Windows.Controls.Viewport3D> 。|  
|<xref:System.Windows.UIElement.IsHitTestVisible%2A>|如果 `Viewport3D.IsHitTestVisible` 在 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.Viewport3D> 执行鼠标命中测试时无需考虑的内容，则设置为 false。  对3D 内容进行命中测试是在软件中完成的，很大的网格可能会很慢。 <xref:System.Windows.UIElement.IsHitTestVisible%2A> 默认情况下， (慢速) 启用 <xref:System.Windows.Controls.Viewport3D> 。|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D>|仅当需要不同的材料或转换时才创建不同的模型。  否则，请尝试合并多个 <xref:System.Windows.Media.Media3D.GeometryModel3D> 具有相同材料的实例，并将转换为一些更大的 <xref:System.Windows.Media.Media3D.GeometryModel3D> <xref:System.Windows.Media.Media3D.MeshGeometry3D> 实例。|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|网格动画-基于每个帧更改网格的各个顶点，在中并非始终有效 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。  若要在每个顶点被修改时最大程度地降低更改通知的性能影响，请在执行按顶点修改之前，先将网格从可视化树中分离出来。  修饰网格后，将其重新附加到可视化树。  同时，尝试最大程度地减少将以这种方式进行动画处理的网格的大小。|  
|三维消除锯齿|若要提高呈现速度，请 <xref:System.Windows.Controls.Viewport3D> 通过将附加属性设置为来禁用的多级 <xref:System.Windows.Media.RenderOptions.EdgeMode%2A> `Aliased` 。  默认情况下，在 Windows 上启用3D 消除，每像素4个样本。|  
|文本|三维场景中的实时文本 (实时，因为它处于 <xref:System.Windows.Media.DrawingBrush> 或 <xref:System.Windows.Media.VisualBrush>) 可能很慢。 尝试使用文本的图像，而不是通过 <xref:System.Windows.Media.Imaging.RenderTargetBitmap>)  (，除非文本会更改。|  
|<xref:System.Windows.Media.TileBrush>|如果在 <xref:System.Windows.Media.VisualBrush> <xref:System.Windows.Media.DrawingBrush> 三维场景中必须使用或，因为画笔的内容不是静态的，请尝试缓存画笔 (将附加属性设置 <xref:System.Windows.Media.RenderOptions.CachingHint%2A> 为 `Cache`) 。  设置与附加属性和)  (的最小和最大缩放失效阈值， <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> 以便不会频繁地重新生成缓存的画笔，同时仍保持所需的质量级别。  默认情况下， <xref:System.Windows.Media.DrawingBrush> 和不会被 <xref:System.Windows.Media.VisualBrush> 缓存，这意味着，每次必须重新呈现使用画笔绘制的内容时，必须先将该画笔的整个内容重新呈现到中间图面。|  
|<xref:System.Windows.Media.Effects.BitmapEffect>|<xref:System.Windows.Media.Effects.BitmapEffect> 强制呈现所有受影响的内容而不进行硬件加速。  为了获得最佳性能，请不要使用 <xref:System.Windows.Media.Effects.BitmapEffect> 。|  
  
## <a name="performance-impact-medium"></a>性能影响：中型  
  
|属性|建议|  
|-|-|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|如果将网格定义为带有共享顶点的相邻三角形，并且这些顶点具有相同的位置、法线和纹理坐标，则只需定义一次每个共享顶点，然后使用索引定义三角形 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> 。|  
|<xref:System.Windows.Media.ImageBrush>|当你在使用 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 和/或) 时，可以显式控制 (的大小 <xref:System.Windows.Media.ImageBrush> 。  请注意，较低的分辨率纹理会降低视觉质量，因此请尝试在质量和性能之间找到适当的平衡点。|  
|不透明度|在呈现半透明三维内容 (例如反射) 时，通过或) 使用画笔或材料 (上的 opacity 属性， <xref:System.Windows.Media.Brush.Opacity%2A> <xref:System.Windows.Media.Media3D.DiffuseMaterial.Color%2A> 而不是 <xref:System.Windows.Controls.Viewport3D> 通过将设置 `Viewport3D.Opacity` 为小于1的值来创建单独的半透明。|  
|<xref:System.Windows.Controls.Viewport3D>|最大程度地减少 <xref:System.Windows.Controls.Viewport3D> 场景中使用的对象数。  在相同的 Viewport3D 中放置许多3D 模型，而不是为每个模型创建单独的 Viewport3D 实例。|  
|<xref:System.Windows.Freezable>|通常，重复使用 <xref:System.Windows.Media.Media3D.MeshGeometry3D> 、 <xref:System.Windows.Media.Media3D.GeometryModel3D> 、画笔和材料是有益的。  所有都是 multiparentable，因为它们是从派生的 `Freezable` 。|  
|<xref:System.Windows.Freezable>|<xref:System.Windows.Freezable.Freeze%2A>当应用程序中的属性保持不变时，在可冻结对象上调用方法。  冻结可降低工作集和提高速度。|  
|<xref:System.Windows.Media.Brush>|<xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.VisualBrush> <xref:System.Windows.Media.DrawingBrush> 当画笔的内容不会更改时使用，而不是。  可以通过将二维内容转换为 <xref:System.Windows.Controls.Image> <xref:System.Windows.Media.Imaging.RenderTargetBitmap> ，然后在中使用 <xref:System.Windows.Media.ImageBrush> 。|  
|<xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>|不要使用 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> ，除非确实需要查看的背面 <xref:System.Windows.Media.Media3D.GeometryModel3D> 。|  
|<xref:System.Windows.Media.Media3D.Light>|速度 (最快到最慢) ：<br /><br /> <xref:System.Windows.Media.Media3D.AmbientLight><br /><br /> <xref:System.Windows.Media.Media3D.DirectionalLight><br /><br /> <xref:System.Windows.Media.Media3D.PointLight><br /><br /> <xref:System.Windows.Media.Media3D.SpotLight>|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|尝试在这些限制下保留网格大小：<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A>： 20001 <xref:System.Windows.Media.Media3D.Point3D> 实例<br /><br /> <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A>： 60003 <xref:System.Int32> 实例|  
|<xref:System.Windows.Media.Media3D.Material>|材料速度 (最快到最慢) ：<br /><br /> <xref:System.Windows.Media.Media3D.EmissiveMaterial><br /><br /> <xref:System.Windows.Media.Media3D.DiffuseMaterial><br /><br /> <xref:System.Windows.Media.Media3D.SpecularMaterial>|  
|<xref:System.Windows.Media.Brush>|[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 三维不会 (黑色的环境画笔、清晰的画笔等 ) 以一致的方式进行。  请考虑从场景中省略这些。|  
|<xref:System.Windows.Media.Media3D.MaterialGroup>|中的每个都 <xref:System.Windows.Media.Media3D.Material> 将 <xref:System.Windows.Media.Media3D.MaterialGroup> 导致另一个呈现阶段，其中包括许多材料，甚至是简单的材料，这会大幅增加对 GPU 的填充需求。  最大程度地减少中的资料数量 <xref:System.Windows.Media.Media3D.MaterialGroup> 。|  
  
## <a name="performance-impact-low"></a>性能影响：低  
  
|属性|建议|  
|-|-|  
|<xref:System.Windows.Media.Media3D.Transform3DGroup>|如果不需要动画或数据绑定，请使用单个，而不是使用包含多个转换的转换组，而是将 <xref:System.Windows.Media.Media3D.MatrixTransform3D> 其设置为在转换组中独立存在的所有转换的乘积。|  
|<xref:System.Windows.Media.Media3D.Light>|最大程度地减少场景中光线的数目。 场景中的光太多将强制回退 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 到软件呈现。  限制大约为110个 <xref:System.Windows.Media.Media3D.DirectionalLight> 对象、70个对象 <xref:System.Windows.Media.Media3D.PointLight> 或40个 <xref:System.Windows.Media.Media3D.SpotLight> 对象。|  
|<xref:System.Windows.Media.Media3D.ModelVisual3D>|将对象放入不同的实例，从而将其从静态对象中分离出来 <xref:System.Windows.Media.Media3D.ModelVisual3D> 。  ModelVisual3D 比 "更粗"， <xref:System.Windows.Media.Media3D.GeometryModel3D> 因为它会缓存已转换的边界。  GeometryModel3D 优化为模型;ModelVisual3D 优化为场景节点。  使用 ModelVisual3D 将 GeometryModel3D 的共享实例放入场景。|  
|<xref:System.Windows.Media.Media3D.Light>|最大程度地减少场景中灯光数量的更改次数。  对于每次更改的光源，都将强制重新生成和重新编译着色器，除非该配置以前已 (，因此其) 的着色器已缓存。|  
|亮|黑色光源不可见，但会将其添加到渲染时间;请考虑省略它们。|  
|<xref:System.Windows.Media.Media3D.MeshGeometry3D>|若要最大程度地减少中大型集合的构造时间 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] ，如 MeshGeometry3D's <xref:System.Windows.Media.Media3D.MeshGeometry3D.Positions%2A> 、 <xref:System.Windows.Media.Media3D.MeshGeometry3D.Normals%2A> 、 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TextureCoordinates%2A> 和 <xref:System.Windows.Media.Media3D.MeshGeometry3D.TriangleIndices%2A> ，请在值填充之前预先调整集合的大小。 如果可能，请传递集合的构造函数预填充的数据结构，例如数组或列表。|  
  
## <a name="see-also"></a>另请参阅

- [三维图形概述](3-d-graphics-overview.md)
