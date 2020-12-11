---
title: 如何：实现自定义 ToolStripRenderer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
ms.openlocfilehash: 4a84571bf8b81cd26c864edcd4d313a4009dda16
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971164"
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a><span data-ttu-id="d2d72-102">如何：实现自定义 ToolStripRenderer</span><span class="sxs-lookup"><span data-stu-id="d2d72-102">How to: Implement a Custom ToolStripRenderer</span></span>
<span data-ttu-id="d2d72-103">可以通过实现从 <xref:System.Windows.Forms.ToolStripRenderer> 中派生的类来自定义 <xref:System.Windows.Forms.ToolStrip> 控件的外观。</span><span class="sxs-lookup"><span data-stu-id="d2d72-103">You can customize the appearance of a <xref:System.Windows.Forms.ToolStrip> control by implementing a class that derives from <xref:System.Windows.Forms.ToolStripRenderer>.</span></span> <span data-ttu-id="d2d72-104">这使你可以灵活地创建一个不同于 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 类和 <xref:System.Windows.Forms.ToolStripSystemRenderer> 类提供的外观的外观。</span><span class="sxs-lookup"><span data-stu-id="d2d72-104">This gives you the flexibility to create an appearance that differs from the appearance provided the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> and <xref:System.Windows.Forms.ToolStripSystemRenderer> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2d72-105">示例</span><span class="sxs-lookup"><span data-stu-id="d2d72-105">Example</span></span>  
 <span data-ttu-id="d2d72-106">以下代码示例演示了如何实现一个自定义 <xref:System.Windows.Forms.ToolStripRenderer> 类。</span><span class="sxs-lookup"><span data-stu-id="d2d72-106">The following code example demonstrates how to implement a custom <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="d2d72-107">在此示例中，`GridStrip` 控件实现了一个滑动磁贴拼图，这样用户就可以在表布局中移动磁贴，以形成图像。</span><span class="sxs-lookup"><span data-stu-id="d2d72-107">In this example, the `GridStrip` control implements a sliding-tile puzzle, which allows the user to move tiles in a table layout to form an image.</span></span> <span data-ttu-id="d2d72-108">某个自定义 <xref:System.Windows.Forms.ToolStrip> 控件在网格布局中排列其 <xref:System.Windows.Forms.ToolStripButton> 控件。</span><span class="sxs-lookup"><span data-stu-id="d2d72-108">A custom <xref:System.Windows.Forms.ToolStrip> control arranges its <xref:System.Windows.Forms.ToolStripButton> controls in a grid layout.</span></span> <span data-ttu-id="d2d72-109">布局包含一个空单元格，用户可以通过拖放操作，将相邻的磁贴滑动到其中。</span><span class="sxs-lookup"><span data-stu-id="d2d72-109">The layout contains one empty cell, into which the user can slide an adjacent tile by using a drag-and-drop operation.</span></span> <span data-ttu-id="d2d72-110">用户可以移动的磁贴会突出显示。</span><span class="sxs-lookup"><span data-stu-id="d2d72-110">Tiles that the user can move are highlighted.</span></span>  
  
 <span data-ttu-id="d2d72-111">`GridStripRenderer` 类自定义了 `GridStrip` 控件外观的三个方面：</span><span class="sxs-lookup"><span data-stu-id="d2d72-111">The `GridStripRenderer` class customizes three aspects of the `GridStrip` control's appearance:</span></span>  
  
- <span data-ttu-id="d2d72-112">`GridStrip` 边框</span><span class="sxs-lookup"><span data-stu-id="d2d72-112">`GridStrip` border</span></span>  
  
- <span data-ttu-id="d2d72-113"><xref:System.Windows.Forms.ToolStripButton> 边框</span><span class="sxs-lookup"><span data-stu-id="d2d72-113"><xref:System.Windows.Forms.ToolStripButton> border</span></span>  
  
- <span data-ttu-id="d2d72-114"><xref:System.Windows.Forms.ToolStripButton> 图像</span><span class="sxs-lookup"><span data-stu-id="d2d72-114"><xref:System.Windows.Forms.ToolStripButton> image</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d2d72-115">编译代码</span><span class="sxs-lookup"><span data-stu-id="d2d72-115">Compiling the Code</span></span>  
 <span data-ttu-id="d2d72-116">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="d2d72-116">This example requires:</span></span>  
  
- <span data-ttu-id="d2d72-117">对 System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d2d72-117">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2d72-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2d72-118">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="d2d72-119">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="d2d72-119">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
