---
title: 在设计时排列 Windows 窗体上的 WPF 内容
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
ms.openlocfilehash: 9977edf657468ecb5269d22df838f8fedc79e461
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957495"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="1eb5a-102">演练：在设计时在 Windows 窗体上排列 WPF 内容</span><span class="sxs-lookup"><span data-stu-id="1eb5a-102">Walkthrough: Arrange WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="1eb5a-103">本文介绍如何使用 Windows 窗体布局功能（如锚定和对齐线）将 Windows Presentation Foundation (WPF) 控件。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-103">This article shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1eb5a-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="1eb5a-104">Prerequisites</span></span>

<span data-ttu-id="1eb5a-105">若要完成本演练，必须具有 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="1eb5a-106">创建项目</span><span class="sxs-lookup"><span data-stu-id="1eb5a-106">Create the project</span></span>

<span data-ttu-id="1eb5a-107">打开 Visual Studio，并在名为的 Visual Basic 或 Visual c # 中创建新的 Windows 窗体应用程序项目 `ArrangeElementHost` 。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>

> [!NOTE]
> <span data-ttu-id="1eb5a-108">承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control"></a><span data-ttu-id="1eb5a-109">创建 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="1eb5a-109">Create the WPF control</span></span>

<span data-ttu-id="1eb5a-110">将 WPF 控件添加到项目后，就可以在窗体上对其进行排列。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-110">After you add a WPF control to the project, you can arrange it on the form.</span></span>

1. <span data-ttu-id="1eb5a-111">将新的 WPF <xref:System.Windows.Controls.UserControl> 添加到项目。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-111">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="1eb5a-112">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="1eb5a-113">有关详细信息，请参阅 [演练：在设计时在 Windows 窗体上创建新的 WPF 内容](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="1eb5a-114">在设计视图中，请确保已选中 `UserControl1`。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="1eb5a-115">在 " **属性** " 窗口中，将和属性的值设置 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> 为 **200**。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="1eb5a-116">将属性的值设置 <xref:System.Windows.Controls.Control.Background%2A> 为 **蓝色**。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-116">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

5. <span data-ttu-id="1eb5a-117">生成项目。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-117">Build the project.</span></span>

## <a name="host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="1eb5a-118">在布局面板中承载 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="1eb5a-118">Host WPF controls in a layout panel</span></span>

<span data-ttu-id="1eb5a-119">在布局面板中使用 WPF 控件与使用其他 Windows 窗体控件的方式可以相同。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-119">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>

1. <span data-ttu-id="1eb5a-120">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-120">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="1eb5a-121">在 " **工具箱**" 中，将 <xref:System.Windows.Forms.TableLayoutPanel> 控件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-121">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>

3. <span data-ttu-id="1eb5a-122">在 <xref:System.Windows.Forms.TableLayoutPanel> 控件的智能标记面板上，选择 " **删除最后一行**"。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-122">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>

4. <span data-ttu-id="1eb5a-123">将 <xref:System.Windows.Forms.TableLayoutPanel> 控件的大小调整为更大的宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-123">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>

5. <span data-ttu-id="1eb5a-124">在 " **工具箱**" 中，双击 `UserControl1` 以 `UserControl1` 在控件的第一个单元格中创建的实例 <xref:System.Windows.Forms.TableLayoutPanel> 。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-124">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="1eb5a-125">`UserControl1` 的实例承载在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-125">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

6. <span data-ttu-id="1eb5a-126">在 " **工具箱**" 中，双击 `UserControl1` 以在控件的第二个单元格中创建另一个实例 <xref:System.Windows.Forms.TableLayoutPanel> 。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-126">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="1eb5a-127">在 " **文档大纲** " 窗口中，选择 `tableLayoutPanel1` 。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-127">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span>

8. <span data-ttu-id="1eb5a-128">在 " **属性** " 窗口中，将属性的值设置 <xref:System.Windows.Forms.Control.Padding%2A> 为 **10、10、10、10**。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-128">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to **10, 10, 10, 10**.</span></span>

   <span data-ttu-id="1eb5a-129">调整两个 <xref:System.Windows.Forms.Integration.ElementHost> 控件的大小以适应新的布局。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-129">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>

## <a name="use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="1eb5a-130">使用对齐线对齐 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="1eb5a-130">Use snaplines to align WPF controls</span></span>

