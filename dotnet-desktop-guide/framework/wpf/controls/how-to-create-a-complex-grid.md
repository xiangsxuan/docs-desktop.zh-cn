---
title: 如何创建复杂网格
description: 示例演示如何使用网格控件创建外观类似于月历的布局。
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: ab5490d608b21fe8b29a078dc1f0147f038c27a3
ms.sourcegitcommit: bf5dd80f4d7b202afa90e90d1148402c5474d826
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "96973979"
---
# <a name="how-to-create-a-complex-grid"></a>如何创建复杂网格

此示例演示如何使用 <xref:System.Windows.Controls.Grid> 控件创建外观类似于月历的布局。

## <a name="example"></a>示例

下面的示例使用和类定义八个行和八个列 <xref:System.Windows.Controls.RowDefinition> <xref:System.Windows.Controls.ColumnDefinition> 。 它将 <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> 附加属性与元素一起使用， <xref:System.Windows.Shapes.Rectangle> 这些元素填充各种列和行的背景。 这种设计之所以可行，是因为中的每个单元都可以存在多个元素 <xref:System.Windows.Controls.Grid> ，这是与之间的一个主要区别 <xref:System.Windows.Controls.Grid> <xref:System.Windows.Documents.Table> 。

该示例对列和行使用垂直渐变， <xref:System.Windows.Shapes.Shape.Fill%2A> 以改进日历的视觉对象表示和可读性。 带样式 <xref:System.Windows.Controls.TextBlock> 的元素表示一周中的日期和天数。 <xref:System.Windows.Controls.TextBlock> 元素通过使用在 <xref:System.Windows.FrameworkElement.Margin%2A> 应用程序的样式中定义的属性和对齐属性，在单元格中绝对定位。

[!code-xaml[GridComplex#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]

下图显示了生成的控件，它是一个可自定义的日历：

![生成的控件的屏幕截图](././media/how-to-create-a-complex-grid/wpf-manual-calendar.png)

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Grid?displayProperty=nameWithType>
- <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>
- [使用纯色和渐变进行绘制概述](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [面板概述](panels-overview.md)
- [表概述](../advanced/table-overview.md)
