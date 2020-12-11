---
title: 如何：手动呈现缓冲的图形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually rendering graphics
- graphics [Windows Forms], rendering
ms.assetid: 5192295e-bd8e-45f7-8bd6-5c4f6bd21e61
ms.openlocfilehash: a6655652a7c5dedb8e183356688972c07a705cbc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971436"
---
# <a name="how-to-manually-render-buffered-graphics"></a><span data-ttu-id="903de-102">如何：手动呈现缓冲的图形</span><span class="sxs-lookup"><span data-stu-id="903de-102">How to: Manually Render Buffered Graphics</span></span>
<span data-ttu-id="903de-103">如果你正在管理自己的缓冲图形，你将需要能创建和程序图形缓冲区。</span><span class="sxs-lookup"><span data-stu-id="903de-103">If you are managing your own buffered graphics, you will need to be able to create and render graphics buffers.</span></span> <span data-ttu-id="903de-104">你可以通过调用 <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> 方法，在屏幕上创建与绘图图面相关联的 <xref:System.Drawing.BufferedGraphics> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="903de-104">You can create instances of the <xref:System.Drawing.BufferedGraphics> class that is associated with drawing surfaces on your screen by calling the <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> method.</span></span> <span data-ttu-id="903de-105">此方法会创建一个与特定呈现图面（如表格或控件）关联的 <xref:System.Drawing.BufferedGraphics> 实例。</span><span class="sxs-lookup"><span data-stu-id="903de-105">This method creates a <xref:System.Drawing.BufferedGraphics> instance that is associated with a particular rendering surface, such as a form or control.</span></span> <span data-ttu-id="903de-106">在创建 <xref:System.Drawing.BufferedGraphics> 实例后，可以通过 <xref:System.Drawing.BufferedGraphics.Graphics%2A> 属性，将图形绘制到它表示的缓冲区内。</span><span class="sxs-lookup"><span data-stu-id="903de-106">After you have created a <xref:System.Drawing.BufferedGraphics> instance, you can draw graphics to the buffer it represents through the <xref:System.Drawing.BufferedGraphics.Graphics%2A> property.</span></span> <span data-ttu-id="903de-107">执行所有图形操作之后，可以通过调用 <xref:System.Drawing.BufferedGraphics.Render%2A> 方法将缓冲区的内容复制到屏幕。</span><span class="sxs-lookup"><span data-stu-id="903de-107">After you have performed all graphics operations, you can copy the contents of the buffer to the screen by calling the <xref:System.Drawing.BufferedGraphics.Render%2A> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="903de-108">如果执行自己的呈现，内存消耗将会增加，但可能只是略微增加。</span><span class="sxs-lookup"><span data-stu-id="903de-108">If you perform your own rendering, memory consumption will increase, though the increase may only be slight.</span></span>  
  
### <a name="to-manually-display-buffered-graphics"></a><span data-ttu-id="903de-109">手动显示缓冲图形</span><span class="sxs-lookup"><span data-stu-id="903de-109">To manually display buffered graphics</span></span>  
  
1. <span data-ttu-id="903de-110">获取对 <xref:System.Drawing.BufferedGraphicsContext> 类的实例的引用。</span><span class="sxs-lookup"><span data-stu-id="903de-110">Obtain a reference to an instance of the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="903de-111">有关详细信息，请参阅 [如何：手动管理缓冲图形](how-to-manually-manage-buffered-graphics.md)。</span><span class="sxs-lookup"><span data-stu-id="903de-111">For more information, see [How to: Manually Manage Buffered Graphics](how-to-manually-manage-buffered-graphics.md).</span></span>  
  
2. <span data-ttu-id="903de-112">如下列代码示例所示，通过调用 <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> 方法，创建 <xref:System.Drawing.BufferedGraphics> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="903de-112">Create an instance of the <xref:System.Drawing.BufferedGraphics> class by calling the <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> method, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#21)]  
  
3. <span data-ttu-id="903de-113">通过设置 <xref:System.Drawing.BufferedGraphics.Graphics%2A> 属性将图形绘制到图形缓冲区内。</span><span class="sxs-lookup"><span data-stu-id="903de-113">Draw graphics to the graphics buffer by setting the <xref:System.Drawing.BufferedGraphics.Graphics%2A> property.</span></span> <span data-ttu-id="903de-114">例如：</span><span class="sxs-lookup"><span data-stu-id="903de-114">For example:</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#22)]  
  
4. <span data-ttu-id="903de-115">当你已完成所有对图形缓冲区的绘制操作时，调用 <xref:System.Drawing.BufferedGraphics.Render%2A> 方法将缓冲区呈现到与该缓冲区关联的绘图图面或指定的绘图图面，如下列代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="903de-115">When you have completed all of your drawing operations to the graphics buffer, call the <xref:System.Drawing.BufferedGraphics.Render%2A> method to render the buffer, either to the drawing surface associated with that buffer, or to a specified drawing surface, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#23)]  
  
5. <span data-ttu-id="903de-116">在完成图形呈现后，调用 <xref:System.Drawing.BufferedGraphics> 实例上的 `Dispose` 方法释放系统资源。</span><span class="sxs-lookup"><span data-stu-id="903de-116">After you are finished rendering graphics, call the `Dispose` method on the <xref:System.Drawing.BufferedGraphics> instance to free system resources.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#24)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#24)]  
  
## <a name="see-also"></a><span data-ttu-id="903de-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="903de-117">See also</span></span>

- <xref:System.Drawing.BufferedGraphicsContext>
- <xref:System.Drawing.BufferedGraphics>
- [<span data-ttu-id="903de-118">双缓冲图形</span><span class="sxs-lookup"><span data-stu-id="903de-118">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="903de-119">如何：手动管理缓冲的图形</span><span class="sxs-lookup"><span data-stu-id="903de-119">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)
