---
title: 如何：将数据绑定到 InkCanvas
ms.date: 03/30/2017
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
ms.openlocfilehash: 5d3fc0ed7b6176d7bc68bf20af42c311b5563908
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973492"
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a><span data-ttu-id="a2007-102">如何：将数据绑定到 InkCanvas</span><span class="sxs-lookup"><span data-stu-id="a2007-102">How to: Data Bind to an InkCanvas</span></span>
## <a name="example"></a><span data-ttu-id="a2007-103">示例</span><span class="sxs-lookup"><span data-stu-id="a2007-103">Example</span></span>  
 <span data-ttu-id="a2007-104">下面的示例演示如何将的 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 属性绑定 <xref:System.Windows.Controls.InkCanvas> 到另一个 <xref:System.Windows.Controls.InkCanvas> 。</span><span class="sxs-lookup"><span data-stu-id="a2007-104">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.Strokes%2A> property of an <xref:System.Windows.Controls.InkCanvas> to another <xref:System.Windows.Controls.InkCanvas>.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 <span data-ttu-id="a2007-105">下面的示例演示如何将属性绑定 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 到数据源。</span><span class="sxs-lookup"><span data-stu-id="a2007-105">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property to a data source.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 <span data-ttu-id="a2007-106">下面的示例在 XAML 中声明了两个 <xref:System.Windows.Controls.InkCanvas> 对象，并在这些对象和其他数据源之间建立了数据绑定。</span><span class="sxs-lookup"><span data-stu-id="a2007-106">The following example declares two <xref:System.Windows.Controls.InkCanvas> objects in XAML and establishes data binding between them and other data sources.</span></span>  <span data-ttu-id="a2007-107">第一个 <xref:System.Windows.Controls.InkCanvas> （称为 `ic` ）绑定到两个数据源。</span><span class="sxs-lookup"><span data-stu-id="a2007-107">The first <xref:System.Windows.Controls.InkCanvas>, called `ic`, is bound to two data sources.</span></span>  <span data-ttu-id="a2007-108"><xref:System.Windows.Controls.InkCanvas.EditingMode%2A>上的和 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 属性 `ic` 绑定到 <xref:System.Windows.Controls.ListBox> 对象，后者又绑定到 XAML 中定义的数组。</span><span class="sxs-lookup"><span data-stu-id="a2007-108">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> and <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties on `ic` are bound to <xref:System.Windows.Controls.ListBox> objects, which are in turn bound to arrays defined in the XAML.</span></span>  <span data-ttu-id="a2007-109"><xref:System.Windows.Controls.InkCanvas.EditingMode%2A> <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 第二个的、和属性 <xref:System.Windows.Controls.InkCanvas> 绑定到第一个 <xref:System.Windows.Controls.InkCanvas> `ic` 。</span><span class="sxs-lookup"><span data-stu-id="a2007-109">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, and <xref:System.Windows.Controls.InkCanvas.Strokes%2A> properties of the second <xref:System.Windows.Controls.InkCanvas> are bound to the first <xref:System.Windows.Controls.InkCanvas>, `ic`.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
