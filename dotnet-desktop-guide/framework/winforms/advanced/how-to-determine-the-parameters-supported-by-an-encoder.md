---
title: 如何：确定编码器支持的参数
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 3e5345180e0ff3321b9ef0b885b836d3e9456f28
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970313"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a>如何：确定编码器支持的参数
你可以调整图像参数，如质量和压缩级别，但你必须知道给定图像编码器支持哪些参数。 <xref:System.Drawing.Image>类提供方法， <xref:System.Drawing.Image.GetEncoderParameterList%2A> 以便您可以确定特定编码器支持的图像参数。 使用 GUID 指定编码器。 <xref:System.Drawing.Image.GetEncoderParameterList%2A>方法返回对象的数组 <xref:System.Drawing.Imaging.EncoderParameter> 。  
  
## <a name="example"></a>示例  
 下面的示例代码输出 JPEG 编码器支持的参数。 使用类概述中的参数类别列表和关联 Guid <xref:System.Drawing.Imaging.Encoder> 来确定每个参数的类别。  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- Windows 窗体应用程序。  
  
- 一个 <xref:System.Windows.Forms.PaintEventArgs> ，它是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>另请参阅

- [如何：列出已安装的编码器](how-to-list-installed-encoders.md)
- [位图类型](types-of-bitmaps.md)
- [在托管 GDI+ 中使用图像编码器和解码器](using-image-encoders-and-decoders-in-managed-gdi.md)
