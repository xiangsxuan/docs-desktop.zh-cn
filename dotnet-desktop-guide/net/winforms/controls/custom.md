---
title: 自定义控件的类型
description: 了解可在 .NET 的 Windows 窗体中创建的不同类型的自定义控件。
ms.date: 10/26/2020
ms.topic: overview
f1_keywords:
- UserControl
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.openlocfilehash: 25430adf6efbb4c1f323496ce46cdea5aa0bb95c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941960"
---
# <a name="types-of-custom-controls-windows-forms-net"></a>自定义控件的类型（Windows 窗体 .NET）

可使用 Windows 窗体开发和实现新的控件。 可以创建新的用户控件，通过继承来修改现有控件，并编写可自行进行绘制的自定义控件。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

确定创建何种类型的控件可能令人困惑。 本文重点介绍各种可继承控件之间的差异，并提供有关如何为项目选择某种特定控件的信息。

<table>
<thead>
  <tr>
    <th>如果出现如下情况</th>
    <th>创建以下内容</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>
        <ul>
            <li>你想要将多个 Windows 窗体控件的功能组合到单个可重用单元。</li>
        </ul>
    </td>
    <td><a href="#composite-controls">复合控件</a>，方式是从 <a href="/dotnet/api/system.windows.forms.usercontrol">System.Windows.Forms.UserControl</a> 继承。</td>
  </tr>
  <tr>
    <td>
        <ul>
            <li>大部分所需功能与现有的 Windows 窗体控件相同。</li>
            <li>你不需要自定义图形用户界面，或者想为现有控件设计一个新的图形用户界面。</li>
        </ul>
    </td>
    <td><a href="#extended-controls">扩展控件</a>，方式是从某一特定 Windows 窗体控件继承。</td>
  </tr>
  <tr>
    <td>
        <ul>
            <li>你想要提供控件的自定义图形表示形式。</li>
            <li>你需要实现不能通过标准控件实现的自定义功能。</li>
        </ul>
    </td>
    <td><a href="#custom-controls">自定义控件</a>，方式是从 <a href="/dotnet/api/system.windows.forms.control">System.Windows.Forms.Control</a> 继承。</td>
  </tr>
</tbody>
</table>

## <a name="base-control-class"></a>基控件类

<xref:System.Windows.Forms.Control> 类是 Windows 窗体控件的基类。 它提供了在 Windows 窗体应用程序中进行可视化显示所需的基础结构，并提供了以下功能：

- 公开窗口句柄。
- 管理消息路由。
- 提供鼠标和键盘事件，以及许多其他用户界面事件。
- 提供高级布局功能。
- 包含特定于可视化显示的多个属性，如 <xref:System.Windows.Forms.Control.ForeColor%2A>、<xref:System.Windows.Forms.Control.BackColor%2A>、<xref:System.Windows.Forms.Control.Height%2A> 和 <xref:System.Windows.Forms.Control.Width%2A>。
- 为 Windows 窗体控件充当 Microsoft® ActiveX® 控件提供必需的安全性和线程支持。

由于基类提供了大量基础结构，因此开发你自己的 Windows 窗体控件相对比较简单。

## <a name="composite-controls"></a>复合控件

复合控件是封装在公共容器内的 Windows 窗体控件的集合。 这种控件有时称为用户控件。 其包含的控件称为构成控件。

复合控件包含与每个包含的 Windows 窗体控件相关联的所有固有功能，允许选择性地公开和绑定它们的属性。 复合控件还提供了大量的默认键盘处理功能，用户不需要进行任何额外的开发。

例如，可以生成复合控件，以显示来自数据库的客户地址数据。 此控件将包括用于显示数据库字段的 <xref:System.Windows.Forms.DataGridView> 控件、用于处理到数据源的绑定的 <xref:System.Windows.Forms.BindingSource>，以及用于在记录之间移动的 <xref:System.Windows.Forms.BindingNavigator> 控件。 可以选择性地公开数据绑定属性，还可以将整个控件打包并在不同应用程序之间重复使用。<!-- TODO For an example of this kind of composite control, see [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).-->

