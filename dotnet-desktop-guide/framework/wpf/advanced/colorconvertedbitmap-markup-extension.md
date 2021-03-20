---
title: ColorConvertedBitmap 标记扩展
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: b3b24faa1e56d0dec500f065cf801277003f9b7e
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104666142"
---
# <a name="colorconvertedbitmap-markup-extension"></a>ColorConvertedBitmap 标记扩展
提供一种方法，用于指定没有嵌入的配置文件的位图源。 颜色上下文/配置文件由 URI 指定，与映像源 URI 相同。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" ... />
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`imageSource`|方式位图的 URI。|  
|`sourceIIC`|源配置文件配置的 URI。|  
|`destinationIIC`|目标配置文件配置的 URI|  
  
## <a name="remarks"></a>备注  
 此标记扩展用于填充一组相关的图像源属性值，例如 <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A> 。  
  
 特性语法是最常用于该标记扩展的语法。 `ColorConvertedBitmap``ColorConvertedBitmapExtension`无法在属性元素语法中使用 (或) ，因为只能将值设置为初始构造函数上的值，这是扩展标识符后面的字符串。  
  
 `ColorConvertedBitmap` 是标记扩展。 当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。 有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)
- [图像处理概述](../graphics-multimedia/imaging-overview.md)
