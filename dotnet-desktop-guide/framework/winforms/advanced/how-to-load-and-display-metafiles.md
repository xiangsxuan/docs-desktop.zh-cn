---
title: 如何：加载和显示图元文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971438"
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="daa36-102">如何：加载和显示图元文件</span><span class="sxs-lookup"><span data-stu-id="daa36-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="daa36-103"><xref:System.Drawing.Imaging.Metafile>类继承自 <xref:System.Drawing.Image> 类，提供用于记录、显示和检查矢量图像的方法。</span><span class="sxs-lookup"><span data-stu-id="daa36-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="daa36-104">示例</span><span class="sxs-lookup"><span data-stu-id="daa36-104">Example</span></span>  
 <span data-ttu-id="daa36-105">若要在屏幕上显示矢量图像 (图元文件) ，需要 <xref:System.Drawing.Imaging.Metafile> 对象和 <xref:System.Drawing.Graphics> 对象。</span><span class="sxs-lookup"><span data-stu-id="daa36-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="daa36-106">将 (或) 流的文件名称传递到 <xref:System.Drawing.Imaging.Metafile> 构造函数。</span><span class="sxs-lookup"><span data-stu-id="daa36-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="daa36-107">创建 <xref:System.Drawing.Imaging.Metafile> 对象后， <xref:System.Drawing.Imaging.Metafile> 将该对象传递给对象的 <xref:System.Drawing.Graphics.DrawImage%2A> 方法 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="daa36-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="daa36-108">该示例 <xref:System.Drawing.Imaging.Metafile> 从 EMF (增强型图元文件) 文件创建一个对象，然后在 (60，10) 的左上角绘制图像。</span><span class="sxs-lookup"><span data-stu-id="daa36-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="daa36-109">下图显示了在指定位置绘制的图元文件。</span><span class="sxs-lookup"><span data-stu-id="daa36-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="daa36-110">![显示图像位置的屏幕截图。](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="daa36-110">![Screenshot showing image position.](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="daa36-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="daa36-111">Compiling the Code</span></span>  
 <span data-ttu-id="daa36-112">前面的示例旨在与 Windows 窗体一起使用，并且它需要作为 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="daa36-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daa36-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="daa36-113">See also</span></span>

- [<span data-ttu-id="daa36-114">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="daa36-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
