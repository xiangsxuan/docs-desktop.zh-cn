---
title: 如何：创建特定形状的 Windows 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], rounded
- Windows Forms, custom shapes
- Windows Forms, shaped
- shaped forms
- forms [Windows Forms], changing the shape of
- forms [Windows Forms], circular
- forms [Windows Forms], nonrectangular
- Windows Forms, nonrectangular shape
- Windows Forms, rounded
- Windows Forms, circular
- forms [Windows Forms], custom shapes
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
ms.openlocfilehash: 3c90e6d5d2613239e513f8ec30d67b58084cba5e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970576"
---
# <a name="how-to-create-a-shaped-windows-form"></a><span data-ttu-id="aa9f1-102">如何：创建特定形状的 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="aa9f1-102">How to: Create a Shaped Windows Form</span></span>
<span data-ttu-id="aa9f1-103">此示例为窗体提供了一个随窗体一起调整大小的椭圆形形状。</span><span class="sxs-lookup"><span data-stu-id="aa9f1-103">This example gives a form an elliptical shape that resizes with the form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa9f1-104">示例</span><span class="sxs-lookup"><span data-stu-id="aa9f1-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="aa9f1-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="aa9f1-105">Compiling the Code</span></span>  
 <span data-ttu-id="aa9f1-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="aa9f1-106">This example requires:</span></span>  
  
- <span data-ttu-id="aa9f1-107">对 <xref:System.Windows.Forms> 和 <xref:System.Drawing> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="aa9f1-107">References to the <xref:System.Windows.Forms> and <xref:System.Drawing> namespaces.</span></span>  
  
 <span data-ttu-id="aa9f1-108">此示例将重写 <xref:System.Windows.Forms.Control.OnPaint%2A> 方法以更改窗体的形状。</span><span class="sxs-lookup"><span data-stu-id="aa9f1-108">This example overrides the <xref:System.Windows.Forms.Control.OnPaint%2A> method to change the shape of the form.</span></span> <span data-ttu-id="aa9f1-109">若要使用此代码，请复制方法声明以及方法内的绘制代码。</span><span class="sxs-lookup"><span data-stu-id="aa9f1-109">To use this code, copy the method declaration as well as the drawing code inside the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa9f1-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa9f1-110">See also</span></span>

- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Region>
- <xref:System.Drawing>
- <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>
- <xref:System.Windows.Forms.Control.Region%2A>
- [<span data-ttu-id="aa9f1-111">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="aa9f1-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
