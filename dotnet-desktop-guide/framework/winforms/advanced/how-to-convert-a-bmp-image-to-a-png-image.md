---
title: 如何：将 BMP 图像转换为 PNG 图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BMP images [Windows Forms], converting to PNG
- image formats [Windows Forms], converting between
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
ms.openlocfilehash: 59200941aa0f872a0bd99510bfaa8a8b878a9061
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970664"
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a>如何：将 BMP 图像转换为 PNG 图像
通常，需要转换图像文件格式。 可以通过调用 <xref:System.Drawing.Image> 类的 <xref:System.Drawing.Image.Save%2A> 方法，并将 <xref:System.Drawing.Imaging.ImageFormat> 指定为所需的图像文件格式来轻松完成转换。  
  
## <a name="example"></a>示例  
 以下示例从一个类型加载 BMP 图像，并以 PNG 格式保存该图像。  
  
 [!code-csharp[UsingImageEncodersDecoders#4](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- Windows 窗体应用程序。  
  
- 对 `System.Drawing.Imaging` 命名空间的引用。  
  
## <a name="see-also"></a>另请参阅

- [如何：列出已安装的编码器](how-to-list-installed-encoders.md)
- [在托管 GDI+ 中使用图像编码器和解码器](using-image-encoders-and-decoders-in-managed-gdi.md)
- [位图类型](types-of-bitmaps.md)
