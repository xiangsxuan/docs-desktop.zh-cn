---
title: 如何：列出已安装的解码器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: 961862d6212b7e76812fc222d3a99f08528d9a16
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971440"
---
# <a name="how-to-list-installed-decoders"></a>如何：列出已安装的解码器
你可能需要列出计算机上可用的图像解码器，以确定应用程序是否可以读取特定的图像文件格式。 <xref:System.Drawing.Imaging.ImageCodecInfo>类提供 <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> 静态方法，以便您可以确定可用的图像解码器。 <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> 返回对象的数组 <xref:System.Drawing.Imaging.ImageCodecInfo> 。  
  
## <a name="example"></a>示例  
 下面的代码示例输出已安装的解码器及其属性值的列表。  
  
 [!code-csharp[UsingImageEncodersDecoders#2](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- Windows 窗体应用程序。  
  
- 一个 <xref:System.Windows.Forms.PaintEventArgs> ，它是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>另请参阅

- [如何：列出已安装的编码器](how-to-list-installed-encoders.md)
- [在托管 GDI+ 中使用图像编码器和解码器](using-image-encoders-and-decoders-in-managed-gdi.md)
