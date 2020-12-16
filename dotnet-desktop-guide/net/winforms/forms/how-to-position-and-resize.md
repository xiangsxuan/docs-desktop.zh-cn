---
title: 定位窗体并重设其大小
description: 了解如何在 .NET Windows 窗体和 Visual Studio 中设置窗体的大小和位置。 大小和位置可以在 Visual Studio 设计器中设置，也可以通过代码设置。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning Windows Forms
- resizing Windows Forms
- Windows Forms, location
- Windows Forms, size
ms.openlocfilehash: 4fdaff7589669ae2e216d08feda5368835b50b5b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942009"
---
# <a name="how-to-position-and-size-a-form-windows-forms-net"></a>如何定位窗体并重设其大小（Windows 窗体 .NET）

创建窗体时，大小和位置最初设置为默认值。 窗体的默认大小通常为 800x500 像素的宽度和高度。 显示窗体时的初始位置取决于一些不同的设置。

可以在设计时使用 Visual Studio 更改窗体的大小，也可以在运行时使用代码更改窗体的大小。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="resize-with-the-designer"></a>使用设计器重设大小

在将[新窗体添加到项目](how-to-add.md)后，可以通过两种不同的方式来设置窗体的大小。 第一种方式是，使用设计器中的大小调整手柄来设置窗体大小。 通过拖动右边缘、底边缘或角，可以调整窗体的大小。

:::image type="content" source="media/how-to-position-and-resize/designer-grips.png" alt-text="右键单击解决方案资源管理器，将新窗体添加到带有调整手柄的 Windows 窗体项目中":::

在设计器处于打开状态时，第二种重设窗体大小的方法是通过“属性”窗格。 选择窗体，然后在 Visual Studio 中找到“属性”窗格。 向下滚动至“大小”并将其展开。 可以手动设置“宽度”和“高度” 。

:::image type="content" source="media/how-to-position-and-resize/designer-properties-size.png" alt-text="右键单击解决方案资源管理器，将新窗体添加到 Windows 窗体项目中":::

## <a name="resize-in-code"></a>在代码中重设大小

尽管设计器会设置窗体的起始大小，也可以通过代码来重设窗体大小。 当应用程序的某些相关内容确定窗体的默认大小不够时，使用代码来调整窗体的大小很有用。

若要重设窗体的大小，请更改 <xref:System.Windows.Forms.Form.Size%2A>，它表示窗体的宽度和高度。

### <a name="resize-the-current-form"></a>重设当前窗体的大小

只要代码在窗体的上下文中运行，就可以更改当前窗体的大小。 例如，如果 `Form1` 上有一个按钮，则单击该按钮时，将调用 `Click` 事件处理程序来重设窗体的大小：

```csharp
private void button1_Click(object sender, EventArgs e) =>
    Size = new Size(250, 200);
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Size = New Drawing.Size(250, 200)
End Sub
```

### <a name="resize-a-different-form"></a>重设其他窗体的大小

创建其他窗体后，可以使用引用该窗体的变量来更改其大小。 例如，假设有两个窗体：`Form1`（在本示例中为启动窗体）和 `Form2`。 `Form1` 有一个按钮，单击该按钮时，将调用 `Click` 事件。 此事件的处理程序创建 `Form2` 窗体的新实例、设置大小，然后显示该实例：

```csharp
private void button1_Click(object sender, EventArgs e)
{
    Form2 form = new Form2();
    form.Size = new Size(250, 200);
    form.Show();
}
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Dim form = New Form2 With {
        .Size = New Drawing.Size(250, 200)
    }
    form.Show()
End Sub
```

如果未手动设置 `Size`，则窗体的默认大小即在设计时设置的大小。

## <a name="position-with-the-designer"></a>使用设计器定位

创建并显示窗体实例时，窗体的初始位置由 <xref:System.Windows.Forms.Form.StartPosition%2A> 属性决定。 <xref:System.Windows.Forms.Form.Location%2A> 属性保存窗体的当前位置。 可以通过设计器设置这两个属性。

