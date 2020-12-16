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
# <a name="how-to-position-and-size-a-form-windows-forms-net"></a><span data-ttu-id="168f7-104">如何定位窗体并重设其大小（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="168f7-104">How to position and size a form (Windows Forms .NET)</span></span>

<span data-ttu-id="168f7-105">创建窗体时，大小和位置最初设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="168f7-105">When a form is created, the size and location is initially set to a default value.</span></span> <span data-ttu-id="168f7-106">窗体的默认大小通常为 800x500 像素的宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="168f7-106">The default size of a form is generally a width and height of _800x500_ pixels.</span></span> <span data-ttu-id="168f7-107">显示窗体时的初始位置取决于一些不同的设置。</span><span class="sxs-lookup"><span data-stu-id="168f7-107">The initial location, when the form is displayed, depends on a few different settings.</span></span>

<span data-ttu-id="168f7-108">可以在设计时使用 Visual Studio 更改窗体的大小，也可以在运行时使用代码更改窗体的大小。</span><span class="sxs-lookup"><span data-stu-id="168f7-108">You can change the size of a form at design time with Visual Studio, and at run time with code.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="resize-with-the-designer"></a><span data-ttu-id="168f7-109">使用设计器重设大小</span><span class="sxs-lookup"><span data-stu-id="168f7-109">Resize with the designer</span></span>

<span data-ttu-id="168f7-110">在将[新窗体添加到项目](how-to-add.md)后，可以通过两种不同的方式来设置窗体的大小。</span><span class="sxs-lookup"><span data-stu-id="168f7-110">After [adding a new form](how-to-add.md) to the project, the size of a form is set in two different ways.</span></span> <span data-ttu-id="168f7-111">第一种方式是，使用设计器中的大小调整手柄来设置窗体大小。</span><span class="sxs-lookup"><span data-stu-id="168f7-111">First, you can set it is with the size grips in the designer.</span></span> <span data-ttu-id="168f7-112">通过拖动右边缘、底边缘或角，可以调整窗体的大小。</span><span class="sxs-lookup"><span data-stu-id="168f7-112">By dragging either the right edge, bottom edge, or the corner, you can resize the form.</span></span>

:::image type="content" source="media/how-to-position-and-resize/designer-grips.png" alt-text="右键单击解决方案资源管理器，将新窗体添加到带有调整手柄的 Windows 窗体项目中":::

<span data-ttu-id="168f7-114">在设计器处于打开状态时，第二种重设窗体大小的方法是通过“属性”窗格。</span><span class="sxs-lookup"><span data-stu-id="168f7-114">The second way you can resize the form while the designer is open, is through the properties pane.</span></span> <span data-ttu-id="168f7-115">选择窗体，然后在 Visual Studio 中找到“属性”窗格。</span><span class="sxs-lookup"><span data-stu-id="168f7-115">Select the form, then find the **Properties** pane in Visual Studio.</span></span> <span data-ttu-id="168f7-116">向下滚动至“大小”并将其展开。</span><span class="sxs-lookup"><span data-stu-id="168f7-116">Scroll down to **size** and expand it.</span></span> <span data-ttu-id="168f7-117">可以手动设置“宽度”和“高度” 。</span><span class="sxs-lookup"><span data-stu-id="168f7-117">You can set the **Width** and **Height** manually.</span></span>

:::image type="content" source="media/how-to-position-and-resize/designer-properties-size.png" alt-text="右键单击解决方案资源管理器，将新窗体添加到 Windows 窗体项目中":::

## <a name="resize-in-code"></a><span data-ttu-id="168f7-119">在代码中重设大小</span><span class="sxs-lookup"><span data-stu-id="168f7-119">Resize in code</span></span>

<span data-ttu-id="168f7-120">尽管设计器会设置窗体的起始大小，也可以通过代码来重设窗体大小。</span><span class="sxs-lookup"><span data-stu-id="168f7-120">Even though the designer sets the starting size of a form, you can resize it through code.</span></span> <span data-ttu-id="168f7-121">当应用程序的某些相关内容确定窗体的默认大小不够时，使用代码来调整窗体的大小很有用。</span><span class="sxs-lookup"><span data-stu-id="168f7-121">Using code to resize a form is useful when something about your application determines that the default size of the form is insufficient.</span></span>

