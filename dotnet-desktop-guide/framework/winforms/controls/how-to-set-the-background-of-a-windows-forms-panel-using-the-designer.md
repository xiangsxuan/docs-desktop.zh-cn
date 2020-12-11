---
title: 使用设计器设置面板的背景
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 8bdefba433632f7ba02f549a549c52c7aa56c2d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972668"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>如何：使用设计器设置 Windows 窗体面板的背景

Windows 窗体 <xref:System.Windows.Forms.Panel> 控件可以同时显示背景色和背景图像。 <xref:System.Windows.Forms.Control.BackColor%2A>属性为面板中包含的控件（如标签和单选按钮）设置背景色。 如果 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 未设置该属性，则所 <xref:System.Windows.Forms.Control.BackColor%2A> 选内容将填充所有面板。 如果 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 设置了属性，则该图像将显示在面板中包含的控件后。

下面的过程需要一个具有包含控件的窗体的 **Windows 应用程序** 项目 <xref:System.Windows.Forms.Panel> 。 有关如何在 Visual Studio 中设置此类项目的信息，请参阅 [如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 和 [如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

## <a name="set-the-background-in-the-windows-forms-designer"></a>在 Windows 窗体设计器中设置背景

1. 在 Visual Studio 中打开项目，然后选择 <xref:System.Windows.Forms.Panel> 控件。

2. 在 " **属性** " 窗口中，单击属性旁边的箭头按钮， <xref:System.Windows.Forms.Control.BackColor%2A> 以显示带有三个选项卡的窗口。

3. 选择 " **自定义** " 选项卡以显示颜色调色板。

4. 选择 " **Web** " 或 " **系统** " 选项卡以显示颜色的预定义名称列表，然后选择一种颜色。

5. 在 " **属性** " 窗口中，单击属性旁边的箭头按钮 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 。

6. 在 " **打开** " 对话框中，选择要显示的文件。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [面板控件](panel-control-windows-forms.md)
- [Panel 控件概述](panel-control-overview-windows-forms.md)
- [如何：通过使用设计器使用 Windows 窗体 Panel 控件对控件进行分组](group-controls-with-wf-panel-control-using-the-designer.md)
