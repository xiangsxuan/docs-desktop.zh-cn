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
# <a name="how-to-display-an-image-on-a-control-windows-forms-net"></a><span data-ttu-id="0e38d-104">如何在控件上显示图像（Windows 窗体 .NET）</span><span class="sxs-lookup"><span data-stu-id="0e38d-104">How to display an image on a control (Windows Forms .NET)</span></span>

<span data-ttu-id="0e38d-105">多个 Windows 窗体控件可以显示图像。</span><span class="sxs-lookup"><span data-stu-id="0e38d-105">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="0e38d-106">这些图像可以是表明控件用途的图标，如表示“保存”命令的按钮上的软盘图标。</span><span class="sxs-lookup"><span data-stu-id="0e38d-106">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the Save command.</span></span> <span data-ttu-id="0e38d-107">此外，图标还可以作为背景图像，为控件提供所需的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="0e38d-107">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="designer"></a><span data-ttu-id="0e38d-108">Designer</span><span class="sxs-lookup"><span data-stu-id="0e38d-108">Designer</span></span>

<span data-ttu-id="0e38d-109">在 Visual Studio 的“属性”窗口中，选择控件的 Image 或 BackgroundImage 属性，然后选择省略号（![Visual Studio 中的省略号按钮](../media/visual-studio-ellipsis-button.png)）以显示“选择资源”对话框，然后选择要显示的图像   。</span><span class="sxs-lookup"><span data-stu-id="0e38d-109">In the **Properties** window of Visual Studio, select the **Image** or **BackgroundImage** property of the control, and then select the ellipsis (![Ellipsis button in Visual Studio](../media/visual-studio-ellipsis-button.png)) to display the **Select Resource** dialog box and then select the image you want to display.</span></span>

:::image type="content" source="media/how-to-add-a-picture-to-a-control/properties-image.png" alt-text="“属性”对话框，其中选中了 Image 属性":::

## <a name="programmatic"></a><span data-ttu-id="0e38d-111">编程</span><span class="sxs-lookup"><span data-stu-id="0e38d-111">Programmatic</span></span>

<span data-ttu-id="0e38d-112">将控件的 `Image` 或 `BackgroundImage` 属性设置为类型 <xref:System.Drawing.Image> 的对象。</span><span class="sxs-lookup"><span data-stu-id="0e38d-112">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="0e38d-113">通常，将使用 <xref:System.Drawing.Image.FromFile%2A> 方法从文件中加载图像。</span><span class="sxs-lookup"><span data-stu-id="0e38d-113">Generally, you'll be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>

<span data-ttu-id="0e38d-114">在下面的代码示例中，为图像位置设置的路径是“My Pictures”文件夹。</span><span class="sxs-lookup"><span data-stu-id="0e38d-114">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="0e38d-115">大多数运行 Windows 操作系统的计算机都包含此目录。</span><span class="sxs-lookup"><span data-stu-id="0e38d-115">Most computers running the Windows operating system include this directory.</span></span> <span data-ttu-id="0e38d-116">这还使得具有最低系统访问级别的用户能够安全运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="0e38d-116">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="0e38d-117">下面的代码示例要求你已具有一个添加了 <xref:System.Windows.Forms.PictureBox> 控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="0e38d-117">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0e38d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e38d-118">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
