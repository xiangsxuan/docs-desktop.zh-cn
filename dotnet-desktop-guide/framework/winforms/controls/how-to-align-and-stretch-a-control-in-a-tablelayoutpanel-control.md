---
title: 如何：在 TableLayoutPanel 控件中对齐和拉伸控件
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: fd32593bcad9e3f3ef93edee8aa2659d423f9feb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971903"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a>如何：在 TableLayoutPanel 控件中对齐和拉伸控件

您可以 <xref:System.Windows.Forms.TableLayoutPanel> 使用和属性在中对齐和拉伸 <xref:System.Windows.Forms.Control.Anchor%2A> 控件 <xref:System.Windows.Forms.Control.Dock%2A> 。

## <a name="align-and-stretch-a-control"></a>对齐和拉伸控件

1. 在 Visual Studio 中，将 <xref:System.Windows.Forms.TableLayoutPanel> 控件从 " **工具箱** " 拖到窗体上。

2. 将 <xref:System.Windows.Forms.Button> 控件从 " **工具箱** " 拖放到控件的左上角单元格中 <xref:System.Windows.Forms.TableLayoutPanel> 。 <xref:System.Windows.Forms.Button>控件在单元格中居中。

3. 将控件的属性的值设置 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Anchor%2A> 为 `Left,Right` 。 <xref:System.Windows.Forms.Button>控件拉伸以匹配单元格的宽度。

4. 将控件的属性的值设置 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Anchor%2A> 为 `Top,Bottom` 。 <xref:System.Windows.Forms.Button>控件拉伸以匹配单元的高度。

5. 将控件的属性的值设置 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Dock%2A> 为 <xref:System.Windows.Forms.DockStyle.Fill> 。 <xref:System.Windows.Forms.Button>控件扩展以填充单元格。

6. 将控件的属性的值设置 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Dock%2A> 为 <xref:System.Windows.Forms.DockStyle.None> 。 <xref:System.Windows.Forms.Button>控件将恢复为其原始大小并移动到单元格的左上角。 **Windows 窗体设计器** 已将属性设置 <xref:System.Windows.Forms.Control.Anchor%2A> 为 `Top, Left` 。

7. 将控件的属性的值设置 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Anchor%2A> 为 `Bottom,Right` 。 <xref:System.Windows.Forms.Button>控件移动到单元格的右下角。

8. 将控件的属性的值设置 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Anchor%2A> 为 <xref:System.Windows.Forms.AnchorStyles.None> 。 <xref:System.Windows.Forms.Button>控件移动到单元格的中心。

## <a name="see-also"></a>另请参阅

- [TableLayoutPanel 控件](tablelayoutpanel-control-windows-forms.md)
