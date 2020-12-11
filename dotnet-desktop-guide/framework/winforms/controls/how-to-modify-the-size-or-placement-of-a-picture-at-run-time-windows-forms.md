---
title: 如何：在运行时修改图片的大小或位置
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
ms.openlocfilehash: fea813d7b9fe585e35b729b8b64e3a5f414ef76d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971155"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="292eb-102">如何：在运行时修改图片的大小或位置（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="292eb-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="292eb-103">如果 <xref:System.Windows.Forms.PictureBox> 对窗体使用 Windows 窗体控件，则可以将 <xref:System.Windows.Forms.PictureBox.SizeMode%2A> 其上的属性设置为：</span><span class="sxs-lookup"><span data-stu-id="292eb-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
- <span data-ttu-id="292eb-104">将图片的左上角与控件的左上角对齐</span><span class="sxs-lookup"><span data-stu-id="292eb-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
- <span data-ttu-id="292eb-105">使图片在控件内居中</span><span class="sxs-lookup"><span data-stu-id="292eb-105">Center the picture within the control</span></span>  
  
- <span data-ttu-id="292eb-106">调整控件的大小以适应它所显示的图片</span><span class="sxs-lookup"><span data-stu-id="292eb-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
- <span data-ttu-id="292eb-107">伸展显示的任何图片以适应控件</span><span class="sxs-lookup"><span data-stu-id="292eb-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="292eb-108">拉伸图片 (尤其是位图格式的图片) 会导致图像质量损失。</span><span class="sxs-lookup"><span data-stu-id="292eb-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="292eb-109">图元文件是在运行时绘制图像的图形说明的列表，更适合于拉伸而不是位图。</span><span class="sxs-lookup"><span data-stu-id="292eb-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="292eb-110">在运行时设置 Picturebox1.sizemode 属性</span><span class="sxs-lookup"><span data-stu-id="292eb-110">To set the SizeMode property at run time</span></span>  
  
1. <span data-ttu-id="292eb-111">设置 <xref:System.Windows.Forms.PictureBox.SizeMode%2A> 为 <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (默认) 、、 <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> 或 <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> 。</span><span class="sxs-lookup"><span data-stu-id="292eb-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="292eb-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> 表示将图像放置在控件的左上角;如果图像大于控件，将剪裁其下边缘和右边缘。</span><span class="sxs-lookup"><span data-stu-id="292eb-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="292eb-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> 表示图像在控件内居中;如果图像大于控件，则裁剪图片的外边缘。</span><span class="sxs-lookup"><span data-stu-id="292eb-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="292eb-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> 表示将控件的大小调整为图像的大小。</span><span class="sxs-lookup"><span data-stu-id="292eb-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="292eb-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> 为反向，表示图像的大小调整为控件的大小。</span><span class="sxs-lookup"><span data-stu-id="292eb-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="292eb-116">在下面的示例中，为图像的位置设置的路径是 "我的文档" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="292eb-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="292eb-117">这样做是因为您可以假定大多数运行 Windows 操作系统的计算机都包含此目录。</span><span class="sxs-lookup"><span data-stu-id="292eb-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="292eb-118">这还使得具有最低系统访问级别的用户能够安全运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="292eb-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="292eb-119">下面的示例假设窗体 <xref:System.Windows.Forms.PictureBox> 已添加控件。</span><span class="sxs-lookup"><span data-stu-id="292eb-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="292eb-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="292eb-120">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="292eb-121">如何：使用设计器加载图片</span><span class="sxs-lookup"><span data-stu-id="292eb-121">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="292eb-122">PictureBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="292eb-122">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="292eb-123">如何：在运行时设置图片</span><span class="sxs-lookup"><span data-stu-id="292eb-123">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="292eb-124">PictureBox 控件</span><span class="sxs-lookup"><span data-stu-id="292eb-124">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
