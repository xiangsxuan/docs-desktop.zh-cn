---
title: TableLayoutPanel 控件中的自动调整大小行为
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
ms.openlocfilehash: daeca48c4fcfaf83d6506ba07d60ec2dcfdcace7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971324"
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a>TableLayoutPanel 控件中的自动调整大小行为
## <a name="distinct-autosize-behaviors"></a>不同的 AutoSize 行为  
 <xref:System.Windows.Forms.TableLayoutPanel>控件支持通过以下方式自动调整大小行为：  
  
- 通过 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性;  
  
- 通过 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> <xref:System.Windows.Forms.TableLayoutPanel> 控件的列和行样式的属性。  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a>具有行和列样式的 AutoSize 属性  
 下表描述了 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性和 <xref:System.Windows.Forms.TableLayoutPanel> 控件的列和行样式之间的交互。  
  
|自动调整大小|样式交互|  
|----------------------|-----------------------|  
|`false`|<xref:System.Windows.Forms.TableLayoutPanel>控件从左到右前进，并按以下顺序为列或行分配空间。<br /><br /> 1. 如果 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 属性设置为，则 <xref:System.Windows.Forms.SizeType.Absolute> 分配或指定的像素数 <xref:System.Windows.Forms.ColumnStyle.Width%2A> <xref:System.Windows.Forms.RowStyle.Height%2A> 。<br />2. 如果将 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> 属性设置为 <xref:System.Windows.Forms.SizeType.AutoSize> ，则会分配子控件的方法返回的像素数 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 。<br />3. 在 <xref:System.Windows.Forms.SizeType.Absolute> 分配所有和 <xref:System.Windows.Forms.SizeType.AutoSize> 列或行的空间后，任何设置为的列或行 <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> <xref:System.Windows.Forms.SizeType.Percent> 均用于按比例分配剩余可用空间|  
|`true`|与以前的交互类似，但 <xref:System.Windows.Forms.SizeType.Percent> 列或行的自动调整大小方面除外。<br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>控件扩展列或行以创建足够的可用空间，因此没有样式的列或行可 <xref:System.Windows.Forms.SizeType.Percent> 剪辑其内容。 <xref:System.Windows.Forms.TableLayoutPanel>控件根据或属性，按比例分配新的 <xref:System.Windows.Forms.ColumnStyle.Width%2A> 空间 <xref:System.Windows.Forms.RowStyle.Height%2A> 。|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.TableLayoutPanel>
- [TableLayoutPanel 控件概述](tablelayoutpanel-control-overview.md)
