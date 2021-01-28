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
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a>演练：在设计时在 Windows 窗体上排列 WPF 内容

本文介绍如何使用 Windows 窗体布局功能（如锚定和对齐线）将 Windows Presentation Foundation (WPF) 控件。

## <a name="prerequisites"></a>先决条件

若要完成本演练，必须具有 Visual Studio。

## <a name="create-the-project"></a>创建项目

打开 Visual Studio，并在名为的 Visual Basic 或 Visual c # 中创建新的 Windows 窗体应用程序项目 `ArrangeElementHost` 。

> [!NOTE]
> 承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。

## <a name="create-the-wpf-control"></a>创建 WPF 控件

将 WPF 控件添加到项目后，就可以在窗体上对其进行排列。

1. 将新的 WPF <xref:System.Windows.Controls.UserControl> 添加到项目。 使用控件类型的默认名称，`UserControl1.xaml`。 有关详细信息，请参阅 [演练：在设计时在 Windows 窗体上创建新的 WPF 内容](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。

2. 在设计视图中，请确保已选中 `UserControl1`。

3. 在 " **属性** " 窗口中，将和属性的值设置 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> 为 **200**。

4. 将属性的值设置 <xref:System.Windows.Controls.Control.Background%2A> 为 **蓝色**。

5. 生成项目。

## <a name="host-wpf-controls-in-a-layout-panel"></a>在布局面板中承载 WPF 控件

在布局面板中使用 WPF 控件与使用其他 Windows 窗体控件的方式可以相同。

1. 在 Windows 窗体设计器中打开 `Form1`。

2. 在 " **工具箱**" 中，将 <xref:System.Windows.Forms.TableLayoutPanel> 控件拖到窗体上。

3. 在 <xref:System.Windows.Forms.TableLayoutPanel> 控件的智能标记面板上，选择 " **删除最后一行**"。

4. 将 <xref:System.Windows.Forms.TableLayoutPanel> 控件的大小调整为更大的宽度和高度。

5. 在 " **工具箱**" 中，双击 `UserControl1` 以 `UserControl1` 在控件的第一个单元格中创建的实例 <xref:System.Windows.Forms.TableLayoutPanel> 。

   `UserControl1` 的实例承载在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。

6. 在 " **工具箱**" 中，双击 `UserControl1` 以在控件的第二个单元格中创建另一个实例 <xref:System.Windows.Forms.TableLayoutPanel> 。

7. 在 " **文档大纲** " 窗口中，选择 `tableLayoutPanel1` 。

8. 在 " **属性** " 窗口中，将属性的值设置 <xref:System.Windows.Forms.Control.Padding%2A> 为 **10、10、10、10**。

   调整两个 <xref:System.Windows.Forms.Integration.ElementHost> 控件的大小以适应新的布局。

## <a name="use-snaplines-to-align-wpf-controls"></a>使用对齐线对齐 WPF 控件

使用对齐线能够轻松对齐窗体上的控件。 还可以使用对齐线对齐 WPF 控件。 有关详细信息，请参阅 [演练：使用对齐线排列 Windows 窗体上的控件](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)。

1. 从 " **工具箱**" 中，将的实例拖 `UserControl1` 到窗体上，并将其放在控件下的空间中 <xref:System.Windows.Forms.TableLayoutPanel> 。

   `UserControl1` 的实例承载在名为 `elementHost3` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。

2. 使用对齐线，将 `elementHost3` 的左边缘与 <xref:System.Windows.Forms.TableLayoutPanel> 控件的左边缘对齐。

3. 使用对齐线，将 `elementHost3` 按与 <xref:System.Windows.Forms.TableLayoutPanel> 控件相同的宽度排列。

4. 朝着 <xref:System.Windows.Forms.TableLayoutPanel> 控件移动 `elementHost3`，直到控件间显示居中对齐线。

5. 在 " **属性** " 窗口中，将 "Margin" 属性的值设置为 **20、20、20、20**。

6. 向远离 <xref:System.Windows.Forms.TableLayoutPanel> 控件的方向移动 `elementHost3`，直到再次显示居中对齐线。 现在，居中对齐线指示边距为 20。

7. 向 `elementHost3` 右移动，直到其左边缘与的左边缘对齐 `elementHost1` 。

8. 更改 `elementHost3` 的宽度，直到其右边缘与 `elementHost2` 的右边缘对齐。

## <a name="anchor-and-dock-wpf-controls"></a>定位和停靠 WPF 控件

窗体上承载的 WPF 控件具有与其他 Windows 窗体控件相同的锚定和停靠行为。

1. 选择 `elementHost1`。

2. 在 " **属性** " 窗口中，将 <xref:System.Windows.Forms.Control.Anchor%2A> 属性设置为 **顶部、底部、左侧和右侧**。

3. 将 <xref:System.Windows.Forms.TableLayoutPanel> 控件的大小调整为更大。

   调整 `elementHost1` 控件大小，以填充单元格。

4. 选择 `elementHost2`。

5. 在 " **属性** " 窗口中，将属性的值设置 <xref:System.Windows.Forms.Control.Dock%2A> 为 <xref:System.Windows.Forms.DockStyle.Fill> 。

   调整 `elementHost2` 控件大小，以填充单元格。

6. 选择 <xref:System.Windows.Forms.TableLayoutPanel> 控件。

7. 将其 <xref:System.Windows.Forms.Control.Dock%2A> 属性的值设置为 <xref:System.Windows.Forms.DockStyle.Top>。

8. 选择 `elementHost3`。

9. 将其 <xref:System.Windows.Forms.Control.Dock%2A> 属性的值设置为 <xref:System.Windows.Forms.DockStyle.Fill>。

   调整 `elementHost3` 控件大小，以填充窗体上的剩余空间。

10. 调整窗体大小。

    所有三个 <xref:System.Windows.Forms.Integration.ElementHost> 控件将相应地调整大小。

    有关详细信息，请参阅 [如何：在 TableLayoutPanel 控件中锚定和停靠子控件](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [如何：在 TableLayoutPanel 控件中锚定和停靠子控件](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [如何：设计时将控件与窗体边缘对齐](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [演练：使用对齐线在 Windows 窗体上排列控件](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [迁移和互操作性](/dotnet/framework/wpf/advanced/migration-and-interoperability)
- [使用 WPF 控件](using-wpf-controls.md)
- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
