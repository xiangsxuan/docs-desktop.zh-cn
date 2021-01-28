---
title: 从现有控件继承
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
ms.openlocfilehash: 7d9766c1bb1812cc5978221ccec42f5eb2c8c4ff
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957716"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>如何：从现有 Windows 窗体控件继承

如果想要扩展现有控件的功能，可以通过继承创建一个派生自现有控件的控件。 从现有控件继承时，将继承该控件的的所有功能和可视属性。 例如，如果您正在创建一个从继承的控件 <xref:System.Windows.Forms.Button> ，则新控件的外观和行为与标准控件完全相同 <xref:System.Windows.Forms.Button> 。 然后可以通过实现自定义方法和属性来扩展或修改新控件的功能。 在某些控件中，还可以通过重写继承控件的方法来更改该控件的可视外观 <xref:System.Windows.Forms.Control.OnPaint%2A> 。

## <a name="to-create-an-inherited-control"></a>创建继承的控件

1. 在 Visual Studio 中，创建一个新的 **Windows 窗体应用程序** 项目。

1. 从“项目”菜单中选择“添加新项”。

    “添加新项”  对话框随即出现。

1. 在“添加新项”对话框中，双击“自定义控件”。

    一个新的自定义控件将被添加到项目中。

1. 如果使用的是：

    - Visual Basic 上，单击 **解决方案资源管理器** 顶部的 " **显示所有文件**"。 展开 CustomControl1.vb，然后在“代码编辑器”中打开 CustomControl1.Designer.vb。
    - C # 中，在代码编辑器中打开 CustomControl1.cs。

1. 找到继承自的类声明 <xref:System.Windows.Forms.Control> 。

1. 将基类更改为要从中继承的控件。

     例如，如果要从继承 <xref:System.Windows.Forms.Button> ，请将类声明更改为以下内容：

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. 如果使用的是 Visual Basic，则保存并关闭 CustomControl1.Designer.vb。 在“代码编辑器”中打开 CustomControl1.vb。

1. 实现控件将纳入的任何自定义方法或属性。

1. 如果要修改控件的图形外观，请重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法。

    > [!NOTE]
    > 重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 将不允许修改所有控件的外观。 这些控件具有 Windows (完成的所有绘制，例如 <xref:System.Windows.Forms.TextBox>) 从不调用其 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法，因此永远不会使用自定义代码。 请参阅要修改的特定控件的帮助文档，查看该 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法是否可用。 有关所有 Windows 窗体控件的列表，请参阅[在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)。 如果某个控件未 <xref:System.Windows.Forms.Control.OnPaint%2A> 列出为成员方法，则不能通过重写此方法来更改其外观。 有关自定义绘制的详细信息，请参阅[自定义控件的绘制和呈现](custom-control-painting-and-rendering.md)。

    ```vb
    Protected Overrides Sub OnPaint(ByVal e As _
       System.Windows.Forms.PaintEventArgs)
       MyBase.OnPaint(e)
       ' Insert code to do custom painting.
       ' If you want to completely change the appearance of your control,
       ' do not call MyBase.OnPaint(e).
    End Sub
    ```

    ```csharp
    protected override void OnPaint(PaintEventArgs pe)
    {
       base.OnPaint(pe);
       // Insert code to do custom painting.
       // If you want to completely change the appearance of your control,
       // do not call base.OnPaint(pe).
    }
    ```

1. 保存并测试控件。

## <a name="see-also"></a>另请参阅

- [各种自定义控件](varieties-of-custom-controls.md)
- [如何：从 Control 类继承](how-to-inherit-from-the-control-class.md)
- [如何：从 UserControl 类继承](how-to-inherit-from-the-usercontrol-class.md)
- [如何：创作 Windows 窗体的控件](how-to-author-controls-for-windows-forms.md)
- [Visual Basic 中继承的事件处理程序疑难解答](/dotnet/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers)
- [演练：从 Windows 窗体控件继承](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
