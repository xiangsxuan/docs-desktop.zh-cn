---
title: 如何：创建缩略图图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 786a92d99f5e7a0c27f502efa9a5fe617ac4d4d6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970321"
---
# <a name="how-to-create-thumbnail-images"></a><span data-ttu-id="86ec0-102">如何：创建缩略图图像</span><span class="sxs-lookup"><span data-stu-id="86ec0-102">How to: Create Thumbnail Images</span></span>
<span data-ttu-id="86ec0-103">缩略图是图像的小型版本。</span><span class="sxs-lookup"><span data-stu-id="86ec0-103">A thumbnail image is a small version of an image.</span></span> <span data-ttu-id="86ec0-104">可以通过调用对象的方法来创建缩略图 <xref:System.Drawing.Image.GetThumbnailImage%2A> <xref:System.Drawing.Image> 。</span><span class="sxs-lookup"><span data-stu-id="86ec0-104">You can create a thumbnail image by calling the <xref:System.Drawing.Image.GetThumbnailImage%2A> method of an <xref:System.Drawing.Image> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86ec0-105">示例</span><span class="sxs-lookup"><span data-stu-id="86ec0-105">Example</span></span>  
 <span data-ttu-id="86ec0-106">下面的示例 <xref:System.Drawing.Image> 从 JPG 文件构造对象。</span><span class="sxs-lookup"><span data-stu-id="86ec0-106">The following example constructs an <xref:System.Drawing.Image> object from a JPG file.</span></span> <span data-ttu-id="86ec0-107">原始图像的宽度为640像素，高度为479像素。</span><span class="sxs-lookup"><span data-stu-id="86ec0-107">The original image has a width of 640 pixels and a height of 479 pixels.</span></span> <span data-ttu-id="86ec0-108">此代码创建一个宽度为100像素、高度为100像素的缩略图。</span><span class="sxs-lookup"><span data-stu-id="86ec0-108">The code creates a thumbnail image that has a width of 100 pixels and a height of 100 pixels.</span></span>  
  
 <span data-ttu-id="86ec0-109">下图显示了缩略图：</span><span class="sxs-lookup"><span data-stu-id="86ec0-109">The following illustration shows the thumbnail image:</span></span>  
  
 ![显示输出缩略图的屏幕截图。](./media/how-to-create-thumbnail-images/construct-thumbnail-image.png)  
  
> [!NOTE]
> <span data-ttu-id="86ec0-111">在此示例中，声明了回调方法，但从未使用过。</span><span class="sxs-lookup"><span data-stu-id="86ec0-111">In this example, a callback method is declared, but never used.</span></span> <span data-ttu-id="86ec0-112">这支持所有版本的 GDI +。</span><span class="sxs-lookup"><span data-stu-id="86ec0-112">This supports all versions of GDI+.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="86ec0-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="86ec0-113">Compiling the Code</span></span>  
 <span data-ttu-id="86ec0-114">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="86ec0-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="86ec0-115">若要运行该示例，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="86ec0-115">To run the example, follow these steps:</span></span>  
  
1. <span data-ttu-id="86ec0-116">创建新的 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="86ec0-116">Create a new Windows Forms application.</span></span>  
  
2. <span data-ttu-id="86ec0-117">将示例代码添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="86ec0-117">Add the example code to the form.</span></span>  
  
3. <span data-ttu-id="86ec0-118">为窗体事件创建处理程序 <xref:System.Windows.Forms.Control.Paint></span><span class="sxs-lookup"><span data-stu-id="86ec0-118">Create a handler for the form's <xref:System.Windows.Forms.Control.Paint> event</span></span>  
  
4. <span data-ttu-id="86ec0-119">在 <xref:System.Windows.Forms.Control.Paint> 处理程序中，调用 `GetThumbnail` 方法并传递 `e` <xref:System.Windows.Forms.PaintEventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="86ec0-119">In the <xref:System.Windows.Forms.Control.Paint> handler, call the `GetThumbnail` method and pass `e` for <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
5. <span data-ttu-id="86ec0-120">查找要建立缩略图的图像文件。</span><span class="sxs-lookup"><span data-stu-id="86ec0-120">Find an image file that you want to make a thumbnail of.</span></span>  
  
6. <span data-ttu-id="86ec0-121">在 `GetThumbnail` 方法中，指定映像的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="86ec0-121">In the `GetThumbnail` method, specify the path and file name to your image.</span></span>  
  
7. <span data-ttu-id="86ec0-122">按 F5 运行该示例。</span><span class="sxs-lookup"><span data-stu-id="86ec0-122">Press F5 to run the example.</span></span>  
  
     <span data-ttu-id="86ec0-123">窗体上将显示 100 x 100 缩略图图像。</span><span class="sxs-lookup"><span data-stu-id="86ec0-123">A 100 by 100 thumbnail image appears on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86ec0-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86ec0-124">See also</span></span>

- [<span data-ttu-id="86ec0-125">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="86ec0-125">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="86ec0-126">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="86ec0-126">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
