---
title: 如何：在设计时复制并粘贴 ElementHost 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: 82312cdc2d5bf8d81b0eb53e3e8a3fdb3319a72f
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98956910"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a>如何：复制和粘贴 ElementHost 控件

此过程演示如何在 Visual Studio 中的 Windows 窗体上复制 Windows Presentation Foundation (WPF) 控件。

1. 在 Visual Studio 中，将一个新的 WPF 添加 <xref:System.Windows.Controls.UserControl> 到 Windows 窗体项目。 使用控件类型的默认名称，`UserControl1.xaml`。 有关详细信息，请参阅 [演练：在设计时在 Windows 窗体上创建新的 WPF 内容](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。

2. 在 " **属性** " 窗口中，将的和属性的值设置 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> `UserControl1` 为 **200**。

3. 将属性的值设置 <xref:System.Windows.Controls.Control.Background%2A> 为 **蓝色**。

4. 生成项目。

5. 在 Windows 窗体设计器中打开 `Form1`。

6. 从 " **工具箱**" 中，将的实例拖 `UserControl1` 到窗体上。

   `UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。

7. `elementHost1`选中此选项后，按 **Ctrl** + **C** 将其复制到剪贴板。

8. 按 **Ctrl** + **V** 将复制的控件粘贴到窗体上。

   <xref:System.Windows.Forms.Integration.ElementHost> `elementHost2` 在窗体上创建一个名为的新控件。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [迁移和互操作性](/dotnet/framework/wpf/advanced/migration-and-interoperability)
- [使用 WPF 控件](using-wpf-controls.md)
- [在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
