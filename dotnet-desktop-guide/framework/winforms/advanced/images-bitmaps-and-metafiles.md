---
title: 图像、位图和图元文件
ms.date: 03/30/2017
helpviewer_keywords:
- metafiles [Windows Forms], about metafiles
- bitmaps [Windows Forms], about bitmaps
- images [Windows Forms], about images
- Windows Forms, images
ms.assetid: 7152b45b-a55c-49bc-8c78-ae002a844f71
ms.openlocfilehash: 5f50d21f4793efb497eb5b030d96a7dc3ab54a04
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971631"
---
# <a name="images-bitmaps-and-metafiles"></a><span data-ttu-id="4dc1d-102">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="4dc1d-102">Images, Bitmaps, and Metafiles</span></span>
<span data-ttu-id="4dc1d-103">`Image` 类是一个抽象基类，提供用于处理光栅图像（位图）和矢量图像（图元文件）的方法。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-103">The `Image` class is an abstract base class that provides methods for working with raster images (bitmaps) and vector images (metafiles).</span></span> <span data-ttu-id="4dc1d-104">`Bitmap` 类和 <xref:System.Drawing.Imaging.Metafile> 类从 `Image` 类继承。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-104">The `Bitmap` class and the <xref:System.Drawing.Imaging.Metafile> class both inherit from the `Image` class.</span></span> <span data-ttu-id="4dc1d-105">`Bitmap` 类通过提供用于加载、保存和操作光栅图像的附加方法，在 `Image` 类的功能上进行扩展。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-105">The `Bitmap` class expands on the capabilities of the `Image` class by providing additional methods for loading, saving, and manipulating raster images.</span></span> <span data-ttu-id="4dc1d-106"><xref:System.Drawing.Imaging.Metafile> 类通过提供用于记录和检查矢量图像的附加方法，在 `Image` 类的功能上进行扩展。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-106">The <xref:System.Drawing.Imaging.Metafile> class expands on the capabilities of the `Image` class by providing additional methods for recording and examining vector images.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4dc1d-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="4dc1d-107">In This Section</span></span>  
 [<span data-ttu-id="4dc1d-108">位图类型</span><span class="sxs-lookup"><span data-stu-id="4dc1d-108">Types of Bitmaps</span></span>](types-of-bitmaps.md)  
 <span data-ttu-id="4dc1d-109">解说不同的图像格式。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-109">Discusses the various image formats.</span></span>  
  
 [<span data-ttu-id="4dc1d-110">GDI+ 中的图元文件</span><span class="sxs-lookup"><span data-stu-id="4dc1d-110">Metafiles in GDI+</span></span>](metafiles-in-gdi.md)  
 <span data-ttu-id="4dc1d-111">讨论对图元文件的 GDI + 支持。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-111">Discusses GDI+ support for metafiles.</span></span>  
  
 [<span data-ttu-id="4dc1d-112">在 GDI+ 中绘制、定位和克隆图像</span><span class="sxs-lookup"><span data-stu-id="4dc1d-112">Drawing, Positioning, and Cloning Images in GDI+</span></span>](drawing-positioning-and-cloning-images-in-gdi.md)  
 <span data-ttu-id="4dc1d-113">讨论如何使用托管代码绘制矢量和光栅图像。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-113">Discusses methods for drawing vector and raster images with managed code.</span></span>  
  
 [<span data-ttu-id="4dc1d-114">在 GDI+ 中裁切和缩放图像</span><span class="sxs-lookup"><span data-stu-id="4dc1d-114">Cropping and Scaling Images in GDI+</span></span>](cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="4dc1d-115">介绍如何使用托管代码剪切和缩放矢量和光栅图像</span><span class="sxs-lookup"><span data-stu-id="4dc1d-115">Discusses methods for cropping and scaling vector and raster images with managed code</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4dc1d-116">参考</span><span class="sxs-lookup"><span data-stu-id="4dc1d-116">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="4dc1d-117">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-117">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="4dc1d-118">描述此类并提供指向其所有成员的链接</span><span class="sxs-lookup"><span data-stu-id="4dc1d-118">Describes this class and has links to all of its members</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4dc1d-119">相关章节</span><span class="sxs-lookup"><span data-stu-id="4dc1d-119">Related Sections</span></span>  
 [<span data-ttu-id="4dc1d-120">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="4dc1d-120">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)  
 <span data-ttu-id="4dc1d-121">包含指向演示如何在应用程序中使用图像的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="4dc1d-121">Contains links to topics that demonstrate how to use images in your application.</span></span>
