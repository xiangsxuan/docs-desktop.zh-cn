---
title: 设置控件显示的图像
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: 5df0068c8462bbaab0cb0135de1dd1b91ababe06
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972667"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="25838-102">如何：设置 Windows 窗体控件显示的图像</span><span class="sxs-lookup"><span data-stu-id="25838-102">How to: Set the image displayed by a Windows Forms control</span></span>

<span data-ttu-id="25838-103">若干 Windows 窗体控件可以显示图像。</span><span class="sxs-lookup"><span data-stu-id="25838-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="25838-104">这些图像可以是阐明控件用途的图标，如表示 "保存" 命令的按钮上的 "磁盘" 图标。</span><span class="sxs-lookup"><span data-stu-id="25838-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the Save command.</span></span> <span data-ttu-id="25838-105">此外，图标还可以是背景图像，为控件指定所需的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="25838-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>

## <a name="programmatic"></a><span data-ttu-id="25838-106">编程</span><span class="sxs-lookup"><span data-stu-id="25838-106">Programmatic</span></span>

<span data-ttu-id="25838-107">将控件的 `Image` 或 `BackgroundImage` 属性设置为类型的对象 <xref:System.Drawing.Image> 。</span><span class="sxs-lookup"><span data-stu-id="25838-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="25838-108">通常，将使用方法从文件中加载图像 <xref:System.Drawing.Image.FromFile%2A> 。</span><span class="sxs-lookup"><span data-stu-id="25838-108">Generally, you'll be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>

<span data-ttu-id="25838-109">在下面的代码示例中，为图像的位置设置的路径是 " **我的图片** " 文件夹。</span><span class="sxs-lookup"><span data-stu-id="25838-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="25838-110">大多数运行 Windows 操作系统的计算机都包含此目录。</span><span class="sxs-lookup"><span data-stu-id="25838-110">Most computers running the Windows operating system include this directory.</span></span> <span data-ttu-id="25838-111">这还可以使具有最低系统访问级别的用户安全运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="25838-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="25838-112">下面的代码示例要求您已具有一个已添加控件的窗体 <xref:System.Windows.Forms.PictureBox> 。</span><span class="sxs-lookup"><span data-stu-id="25838-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```cpp
// Replace the image named below with your own icon.
pictureBox1->Image = Image::FromFile(String::Concat
   (System::Environment::GetFolderPath
   (System::Environment::SpecialFolder::MyPictures),
   "\\Image.gif"));
```

## <a name="designer"></a><span data-ttu-id="25838-113">Designer</span><span class="sxs-lookup"><span data-stu-id="25838-113">Designer</span></span>

1. <span data-ttu-id="25838-114">在 Visual Studio 的 " **属性** " 窗口中，选择控件的 **Image** 或 **BackgroundImage** 属性，然后选择 " ![ Visual studio) 中的省略号 (省略号按钮， ](./media/visual-studio-ellipsis-button.png) 以显示" **选择资源** "对话框。</span><span class="sxs-lookup"><span data-stu-id="25838-114">In the **Properties** window of Visual Studio, select the **Image** or **BackgroundImage** property of the control, and then select the ellipsis (![Ellipsis button in Visual Studio](./media/visual-studio-ellipsis-button.png)) to display the **Select Resource** dialog box.</span></span>

2. <span data-ttu-id="25838-115">选择要显示的图像。</span><span class="sxs-lookup"><span data-stu-id="25838-115">Select the image you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="25838-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25838-116">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
