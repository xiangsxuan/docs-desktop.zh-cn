---
title: 如何：旋转、反射和倾斜图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 80ac92d545d9be7a4a611038eaaadbbdbe2e8ecf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971420"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>如何：旋转、反射和倾斜图像
可以通过指定原始图像左上角、右上角和左下角的目标点来旋转、反射和倾斜图像。 三个目标点确定将原始矩形图像映射到平行四边形的仿射转换。  
  
## <a name="example"></a>示例  
 例如，假设原始图像是一个矩形，左上角的 (0，0) ，右上角的 (100，0) ，左下角位于 (0，50) 。 现在假设你将这三个点映射到目标点，如下所示。  
  
|原始点|目标点|  
|--------------------|-----------------------|  
|左上 (0，0) |(200, 20)|  
|右上 (100，0) |(110, 100)|  
|左下 (0，50) |(250, 30)|  
  
 下图显示了原始图像和映射到平行四边形的图像。 原始图像已被扭曲、反射、旋转和平移。 沿原始图像上边缘的 x 轴映射到通过 (200，20) 和 (110，100) 运行的行。 沿原始图像左边缘的 y 轴映射到通过 (200，20) 和 (250，30) 运行的行。  
  
 ![原始图像和映射到平行四边形的图像。](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-illustration.gif)  
  
 下图显示了应用于照片图像的类似转换：  
  
 ![Climber 和映射到平行四边形的图片的图片。](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-photo.png)  
  
 下图显示了应用于图元文件的类似转换：  
  
 ![映射到平行四边形的形状和文本的插图。](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-metafile.png)  
  
 下面的示例生成第一个图中显示的图像。  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。 请确保将替换为在 `Stripes.bmp` 系统中有效的图像的路径。  
  
## <a name="see-also"></a>另请参阅

- [使用图像、位图、图标和图元文件](working-with-images-bitmaps-icons-and-metafiles.md)