<span data-ttu-id="168f7-122">若要重设窗体的大小，请更改 <xref:System.Windows.Forms.Form.Size%2A>，它表示窗体的宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="168f7-122">To resize a form, change the <xref:System.Windows.Forms.Form.Size%2A>, which represents the width and height of the form.</span></span>

### <a name="resize-the-current-form"></a><span data-ttu-id="168f7-123">重设当前窗体的大小</span><span class="sxs-lookup"><span data-stu-id="168f7-123">Resize the current form</span></span>

<span data-ttu-id="168f7-124">只要代码在窗体的上下文中运行，就可以更改当前窗体的大小。</span><span class="sxs-lookup"><span data-stu-id="168f7-124">You can change the size of the current form as long as the code is running within the context of the form.</span></span> <span data-ttu-id="168f7-125">例如，如果 `Form1` 上有一个按钮，则单击该按钮时，将调用 `Click` 事件处理程序来重设窗体的大小：</span><span class="sxs-lookup"><span data-stu-id="168f7-125">For example, if you have `Form1` with a button on it, that when clicked invokes the `Click` event handler to resize the form:</span></span>

```csharp
private void button1_Click(object sender, EventArgs e) =>
    Size = new Size(250, 200);
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Size = New Drawing.Size(250, 200)
End Sub
```

### <a name="resize-a-different-form"></a><span data-ttu-id="168f7-126">重设其他窗体的大小</span><span class="sxs-lookup"><span data-stu-id="168f7-126">Resize a different form</span></span>

<span data-ttu-id="168f7-127">创建其他窗体后，可以使用引用该窗体的变量来更改其大小。</span><span class="sxs-lookup"><span data-stu-id="168f7-127">You can change the size of another form after it's created by using the variable referencing the form.</span></span> <span data-ttu-id="168f7-128">例如，假设有两个窗体：`Form1`（在本示例中为启动窗体）和 `Form2`。</span><span class="sxs-lookup"><span data-stu-id="168f7-128">For example, let's say you have two forms, `Form1` (the startup form in this example) and `Form2`.</span></span> <span data-ttu-id="168f7-129">`Form1` 有一个按钮，单击该按钮时，将调用 `Click` 事件。</span><span class="sxs-lookup"><span data-stu-id="168f7-129">`Form1` has a button that when clicked, invokes the `Click` event.</span></span> <span data-ttu-id="168f7-130">此事件的处理程序创建 `Form2` 窗体的新实例、设置大小，然后显示该实例：</span><span class="sxs-lookup"><span data-stu-id="168f7-130">The handler of this event creates a new instance of the `Form2` form, sets the size, and then displays it:</span></span>

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

<span data-ttu-id="168f7-131">如果未手动设置 `Size`，则窗体的默认大小即在设计时设置的大小。</span><span class="sxs-lookup"><span data-stu-id="168f7-131">If the `Size` isn't manually set, the form's default size is what it was set to during design-time.</span></span>

## <a name="position-with-the-designer"></a><span data-ttu-id="168f7-132">使用设计器定位</span><span class="sxs-lookup"><span data-stu-id="168f7-132">Position with the designer</span></span>

<span data-ttu-id="168f7-133">创建并显示窗体实例时，窗体的初始位置由 <xref:System.Windows.Forms.Form.StartPosition%2A> 属性决定。</span><span class="sxs-lookup"><span data-stu-id="168f7-133">When a form instance is created and displayed, the initial location of the form is determined by the <xref:System.Windows.Forms.Form.StartPosition%2A> property.</span></span> <span data-ttu-id="168f7-134"><xref:System.Windows.Forms.Form.Location%2A> 属性保存窗体的当前位置。</span><span class="sxs-lookup"><span data-stu-id="168f7-134">The <xref:System.Windows.Forms.Form.Location%2A> property holds the current location the form.</span></span> <span data-ttu-id="168f7-135">可以通过设计器设置这两个属性。</span><span class="sxs-lookup"><span data-stu-id="168f7-135">Both properties can be set through the designer.</span></span>

