---
title: 在 GDI+ 中裁切和缩放图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
ms.openlocfilehash: c3cdb06e99770808461f9266fb5f07df9074149b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970678"
---
# <a name="cropping-and-scaling-images-in-gdi"></a><span data-ttu-id="e0815-102">在 GDI+ 中裁切和缩放图像</span><span class="sxs-lookup"><span data-stu-id="e0815-102">Cropping and Scaling Images in GDI+</span></span>
<span data-ttu-id="e0815-103">可以使用类的 <xref:System.Drawing.Graphics.DrawImage%2A> 方法 <xref:System.Drawing.Graphics> 来绘制和定位矢量图像和光栅图像。</span><span class="sxs-lookup"><span data-stu-id="e0815-103">You can use the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> class to draw and position vector images and raster images.</span></span> <span data-ttu-id="e0815-104"><xref:System.Drawing.Graphics.DrawImage%2A> 是一种重载方法，因此可以通过多种方式为其提供参数。</span><span class="sxs-lookup"><span data-stu-id="e0815-104"><xref:System.Drawing.Graphics.DrawImage%2A> is an overloaded method, so there are several ways you can supply it with arguments.</span></span>  
  
## <a name="drawimage-variations"></a><span data-ttu-id="e0815-105">DrawImage 变体</span><span class="sxs-lookup"><span data-stu-id="e0815-105">DrawImage Variations</span></span>  
 <span data-ttu-id="e0815-106">方法的一个变体 <xref:System.Drawing.Graphics.DrawImage%2A> 接收 <xref:System.Drawing.Bitmap> 和一个 <xref:System.Drawing.Rectangle> 。</span><span class="sxs-lookup"><span data-stu-id="e0815-106">One variation of the <xref:System.Drawing.Graphics.DrawImage%2A> method receives a <xref:System.Drawing.Bitmap> and a <xref:System.Drawing.Rectangle>.</span></span> <span data-ttu-id="e0815-107">该矩形指定绘制操作的目标;也就是说，它指定要在其中绘制图像的矩形。</span><span class="sxs-lookup"><span data-stu-id="e0815-107">The rectangle specifies the destination for the drawing operation; that is, it specifies the rectangle in which to draw the image.</span></span> <span data-ttu-id="e0815-108">如果目标矩形的大小与原始图像的大小不同，则对图像进行缩放以适合目标矩形。</span><span class="sxs-lookup"><span data-stu-id="e0815-108">If the size of the destination rectangle is different from the size of the original image, the image is scaled to fit the destination rectangle.</span></span> <span data-ttu-id="e0815-109">下面的代码示例演示如何绘制三次同一图像：一次不进行缩放，一次使用扩展，一次使用压缩：</span><span class="sxs-lookup"><span data-stu-id="e0815-109">The following code example shows how to draw the same image three times: once with no scaling, once with an expansion, and once with a compression:</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 <span data-ttu-id="e0815-110">下图显示了三个图片。</span><span class="sxs-lookup"><span data-stu-id="e0815-110">The following illustration shows the three pictures.</span></span>  
  
 <span data-ttu-id="e0815-111">![缩放](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span><span class="sxs-lookup"><span data-stu-id="e0815-111">![Scaling](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span></span>  
  
 <span data-ttu-id="e0815-112">此方法的某些变体 <xref:System.Drawing.Graphics.DrawImage%2A> 具有源矩形参数和目标矩形参数。</span><span class="sxs-lookup"><span data-stu-id="e0815-112">Some variations of the <xref:System.Drawing.Graphics.DrawImage%2A> method have a source-rectangle parameter as well as a destination-rectangle parameter.</span></span> <span data-ttu-id="e0815-113">源矩形参数指定要绘制的原始图像部分。</span><span class="sxs-lookup"><span data-stu-id="e0815-113">The source-rectangle parameter specifies the portion of the original image to draw.</span></span> <span data-ttu-id="e0815-114">目标矩形指定要在其中绘制图像的一部分的矩形。</span><span class="sxs-lookup"><span data-stu-id="e0815-114">The destination rectangle specifies the rectangle in which to draw that portion of the image.</span></span> <span data-ttu-id="e0815-115">如果目标矩形的大小不同于源矩形的大小，则会缩放图片以适应目标矩形。</span><span class="sxs-lookup"><span data-stu-id="e0815-115">If the size of the destination rectangle is different from the size of the source rectangle, the picture is scaled to fit the destination rectangle.</span></span>  
  
 <span data-ttu-id="e0815-116">下面的代码示例演示如何 <xref:System.Drawing.Bitmap> 从文件 Runner.jpg 构造。</span><span class="sxs-lookup"><span data-stu-id="e0815-116">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Runner.jpg.</span></span> <span data-ttu-id="e0815-117">在 (0，0) 绘制整个图像而不进行缩放。</span><span class="sxs-lookup"><span data-stu-id="e0815-117">The entire image is drawn with no scaling at (0, 0).</span></span> <span data-ttu-id="e0815-118">然后，图像的一小部分绘制两次：一次使用压缩，一次使用扩展。</span><span class="sxs-lookup"><span data-stu-id="e0815-118">Then a small portion of the image is drawn twice: once with a compression and once with an expansion.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 <span data-ttu-id="e0815-119">下图显示了未缩放的图像，以及压缩和扩展的图像部分。</span><span class="sxs-lookup"><span data-stu-id="e0815-119">The following illustration shows the unscaled image, and the compressed and expanded image portions.</span></span>  
  
 <span data-ttu-id="e0815-120">![裁剪和缩放](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span><span class="sxs-lookup"><span data-stu-id="e0815-120">![Cropping and Scaling](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0815-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0815-121">See also</span></span>

- [<span data-ttu-id="e0815-122">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="e0815-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="e0815-123">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="e0815-123">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