<span data-ttu-id="1eb5a-131">使用对齐线能够轻松对齐窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-131">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="1eb5a-132">还可以使用对齐线对齐 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-132">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="1eb5a-133">有关详细信息，请参阅 [演练：使用对齐线排列 Windows 窗体上的控件](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-133">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

1. <span data-ttu-id="1eb5a-134">从 " **工具箱**" 中，将的实例拖 `UserControl1` 到窗体上，并将其放在控件下的空间中 <xref:System.Windows.Forms.TableLayoutPanel> 。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-134">From the **Toolbox**, drag an instance of `UserControl1` onto the form, and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="1eb5a-135">`UserControl1` 的实例承载在名为 `elementHost3` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-135">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>

2. <span data-ttu-id="1eb5a-136">使用对齐线，将 `elementHost3` 的左边缘与 <xref:System.Windows.Forms.TableLayoutPanel> 控件的左边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-136">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="1eb5a-137">使用对齐线，将 `elementHost3` 按与 <xref:System.Windows.Forms.TableLayoutPanel> 控件相同的宽度排列。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-137">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="1eb5a-138">朝着 <xref:System.Windows.Forms.TableLayoutPanel> 控件移动 `elementHost3`，直到控件间显示居中对齐线。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-138">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>

5. <span data-ttu-id="1eb5a-139">在 " **属性** " 窗口中，将 "Margin" 属性的值设置为 **20、20、20、20**。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-139">In the **Properties** window, set the value of the Margin property to **20, 20, 20, 20**.</span></span>

6. <span data-ttu-id="1eb5a-140">向远离 <xref:System.Windows.Forms.TableLayoutPanel> 控件的方向移动 `elementHost3`，直到再次显示居中对齐线。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-140">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="1eb5a-141">现在，居中对齐线指示边距为 20。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-141">The center snapline now indicates a margin of 20.</span></span>

7. <span data-ttu-id="1eb5a-142">向 `elementHost3` 右移动，直到其左边缘与的左边缘对齐 `elementHost1` 。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-142">Move `elementHost3` to the right until its left edge aligns with the left edge of `elementHost1`.</span></span>

8. <span data-ttu-id="1eb5a-143">更改 `elementHost3` 的宽度，直到其右边缘与 `elementHost2` 的右边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-143">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>

## <a name="anchor-and-dock-wpf-controls"></a><span data-ttu-id="1eb5a-144">定位和停靠 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="1eb5a-144">Anchor and dock WPF controls</span></span>

<span data-ttu-id="1eb5a-145">窗体上承载的 WPF 控件具有与其他 Windows 窗体控件相同的锚定和停靠行为。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-145">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>

1. <span data-ttu-id="1eb5a-146">选择 `elementHost1`。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-146">Select `elementHost1`.</span></span>

2. <span data-ttu-id="1eb5a-147">在 " **属性** " 窗口中，将 <xref:System.Windows.Forms.Control.Anchor%2A> 属性设置为 **顶部、底部、左侧和右侧**。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-147">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>

3. <span data-ttu-id="1eb5a-148">将 <xref:System.Windows.Forms.TableLayoutPanel> 控件的大小调整为更大。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-148">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>

   <span data-ttu-id="1eb5a-149">调整 `elementHost1` 控件大小，以填充单元格。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-149">The `elementHost1` control resizes to fill the cell.</span></span>

4. <span data-ttu-id="1eb5a-150">选择 `elementHost2`。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-150">Select `elementHost2`.</span></span>

5. <span data-ttu-id="1eb5a-151">在 " **属性** " 窗口中，将属性的值设置 <xref:System.Windows.Forms.Control.Dock%2A> 为 <xref:System.Windows.Forms.DockStyle.Fill> 。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-151">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="1eb5a-152">调整 `elementHost2` 控件大小，以填充单元格。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-152">The `elementHost2` control resizes to fill the cell.</span></span>

6. <span data-ttu-id="1eb5a-153">选择 <xref:System.Windows.Forms.TableLayoutPanel> 控件。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-153">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="1eb5a-154">将其 <xref:System.Windows.Forms.Control.Dock%2A> 属性的值设置为 <xref:System.Windows.Forms.DockStyle.Top>。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-154">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>

8. <span data-ttu-id="1eb5a-155">选择 `elementHost3`。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-155">Select `elementHost3`.</span></span>

9. <span data-ttu-id="1eb5a-156">将其 <xref:System.Windows.Forms.Control.Dock%2A> 属性的值设置为 <xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-156">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="1eb5a-157">调整 `elementHost3` 控件大小，以填充窗体上的剩余空间。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-157">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>

10. <span data-ttu-id="1eb5a-158">调整窗体大小。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-158">Resize the form.</span></span>

    <span data-ttu-id="1eb5a-159">所有三个 <xref:System.Windows.Forms.Integration.ElementHost> 控件将相应地调整大小。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-159">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>

    <span data-ttu-id="1eb5a-160">有关详细信息，请参阅 [如何：在 TableLayoutPanel 控件中锚定和停靠子控件](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1eb5a-160">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1eb5a-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1eb5a-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="1eb5a-162">如何：在 TableLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="1eb5a-162">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="1eb5a-163">如何：设计时将控件与窗体边缘对齐</span><span class="sxs-lookup"><span data-stu-id="1eb5a-163">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [<span data-ttu-id="1eb5a-164">演练：使用对齐线在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="1eb5a-164">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="1eb5a-165">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="1eb5a-165">Migration and Interoperability</span></span>](/dotnet/framework/wpf/advanced/migration-and-interoperability)
- [<span data-ttu-id="1eb5a-166">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="1eb5a-166">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="1eb5a-167">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="1eb5a-167">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
