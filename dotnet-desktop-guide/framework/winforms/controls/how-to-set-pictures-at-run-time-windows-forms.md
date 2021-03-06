---
title: 如何：在运行时设置图片
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
ms.openlocfilehash: 5cbbfa69f049ef410398c999eb6e9eca3cc9be3f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970971"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>如何：在运行时设置图片（Windows 窗体）

您可以通过编程方式设置 Windows 窗体控件显示的图像 <xref:System.Windows.Forms.PictureBox> 。  
  
### <a name="to-set-a-picture-programmatically"></a>以编程方式设置图片  
  
- <xref:System.Windows.Forms.PictureBox.Image%2A>使用类的方法设置属性 <xref:System.Drawing.Image.FromFile%2A> <xref:System.Drawing.Image> 。  
  
     在下面的示例中，为图像的位置设置的路径是 "我的文档" 文件夹。 这样做是因为您可以假定大多数运行 Windows 操作系统的计算机都包含此目录。 这还使得具有最低系统访问级别的用户能够安全运行应用程序。 下面的示例假设窗体 <xref:System.Windows.Forms.PictureBox> 已添加控件。  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### <a name="to-clear-a-graphic"></a>清除图形  
  
- 首先，释放图像所使用的内存，然后清除图形。 如果内存管理变成问题，垃圾回收将在以后释放内存。  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    > 有关应以这种方式使用方法的原因的详细信息 <xref:System.Drawing.Image.Dispose%2A> ，请参阅 [清理非托管资源](/dotnet/standard/garbage-collection/unmanage)。  
  
     即使在设计时将图形加载到控件中，此代码也会清除图像。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [PictureBox 控件概述](picturebox-control-overview-windows-forms.md)
- [如何：使用设计器加载图片](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [如何：在运行时修改图片的大小或位置](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [PictureBox 控件](picturebox-control-windows-forms.md)
