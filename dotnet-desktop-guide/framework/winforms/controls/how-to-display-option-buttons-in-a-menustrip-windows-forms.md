---
title: 如何：在 MenuStrip 中显示选项按钮
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: f3010e71396ce562e9dbdefd4b75b36f3a81ffb3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972054"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>如何：在 MenuStrip 中显示选项按钮（Windows 窗体）

选项按钮（也称为单选按钮）与复选框类似，只是用户一次只能选择一个。 尽管默认情况下 <xref:System.Windows.Forms.ToolStripMenuItem> ，类不提供选项按钮行为，但类提供了可自定义的复选框行为，以便实现控件中菜单项的选项按钮行为 <xref:System.Windows.Forms.MenuStrip> 。

当 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 菜单项的属性为时 `true` ，用户可以单击该项来切换选中标记的显示。 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>属性指示项的当前状态。 若要实现基本的选项按钮行为，您必须确保在选择某一项时，将 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 之前选择的项的属性设置为 `false` 。

下面的过程介绍如何在继承类的类中实现此功能和附加功能 <xref:System.Windows.Forms.ToolStripMenuItem> 。 `ToolStripRadioButtonMenuItem`类将重写成员（例如和）， <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> 以提供选项按钮的选择行为和外观。 此外，此类将重写 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 属性，以便禁用子菜单上的选项，除非选择了父项。

## <a name="to-implement-option-button-selection-behavior"></a>实现选项按钮选择行为

1. 将 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 属性初始化为 `true` 以启用项目选择。

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. 重写 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> 方法，以便在选择新项时清除对以前选定项的选择。

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. 重写 <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> 方法以确保单击已选择的项将不会清除所选内容。

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a>修改选项按钮项的外观

1. <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>通过使用类，重写方法以将默认的复选标记替换为选项按钮 <xref:System.Windows.Forms.RadioButtonRenderer> 。

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. 重写 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A> 、 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A> 、 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A> 和 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> 方法以跟踪鼠标的状态，并确保 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> 方法绘制正确的选项按钮状态。

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>在未选择父项时禁用子菜单上的选项

1. 重写 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 属性，以便在项具有值为且值为的父项时禁用该项 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> `true` <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> `false` 。

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. 重写 <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> 方法以订阅 <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> 父项的事件。

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. 在父项事件的处理程序中 <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> ，使项无效以便用新的启用状态更新显示。

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a>示例

下面的代码示例提供了完整的 `ToolStripRadioButtonMenuItem` 类，以及一个 <xref:System.Windows.Forms.Form> `Program` 用于演示选项按钮行为的类和类。

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a>编译代码

此示例需要：

- 对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [MenuStrip 控件](menustrip-control-windows-forms.md)
- [如何：实现自定义 ToolStripRenderer](how-to-implement-a-custom-toolstriprenderer.md)
