---
title: 使用图像、位图、图标和图元文件
ms.date: 03/30/2017
helpviewer_keywords:
- metafiles [Windows Forms], working with
- examples [Windows Forms], bitmaps
- examples [Windows Forms], images
- bitmaps [Windows Forms], working with
- images [Windows Forms], working with
- examples [Windows Forms], metafiles
ms.assetid: a626d701-bd99-4fd8-b92f-7b8f794e042b
ms.openlocfilehash: 8c778018a2d78fbec67a3bf41b5cbaa8e4bfb606
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971346"
---
# <a name="working-with-images-bitmaps-icons-and-metafiles"></a><span data-ttu-id="1c522-102">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="1c522-102">Working with Images, Bitmaps, Icons, and Metafiles</span></span>
<span data-ttu-id="1c522-103">GDI + 提供了 `Bitmap` 用于处理光栅图像的类和 `Metafile` 用于处理矢量图像的类。</span><span class="sxs-lookup"><span data-stu-id="1c522-103">GDI+ provides the `Bitmap` class for working with raster images and the `Metafile` class for working with vector images.</span></span> <span data-ttu-id="1c522-104">`Bitmap` 和 `Metafile` 类都继承自 `Image` 类。</span><span class="sxs-lookup"><span data-stu-id="1c522-104">The `Bitmap` and the `Metafile` classes both inherit from the `Image` class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c522-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="1c522-105">In This Section</span></span>  
 [<span data-ttu-id="1c522-106">如何：在屏幕上绘制现有位图</span><span class="sxs-lookup"><span data-stu-id="1c522-106">How to: Draw an Existing Bitmap to the Screen</span></span>](how-to-draw-an-existing-bitmap-to-the-screen.md)  
 <span data-ttu-id="1c522-107">介绍如何加载和绘制位图。</span><span class="sxs-lookup"><span data-stu-id="1c522-107">Describes how to load and draw bitmaps.</span></span>  
  
 [<span data-ttu-id="1c522-108">如何：加载和显示图元文件</span><span class="sxs-lookup"><span data-stu-id="1c522-108">How to: Load and Display Metafiles</span></span>](how-to-load-and-display-metafiles.md)  
 <span data-ttu-id="1c522-109">展示如何加载和绘制图元文件。</span><span class="sxs-lookup"><span data-stu-id="1c522-109">Shows how to load and draw metafiles.</span></span>  
  
 [<span data-ttu-id="1c522-110">在 GDI+ 中裁切和缩放图像</span><span class="sxs-lookup"><span data-stu-id="1c522-110">Cropping and Scaling Images in GDI+</span></span>](cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="1c522-111">说明如何裁剪和缩放矢量图像和光栅图像。</span><span class="sxs-lookup"><span data-stu-id="1c522-111">Explains how to crop and scale vector and raster images.</span></span>  
  
 [<span data-ttu-id="1c522-112">如何：旋转、反射和倾斜图像</span><span class="sxs-lookup"><span data-stu-id="1c522-112">How to: Rotate, Reflect, and Skew Images</span></span>](how-to-rotate-reflect-and-skew-images.md)  
 <span data-ttu-id="1c522-113">描述如何绘制旋转、反射和倾斜图像。</span><span class="sxs-lookup"><span data-stu-id="1c522-113">Describes how to draw rotated, reflected and skewed images.</span></span>  
  
 [<span data-ttu-id="1c522-114">如何：在缩放时使用插值模式控制图像质量</span><span class="sxs-lookup"><span data-stu-id="1c522-114">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>](how-to-use-interpolation-mode-to-control-image-quality-during-scaling.md)  
 <span data-ttu-id="1c522-115">展示如何使用 <xref:System.Drawing.Drawing2D.InterpolationMode> 枚举来更改图像质量。</span><span class="sxs-lookup"><span data-stu-id="1c522-115">Shows how to use the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to change image quality.</span></span>  
  
 [<span data-ttu-id="1c522-116">如何：创建缩略图图像</span><span class="sxs-lookup"><span data-stu-id="1c522-116">How to: Create Thumbnail Images</span></span>](how-to-create-thumbnail-images.md)  
 <span data-ttu-id="1c522-117">描述如何创建缩略图像。</span><span class="sxs-lookup"><span data-stu-id="1c522-117">Describes how to create thumbnail images.</span></span>  
  
 [<span data-ttu-id="1c522-118">如何：通过避免自动缩放来改善性能</span><span class="sxs-lookup"><span data-stu-id="1c522-118">How to: Improve Performance by Avoiding Automatic Scaling</span></span>](how-to-improve-performance-by-avoiding-automatic-scaling.md)  
 <span data-ttu-id="1c522-119">说明如何在不进行自动缩放的情况下绘制图像。</span><span class="sxs-lookup"><span data-stu-id="1c522-119">Explains how to draw an image without automatic scaling.</span></span>  
  
 [<span data-ttu-id="1c522-120">如何：读取图像元数据</span><span class="sxs-lookup"><span data-stu-id="1c522-120">How to: Read Image Metadata</span></span>](how-to-read-image-metadata.md)  
 <span data-ttu-id="1c522-121">描述如何从图像读取元数据。</span><span class="sxs-lookup"><span data-stu-id="1c522-121">Describes how to read metadata from an image.</span></span>  
  
 [<span data-ttu-id="1c522-122">如何：在运行时创建位图</span><span class="sxs-lookup"><span data-stu-id="1c522-122">How to: Create a Bitmap at Run Time</span></span>](how-to-create-a-bitmap-at-run-time.md)  
 <span data-ttu-id="1c522-123">展示如何在运行时绘制位图。</span><span class="sxs-lookup"><span data-stu-id="1c522-123">Shows how to draw a bitmap at runtime.</span></span>  
  
 [<span data-ttu-id="1c522-124">如何：提取与 Windows 窗体中的文件关联的图标</span><span class="sxs-lookup"><span data-stu-id="1c522-124">How to: Extract the Icon Associated with a File in Windows Forms</span></span>](how-to-extract-the-icon-associated-with-a-file-in-windows-forms.md)  
 <span data-ttu-id="1c522-125">描述如何提取作为文件的嵌入资源的图标。</span><span class="sxs-lookup"><span data-stu-id="1c522-125">Describes how to extract an icon that is an embedded resource of a file.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1c522-126">参考</span><span class="sxs-lookup"><span data-stu-id="1c522-126">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="1c522-127">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="1c522-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Imaging.Metafile>  
 <span data-ttu-id="1c522-128">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="1c522-128">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="1c522-129">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="1c522-129">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1c522-130">相关章节</span><span class="sxs-lookup"><span data-stu-id="1c522-130">Related Sections</span></span>  
 [<span data-ttu-id="1c522-131">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="1c522-131">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)  
 <span data-ttu-id="1c522-132">包含指向讨论位图不同类型的主题的链接并在应用程序中对它们进行处操作。</span><span class="sxs-lookup"><span data-stu-id="1c522-132">Contains links to topics that discuss different types of bitmaps and manipulating them in your applications.</span></span>
