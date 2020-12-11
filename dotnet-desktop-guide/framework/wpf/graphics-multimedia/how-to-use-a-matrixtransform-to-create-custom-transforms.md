---
title: 如何：使用 MatrixTransform 创建自定义变换
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 1971d5fe9422c5138f140517e6fd4c9f9b2cf48b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973417"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a>如何：使用 MatrixTransform 创建自定义变换
此示例演示如何使用 <xref:System.Windows.Media.MatrixTransform> 转换 (移动) 的位置、拉伸和倾斜 <xref:System.Windows.Controls.Button> 。  
  
> [!NOTE]
> 使用 <xref:System.Windows.Media.MatrixTransform> 类可创建不由 <xref:System.Windows.Media.RotateTransform> 、 <xref:System.Windows.Media.SkewTransform> 、 <xref:System.Windows.Media.ScaleTransform> 或类提供的自定义转换 <xref:System.Windows.Media.TranslateTransform> 。  
  
## <a name="example"></a>示例  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [转换概述](transforms-overview.md)
- [操作指南主题](transformations-how-to-topics.md)
- [WPF 中的形状和基本图形概述](shapes-and-basic-drawing-in-wpf-overview.md)
