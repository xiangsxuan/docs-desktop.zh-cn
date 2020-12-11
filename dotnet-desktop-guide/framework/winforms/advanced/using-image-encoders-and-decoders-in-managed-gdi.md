---
title: 在托管 GDI+ 中使用图像编码器和解码器
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: 8cd66f3ce3da462867da9e23c38b3f6d877c058c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971370"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a>在托管 GDI+ 中使用图像编码器和解码器
<xref:System.Drawing>命名空间提供 <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> 用于存储和操作图像的和类。 通过使用 GDI + 中的图像编码器，可以将图像从内存写入磁盘。 通过使用 GDI + 中的图像解码器，你可以将映像从磁盘加载到内存。 编码器将或对象中的数据 <xref:System.Drawing.Image> 转换 <xref:System.Drawing.Bitmap> 为指定的磁盘文件格式。 解码器将磁盘文件中的数据转换为和对象所需的格式 <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> 。  
  
 GDI + 具有支持以下文件类型的内置编码器和解码器：  
  
- BMP  
  
- GIF  
  
- JPEG  
  
- PNG  
  
- TIFF  
  
 GDI + 还具有支持以下文件类型的内置解码器：  
  
- WMF  
  
- EMF  
  
- 按钮  
  
 以下主题更详细地讨论了编码器和解码器：  
  
## <a name="in-this-section"></a>本节内容  
 [如何：列出已安装的编码器](how-to-list-installed-encoders.md)  
 描述如何列出计算机上可用的编码器。  
  
 [如何：列出已安装的解码器](how-to-list-installed-decoders.md)  
 介绍如何列出计算机上可用的解码器。  
  
 [如何：确定编码器支持的参数](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 描述如何列出 <xref:System.Drawing.Imaging.EncoderParameters> 编码器支持的。  
  
 [如何：将 BMP 图像转换为 PNG 图像](how-to-convert-a-bmp-image-to-a-png-image.md)  
 描述如何以不同的图像格式保存图像。  
  
 [如何：设置 JPEG 压缩级别](how-to-set-jpeg-compression-level.md)  
 介绍如何更改图像的质量级别。  
  
## <a name="reference"></a>参考  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a>相关章节  
 [关于 GDI+ 托管代码](about-gdi-managed-code.md)  
  
 [图像、位图和图元文件](images-bitmaps-and-metafiles.md)
