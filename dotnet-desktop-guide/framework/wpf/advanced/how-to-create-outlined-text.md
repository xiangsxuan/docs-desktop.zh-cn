---
title: 如何：创建空心文字
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: 12da12320a09fa825d9c75d4a6e5e3264724de77
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604345"
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="e14cc-102">如何：创建空心文本</span><span class="sxs-lookup"><span data-stu-id="e14cc-102">How to: Create outlined text</span></span>

<span data-ttu-id="e14cc-103">在大多数情况下，当你将装饰添加到应用程序中的文本字符串时， [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 将在离散字符或标志符号的集合中使用文本。</span><span class="sxs-lookup"><span data-stu-id="e14cc-103">In most cases, when you're adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="e14cc-104">例如，可以创建线性渐变画笔，并将其应用于对象的 <xref:System.Windows.Controls.Control.Foreground%2A> 属性 <xref:System.Windows.Controls.TextBox> 。</span><span class="sxs-lookup"><span data-stu-id="e14cc-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="e14cc-105">显示或编辑文本框时，线性渐变画笔会自动应用于文本字符串中的当前字符集。</span><span class="sxs-lookup"><span data-stu-id="e14cc-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 ![使用线性渐变画笔显示的文本](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 <span data-ttu-id="e14cc-107">但是，您还可以将文本转换为 <xref:System.Windows.Media.Geometry> 对象，从而允许您创建其他类型的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="e14cc-107">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="e14cc-108">例如，可以根据 <xref:System.Windows.Media.Geometry> 文本字符串的轮廓创建对象。</span><span class="sxs-lookup"><span data-stu-id="e14cc-108">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 ![使用线性渐变画笔的文本轮廓](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 <span data-ttu-id="e14cc-110">当文本转换为对象时 <xref:System.Windows.Media.Geometry> ，它不再是字符的集合，您不能修改文本字符串中的字符。</span><span class="sxs-lookup"><span data-stu-id="e14cc-110">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="e14cc-111">但是，可修改已转换文本的笔划和填充属性，以此来影响该文本的外观。</span><span class="sxs-lookup"><span data-stu-id="e14cc-111">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="e14cc-112">笔划是指已转换文本的轮廓；填充是指已转换文本的轮廓的内部区域。</span><span class="sxs-lookup"><span data-stu-id="e14cc-112">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="e14cc-113">下面的示例演示了通过修改已转换文本的笔划和填充来创建视觉效果的多种方法。</span><span class="sxs-lookup"><span data-stu-id="e14cc-113">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 ![对填充和笔画使用不同颜色的文本](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![笔画应用了图像画笔的文本](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 <span data-ttu-id="e14cc-116">还可以修改已转换文本的边界框矩形或突出显示的文本。</span><span class="sxs-lookup"><span data-stu-id="e14cc-116">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="e14cc-117">下面的示例演示了一种通过修改已转换文本的笔画和突出显示来创建视觉效果的方法。</span><span class="sxs-lookup"><span data-stu-id="e14cc-117">The following example illustrates a way to create visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 ![将图像画笔应用于笔划和突出显示的文本](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a><span data-ttu-id="e14cc-119">示例</span><span class="sxs-lookup"><span data-stu-id="e14cc-119">Example</span></span>  
 <span data-ttu-id="e14cc-120">将文本转换为对象的关键 <xref:System.Windows.Media.Geometry> 是使用 <xref:System.Windows.Media.FormattedText> 对象。</span><span class="sxs-lookup"><span data-stu-id="e14cc-120">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="e14cc-121">创建此对象后，可以使用 <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> 和 <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> 方法将文本转换为 <xref:System.Windows.Media.Geometry> 对象。</span><span class="sxs-lookup"><span data-stu-id="e14cc-121">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="e14cc-122">第一种方法返回格式化文本的几何图形;第二个方法返回格式化文本的边界框的几何。</span><span class="sxs-lookup"><span data-stu-id="e14cc-122">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="e14cc-123">下面的代码示例演示如何创建 <xref:System.Windows.Media.FormattedText> 对象并检索带格式文本及其边界框的几何。</span><span class="sxs-lookup"><span data-stu-id="e14cc-123">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="e14cc-124">为了显示检索到的 <xref:System.Windows.Media.Geometry> 对象，需要访问 <xref:System.Windows.Media.DrawingContext> 显示已转换文本的对象的。</span><span class="sxs-lookup"><span data-stu-id="e14cc-124">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that's displaying the converted text.</span></span> <span data-ttu-id="e14cc-125">在以下代码示例中，通过创建一个自定义控件对象来实现此访问，该对象派生自支持用户定义的呈现的类。</span><span class="sxs-lookup"><span data-stu-id="e14cc-125">In these code examples, this access is achieved by creating a custom control object that's derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="e14cc-126">若要显示 <xref:System.Windows.Media.Geometry> 自定义控件中的对象，请为方法提供重写 <xref:System.Windows.UIElement.OnRender%2A> 。</span><span class="sxs-lookup"><span data-stu-id="e14cc-126">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="e14cc-127">重写的方法应使用 <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> 方法来绘制 <xref:System.Windows.Media.Geometry> 对象。</span><span class="sxs-lookup"><span data-stu-id="e14cc-127">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  <span data-ttu-id="e14cc-128">有关示例自定义用户控件对象的源，请参阅 [OutlineTextControl.cs For c #](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) 和 [OutlineTextControl for Visual Basic](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb)。</span><span class="sxs-lookup"><span data-stu-id="e14cc-128">For the source of the example custom user control object, see [OutlineTextControl.cs for C#](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) and [OutlineTextControl.vb for Visual Basic](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e14cc-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e14cc-129">See also</span></span>

- [<span data-ttu-id="e14cc-130">绘制格式化文本</span><span class="sxs-lookup"><span data-stu-id="e14cc-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