:::image type="content" source="media/how-to-position-and-resize/startposition.png" alt-text="突出显示起始位置的 Visual Studio 属性窗格":::

| <span data-ttu-id="168f7-137">FormStartPosition Enum</span><span class="sxs-lookup"><span data-stu-id="168f7-137">FormStartPosition Enum</span></span> | <span data-ttu-id="168f7-138">描述</span><span class="sxs-lookup"><span data-stu-id="168f7-138">Description</span></span>                                                                                                      |
|------------------------|------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="168f7-139">CenterParent</span><span class="sxs-lookup"><span data-stu-id="168f7-139">CenterParent</span></span>           | <span data-ttu-id="168f7-140">窗体在其父窗体中居中。</span><span class="sxs-lookup"><span data-stu-id="168f7-140">The form is centered within the bounds of its parent form.</span></span>                                                       |
| <span data-ttu-id="168f7-141">CenterScreen</span><span class="sxs-lookup"><span data-stu-id="168f7-141">CenterScreen</span></span>           | <span data-ttu-id="168f7-142">窗体在当前显示屏中居中。</span><span class="sxs-lookup"><span data-stu-id="168f7-142">The form is centered on the current display.</span></span>                                                                     |
| <span data-ttu-id="168f7-143">手动</span><span class="sxs-lookup"><span data-stu-id="168f7-143">Manual</span></span>                 | <span data-ttu-id="168f7-144">窗体的位置由 [Location](xref:System.Windows.Forms.Form.Location%2A) 属性决定。</span><span class="sxs-lookup"><span data-stu-id="168f7-144">The position of the form is determined by the [Location](xref:System.Windows.Forms.Form.Location%2A) property.</span></span>   |
| <span data-ttu-id="168f7-145">WindowsDefaultBounds</span><span class="sxs-lookup"><span data-stu-id="168f7-145">WindowsDefaultBounds</span></span>   | <span data-ttu-id="168f7-146">窗体位于 Windows 默认位置，且大小重设为 Windows 决定的默认大小。</span><span class="sxs-lookup"><span data-stu-id="168f7-146">The form is positioned at the Windows default location and is resized to the default size determined by Windows.</span></span> |
| <span data-ttu-id="168f7-147">WindowsDefaultLocation</span><span class="sxs-lookup"><span data-stu-id="168f7-147">WindowsDefaultLocation</span></span> | <span data-ttu-id="168f7-148">窗体位于 Windows 默认位置，没有重设大小。</span><span class="sxs-lookup"><span data-stu-id="168f7-148">The form is positioned at the Windows default location and isn't resized.</span></span>                                        |

<span data-ttu-id="168f7-149">[CenterParent](xref:System.Windows.Forms.FormStartPosition.CenterParent) 值仅适用于多文档界面 (MDI) 子窗体或使用 <xref:System.Windows.Window.ShowDialog%2A> 方法显示的常规窗体。</span><span class="sxs-lookup"><span data-stu-id="168f7-149">The [CenterParent](xref:System.Windows.Forms.FormStartPosition.CenterParent) value only works with forms that are either a multiple document interface (MDI) child form, or a normal form that is displayed with the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="168f7-150">`CenterParent` 不影响使用 <xref:System.Windows.Window.Show%2A> 方法显示的常规窗体。</span><span class="sxs-lookup"><span data-stu-id="168f7-150">`CenterParent` has no affect on a normal form that is displayed with the <xref:System.Windows.Window.Show%2A> method.</span></span> <span data-ttu-id="168f7-151">若要让某个窗体（`form` 变量）相对于另一个窗体（`parentForm` 变量）居中，请使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="168f7-151">To center a form (`form` variable) to another form (`parentForm` variable), use the following code:</span></span>

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

## <a name="position-with-code"></a><span data-ttu-id="168f7-152">使用代码定位</span><span class="sxs-lookup"><span data-stu-id="168f7-152">Position with code</span></span>

