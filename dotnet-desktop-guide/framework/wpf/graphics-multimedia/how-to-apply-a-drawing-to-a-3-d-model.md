---
title: 如何：向三维模型应用绘图
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3D models
- 3D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 794ca9a48bcec42c3eee4d8da143f3ae9d27fcf2
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973176"
---
# <a name="how-to-apply-a-drawing-to-a-3d-model"></a>如何：向三维模型应用绘图

此示例演示如何使用 <xref:System.Windows.Media.DrawingBrush> 作为 <xref:System.Windows.Media.Media3D.Material> 应用于三维模型的。

下面的代码将定义 <xref:System.Windows.Media.DrawingGroup> 为的内容 <xref:System.Windows.Media.DrawingBrush> 。  <xref:System.Windows.Media.DrawingBrush>设置为 <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> <xref:System.Windows.Media.Media3D.DiffuseMaterial> 应用于三维平面的的属性。

> [!NOTE]
> 通常需要将复杂对象和值（如下面的绘图）定义为可重复使用的资源，并简化你的代码。 有关详细信息，请参阅 [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define) 。

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>示例

下面的代码显示了整个示例。

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>请参阅

- [XAML 资源](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [创建三维场景](how-to-create-a-3-d-scene.md)
- [Drawing 对象概述](drawing-objects-overview.md)
- [三维图形概述](3-d-graphics-overview.md)