若要创作复合控件，请从 <xref:System.Windows.Forms.UserControl> 类派生。 基类 <xref:System.Windows.Forms.UserControl> 为子控件提供了键盘路由，并使子控件可以作为组进行工作。<!-- TODO For more information, see [Developing a Composite Windows Forms Control](developing-a-composite-windows-forms-control.md).-->

## <a name="extended-controls"></a>扩展控件

你可以从任何现有的 Windows 窗体控件派生继承的控件。 使用此方法，你可以保留 Windows 窗体控件的所有固有功能，然后通过添加自定义属性、方法或其他功能来扩展该功能。 可以使用此选项重写基控件的绘制逻辑，然后通过更改该控件的外观来扩展其用户界面。

例如，可以创建一个由 <xref:System.Windows.Forms.Button> 控件派生的控件，并用它来跟踪用户的单击次数。

在某些控件中，也可以通过重写基类的 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法为控件的图形用户界面添加自定义外观。 对于跟踪单击次数的扩展按钮，可以重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法以调用 <xref:System.Windows.Forms.Control.OnPaint%2A> 的基实现，然后在 <xref:System.Windows.Forms.Button> 控件的工作区的一角绘制单击计数。

## <a name="custom-controls"></a>自定义控件

创建控件的另一种方法是通过从 <xref:System.Windows.Forms.Control> 继承，从头开始充分创建一个控件。 <xref:System.Windows.Forms.Control> 类提供控件所需的所有基本功能（包括鼠标和键盘处理事件），但不提供特定于控件的功能或图形界面。

相比从 <xref:System.Windows.Forms.UserControl> 或现有 Windows 窗体控件继承来说，通过从 <xref:System.Windows.Forms.Control> 类继承来创建控件需要花费更多心思和精力。 由于用户还需执行大量的实现，因此，控件可以具有比复合控件或扩展控件更好的灵活性，而且可以使控件完全满足自己的需要。

若要实现自定义控件，必须编写该控件的 <xref:System.Windows.Forms.Control.OnPaint%2A> 事件的代码，以及所需的任何功能特定的代码。 还可以重写 <xref:System.Windows.Forms.Control.WndProc%2A> 方法并直接处理窗口消息。 这是创建控件的最强大的方法，但若要有效地使用此技术，需熟悉 Microsoft Win32® API。

时钟控件即是一个自定义控件，它复制模拟时钟的外观和行为。 调用自定义绘制来使指针移动，以响应来自内部 <xref:System.Windows.Forms.Timer> 组件的 <xref:System.Windows.Forms.Timer.Tick> 事件。<!-- TODO For more information, see [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md).-->

## <a name="activex-controls"></a>ActiveX 控件

尽管 Windows 窗体基础结构已为承载 Windows 窗体控件进行了优化，但仍可以使用 ActiveX 控件。 Visual Studio 中对此任务提供支持。<!-- TODO For more information, see [How to: Add ActiveX Controls to Windows Forms](how-to-add-activex-controls-to-windows-forms.md).-->

## <a name="windowless-controls"></a>无窗口控件

Microsoft Visual Basic® 6.0 和 ActiveX 技术支持无窗口控件。 Windows 窗体中不支持无窗口控件。

## <a name="custom-design-experience"></a>自定义设计体验

如果需要实现自定义设计时体验，可以创作自己的设计器。 对于复合控件，从 <xref:System.Windows.Forms.Design.ParentControlDesigner> 或 <xref:System.Windows.Forms.Design.DocumentDesigner> 类派生自定义设计器类。 对于扩展控件和自定义控件，从 <xref:System.Windows.Forms.Design.ControlDesigner> 类派生自定义设计器类。

使用 <xref:System.ComponentModel.DesignerAttribute> 将控件与设计器关联。

以下信息已过时，但可能会对你有所帮助。

- [(Visual Studio 2013) 扩展设计时支持](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))。
- [(Visual Studio 2013) 如何：创建利用设计时功能的 Windows 窗体控件](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))。

## <a name="see-also"></a>另请参阅

- [使用控件的概述（Windows 窗体 .NET）](overview.md)

<!-- TODO: link to the ..\custom-controls\ content 

- [Developing Custom Windows Forms Controls](developing-custom-windows-forms-controls.md)
- [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md)
- [Developing a Composite Windows Forms Control](developing-a-composite-windows-forms-control.md)
-->
