---
title: 如何：创建实心画笔
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- solid color brushes
- brushes [Windows Forms], examples
- brushes [Windows Forms], creating solid
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
ms.openlocfilehash: ed9ec1f52b41c83b3cc6e36dedf97f1c00db42e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970574"
---
# <a name="how-to-create-a-solid-brush"></a><span data-ttu-id="27d07-102">如何：创建实心画笔</span><span class="sxs-lookup"><span data-stu-id="27d07-102">How to: Create a Solid Brush</span></span>
<span data-ttu-id="27d07-103">此示例将创建一个 <xref:System.Drawing.SolidBrush> 对象，该对象可供 <xref:System.Drawing.Graphics> 对象用于填充形状。</span><span class="sxs-lookup"><span data-stu-id="27d07-103">This example creates a <xref:System.Drawing.SolidBrush> object that can be used by a <xref:System.Drawing.Graphics> object for filling shapes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27d07-104">示例</span><span class="sxs-lookup"><span data-stu-id="27d07-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="27d07-105">可靠编程</span><span class="sxs-lookup"><span data-stu-id="27d07-105">Robust Programming</span></span>  
 <span data-ttu-id="27d07-106">使用完它们后，应 <xref:System.IDisposable.Dispose%2A> 对使用系统资源的对象（如画笔对象）调用。</span><span class="sxs-lookup"><span data-stu-id="27d07-106">After you have finished using them, you should call <xref:System.IDisposable.Dispose%2A> on objects that consume system resources, such as brush objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d07-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27d07-107">See also</span></span>

- <xref:System.Drawing.SolidBrush>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="27d07-108">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="27d07-108">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="27d07-109">GDI+ 中的画笔和实心形状</span><span class="sxs-lookup"><span data-stu-id="27d07-109">Brushes and Filled Shapes in GDI+</span></span>](brushes-and-filled-shapes-in-gdi.md)
- [<span data-ttu-id="27d07-110">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="27d07-110">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
