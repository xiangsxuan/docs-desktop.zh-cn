---
title: 在控件上显示图像
description: 了解如何在 Windows 窗体控件上显示图像。 许多控件（如 PictureBox）都可以显示图像。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms contr ols
- examples [Windows Forms], controls
ms.openlocfilehash: a0b95d51f852df4c9ddc190903369faa41f7deae
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96941942"
---
# <a name="how-to-display-an-image-on-a-control-windows-forms-net"></a>如何在控件上显示图像（Windows 窗体 .NET）

多个 Windows 窗体控件可以显示图像。 这些图像可以是表明控件用途的图标，如表示“保存”命令的按钮上的软盘图标。 此外，图标还可以作为背景图像，为控件提供所需的外观和行为。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a>Designer

在 Visual Studio 的“属性”窗口中，选择控件的 Image 或 BackgroundImage 属性，然后选择省略号（![Visual Studio 中的省略号按钮](../media/visual-studio-ellipsis-button.png)）以显示“选择资源”对话框，然后选择要显示的图像   。

:::image type="content" source="media/how-to-add-a-picture-to-a-control/properties-image.png" alt-text="“属性”对话框，其中选中了 Image 属性":::

## <a name="programmatic"></a>编程

将控件的 `Image` 或 `BackgroundImage` 属性设置为类型 <xref:System.Drawing.Image> 的对象。 通常，将使用 <xref:System.Drawing.Image.FromFile%2A> 方法从文件中加载图像。

在下面的代码示例中，为图像位置设置的路径是“My Pictures”文件夹。 大多数运行 Windows 操作系统的计算机都包含此目录。 这还使得具有最低系统访问级别的用户能够安全运行应用程序。 下面的代码示例要求你已具有一个添加了 <xref:System.Windows.Forms.PictureBox> 控件的窗体。

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
