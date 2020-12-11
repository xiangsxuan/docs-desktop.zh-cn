---
title: 如何：裁剪和缩放图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: 4257431881565f9160f45795111d374cc680dedd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970315"
---
# <a name="how-to-crop-and-scale-images"></a><span data-ttu-id="0291b-102">如何：裁剪和缩放图像</span><span class="sxs-lookup"><span data-stu-id="0291b-102">How to: Crop and Scale Images</span></span>
<span data-ttu-id="0291b-103"><xref:System.Drawing.Graphics>类提供若干 <xref:System.Drawing.Graphics.DrawImage%2A> 方法，其中一些方法具有可用于裁剪和缩放图像的源和目标矩形参数。</span><span class="sxs-lookup"><span data-stu-id="0291b-103">The <xref:System.Drawing.Graphics> class provides several <xref:System.Drawing.Graphics.DrawImage%2A> methods, some of which have source and destination rectangle parameters that you can use to crop and scale images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0291b-104">示例</span><span class="sxs-lookup"><span data-stu-id="0291b-104">Example</span></span>  
 <span data-ttu-id="0291b-105">下面的示例 <xref:System.Drawing.Image> 从磁盘文件 Apple.gif 构造对象。</span><span class="sxs-lookup"><span data-stu-id="0291b-105">The following example constructs an <xref:System.Drawing.Image> object from the disk file Apple.gif.</span></span> <span data-ttu-id="0291b-106">此代码以原始大小绘制整个 apple 图像。</span><span class="sxs-lookup"><span data-stu-id="0291b-106">The code draws the entire apple image in its original size.</span></span> <span data-ttu-id="0291b-107">然后，该代码调用 <xref:System.Drawing.Graphics.DrawImage%2A> 对象的方法， <xref:System.Drawing.Graphics> 以便在大于原始 apple 图像的目标矩形中绘制 apple 图像的一部分。</span><span class="sxs-lookup"><span data-stu-id="0291b-107">The code then calls the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object to draw a portion of the apple image in a destination rectangle that is larger than the original apple image.</span></span>  
  
 <span data-ttu-id="0291b-108"><xref:System.Drawing.Graphics.DrawImage%2A>方法通过查看由第三个、第四个、第五个和第六个参数指定的源矩形来确定要绘制的 apple 部分。</span><span class="sxs-lookup"><span data-stu-id="0291b-108">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines which portion of the apple to draw by looking at the source rectangle, which is specified by the third, fourth, fifth, and sixth arguments.</span></span> <span data-ttu-id="0291b-109">在这种情况下，apple 将裁剪到宽度的75% 和高度的75%。</span><span class="sxs-lookup"><span data-stu-id="0291b-109">In this case, the apple is cropped to 75 percent of its width and 75 percent of its height.</span></span>  
  
 <span data-ttu-id="0291b-110"><xref:System.Drawing.Graphics.DrawImage%2A>方法通过查看目标矩形（由第二个参数指定），确定要在何处绘制裁剪后的 apple 以及如何进行裁剪。</span><span class="sxs-lookup"><span data-stu-id="0291b-110">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines where to draw the cropped apple and how big to make the cropped apple by looking at the destination rectangle, which is specified by the second argument.</span></span> <span data-ttu-id="0291b-111">在这种情况下，目标矩形的宽度为30%，比原始图像高30%。</span><span class="sxs-lookup"><span data-stu-id="0291b-111">In this case, the destination rectangle is 30 percent wider and 30 percent taller than the original image.</span></span>  
  
 <span data-ttu-id="0291b-112">下图显示了原始 apple 和经过缩放的已裁剪 apple。</span><span class="sxs-lookup"><span data-stu-id="0291b-112">The following illustration shows the original apple and the scaled, cropped apple.</span></span>  
  
 ![原始图像和已裁剪的相同图像的屏幕截图。](./media/how-to-crop-and-scale-images/original-image-cropped-image.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0291b-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="0291b-114">Compiling the Code</span></span>  
 <span data-ttu-id="0291b-115">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="0291b-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="0291b-116">请确保将替换为 `Apple.gif` 在系统中有效的图像文件名和路径。</span><span class="sxs-lookup"><span data-stu-id="0291b-116">Make sure to replace `Apple.gif` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0291b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0291b-117">See also</span></span>

- [<span data-ttu-id="0291b-118">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="0291b-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="0291b-119">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="0291b-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