<span data-ttu-id="168f7-153">尽管可以使用设计器来设置窗体的起始位置，也可以使用代码来更改起始位置模式或手动设置位置。</span><span class="sxs-lookup"><span data-stu-id="168f7-153">Even though the designer can be used to set the starting location of a form, you can use code either change the starting position mode or set the location manually.</span></span> <span data-ttu-id="168f7-154">如果需要相对于屏幕或其他窗体手动定位窗体并重设其大小，则使用代码来定位窗体非常有用。</span><span class="sxs-lookup"><span data-stu-id="168f7-154">Using code to position a form is useful if you need to manually position and size a form in relation to the screen or other forms.</span></span>

### <a name="move-the-current-form"></a><span data-ttu-id="168f7-155">移动当前窗体</span><span class="sxs-lookup"><span data-stu-id="168f7-155">Move the current form</span></span>

<span data-ttu-id="168f7-156">只要代码在窗体的上下文中运行，就可以移动当前窗体。</span><span class="sxs-lookup"><span data-stu-id="168f7-156">You can move the current form as long as the code is running within the context of the form.</span></span> <span data-ttu-id="168f7-157">例如，如果 `Form1` 上有一个按钮，则单击该按钮时，将调用 `Click` 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="168f7-157">For example, if you have `Form1` with a button on it, that when clicked invokes the `Click` event handler.</span></span> <span data-ttu-id="168f7-158">此示例中的处理程序通过设置 <xref:System.Windows.Forms.Form.Location%2A> 属性将窗体的位置更改为屏幕的左上角：</span><span class="sxs-lookup"><span data-stu-id="168f7-158">The handler in this example changes the location of the form to the top-left of the screen by setting the <xref:System.Windows.Forms.Form.Location%2A> property:</span></span>

```csharp
private void button1_Click(object sender, EventArgs e) =>
    Location = new Point(0, 0);
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Location = New Drawing.Point(0, 0)
End Sub
```

### <a name="position-a-different-form"></a><span data-ttu-id="168f7-159">定位其他窗体</span><span class="sxs-lookup"><span data-stu-id="168f7-159">Position a different form</span></span>

<span data-ttu-id="168f7-160">创建其他窗体后，可以使用引用该窗体的变量来更改其位置。</span><span class="sxs-lookup"><span data-stu-id="168f7-160">You can change the location of another form after it's created by using the variable referencing the form.</span></span> <span data-ttu-id="168f7-161">例如，假设有两个窗体：`Form1`（在本示例中为启动窗体）和 `Form2`。</span><span class="sxs-lookup"><span data-stu-id="168f7-161">For example, let's say you have two forms, `Form1` (the startup form in this example) and `Form2`.</span></span> <span data-ttu-id="168f7-162">`Form1` 有一个按钮，单击该按钮时，将调用 `Click` 事件。</span><span class="sxs-lookup"><span data-stu-id="168f7-162">`Form1` has a button that when clicked, invokes the `Click` event.</span></span> <span data-ttu-id="168f7-163">此事件的处理程序创建 `Form2` 窗体的新实例并设置大小：</span><span class="sxs-lookup"><span data-stu-id="168f7-163">The handler of this event creates a new instance of the `Form2` form and sets the size:</span></span>

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

<span data-ttu-id="168f7-164">如果未设置 `Size`，则窗体的默认大小即在设计时设置的大小。</span><span class="sxs-lookup"><span data-stu-id="168f7-164">If the `Size` isn't set, the form's default size is what it was set to at design-time.</span></span>

## <a name="see-also"></a><span data-ttu-id="168f7-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="168f7-165">See also</span></span>

- [<span data-ttu-id="168f7-166">如何向项目添加窗体（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="168f7-166">How to add a form to a project (Windows Forms .NET)</span></span>](how-to-add.md)
- [<span data-ttu-id="168f7-167">事件概述（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="168f7-167">Events overview (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="168f7-168">控件的位置和布局（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="168f7-168">Position and layout of controls (Windows Forms .NET)</span></span>](../controls/layout.md)
