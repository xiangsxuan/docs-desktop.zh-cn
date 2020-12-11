---
title: 在设计时开发控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 4e192983c5818ddb81ed4581d91ae61375bb808e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970076"
---
# <a name="develop-windows-forms-controls-at-design-time"></a>在设计时开发 Windows 窗体控件

.NET Framework 为控件创作者提供了丰富的控件创作技术。 作者不再局限于设计作为现有控件集合的复合控件。 通过继承，可根据现有复合控件或现有 Windows 窗体控件创建自己的控件。 还可以自己设计实现自定义绘制的控件。 这些选项对可视化界面的设计和功能赋予了很大的灵活性。 若要利用这些功能，应熟悉基于对象的编程概念。

> [!NOTE]
> 无需透彻地理解继承，但你可能会发现 [ (Visual Basic) 引用继承基础知识 ](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)会很有用。

如果要创建在 Web 窗体上使用的自定义控件，请参阅[开发自定义 ASP.NET 服务器控件](/previous-versions/aspnet/zt27tfhy(v=vs.100)).。

## <a name="in-this-section"></a>在本节中

[演练：创作复合控件](walkthrough-authoring-a-composite-control-with-visual-csharp.md)\
演示如何在 C# 中创建简单的复合控件。

[演练：从 Windows 窗体控件继承](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)\
演示如何在 C# 中使用继承创建简单的 Windows 窗体控件。

[演练：使用设计操作执行常规任务](perform-common-tasks-design-actions.md)\
演示如何在 Windows 窗体控件上使用智能标记功能。

[演练：通过 DesignerSerializationVisibilityAttribute 序列化标准类型的集合](serializing-collections-designerserializationvisibilityattribute.md)\
演示如何使用 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> 特性序列化集合。

[演练：在设计时调试自定义 Windows 窗体控件](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)\
演示如何调试 Windows 窗体控件的设计时行为。

[演练：创建利用 Visual Studio Design-Time 功能的 Windows 窗体控件](creating-a-wf-control-design-time-features.md)\
演示如何将复合控件紧密集成到设计环境中。

[如何：创作 Windows 窗体的控件](how-to-author-controls-for-windows-forms.md)\
概述实现 Windows 窗体控件的注意事项。

[如何：创作复合控件](how-to-author-composite-controls.md)\
演示如何通过继承复合控件来创建控件。

[如何：从 UserControl 类继承](how-to-inherit-from-the-usercontrol-class.md)\
概述复合控件的创建过程。

[如何：从现有 Windows 窗体控件继承](how-to-inherit-from-existing-windows-forms-controls.md)\
演示如何通过从 control 类继承来创建扩展控件 <xref:System.Windows.Forms.Button> 。

[如何：从 Control 类继承](how-to-inherit-from-the-control-class.md)\
概述如何创建扩展的控件。

[如何：在设计时将控件与窗体边缘对齐](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)\
演示如何使用属性将 <xref:System.Windows.Forms.Control.Dock%2A> 控件与它所占有窗体的边缘对齐。

[如何：在 "选择工具箱项" 对话框中显示控件](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)\
演示安装控件以将其显示在“自定义工具箱”对话框中的过程。

[如何：为控件提供工具箱位图](how-to-provide-a-toolbox-bitmap-for-a-control.md)\
演示如何使用在 <xref:System.Drawing.ToolboxBitmapAttribute> **工具箱** 中的自定义控件旁边显示一个图标。

[如何：测试 UserControl 的 Run-Time 行为](how-to-test-the-run-time-behavior-of-a-usercontrol.md)\
演示如何使用 **UserControl 测试容器** 来测试组合控件的行为。

[Windows 窗体设计器中的设计时错误](design-time-errors-in-the-windows-forms-designer.md)\
说明 Windows 窗体设计器加载失败时出现在 Microsoft Visual Studio 中的设计时错误列表的含义和用法。

[控件和组件创作疑难解答](troubleshooting-control-and-component-authoring.md)\
演示如何诊断和解决创作自定义组件或控件时可能出现的常见问题。

## <a name="reference"></a>参考

- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>

- <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>

## <a name="related-sections"></a>相关章节

[利用 .NET Framework 开发自定义 Windows 窗体控件](developing-custom-windows-forms-controls.md)\
讨论如何通过 .NET Framework 创建自己的自定义控件。

[语言独立性和 Language-Independent 组件](/dotnet/standard/language-independence-and-language-independent-components)\
介绍公共语言运行时，它旨在简化组件的创建和使用。 这种简化的一个重要方面是提高了采用不同编程语言编写的组件间的互操作性。 通过公共语言规范 (CLS) 可创建使用多个编程语言的工具和组件。

[演练：用自定义组件自动填充工具箱](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)\
描述如何在“自定义工具箱”对话框中显示组件或控件。
