---
title: 如何：列出已安装的编码器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: 2634dd96b3aa5edcecde092919eb328b7f3dadc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971691"
---
# <a name="how-to-list-installed-encoders"></a>如何：列出已安装的编码器
你可能需要列出计算机上可用的图像编码器，以确定应用程序是否可以保存到特定的图像文件格式。 <xref:System.Drawing.Imaging.ImageCodecInfo>类提供 <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> 静态方法，以便您可以确定哪些图像编码器可用。 <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> 返回对象的数组 <xref:System.Drawing.Imaging.ImageCodecInfo> 。  
  
## <a name="example"></a>示例  
 下面的代码示例输出安装的编码器及其属性值的列表。  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- Windows 窗体应用程序。  
  
- 一个 <xref:System.Windows.Forms.PaintEventArgs> ，它是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>另请参阅

- [如何：列出已安装的解码器](how-to-list-installed-decoders.md)
- [在托管 GDI+ 中使用图像编码器和解码器](using-image-encoders-and-decoders-in-managed-gdi.md)
