---
title: 如何：在 TableLayoutPanel 控件中锚定和停靠子控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock
helpviewer_keywords:
- layout [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
- TableLayoutPanel control [Windows Forms], child controls
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
ms.openlocfilehash: 0e565b56c31d0776f6e89bbbe0b0681ae184758e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971275"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control"></a>如何：在 TableLayoutPanel 控件中锚定和停靠子控件
<xref:System.Windows.Forms.TableLayoutPanel> 控件支持其子控件中的 <xref:System.Windows.Forms.Control.Anchor%2A> 和 <xref:System.Windows.Forms.Control.Dock%2A> 属性。  
  
### <a name="to-align-a-child-control-in-a-tablelayoutpanel-cell"></a>在 TableLayoutPanel 单元格中对齐子控件  
  
1. 在窗体上创建一个 <xref:System.Windows.Forms.TableLayoutPanel> 控件。  
  
2. 将 <xref:System.Windows.Forms.TableLayoutPanel> 控件的和属性的值 <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> 设置 <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> 为 **1**。  
  
3. 在 <xref:System.Windows.Forms.TableLayoutPanel> 控件中创建一个 <xref:System.Windows.Forms.Button> 控件。 <xref:System.Windows.Forms.Button> 占据单元格的左上角。  
  
4. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性值更改为 `Left`。 <xref:System.Windows.Forms.Button> 控件移动，以便与单元格的左边框对齐。  
  
    > [!NOTE]
    > 此行为与其他容器控件的行为不同。 在其他容器控件中，设置 <xref:System.Windows.Forms.Control.Anchor%2A> 属性后子控件并不移动，而且锚定控件与父容器边界之间的距离在设置 <xref:System.Windows.Forms.Control.Anchor%2A> 属性后是固定的。  
  
5. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性值更改为 `Top, Left`。 <xref:System.Windows.Forms.Button> 控件移动，以占据单元格的左上角。  
  
6. 重复步骤5，将 `Top, Right` <xref:System.Windows.Forms.Button> 控件移动到单元格的右上角。 使用 `Bottom, Left` 和 `Bottom, Right` 值重复步骤。  
  
### <a name="to-stretch-a-child-control-in-a-tablelayoutpanel-cell"></a>若要对齐 TableLayoutPanel 单元格中的某个子控件  
  
1. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性值更改为 `Left, Right`。 调整 <xref:System.Windows.Forms.Button> 控件的大小，以便在单元格中拉伸。  
  
    > [!NOTE]
    > 此行为与其他容器控件的行为不同。 在其他容器控件中，当 <xref:System.Windows.Forms.Control.Anchor%2A> 属性设置为或时，不调整子控件的大小 `Left, Right` `Top, Bottom` 。  
  
2. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性值更改为 `Top, Bottom`。 调整 <xref:System.Windows.Forms.Button> 控件的大小，以便在单元格中自上而下进行拉伸。  
  
3. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性值更改为 `Top, Bottom, Left, Right`。 调整 <xref:System.Windows.Forms.Button> 控件的大小以填充单元格。  
  
4. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性值更改为 `None`。 调整 <xref:System.Windows.Forms.Button> 控件控件的大小并在单元格中居中。  
  
5. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Dock%2A> 属性值更改为 <xref:System.Windows.Forms.DockStyle.Left>。 <xref:System.Windows.Forms.Button> 控件移动，以便与单元格的左边框对齐。 <xref:System.Windows.Forms.Button> 控件的宽度不变，但调整其高度以垂直填充单元格。  
  
    > [!NOTE]
    > 这与其他容器控件中发生的行为相同。  
  
6. 将 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Dock%2A> 属性值更改为 <xref:System.Windows.Forms.DockStyle.Fill>。 调整 <xref:System.Windows.Forms.Button> 控件的大小以填充单元格。  
  
## <a name="example"></a>示例  
 下图显示了在五个单独的 <xref:System.Windows.Forms.TableLayoutPanel> 单元格中锚定的五个按钮。  
  
 ![TableLayoutPanel 锚定](./media/vs-tlpanchor.gif "VS_TLPanchor")  
  
 下图显示了在四个单独的 <xref:System.Windows.Forms.TableLayoutPanel> 单元格的角落中锚定的四个按钮。  
  
 ![TableLayoutPanel 锚定](./media/vs-tlpanchor2.gif "VS_TLPanchor2")  
  
 下图显示了在三个单独的 <xref:System.Windows.Forms.TableLayoutPanel> 单元格中通过锚定而拉伸的三个按钮。  
  
 ![TableLayoutPanel 锚定](./media/vs-tlpanchor3.gif "VS_TLPAnchor3")  
  
 下面的代码示例演示 <xref:System.Windows.Forms.TableLayoutPanel> 控件中 <xref:System.Windows.Forms.Button> 控件的 <xref:System.Windows.Forms.Control.Anchor%2A> 属性值的所有组合。  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.TableLayoutPanel>
- [TableLayoutPanel 控件](tablelayoutpanel-control-windows-forms.md)
