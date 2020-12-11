---
title: 如何：在 TableLayoutPanel 控件中跨行和跨列
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: a215b2b4e05bab5c81d2779d4b67d5b9d57b6ba5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972649"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>如何：在 TableLayoutPanel 控件中跨行和跨列
控件中的控件 <xref:System.Windows.Forms.TableLayoutPanel> 可以跨越相邻的行和列。

## <a name="to-span-columns-and-rows"></a>跨列和行

1. 从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。

2. 将 <xref:System.Windows.Forms.Button> 控件从 " **工具箱** " 拖放到控件的左上角单元格中 <xref:System.Windows.Forms.TableLayoutPanel> 。

3. 将 <xref:System.Windows.Forms.Button> 控件的 **ColumnSpan** 属性设置为 **2**。 请注意，该 <xref:System.Windows.Forms.Button> 控件跨越第一列和第二列。

4. 将 <xref:System.Windows.Forms.Button> 控件的 **RowSpan** 属性设置为 **2**。 请注意，该 <xref:System.Windows.Forms.Button> 控件跨越第一行和第二行。

5. 将 <xref:System.Windows.Forms.Button> 控件的 **ColumnSpan** 属性设置为 **1**。 请注意， <xref:System.Windows.Forms.Button> 控件将移到第一列中，并跨越第一行和第二行。

## <a name="see-also"></a>另请参阅

- [TableLayoutPanel 控件](tablelayoutpanel-control-windows-forms.md)
