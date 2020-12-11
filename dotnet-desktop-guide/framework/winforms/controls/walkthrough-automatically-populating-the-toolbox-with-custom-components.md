---
title: 演练：使用自定义组件自动填充工具箱
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 3ceebbf07c0241996479a6f7f72ab19f4cd9aa05
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972588"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a>演练：使用自定义组件自动填充工具箱

如果组件由当前打开的解决方案中的项目定义，则它们将自动显示在 " **工具箱**" 中，无需执行任何操作。 你还可以通过使用 "[选择工具箱项" 对话框 (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))来使用自定义组件手动填充 **工具箱**，但 **工具箱** 会考虑解决方案生成输出中具有以下所有特性的项：

- 实现 <xref:System.ComponentModel.IComponent> ;

- 未 <xref:System.ComponentModel.ToolboxItemAttribute> 将设置为 `false` ;

- 未 <xref:System.ComponentModel.DesignTimeVisibleAttribute> 将设置为 `false` 。

> [!NOTE]
> **工具箱** 不跟踪引用链，因此它不会显示您的解决方案中不是由项目生成的项。

此演练演示生成组件后，自定义组件自动出现在 **工具箱** 中的方式。 本演练涉及以下任务：

- 创建 Windows 窗体项目。

- 创建自定义组件。

- 创建自定义组件的实例。

- 卸载和重新加载自定义组件。

完成后，你将看到 " **工具箱** " 中填充了已创建的组件。

## <a name="create-the-project"></a>创建项目

1. 在 visual Studio 中，创建一个名为 " `ToolboxExample` (**文件**" "  >  **新建**  >  **项目**" "  >  **Visual c #** " 或 **Visual Basic**  >  **经典桌面**  >  **Windows 窗体应用程序**) 的基于 Windows 的应用程序项目

2. 向项目中添加新组件。 将其命名为 `DemoComponent`。

     有关详细信息，请参阅 [如何：添加新项目项](/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))。

3. 生成项目。

4. 从 " **工具** " 菜单中，单击 " **选项** " 项。 单击 " **Windows 窗体设计器**" 项下的 "**常规**"，并确保 " **AutoToolboxPopulate** " 选项设置为 **True**。

## <a name="create-an-instance-of-a-custom-component"></a>创建自定义组件的实例

下一步是在窗体上创建自定义组件的实例。 因为 **工具箱** 会自动为新组件提供帐户，所以这与创建任何其他组件或控件一样简单。

1. 在 **窗体设计器** 中打开项目的窗体。

2. 在 " **工具箱**" 中，单击名为 " **ToolboxExample 组件**" 的新选项卡。

     单击该选项卡后，你将看到 **DemoComponent**。

    > [!NOTE]
    > 出于性能原因，" **工具箱** " 的 "自动填充" 区域中的组件不显示自定义位图，并且 <xref:System.Drawing.ToolboxBitmapAttribute> 不受支持。 若要在 **工具箱** 中显示自定义组件的图标，请使用 " **选择工具箱项** " 对话框加载组件。

3. 将组件拖到窗体上。

     将创建组件的实例，并将其添加到 **组件栏**。

## <a name="unload-and-reload-a-custom-component"></a>卸载和重新加载自定义组件

**工具箱** 会考虑每个加载的项目中的组件，并且在卸载项目时，它将删除对项目的组件的引用。

1. 从解决方案中卸载项目。

     有关卸载项目的详细信息，请参阅 [如何：卸载和重新加载项目](/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100))。 如果系统提示您保存，请选择 **"是"**。

2. 向解决方案中添加一个新的 **Windows 应用程序** 项目。 在 **设计器** 中打开窗体。

     以前项目中的 " **ToolboxExample 组件** " 选项卡现在已消失。

3. 重新加载 `ToolboxExample` 项目。

     " **ToolboxExample 组件** " 选项卡现在再次出现。

## <a name="next-steps"></a>后续步骤

此演练演示 **工具箱** 会考虑项目的组件，但 **工具箱** 也会考虑控件。 通过在你的解决方案中添加和移除控件项目，试验你自己的自定义控件。

## <a name="see-also"></a>另请参阅

- [“选项”对话框 -&gt;“Windows 窗体设计器”-&gt;“常规”](/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))
- [如何：操作工具箱选项卡](/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))
- [“选择工具箱项”对话框 (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))
- [将控件放在 Windows 窗体上](putting-controls-on-windows-forms.md)
