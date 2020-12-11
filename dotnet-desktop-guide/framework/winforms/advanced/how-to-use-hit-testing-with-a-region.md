---
title: 如何：对区域使用命中测试
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 136f15f1364fb2aed791b4a61d0f11411b055967
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971390"
---
# <a name="how-to-use-hit-testing-with-a-region"></a><span data-ttu-id="7bb0a-102">如何：对区域使用命中测试</span><span class="sxs-lookup"><span data-stu-id="7bb0a-102">How to: Use Hit Testing with a Region</span></span>
<span data-ttu-id="7bb0a-103">命中测试的目的是确定光标是否位于给定对象（如图标或按钮）上。</span><span class="sxs-lookup"><span data-stu-id="7bb0a-103">The purpose of hit testing is to determine whether the cursor is over a given object, such as an icon or a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bb0a-104">示例</span><span class="sxs-lookup"><span data-stu-id="7bb0a-104">Example</span></span>  
 <span data-ttu-id="7bb0a-105">下面的示例通过构造两个矩形区域的并集来创建一个加形区域。</span><span class="sxs-lookup"><span data-stu-id="7bb0a-105">The following example creates a plus-shaped region by forming the union of two rectangular regions.</span></span> <span data-ttu-id="7bb0a-106">假定变量 `point` 保存最近单击的位置。</span><span class="sxs-lookup"><span data-stu-id="7bb0a-106">Assume that the variable `point` holds the location of the most recent click.</span></span> <span data-ttu-id="7bb0a-107">代码将检查是否 `point` 在加号区域中。</span><span class="sxs-lookup"><span data-stu-id="7bb0a-107">The code checks to see whether `point` is in the plus-shaped region.</span></span> <span data-ttu-id="7bb0a-108">如果点位于 (命中) 的区域中，则使用不透明的红色画笔填充区域。</span><span class="sxs-lookup"><span data-stu-id="7bb0a-108">If the point is in the region (a hit), the region is filled with an opaque red brush.</span></span> <span data-ttu-id="7bb0a-109">否则，将用半透明的红色画笔填充区域。</span><span class="sxs-lookup"><span data-stu-id="7bb0a-109">Otherwise, the region is filled with a semitransparent red brush.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7bb0a-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="7bb0a-110">Compiling the Code</span></span>  
 <span data-ttu-id="7bb0a-111">前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="7bb0a-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bb0a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7bb0a-112">See also</span></span>

- <xref:System.Drawing.Region>
- [<span data-ttu-id="7bb0a-113">GDI+ 中的区域</span><span class="sxs-lookup"><span data-stu-id="7bb0a-113">Regions in GDI+</span></span>](regions-in-gdi.md)
- [<span data-ttu-id="7bb0a-114">如何：对区域使用剪裁</span><span class="sxs-lookup"><span data-stu-id="7bb0a-114">How to: Use Clipping with a Region</span></span>](how-to-use-clipping-with-a-region.md)
