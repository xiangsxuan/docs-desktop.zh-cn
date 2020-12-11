---
title: 在 GDI+ 中绘制、定位和克隆图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
ms.openlocfilehash: b5f98e7bdef9ff8ed0a4cd0e040cb92a31f30503
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970826"
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a><span data-ttu-id="ee51b-102">在 GDI+ 中绘制、定位和克隆图像</span><span class="sxs-lookup"><span data-stu-id="ee51b-102">Drawing, Positioning, and Cloning Images in GDI+</span></span>
<span data-ttu-id="ee51b-103">可以使用 <xref:System.Drawing.Bitmap> 类来加载和显示光栅图像，还可以使用 <xref:System.Drawing.Imaging.Metafile> 类加载和显示矢量图像。</span><span class="sxs-lookup"><span data-stu-id="ee51b-103">You can use the <xref:System.Drawing.Bitmap> class to load and display raster images, and you can use the <xref:System.Drawing.Imaging.Metafile> class to load and display vector images.</span></span> <span data-ttu-id="ee51b-104"><xref:System.Drawing.Bitmap>和 <xref:System.Drawing.Imaging.Metafile> 类继承自 <xref:System.Drawing.Image> 类。</span><span class="sxs-lookup"><span data-stu-id="ee51b-104">The <xref:System.Drawing.Bitmap> and <xref:System.Drawing.Imaging.Metafile> classes inherit from the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="ee51b-105">若要显示矢量图像，需要 <xref:System.Drawing.Graphics> 类和的实例 <xref:System.Drawing.Imaging.Metafile> 。</span><span class="sxs-lookup"><span data-stu-id="ee51b-105">To display a vector image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="ee51b-106">若要显示光栅图像，需要 <xref:System.Drawing.Graphics> 类和的实例 <xref:System.Drawing.Bitmap> 。</span><span class="sxs-lookup"><span data-stu-id="ee51b-106">To display a raster image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="ee51b-107">类的实例 <xref:System.Drawing.Graphics> 提供了 <xref:System.Drawing.Graphics.DrawImage%2A> 方法，该方法将 <xref:System.Drawing.Imaging.Metafile> 或 <xref:System.Drawing.Bitmap> 作为参数接收。</span><span class="sxs-lookup"><span data-stu-id="ee51b-107">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawImage%2A> method, which receives the <xref:System.Drawing.Imaging.Metafile> or <xref:System.Drawing.Bitmap> as an argument.</span></span>  
  
## <a name="file-types-and-cloning"></a><span data-ttu-id="ee51b-108">文件类型和克隆</span><span class="sxs-lookup"><span data-stu-id="ee51b-108">File Types and Cloning</span></span>  
 <span data-ttu-id="ee51b-109">下面的代码示例演示如何 <xref:System.Drawing.Bitmap> 从文件 Climber.jpg 构造，并显示位图。</span><span class="sxs-lookup"><span data-stu-id="ee51b-109">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Climber.jpg and displays the bitmap.</span></span> <span data-ttu-id="ee51b-110">在第二个和第三个参数中指定了图像的左上角的目标点， (10，10) 。</span><span class="sxs-lookup"><span data-stu-id="ee51b-110">The destination point for the upper-left corner of the image, (10, 10), is specified in the second and third parameters.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 <span data-ttu-id="ee51b-111">下图显示了该图像。</span><span class="sxs-lookup"><span data-stu-id="ee51b-111">The following illustration shows the image.</span></span>  
  
 <span data-ttu-id="ee51b-112">![图像示例](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span><span class="sxs-lookup"><span data-stu-id="ee51b-112">![Image Sample](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span></span>  
  
 <span data-ttu-id="ee51b-113">可以 <xref:System.Drawing.Bitmap> 从各种图形文件格式构造对象： BMP、GIF、JPEG、EXIF、PNG、TIFF 和图标。</span><span class="sxs-lookup"><span data-stu-id="ee51b-113">You can construct <xref:System.Drawing.Bitmap> objects from a variety of graphics file formats: BMP, GIF, JPEG, EXIF, PNG, TIFF, and ICON.</span></span>  
  
 <span data-ttu-id="ee51b-114">下面的代码示例演示如何 <xref:System.Drawing.Bitmap> 从各种文件类型构造对象，然后显示位图。</span><span class="sxs-lookup"><span data-stu-id="ee51b-114">The following code example shows how to construct <xref:System.Drawing.Bitmap> objects from a variety of file types and then displays the bitmaps.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <span data-ttu-id="ee51b-115"><xref:System.Drawing.Bitmap>类提供了一个 <xref:System.Drawing.Bitmap.Clone%2A> 方法，您可以使用该方法创建现有的副本 <xref:System.Drawing.Bitmap> 。</span><span class="sxs-lookup"><span data-stu-id="ee51b-115">The <xref:System.Drawing.Bitmap> class provides a <xref:System.Drawing.Bitmap.Clone%2A> method that you can use to make a copy of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="ee51b-116"><xref:System.Drawing.Bitmap.Clone%2A>方法具有一个源矩形参数，可用于指定要复制的原始位图部分。</span><span class="sxs-lookup"><span data-stu-id="ee51b-116">The <xref:System.Drawing.Bitmap.Clone%2A> method has a source rectangle parameter that you can use to specify the portion of the original bitmap that you want to copy.</span></span> <span data-ttu-id="ee51b-117">下面的代码示例演示如何 <xref:System.Drawing.Bitmap> 通过克隆现有的上半部分来创建 <xref:System.Drawing.Bitmap> 。</span><span class="sxs-lookup"><span data-stu-id="ee51b-117">The following code example shows how to create a <xref:System.Drawing.Bitmap> by cloning the top half of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="ee51b-118">然后绘制两个图像。</span><span class="sxs-lookup"><span data-stu-id="ee51b-118">Then both images are drawn.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 <span data-ttu-id="ee51b-119">下图显示了这两个图像。</span><span class="sxs-lookup"><span data-stu-id="ee51b-119">The following illustration shows the two images.</span></span>  
  
 <span data-ttu-id="ee51b-120">![裁剪](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span><span class="sxs-lookup"><span data-stu-id="ee51b-120">![Cropping](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee51b-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee51b-121">See also</span></span>

- [<span data-ttu-id="ee51b-122">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="ee51b-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="ee51b-123">如何：创建用于绘制的 Graphics 对象</span><span class="sxs-lookup"><span data-stu-id="ee51b-123">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="ee51b-124">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="ee51b-124">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
