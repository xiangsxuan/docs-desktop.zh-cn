---
title: 如何：构造字体系列和字体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: 2d609525858c7a8ff77c0b86900b4fc7d6b4e39a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970334"
---
# <a name="how-to-construct-font-families-and-fonts"></a><span data-ttu-id="9422d-102">如何：构造字体系列和字体</span><span class="sxs-lookup"><span data-stu-id="9422d-102">How to: Construct Font Families and Fonts</span></span>
<span data-ttu-id="9422d-103">GDI + 将具有相同字样但不同样式的字体分组为字体系列。</span><span class="sxs-lookup"><span data-stu-id="9422d-103">GDI+ groups fonts with the same typeface but different styles into font families.</span></span> <span data-ttu-id="9422d-104">例如，Arial 字体系列包含以下字体：</span><span class="sxs-lookup"><span data-stu-id="9422d-104">For example, the Arial font family contains the following fonts:</span></span>  
  
- <span data-ttu-id="9422d-105">宋体</span><span class="sxs-lookup"><span data-stu-id="9422d-105">Arial Regular</span></span>  
  
- <span data-ttu-id="9422d-106">宋体</span><span class="sxs-lookup"><span data-stu-id="9422d-106">Arial Bold</span></span>  
  
- <span data-ttu-id="9422d-107">宋体</span><span class="sxs-lookup"><span data-stu-id="9422d-107">Arial Italic</span></span>  
  
- <span data-ttu-id="9422d-108">宋体</span><span class="sxs-lookup"><span data-stu-id="9422d-108">Arial Bold Italic</span></span>  
  
 <span data-ttu-id="9422d-109">GDI + 使用四种样式形成系列：常规、粗体、斜体和粗体斜体。</span><span class="sxs-lookup"><span data-stu-id="9422d-109">GDI+ uses four styles to form families: regular, bold, italic, and bold italic.</span></span> <span data-ttu-id="9422d-110">不将形容词（如 *窄幅* 和 *舍入* ）视为样式;它们是系列名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="9422d-110">Adjectives such as *narrow* and *rounded* are not considered styles; rather they are part of the family name.</span></span> <span data-ttu-id="9422d-111">例如，Arial 窄是包含以下成员的字体系列：</span><span class="sxs-lookup"><span data-stu-id="9422d-111">For example, Arial Narrow is a font family with the following members:</span></span>  
  
- <span data-ttu-id="9422d-112">宋体</span><span class="sxs-lookup"><span data-stu-id="9422d-112">Arial Narrow Regular</span></span>  
  
- <span data-ttu-id="9422d-113">宋体</span><span class="sxs-lookup"><span data-stu-id="9422d-113">Arial Narrow Bold</span></span>  
  
- <span data-ttu-id="9422d-114">宋体</span><span class="sxs-lookup"><span data-stu-id="9422d-114">Arial Narrow Italic</span></span>  
  
- <span data-ttu-id="9422d-115">宋体</span><span class="sxs-lookup"><span data-stu-id="9422d-115">Arial Narrow Bold Italic</span></span>  
  
 <span data-ttu-id="9422d-116">在使用 GDI + 绘制文本之前，需要构造一个 <xref:System.Drawing.FontFamily> 对象和一个 <xref:System.Drawing.Font> 对象。</span><span class="sxs-lookup"><span data-stu-id="9422d-116">Before you can draw text with GDI+, you need to construct a <xref:System.Drawing.FontFamily> object and a <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="9422d-117"><xref:System.Drawing.FontFamily>对象指定字样 (例如，Arial) ， <xref:System.Drawing.Font> 对象指定大小、样式和单位。</span><span class="sxs-lookup"><span data-stu-id="9422d-117">The <xref:System.Drawing.FontFamily> object specifies the typeface (for example, Arial), and the <xref:System.Drawing.Font> object specifies the size, style, and units.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9422d-118">示例</span><span class="sxs-lookup"><span data-stu-id="9422d-118">Example</span></span>  
 <span data-ttu-id="9422d-119">下面的示例构造一个常规样式 Arial 字体，大小为16像素。</span><span class="sxs-lookup"><span data-stu-id="9422d-119">The following example constructs a regular style Arial font with a size of 16 pixels.</span></span> <span data-ttu-id="9422d-120">在下面的代码中，传递给构造函数的第一个参数 <xref:System.Drawing.Font.%23ctor%2A> 是 <xref:System.Drawing.FontFamily> 对象。</span><span class="sxs-lookup"><span data-stu-id="9422d-120">In the following code, the first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the <xref:System.Drawing.FontFamily> object.</span></span> <span data-ttu-id="9422d-121">第二个参数指定以第四个参数标识的单位度量的字体大小。</span><span class="sxs-lookup"><span data-stu-id="9422d-121">The second argument specifies the size of the font measured in units identified by the fourth argument.</span></span> <span data-ttu-id="9422d-122">第三个参数标识样式。</span><span class="sxs-lookup"><span data-stu-id="9422d-122">The third argument identifies the style.</span></span>  
  
 <span data-ttu-id="9422d-123"><xref:System.Drawing.GraphicsUnit.Pixel> 是枚举的成员 <xref:System.Drawing.GraphicsUnit> ，并且 <xref:System.Drawing.FontStyle.Regular> 是枚举的成员 <xref:System.Drawing.FontStyle> 。</span><span class="sxs-lookup"><span data-stu-id="9422d-123"><xref:System.Drawing.GraphicsUnit.Pixel> is a member of the <xref:System.Drawing.GraphicsUnit> enumeration, and <xref:System.Drawing.FontStyle.Regular> is a member of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9422d-124">编译代码</span><span class="sxs-lookup"><span data-stu-id="9422d-124">Compiling the Code</span></span>  
 <span data-ttu-id="9422d-125">前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="9422d-125">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9422d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9422d-126">See also</span></span>

- [<span data-ttu-id="9422d-127">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="9422d-127">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="9422d-128">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="9422d-128">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
