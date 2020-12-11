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
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a><span data-ttu-id="25d59-102">如何：在 MenuStrip 中显示选项按钮（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="25d59-102">How to: Display Option Buttons in a MenuStrip (Windows Forms)</span></span>

<span data-ttu-id="25d59-103">选项按钮（也称为单选按钮）与复选框类似，只是用户一次只能选择一个。</span><span class="sxs-lookup"><span data-stu-id="25d59-103">Option buttons, also known as radio buttons, are similar to check boxes except that users can select only one at a time.</span></span> <span data-ttu-id="25d59-104">尽管默认情况下 <xref:System.Windows.Forms.ToolStripMenuItem> ，类不提供选项按钮行为，但类提供了可自定义的复选框行为，以便实现控件中菜单项的选项按钮行为 <xref:System.Windows.Forms.MenuStrip> 。</span><span class="sxs-lookup"><span data-stu-id="25d59-104">Although by default the <xref:System.Windows.Forms.ToolStripMenuItem> class does not provide option-button behavior, the class does provide check-box behavior that you can customize to implement option-button behavior for menu items in a <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="25d59-105">当 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 菜单项的属性为时 `true` ，用户可以单击该项来切换选中标记的显示。</span><span class="sxs-lookup"><span data-stu-id="25d59-105">When the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property of a menu item is `true`, users can click the item to toggle the display of a check mark.</span></span> <span data-ttu-id="25d59-106"><xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>属性指示项的当前状态。</span><span class="sxs-lookup"><span data-stu-id="25d59-106">The <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property indicates the current state of the item.</span></span> <span data-ttu-id="25d59-107">若要实现基本的选项按钮行为，您必须确保在选择某一项时，将 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 之前选择的项的属性设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="25d59-107">To implement basic option-button behavior, you must ensure that when an item is selected, you set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property for the previously selected item to `false`.</span></span>

<span data-ttu-id="25d59-108">下面的过程介绍如何在继承类的类中实现此功能和附加功能 <xref:System.Windows.Forms.ToolStripMenuItem> 。</span><span class="sxs-lookup"><span data-stu-id="25d59-108">The following procedures describe how to implement this and additional functionality in a class that inherits the <xref:System.Windows.Forms.ToolStripMenuItem> class.</span></span> <span data-ttu-id="25d59-109">`ToolStripRadioButtonMenuItem`类将重写成员（例如和）， <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> 以提供选项按钮的选择行为和外观。</span><span class="sxs-lookup"><span data-stu-id="25d59-109">The `ToolStripRadioButtonMenuItem` class overrides members such as <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> and <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> to provide the selection behavior and appearance of option buttons.</span></span> <span data-ttu-id="25d59-110">此外，此类将重写 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 属性，以便禁用子菜单上的选项，除非选择了父项。</span><span class="sxs-lookup"><span data-stu-id="25d59-110">Additionally, this class overrides the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that options on a submenu are disabled unless the parent item is selected.</span></span>

## <a name="to-implement-option-button-selection-behavior"></a><span data-ttu-id="25d59-111">实现选项按钮选择行为</span><span class="sxs-lookup"><span data-stu-id="25d59-111">To implement option-button selection behavior</span></span>

1. <span data-ttu-id="25d59-112">将 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 属性初始化为 `true` 以启用项目选择。</span><span class="sxs-lookup"><span data-stu-id="25d59-112">Initialize the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true` to enable item selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. <span data-ttu-id="25d59-113">重写 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> 方法，以便在选择新项时清除对以前选定项的选择。</span><span class="sxs-lookup"><span data-stu-id="25d59-113">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> method to clear the selection of the previously selected item when a new item is selected.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. <span data-ttu-id="25d59-114">重写 <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> 方法以确保单击已选择的项将不会清除所选内容。</span><span class="sxs-lookup"><span data-stu-id="25d59-114">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> method to ensure that clicking an item that has already been selected will not clear the selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a><span data-ttu-id="25d59-115">修改选项按钮项的外观</span><span class="sxs-lookup"><span data-stu-id="25d59-115">To modify the appearance of the option-button items</span></span>

1. <span data-ttu-id="25d59-116"><xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>通过使用类，重写方法以将默认的复选标记替换为选项按钮 <xref:System.Windows.Forms.RadioButtonRenderer> 。</span><span class="sxs-lookup"><span data-stu-id="25d59-116">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method to replace the default check-mark with an option button by using the <xref:System.Windows.Forms.RadioButtonRenderer> class.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. <span data-ttu-id="25d59-117">重写 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A> 、 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A> 、 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A> 和 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> 方法以跟踪鼠标的状态，并确保 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> 方法绘制正确的选项按钮状态。</span><span class="sxs-lookup"><span data-stu-id="25d59-117">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, and <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> methods to track the state of the mouse and ensure that the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method paints the correct option-button state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a><span data-ttu-id="25d59-118">在未选择父项时禁用子菜单上的选项</span><span class="sxs-lookup"><span data-stu-id="25d59-118">To disable options on a submenu when the parent item is not selected</span></span>

1. <span data-ttu-id="25d59-119">重写 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 属性，以便在项具有值为且值为的父项时禁用该项 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> `true` <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> `false` 。</span><span class="sxs-lookup"><span data-stu-id="25d59-119">Override the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that the item is disabled when it has a parent item with both a <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> value of `true` and a <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> value of `false`.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. <span data-ttu-id="25d59-120">重写 <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> 方法以订阅 <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> 父项的事件。</span><span class="sxs-lookup"><span data-stu-id="25d59-120">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> method to subscribe to the <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event of the parent item.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. <span data-ttu-id="25d59-121">在父项事件的处理程序中 <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> ，使项无效以便用新的启用状态更新显示。</span><span class="sxs-lookup"><span data-stu-id="25d59-121">In the handler for the parent-item <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event, invalidate the item to update the display with the new enabled state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a><span data-ttu-id="25d59-122">示例</span><span class="sxs-lookup"><span data-stu-id="25d59-122">Example</span></span>

<span data-ttu-id="25d59-123">下面的代码示例提供了完整的 `ToolStripRadioButtonMenuItem` 类，以及一个 <xref:System.Windows.Forms.Form> `Program` 用于演示选项按钮行为的类和类。</span><span class="sxs-lookup"><span data-stu-id="25d59-123">The following code example provides the complete `ToolStripRadioButtonMenuItem` class, and a <xref:System.Windows.Forms.Form> class and `Program` class to demonstrate the option-button behavior.</span></span>

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a><span data-ttu-id="25d59-124">编译代码</span><span class="sxs-lookup"><span data-stu-id="25d59-124">Compiling the Code</span></span>

<span data-ttu-id="25d59-125">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="25d59-125">This example requires:</span></span>

- <span data-ttu-id="25d59-126">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="25d59-126">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="25d59-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25d59-127">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [<span data-ttu-id="25d59-128">MenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="25d59-128">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
- [<span data-ttu-id="25d59-129">如何：实现自定义 ToolStripRenderer</span><span class="sxs-lookup"><span data-stu-id="25d59-129">How to: Implement a Custom ToolStripRenderer</span></span>](how-to-implement-a-custom-toolstriprenderer.md)
