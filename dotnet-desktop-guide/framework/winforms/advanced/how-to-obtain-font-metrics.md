---
title: 如何：获取字体规格
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 7d7ad92199bb8a8f01290066f8ae023a14c2f9ce
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971680"
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="c9568-102">如何：获取字体规格</span><span class="sxs-lookup"><span data-stu-id="c9568-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="c9568-103"><xref:System.Drawing.FontFamily>类提供以下方法，这些方法检索特定系列/样式组合的各种度量值：</span><span class="sxs-lookup"><span data-stu-id="c9568-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
- <span data-ttu-id="c9568-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A> (FontStyle) </span><span class="sxs-lookup"><span data-stu-id="c9568-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="c9568-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A> (FontStyle) </span><span class="sxs-lookup"><span data-stu-id="c9568-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="c9568-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A> (FontStyle) </span><span class="sxs-lookup"><span data-stu-id="c9568-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span></span>  
  
- <span data-ttu-id="c9568-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A> (FontStyle) </span><span class="sxs-lookup"><span data-stu-id="c9568-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span></span>  
  
 <span data-ttu-id="c9568-108">这些方法返回的值位于字体设计单元中，因此它们与特定对象的大小和单位无关 <xref:System.Drawing.Font> 。</span><span class="sxs-lookup"><span data-stu-id="c9568-108">The values returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="c9568-109">下图显示了各种度量值：</span><span class="sxs-lookup"><span data-stu-id="c9568-109">The following illustration shows the various metrics:</span></span>
  
 ![字体规格的插图：上升、下降和行距。](./media/how-to-obtain-font-metrics/various-font-metrics.png)  
  
## <a name="example"></a><span data-ttu-id="c9568-111">示例</span><span class="sxs-lookup"><span data-stu-id="c9568-111">Example</span></span>  
 <span data-ttu-id="c9568-112">下面的示例显示 Arial 字体系列的常规样式的指标。</span><span class="sxs-lookup"><span data-stu-id="c9568-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="c9568-113">此代码还会根据 <xref:System.Drawing.Font> Arial 系列) （大小为16像素）创建对象 (，并显示该特定对象的度量值 () （以像素为单位） <xref:System.Drawing.Font> 。</span><span class="sxs-lookup"><span data-stu-id="c9568-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="c9568-114">下图显示了该示例代码的输出：</span><span class="sxs-lookup"><span data-stu-id="c9568-114">The following illustration shows the output of the example code:</span></span>
  
 ![Arial 字体指标的示例代码输出。](./media/how-to-obtain-font-metrics/example-output-code-arial-font.png)  
  
 <span data-ttu-id="c9568-116">请注意上图中输出的前两行。</span><span class="sxs-lookup"><span data-stu-id="c9568-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="c9568-117"><xref:System.Drawing.Font>对象返回的大小为16，而 <xref:System.Drawing.FontFamily> 对象返回的全身高度为2048。</span><span class="sxs-lookup"><span data-stu-id="c9568-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="c9568-118">这两个数字 (16 和 2048) 是在这种情况下，在字体设计单位与 (的单位之间进行转换的关键，这种情况下，对象的) 像素 <xref:System.Drawing.Font> 。</span><span class="sxs-lookup"><span data-stu-id="c9568-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="c9568-119">例如，您可以按如下所示将设计单位中的升高转换为像素：</span><span class="sxs-lookup"><span data-stu-id="c9568-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 ![显示从设计单位到像素的转换的公式](./media/how-to-obtain-font-metrics/convert-font-units-example.png)  
  
 <span data-ttu-id="c9568-121">以下代码通过设置对象的数据成员，使文本垂直放置 <xref:System.Drawing.PointF.Y%2A> <xref:System.Drawing.PointF> 。</span><span class="sxs-lookup"><span data-stu-id="c9568-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="c9568-122">`font.Height`对于每个新的文本行，y 坐标都将增加。</span><span class="sxs-lookup"><span data-stu-id="c9568-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="c9568-123"><xref:System.Drawing.Font.Height%2A>对象的属性 <xref:System.Drawing.Font> 返回该特定对象) 的行距 (以像素为单位 <xref:System.Drawing.Font> 。</span><span class="sxs-lookup"><span data-stu-id="c9568-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="c9568-124">在此示例中，返回的数量 <xref:System.Drawing.Font.Height%2A> 为19。</span><span class="sxs-lookup"><span data-stu-id="c9568-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="c9568-125">请注意，这与 (向上舍入到) 通过将行距度量值转换为像素获得的整数。</span><span class="sxs-lookup"><span data-stu-id="c9568-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="c9568-126">请注意，全身高度 (也称为大小或全身大小) 不是上升和下降之和。</span><span class="sxs-lookup"><span data-stu-id="c9568-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="c9568-127">升高和下降的总和称为单元高度。</span><span class="sxs-lookup"><span data-stu-id="c9568-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="c9568-128">单元高度减去内部前导，等于全身高度。</span><span class="sxs-lookup"><span data-stu-id="c9568-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="c9568-129">单元格高度加上外部前导与行距相等。</span><span class="sxs-lookup"><span data-stu-id="c9568-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c9568-130">编译代码</span><span class="sxs-lookup"><span data-stu-id="c9568-130">Compiling the Code</span></span>  
 <span data-ttu-id="c9568-131">前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="c9568-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9568-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9568-132">See also</span></span>

- [<span data-ttu-id="c9568-133">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="c9568-133">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="c9568-134">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="c9568-134">Using Fonts and Text</span></span>](using-fonts-and-text.md)
