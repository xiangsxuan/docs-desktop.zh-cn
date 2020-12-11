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
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a><span data-ttu-id="a77ed-102">在托管 GDI+ 中使用图像编码器和解码器</span><span class="sxs-lookup"><span data-stu-id="a77ed-102">Using Image Encoders and Decoders in Managed GDI+</span></span>
<span data-ttu-id="a77ed-103"><xref:System.Drawing>命名空间提供 <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> 用于存储和操作图像的和类。</span><span class="sxs-lookup"><span data-stu-id="a77ed-103">The <xref:System.Drawing> namespace provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="a77ed-104">通过使用 GDI + 中的图像编码器，可以将图像从内存写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="a77ed-104">By using image encoders in GDI+, you can write images from memory to disk.</span></span> <span data-ttu-id="a77ed-105">通过使用 GDI + 中的图像解码器，你可以将映像从磁盘加载到内存。</span><span class="sxs-lookup"><span data-stu-id="a77ed-105">By using image decoders in GDI+, you can load images from disk into memory.</span></span> <span data-ttu-id="a77ed-106">编码器将或对象中的数据 <xref:System.Drawing.Image> 转换 <xref:System.Drawing.Bitmap> 为指定的磁盘文件格式。</span><span class="sxs-lookup"><span data-stu-id="a77ed-106">An encoder translates the data in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object into a designated disk file format.</span></span> <span data-ttu-id="a77ed-107">解码器将磁盘文件中的数据转换为和对象所需的格式 <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> 。</span><span class="sxs-lookup"><span data-stu-id="a77ed-107">A decoder translates the data in a disk file to the format required by the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 <span data-ttu-id="a77ed-108">GDI + 具有支持以下文件类型的内置编码器和解码器：</span><span class="sxs-lookup"><span data-stu-id="a77ed-108">GDI+ has built-in encoders and decoders that support the following file types:</span></span>  
  
- <span data-ttu-id="a77ed-109">BMP</span><span class="sxs-lookup"><span data-stu-id="a77ed-109">BMP</span></span>  
  
- <span data-ttu-id="a77ed-110">GIF</span><span class="sxs-lookup"><span data-stu-id="a77ed-110">GIF</span></span>  
  
- <span data-ttu-id="a77ed-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="a77ed-111">JPEG</span></span>  
  
- <span data-ttu-id="a77ed-112">PNG</span><span class="sxs-lookup"><span data-stu-id="a77ed-112">PNG</span></span>  
  
- <span data-ttu-id="a77ed-113">TIFF</span><span class="sxs-lookup"><span data-stu-id="a77ed-113">TIFF</span></span>  
  
 <span data-ttu-id="a77ed-114">GDI + 还具有支持以下文件类型的内置解码器：</span><span class="sxs-lookup"><span data-stu-id="a77ed-114">GDI+ also has built-in decoders that support the following file types:</span></span>  
  
- <span data-ttu-id="a77ed-115">WMF</span><span class="sxs-lookup"><span data-stu-id="a77ed-115">WMF</span></span>  
  
- <span data-ttu-id="a77ed-116">EMF</span><span class="sxs-lookup"><span data-stu-id="a77ed-116">EMF</span></span>  
  
- <span data-ttu-id="a77ed-117">按钮</span><span class="sxs-lookup"><span data-stu-id="a77ed-117">ICON</span></span>  
  
 <span data-ttu-id="a77ed-118">以下主题更详细地讨论了编码器和解码器：</span><span class="sxs-lookup"><span data-stu-id="a77ed-118">The following topics discuss encoders and decoders in more detail:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a77ed-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="a77ed-119">In This Section</span></span>  
 [<span data-ttu-id="a77ed-120">如何：列出已安装的编码器</span><span class="sxs-lookup"><span data-stu-id="a77ed-120">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)  
 <span data-ttu-id="a77ed-121">描述如何列出计算机上可用的编码器。</span><span class="sxs-lookup"><span data-stu-id="a77ed-121">Describes how to list the encoders available on a computer.</span></span>  
  
 [<span data-ttu-id="a77ed-122">如何：列出已安装的解码器</span><span class="sxs-lookup"><span data-stu-id="a77ed-122">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)  
 <span data-ttu-id="a77ed-123">介绍如何列出计算机上可用的解码器。</span><span class="sxs-lookup"><span data-stu-id="a77ed-123">Describes how to list the decoders available on a computer.</span></span>  
  
 [<span data-ttu-id="a77ed-124">如何：确定编码器支持的参数</span><span class="sxs-lookup"><span data-stu-id="a77ed-124">How to: Determine the Parameters Supported by an Encoder</span></span>](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 <span data-ttu-id="a77ed-125">描述如何列出 <xref:System.Drawing.Imaging.EncoderParameters> 编码器支持的。</span><span class="sxs-lookup"><span data-stu-id="a77ed-125">Describes how to list the <xref:System.Drawing.Imaging.EncoderParameters> supported by an encoder.</span></span>  
  
 [<span data-ttu-id="a77ed-126">如何：将 BMP 图像转换为 PNG 图像</span><span class="sxs-lookup"><span data-stu-id="a77ed-126">How to: Convert a BMP image to a PNG image</span></span>](how-to-convert-a-bmp-image-to-a-png-image.md)  
 <span data-ttu-id="a77ed-127">描述如何以不同的图像格式保存图像。</span><span class="sxs-lookup"><span data-stu-id="a77ed-127">Describes how to save a image in a different image format.</span></span>  
  
 [<span data-ttu-id="a77ed-128">如何：设置 JPEG 压缩级别</span><span class="sxs-lookup"><span data-stu-id="a77ed-128">How to: Set JPEG Compression Level</span></span>](how-to-set-jpeg-compression-level.md)  
 <span data-ttu-id="a77ed-129">介绍如何更改图像的质量级别。</span><span class="sxs-lookup"><span data-stu-id="a77ed-129">Describes how to change the quality level of an image.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a77ed-130">参考</span><span class="sxs-lookup"><span data-stu-id="a77ed-130">Reference</span></span>  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a><span data-ttu-id="a77ed-131">相关章节</span><span class="sxs-lookup"><span data-stu-id="a77ed-131">Related Sections</span></span>  
 [<span data-ttu-id="a77ed-132">关于 GDI+ 托管代码</span><span class="sxs-lookup"><span data-stu-id="a77ed-132">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
  
 [<span data-ttu-id="a77ed-133">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="a77ed-133">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
