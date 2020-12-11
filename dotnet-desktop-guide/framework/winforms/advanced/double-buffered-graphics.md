---
title: 双缓冲图形
ms.date: 03/30/2017
helpviewer_keywords:
- double buffering
- graphics [Windows Forms], double-buffered
- flicker [Windows Forms], reducing with double buffering
- examples [Windows Forms], double-buffered graphics
ms.assetid: 4f6fef99-0972-436e-9d73-0167e4033f71
ms.openlocfilehash: 20ec03e6b84110f7ea00c134dc18b23f233c5f58
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970909"
---
# <a name="double-buffered-graphics"></a>双缓冲图形
对图形进行编程时出现闪烁是一个常见问题。 需要多个复杂画图操作的图形操作可导致呈现的图像出现闪烁或具有不可接受的外观。 为解决这些问题，.NET Framework 提供了双缓冲功能。  
  
 双缓冲使用内容缓冲来解决与多个画图操作相关的闪烁问题。 启用双缓冲后，所有画图操作会首先呈现到内存缓冲而不是屏幕上的绘图图面。 所有画图操作完成后，内存缓冲会直接复制到与之关联的绘图图面。 由于屏幕上仅执行一个图形操作，因此与复杂画图操作相关的图像闪烁可得以消除。  
  
## <a name="default-double-buffering"></a>默认双缓冲  
 在应用程序中使用双缓冲的最简单方式是对 .NET Framework 所提供的的窗体和控件使用默认双缓冲。 可以通过将 <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 属性设置为或，通过使用方法为 Windows 窗体和编写的 Windows 控件启用默认双缓冲 `true` <xref:System.Windows.Forms.Control.SetStyle%2A> 。 有关详细信息，请参阅[如何：通过对窗体和控件使用双缓冲来减少图形闪烁](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)。  
  
## <a name="manually-managing-buffered-graphics"></a>手动管理缓冲图形  
 对于更高级的双缓冲方案（如动画或高级内存管理），可使用 .NET Framework 类来实现自己的双缓冲逻辑。 负责分配和管理单个图形缓冲区的类是 <xref:System.Drawing.BufferedGraphicsContext> 类。 每个应用程序域都有自己的默认 <xref:System.Drawing.BufferedGraphicsContext> 实例，用于管理该应用程序的所有默认双缓冲。 在大多数情况下，每个应用程序只能有一个应用程序域，因此 <xref:System.Drawing.BufferedGraphicsContext> 每个应用程序通常有一个默认值。 默认 <xref:System.Drawing.BufferedGraphicsContext> 实例由 <xref:System.Drawing.BufferedGraphicsManager> 类管理。 可以通过调用来检索对默认实例的引用 <xref:System.Drawing.BufferedGraphicsContext> <xref:System.Drawing.BufferedGraphicsManager.Current%2A> 。 你还可以创建一个专用 <xref:System.Drawing.BufferedGraphicsContext> 实例，该实例可以提高以图形方式密集型应用程序的性能。 有关如何创建实例的信息 <xref:System.Drawing.BufferedGraphicsContext> ，请参阅 [如何：手动管理缓冲图形](how-to-manually-manage-buffered-graphics.md)。  
  
## <a name="manually-displaying-buffered-graphics"></a>手动显示缓冲图形  
 可以 <xref:System.Drawing.BufferedGraphicsContext> 通过调用返回类的实例的，使用类的实例来创建图形缓冲区 <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A?displayProperty=nameWithType> <xref:System.Drawing.BufferedGraphics> 。 <xref:System.Drawing.BufferedGraphics>对象管理与呈现图面（如窗体或控件）关联的内存缓冲区。  
  
 在实例化后， <xref:System.Drawing.BufferedGraphics> 类管理到内存中图形缓冲区的呈现。 可以通过呈现图形到内存缓冲区 <xref:System.Drawing.BufferedGraphics.Graphics%2A> ，这会公开 <xref:System.Drawing.Graphics> 直接表示内存缓冲区的对象。 您可以像 <xref:System.Drawing.Graphics> 对 <xref:System.Drawing.Graphics> 表示绘图图面的对象一样绘制到此对象。 将所有图形绘制到缓冲区后，可以使用将 <xref:System.Drawing.BufferedGraphics.Render%2A?displayProperty=nameWithType> 缓冲区的内容复制到屏幕上的绘图图面。  
  
 有关使用类的详细信息 <xref:System.Drawing.BufferedGraphics> ，请参阅 [手动呈现缓冲图形](how-to-manually-render-buffered-graphics.md)。 有关呈现图形的详细信息，请参阅 [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.BufferedGraphics>
- <xref:System.Drawing.BufferedGraphicsContext>
- <xref:System.Drawing.BufferedGraphicsManager>
- [如何：手动呈现缓冲的图形](how-to-manually-render-buffered-graphics.md)
- [如何：通过对窗体和控件使用双缓冲来减少图形闪烁](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)
- [如何：手动管理缓冲的图形](how-to-manually-manage-buffered-graphics.md)
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