:::image type="content" source="media/how-to-position-and-resize/startposition.png" alt-text="突出显示起始位置的 Visual Studio 属性窗格":::

| FormStartPosition Enum | 描述                                                                                                      |
|------------------------|------------------------------------------------------------------------------------------------------------------|
| CenterParent           | 窗体在其父窗体中居中。                                                       |
| CenterScreen           | 窗体在当前显示屏中居中。                                                                     |
| 手动                 | 窗体的位置由 [Location](xref:System.Windows.Forms.Form.Location%2A) 属性决定。   |
| WindowsDefaultBounds   | 窗体位于 Windows 默认位置，且大小重设为 Windows 决定的默认大小。 |
| WindowsDefaultLocation | 窗体位于 Windows 默认位置，没有重设大小。                                        |

[CenterParent](xref:System.Windows.Forms.FormStartPosition.CenterParent) 值仅适用于多文档界面 (MDI) 子窗体或使用 <xref:System.Windows.Window.ShowDialog%2A> 方法显示的常规窗体。 `CenterParent` 不影响使用 <xref:System.Windows.Window.Show%2A> 方法显示的常规窗体。 若要让某个窗体（`form` 变量）相对于另一个窗体（`parentForm` 变量）居中，请使用以下代码：

```csharp
form.StartPosition = FormStartPosition.Manual;
form.Location = new Point(parentForm.Width / 2 - form.Width / 2 + parentForm.Location.X,
                          parentForm.Height / 2 - form.Height / 2 + parentForm.Location.Y);
form.Show();
```

```vb
form.StartPosition = Windows.Forms.FormStartPosition.CenterParent.Manual
form.Location = New Drawing.Point(parentForm.Width / 2 - form.Width / 2 + parentForm.Location.X,
                                  parentForm.Height / 2 - form.Height / 2 + parentForm.Location.Y)

form.Show()
```

## <a name="position-with-code"></a>使用代码定位

尽管可以使用设计器来设置窗体的起始位置，也可以使用代码来更改起始位置模式或手动设置位置。 如果需要相对于屏幕或其他窗体手动定位窗体并重设其大小，则使用代码来定位窗体非常有用。

### <a name="move-the-current-form"></a>移动当前窗体

只要代码在窗体的上下文中运行，就可以移动当前窗体。 例如，如果 `Form1` 上有一个按钮，则单击该按钮时，将调用 `Click` 事件处理程序。 此示例中的处理程序通过设置 <xref:System.Windows.Forms.Form.Location%2A> 属性将窗体的位置更改为屏幕的左上角：

```csharp
private void button1_Click(object sender, EventArgs e) =>
    Location = new Point(0, 0);
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Location = New Drawing.Point(0, 0)
End Sub
```

### <a name="position-a-different-form"></a>定位其他窗体

创建其他窗体后，可以使用引用该窗体的变量来更改其位置。 例如，假设有两个窗体：`Form1`（在本示例中为启动窗体）和 `Form2`。 `Form1` 有一个按钮，单击该按钮时，将调用 `Click` 事件。 此事件的处理程序创建 `Form2` 窗体的新实例并设置大小：

```csharp
private void button1_Click(object sender, EventArgs e)
{
    Form2 form = new Form2();
    form.Size = new Size(250, 200);
    form.Show();
}
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Dim form = New Form2 With {
        .Size = New Drawing.Size(250, 200)
    }
    form.Show()
End Sub
```

如果未设置 `Size`，则窗体的默认大小即在设计时设置的大小。

## <a name="see-also"></a>另请参阅

- [如何向项目添加窗体（Windows 窗体 .NET）](how-to-add.md)
- [事件概述（Windows 窗体 .NET）](events.md)
- [控件的位置和布局（Windows 窗体 .NET）](../controls/layout.md)
