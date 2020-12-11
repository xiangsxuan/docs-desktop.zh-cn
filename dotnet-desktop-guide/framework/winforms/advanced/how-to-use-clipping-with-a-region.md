---
title: 如何：对区域使用剪裁
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: e62be137b36a2f369c02151466154f6b3bab090b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971396"
---
# <a name="how-to-use-clipping-with-a-region"></a><span data-ttu-id="33b81-102">如何：对区域使用剪裁</span><span class="sxs-lookup"><span data-stu-id="33b81-102">How to: Use Clipping with a Region</span></span>
<span data-ttu-id="33b81-103">类的属性之一 <xref:System.Drawing.Graphics> 是剪辑区域。</span><span class="sxs-lookup"><span data-stu-id="33b81-103">One of the properties of the <xref:System.Drawing.Graphics> class is the clip region.</span></span> <span data-ttu-id="33b81-104">给定对象完成的所有绘图 <xref:System.Drawing.Graphics> 仅限于该对象的剪辑区域 <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="33b81-104">All drawing done by a given <xref:System.Drawing.Graphics> object is restricted to the clip region of that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="33b81-105">可以通过调用方法设置剪辑区域 <xref:System.Drawing.Graphics.SetClip%2A> 。</span><span class="sxs-lookup"><span data-stu-id="33b81-105">You can set the clip region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33b81-106">示例</span><span class="sxs-lookup"><span data-stu-id="33b81-106">Example</span></span>  
 <span data-ttu-id="33b81-107">下面的示例构造一个包含单个多边形的路径。</span><span class="sxs-lookup"><span data-stu-id="33b81-107">The following example constructs a path that consists of a single polygon.</span></span> <span data-ttu-id="33b81-108">然后，代码基于该路径构造一个区域。</span><span class="sxs-lookup"><span data-stu-id="33b81-108">Then the code constructs a region, based on that path.</span></span> <span data-ttu-id="33b81-109">区域将传递给对象的 <xref:System.Drawing.Graphics.SetClip%2A> 方法 <xref:System.Drawing.Graphics> ，然后绘制两个字符串。</span><span class="sxs-lookup"><span data-stu-id="33b81-109">The region is passed to the <xref:System.Drawing.Graphics.SetClip%2A> method of a <xref:System.Drawing.Graphics> object, and then two strings are drawn.</span></span>  
  
 <span data-ttu-id="33b81-110">下图显示了剪切的字符串：</span><span class="sxs-lookup"><span data-stu-id="33b81-110">The following illustration shows the clipped strings:</span></span>  
  
 ![显示已剪裁字符串的屏幕截图。](./media/how-to-use-clipping-with-a-region/clipped-strings-polygon.png)  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="33b81-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="33b81-112">Compiling the Code</span></span>  
 <span data-ttu-id="33b81-113">前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="33b81-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b81-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33b81-114">See also</span></span>

- [<span data-ttu-id="33b81-115">GDI+ 中的区域</span><span class="sxs-lookup"><span data-stu-id="33b81-115">Regions in GDI+</span></span>](regions-in-gdi.md)
- [<span data-ttu-id="33b81-116">使用区域</span><span class="sxs-lookup"><span data-stu-id="33b81-116">Using Regions</span></span>](using-regions.md)
