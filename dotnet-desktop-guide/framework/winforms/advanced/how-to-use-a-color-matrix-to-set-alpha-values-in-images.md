---
title: 如何：使用颜色矩阵设置图像中的 Alpha 值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 73e820845d040856a0ae367da8b9371ad6afa142
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971397"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a><span data-ttu-id="bdbff-102">如何：使用颜色矩阵设置图像中的 Alpha 值</span><span class="sxs-lookup"><span data-stu-id="bdbff-102">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>
<span data-ttu-id="bdbff-103"><xref:System.Drawing.Bitmap>类 (，该类继承自 <xref:System.Drawing.Image> 类) ， <xref:System.Drawing.Imaging.ImageAttributes> 类提供用于获取和设置像素值的功能。</span><span class="sxs-lookup"><span data-stu-id="bdbff-103">The <xref:System.Drawing.Bitmap> class (which inherits from the <xref:System.Drawing.Image> class) and the <xref:System.Drawing.Imaging.ImageAttributes> class provide functionality for getting and setting pixel values.</span></span> <span data-ttu-id="bdbff-104">您可以使用 <xref:System.Drawing.Imaging.ImageAttributes> 类修改整个图像的 alpha 值，也可以调用 <xref:System.Drawing.Bitmap.SetPixel%2A> 类的方法 <xref:System.Drawing.Bitmap> 来修改单个像素值。</span><span class="sxs-lookup"><span data-stu-id="bdbff-104">You can use the <xref:System.Drawing.Imaging.ImageAttributes> class to modify the alpha values for an entire image, or you can call the <xref:System.Drawing.Bitmap.SetPixel%2A> method of the <xref:System.Drawing.Bitmap> class to modify individual pixel values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdbff-105">示例</span><span class="sxs-lookup"><span data-stu-id="bdbff-105">Example</span></span>  
 <span data-ttu-id="bdbff-106"><xref:System.Drawing.Imaging.ImageAttributes>类具有许多可用于在呈现过程中修改图像的属性。</span><span class="sxs-lookup"><span data-stu-id="bdbff-106">The <xref:System.Drawing.Imaging.ImageAttributes> class has many properties that you can use to modify images during rendering.</span></span> <span data-ttu-id="bdbff-107">在下面的示例中， <xref:System.Drawing.Imaging.ImageAttributes> 对象用于将所有 alpha 值设置为80% 的值。</span><span class="sxs-lookup"><span data-stu-id="bdbff-107">In the following example, an <xref:System.Drawing.Imaging.ImageAttributes> object is used to set all the alpha values to 80 percent of what they were.</span></span> <span data-ttu-id="bdbff-108">这是通过初始化颜色矩阵并将矩阵中的 alpha 缩放值设置为0.8 来完成的。</span><span class="sxs-lookup"><span data-stu-id="bdbff-108">This is done by initializing a color matrix and setting the alpha scaling value in the matrix to 0.8.</span></span> <span data-ttu-id="bdbff-109">颜色矩阵的地址将传递给 <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> 对象的方法 <xref:System.Drawing.Imaging.ImageAttributes> ，对象将传递给对象的 <xref:System.Drawing.Imaging.ImageAttributes> <xref:System.Drawing.Graphics.DrawString%2A> 方法 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="bdbff-109">The address of the color matrix is passed to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object, and the <xref:System.Drawing.Imaging.ImageAttributes> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="bdbff-110">在呈现过程中，位图中的 alpha 值将转换为它们的80%。</span><span class="sxs-lookup"><span data-stu-id="bdbff-110">During rendering, the alpha values in the bitmap are converted to 80 percent of what they were.</span></span> <span data-ttu-id="bdbff-111">这会导致图像与背景混合。</span><span class="sxs-lookup"><span data-stu-id="bdbff-111">This results in an image that is blended with the background.</span></span> <span data-ttu-id="bdbff-112">如下图所示，位图图像看起来是透明的;您可以看到它的实心黑色直线。</span><span class="sxs-lookup"><span data-stu-id="bdbff-112">As the following illustration shows, the bitmap image looks transparent; you can see the solid black line through it.</span></span>  
  
 <span data-ttu-id="bdbff-113">![使用矩阵进行 alpha 混合的屏幕截图。](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "image2")</span><span class="sxs-lookup"><span data-stu-id="bdbff-113">![Screenshot of alpha blending using a matrix.](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "image2")</span></span>  
  
 <span data-ttu-id="bdbff-114">如果图像位于背景的空白部分，则图像已与白色颜色混合。</span><span class="sxs-lookup"><span data-stu-id="bdbff-114">Where the image is over the white portion of the background, the image has been blended with the color white.</span></span> <span data-ttu-id="bdbff-115">如果图像与黑色线条交叉，图像会与黑色混合。</span><span class="sxs-lookup"><span data-stu-id="bdbff-115">Where the image crosses the black line, the image is blended with the color black.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bdbff-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="bdbff-116">Compiling the Code</span></span>  
 <span data-ttu-id="bdbff-117">前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="bdbff-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdbff-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdbff-118">See also</span></span>

- [<span data-ttu-id="bdbff-119">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="bdbff-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="bdbff-120">Alpha 混合线条和填充</span><span class="sxs-lookup"><span data-stu-id="bdbff-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
