---
title: 绘制格式化文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF]
- typography [WPF], drawing formatted text
- formatted text [WPF]
- drawing [WPF], formatted text
ms.assetid: b1d851c1-331c-4814-9964-6fe769db6f1f
ms.openlocfilehash: 3a2f80832a905579455b21cdfef6770640ef74fd
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665497"
---
# <a name="drawing-formatted-text"></a>绘制格式化文本

本主题概述对象的功能 <xref:System.Windows.Media.FormattedText> 。 此对象为在 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 应用程序中绘制文本提供低级别控制。  

## <a name="technology-overview"></a>技术概述  

 <xref:System.Windows.Media.FormattedText>对象允许您绘制多行文本，在这种情况下，文本中的每个字符都可以单独设置格式。 下例演示应用了多种格式的文本。  
  
 ![使用 FormattedText 对象显示的文本](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)  
  
> [!NOTE]
> 对于从 Win32 API 迁移的开发人员，" [Win32 迁移](#win32_migration) " 部分中的表列出了 win32 DrawText 标志和中的近似等效项 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。  
  
### <a name="reasons-for-using-formatted-text"></a>使用格式化文本的原因  

 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 包括多个用于在屏幕中绘制文本的控件。 每个控件都面向不同的方案，并具有自己的功能和限制列表。 通常， <xref:System.Windows.Controls.TextBlock> 当要求提供有限文本支持时，应使用元素，例如中的 brief 句子 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 。 <xref:System.Windows.Controls.Label> 需要最少文本支持时，可以使用。 有关详细信息，请参阅 [WPF 中的文档](documents-in-wpf.md)。  
  
 <xref:System.Windows.Media.FormattedText>对象提供比文本控件更大的文本格式功能 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] ，并且在要使用文本作为装饰元素时非常有用。 有关详细信息，请参阅下一节[将格式化文本转换为几何图形](#converting_formatted_text)。  
  
 此外， <xref:System.Windows.Media.FormattedText> 对象对于创建面向文本的派生对象非常有用 <xref:System.Windows.Media.DrawingVisual> 。 <xref:System.Windows.Media.DrawingVisual> 是一个轻量绘图类，用于呈现形状、图像或文本。 有关详细信息，请参阅[使用 DrawingVisuals 执行测试示例](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual)。  
  
## <a name="using-the-formattedtext-object"></a>使用 FormattedText 对象  

 若要创建格式化文本，请调用 <xref:System.Windows.Media.FormattedText.%23ctor%2A> 构造函数来创建 <xref:System.Windows.Media.FormattedText> 对象。 创建初始格式化文本字符串后，便可应用某一范围的格式样式。  
  
 使用 <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> 属性将文本限制为特定宽度。 文本将自动换行，避免超过指定宽度。 使用 <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A> 属性将文本限制为特定高度。 超过指定高度的文本将显示一个省略号“…”。  
  
 ![与换行和省略号一起显示的文本。](./media/drawing-formatted-text/formatted-text-wordwrap-ellipsis.png)
  
 可向一个或多个字符应用多种格式样式。 例如，可以调用 <xref:System.Windows.Media.FormattedText.SetFontSize%2A> 和 <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> 方法来更改文本中前五个字符的格式设置。  
  
 下面的代码示例创建一个 <xref:System.Windows.Media.FormattedText> 对象，然后将多个格式设置样式应用于该文本。  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>字号度量单位  

 与应用程序中的其他文本对象一样 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] ， <xref:System.Windows.Media.FormattedText> 对象使用与设备无关的像素作为度量单位。 但是，大多数 Win32 应用程序都使用点作为度量单位。 如果要在应用程序中使用以点为单位的显示文本 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] ，则需要将每个单位)  (1/96th 每英寸转换为点的与设备无关的单位。 以下代码示例演示如何执行此转换。  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>

### <a name="converting-formatted-text-to-a-geometry"></a>将格式化文本转换为几何图形  

 您可以将格式化文本转换为 <xref:System.Windows.Media.Geometry> 对象，从而允许您创建其他类型的视觉对象。 例如，可以根据 <xref:System.Windows.Media.Geometry> 文本字符串的轮廓创建对象。  
  
 ![使用线性渐变画笔的文本轮廓](./media/typography-in-wpf/text-outline-linear-gradient.jpg)
  
 以下示例说明了几种通过修改已转换文本的笔划、填充和突出显示来创建悦目的视觉效果的方法。  
  
 ![对填充和笔画使用不同颜色的文本](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![笔画应用了图像画笔的文本](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![将图像画笔应用于笔划和突出显示的文本](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 当文本转换为对象时 <xref:System.Windows.Media.Geometry> ，它不再是字符的集合，您不能修改文本字符串中的字符。 但是，可修改已转换文本的笔划和填充属性，以此来影响该文本的外观。 笔划是指已转换文本的轮廓；填充是指已转换文本的轮廓的内部区域。 有关详细信息，请参阅[创建轮廓文本](how-to-create-outlined-text.md)。  
  
 您还可以将格式化文本转换为 <xref:System.Windows.Media.PathGeometry> 对象，并使用该对象突出显示文本。 例如，您可以将动画应用于对象， <xref:System.Windows.Media.PathGeometry> 以使动画遵循格式化文本的轮廓。  
  
 下面的示例显示已转换为对象的格式化文本 <xref:System.Windows.Media.PathGeometry> 。 经过动画处理的椭圆会沿着所呈现文本的笔划路径显示。  
  
 ![沿着文本路径几何图形运动的球](./media/drawing-formatted-text/sphere-following-geometry-path.gif)  
沿着文本路径几何图形运动的球  
  
 有关详细信息，请参阅[如何：为文本创建 PathGeometry 动画](/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))。  
  
 将格式化文本转换为对象后，可以为其创建其他有趣的用途 <xref:System.Windows.Media.PathGeometry> 。 例如，可剪辑视频，以便在格式化文本中显示。  
  
 ![文本路径几何图形中的视频显示](./media/drawing-formatted-text/video-displaying-text-path-geometry.png)
  
<a name="win32_migration"></a>

## <a name="win32-migration"></a>Win32 迁移  

 <xref:System.Windows.Media.FormattedText>用于绘制文本的功能与 Win32 DrawText 函数的功能类似。 对于从 Win32 API 迁移的开发人员，下表列出了 Win32 DrawText 标志和中的近似等效项 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 。  
  
|DrawText 标志|WPF 等效项|备注|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|使用 <xref:System.Windows.Media.FormattedText.Height%2A> 属性计算相应的 Win32 DrawText "y" 位置。|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|使用 <xref:System.Windows.Media.FormattedText.Height%2A> 和 <xref:System.Windows.Media.FormattedText.Width%2A> 属性计算输出矩形。|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|使用 <xref:System.Windows.Media.FormattedText.TextAlignment%2A> 属性，其值设置为 <xref:System.Windows.TextAlignment.Center> 。|  
|DT_EDITCONTROL|无|不需要。 间距宽度和最后一行的呈现与框架编辑控件中的相同。|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|使用 <xref:System.Windows.Media.FormattedText.Trimming%2A> 带有值的属性 <xref:System.Windows.TextTrimming.CharacterEllipsis> 。<br /><br /> 用于 <xref:System.Windows.TextTrimming.WordEllipsis> 获取具有 DT_WORD_ELIPSIS END 省略号的 Win32 DT_END_ELLIPSIS —在这种情况下，字符省略号仅出现在不适合单个行的单词上。|  
|DT_EXPAND_TABS|无|不需要。 制表符自动扩展为在每 4 个 em 后停止，这大约为 8 个与语言无关的字符的宽度。|  
|DT_EXTERNALLEADING|无|不需要。 行距中始终包括外部间隙。 使用 <xref:System.Windows.Media.FormattedText.LineHeight%2A> 属性可创建用户定义的行距。|  
|DT_HIDEPREFIX|无|不支持。 构造对象之前，请从字符串中删除 "&" <xref:System.Windows.Media.FormattedText> 。|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|这是默认文本对齐方式。 使用 <xref:System.Windows.Media.FormattedText.TextAlignment%2A> 属性，其值设置为 <xref:System.Windows.TextAlignment.Left> 。 （仅限 WPF）|  
|DT_MODIFYSTRING|无|不支持。|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|剪辑不会自动发生。 如果要剪裁文本，请使用 <xref:System.Windows.Media.Visual.VisualClip%2A> 属性。|  
|DT_NOFULLWIDTHCHARBREAK|无|不支持。|  
|DT_NOPREFIX|无|不需要。 字符串中的“&”字符始终作为正常字符处理。|  
|DT_PATHELLIPSIS|无|使用 <xref:System.Windows.Media.FormattedText.Trimming%2A> 带有值的属性 <xref:System.Windows.TextTrimming.WordEllipsis> 。|  
|DT_PREFIX|无|不支持。 如果要将下划线用于文本（如快捷键或链接），请使用 <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A> 方法。|  
|DT_PREFIXONLY|无|不支持。|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|使用 <xref:System.Windows.Media.FormattedText.TextAlignment%2A> 属性，其值设置为 <xref:System.Windows.TextAlignment.Right> 。 （仅限 WPF）|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|将 <xref:System.Windows.Media.FormattedText.FlowDirection%2A> 属性设置为 <xref:System.Windows.FlowDirection.RightToLeft>。|  
|DT_SINGLELINE|无|不需要。 <xref:System.Windows.Media.FormattedText> 除非 <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> 设置了属性，或者文本包含回车符/换行符 (CR/LF) ，否则对象将表现为单行控件。|  
|DT_TABSTOP|无|不支持用户定义的制表位位置。|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|不需要。 上对齐是默认设置。 可以通过使用属性来定义其他垂直定位值 <xref:System.Windows.Media.FormattedText.Height%2A> ，以便计算相应的 Win32 DrawText "y" 位置。|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|使用 <xref:System.Windows.Media.FormattedText.Height%2A> 属性计算相应的 Win32 DrawText "y" 位置。|  
|DT_WORDBREAK|无|不需要。 自动对对象进行断字 <xref:System.Windows.Media.FormattedText> 。 无法禁用它。|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|使用 <xref:System.Windows.Media.FormattedText.Trimming%2A> 带有值的属性 <xref:System.Windows.TextTrimming.WordEllipsis> 。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.FormattedText>
- [WPF 中的文档](documents-in-wpf.md)
- [WPF 中的版式](typography-in-wpf.md)
- [创建空心文本](how-to-create-outlined-text.md)
- [如何：为文本创建 PathGeometry 动画](/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))
