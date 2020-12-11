---
title: 如何：创建专用的字体集合
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
ms.openlocfilehash: 0bb7293a5423004a13cf98b79bba0a6c411a7c97
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970578"
---
# <a name="how-to-create-a-private-font-collection"></a><span data-ttu-id="22bc9-102">如何：创建专用的字体集合</span><span class="sxs-lookup"><span data-stu-id="22bc9-102">How to: Create a Private Font Collection</span></span>
<span data-ttu-id="22bc9-103"><xref:System.Drawing.Text.PrivateFontCollection>类继承自 <xref:System.Drawing.Text.FontCollection> 抽象基类。</span><span class="sxs-lookup"><span data-stu-id="22bc9-103">The <xref:System.Drawing.Text.PrivateFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="22bc9-104">可以使用 <xref:System.Drawing.Text.PrivateFontCollection> 对象为应用程序维护一组字体。</span><span class="sxs-lookup"><span data-stu-id="22bc9-104">You can use a <xref:System.Drawing.Text.PrivateFontCollection> object to maintain a set of fonts specifically for your application.</span></span> <span data-ttu-id="22bc9-105">专用字体集合可以包含已安装的系统字体以及计算机上尚未安装的字体。</span><span class="sxs-lookup"><span data-stu-id="22bc9-105">A private font collection can include installed system fonts as well as fonts that have not been installed on the computer.</span></span> <span data-ttu-id="22bc9-106">若要将字体文件添加到专用字体集合，请调用 <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> 对象的方法 <xref:System.Drawing.Text.PrivateFontCollection> 。</span><span class="sxs-lookup"><span data-stu-id="22bc9-106">To add a font file to a private font collection, call the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> method of a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="22bc9-107"><xref:System.Drawing.Text.FontCollection.Families%2A>对象的属性 <xref:System.Drawing.Text.PrivateFontCollection> 包含对象的数组 <xref:System.Drawing.FontFamily> 。</span><span class="sxs-lookup"><span data-stu-id="22bc9-107">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of a <xref:System.Drawing.Text.PrivateFontCollection> object contains an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
 <span data-ttu-id="22bc9-108">专用字体集合中的字体系列数量不一定与已添加到集合中的字体文件的数目相同。</span><span class="sxs-lookup"><span data-stu-id="22bc9-108">The number of font families in a private font collection is not necessarily the same as the number of font files that have been added to the collection.</span></span> <span data-ttu-id="22bc9-109">例如，假设将 tff、tff 和 TimesBd 等文件添加到集合。</span><span class="sxs-lookup"><span data-stu-id="22bc9-109">For example, suppose you add the files ArialBd.tff, Times.tff, and TimesBd.tff to a collection.</span></span> <span data-ttu-id="22bc9-110">由于 tff 和 TimesBd 属于同一系列，因此在集合中将有三个文件，但只包含两个系列。</span><span class="sxs-lookup"><span data-stu-id="22bc9-110">There will be three files but only two families in the collection because Times.tff and TimesBd.tff belong to the same family.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22bc9-111">示例</span><span class="sxs-lookup"><span data-stu-id="22bc9-111">Example</span></span>  
 <span data-ttu-id="22bc9-112">下面的示例将以下三个字体文件添加到 <xref:System.Drawing.Text.PrivateFontCollection> 对象：</span><span class="sxs-lookup"><span data-stu-id="22bc9-112">The following example adds the following three font files to a <xref:System.Drawing.Text.PrivateFontCollection> object:</span></span>  
  
- <span data-ttu-id="22bc9-113">C： \\ *systemroot*\Fonts\Arial.tff (Arial，常规) </span><span class="sxs-lookup"><span data-stu-id="22bc9-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, regular)</span></span>  
  
- <span data-ttu-id="22bc9-114">C： \\ *systemroot*\Fonts\CourBI.tff (宋体，黑体) </span><span class="sxs-lookup"><span data-stu-id="22bc9-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New, bold italic)</span></span>  
  
- <span data-ttu-id="22bc9-115">C： \\ *systemroot*\Fonts\TimesBd.tff (New 罗马，bold) </span><span class="sxs-lookup"><span data-stu-id="22bc9-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, bold)</span></span>  
  
 <span data-ttu-id="22bc9-116">代码 <xref:System.Drawing.FontFamily> 从对象的属性中检索对象的数组 <xref:System.Drawing.Text.FontCollection.Families%2A> <xref:System.Drawing.Text.PrivateFontCollection> 。</span><span class="sxs-lookup"><span data-stu-id="22bc9-116">The code retrieves an array of <xref:System.Drawing.FontFamily> objects from the <xref:System.Drawing.Text.FontCollection.Families%2A> property of the <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="22bc9-117">对于集合中的每个 <xref:System.Drawing.FontFamily> 对象，代码会调用 <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> 方法，以确定是否有各种样式 (常规、粗体、斜体、粗体倾斜、下划线和删除线) 可用。</span><span class="sxs-lookup"><span data-stu-id="22bc9-117">For each <xref:System.Drawing.FontFamily> object in the collection, the code calls the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method to determine whether various styles (regular, bold, italic, bold italic, underline, and strikeout) are available.</span></span> <span data-ttu-id="22bc9-118">传递给方法的参数 <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> 是枚举的成员 <xref:System.Drawing.FontStyle> 。</span><span class="sxs-lookup"><span data-stu-id="22bc9-118">The arguments passed to the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method are members of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 <span data-ttu-id="22bc9-119">如果给定的系列/样式组合可用， <xref:System.Drawing.Font> 则使用该系列和样式构造对象。</span><span class="sxs-lookup"><span data-stu-id="22bc9-119">If a given family/style combination is available, a <xref:System.Drawing.Font> object is constructed using that family and style.</span></span> <span data-ttu-id="22bc9-120">传递给构造函数的第一个自变量 <xref:System.Drawing.Font.%23ctor%2A> 是字体系列名称， (不是 <xref:System.Drawing.FontFamily> 对象，) 构造函数的其他变体的情况 <xref:System.Drawing.Font.%23ctor%2A> 。</span><span class="sxs-lookup"><span data-stu-id="22bc9-120">The first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the font family name (not a <xref:System.Drawing.FontFamily> object as is the case for other variations of the <xref:System.Drawing.Font.%23ctor%2A> constructor).</span></span> <span data-ttu-id="22bc9-121"><xref:System.Drawing.Font>构造对象后，它将传递给 <xref:System.Drawing.Graphics.DrawString%2A> 类的方法， <xref:System.Drawing.Graphics> 以显示系列名称以及样式的名称。</span><span class="sxs-lookup"><span data-stu-id="22bc9-121">After the <xref:System.Drawing.Font> object is constructed, it is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class to display the family name along with the name of the style.</span></span>  
  
 <span data-ttu-id="22bc9-122">以下代码的输出类似于下图所示的输出：</span><span class="sxs-lookup"><span data-stu-id="22bc9-122">The output of the following code is similar to the output shown in the following illustration:</span></span>  
  
 ![显示各种字体文本的屏幕截图。](./media/how-to-create-a-private-font-collection/various-fonts-text-output.png)  
  
 <span data-ttu-id="22bc9-124">在以下代码示例中，tff (已添加到专用字体集合中) 是 Arial 常规样式的字体文件。</span><span class="sxs-lookup"><span data-stu-id="22bc9-124">Arial.tff (which was added to the private font collection in the following code example) is the font file for the Arial regular style.</span></span> <span data-ttu-id="22bc9-125">但请注意，除 Arial 字体家族外，程序输出显示了几种不同的可用样式。</span><span class="sxs-lookup"><span data-stu-id="22bc9-125">Note, however, that the program output shows several available styles other than regular for the Arial font family.</span></span> <span data-ttu-id="22bc9-126">这是因为 GDI + 可以从常规样式模拟粗体、斜体和粗体斜体样式。</span><span class="sxs-lookup"><span data-stu-id="22bc9-126">That is because GDI+ can simulate the bold, italic, and bold italic styles from the regular style.</span></span> <span data-ttu-id="22bc9-127">GDI + 还可以从常规样式生成下划线和 strikeouts。</span><span class="sxs-lookup"><span data-stu-id="22bc9-127">GDI+ can also produce underlines and strikeouts from the regular style.</span></span>  
  
 <span data-ttu-id="22bc9-128">同样，GDI + 可以从粗体样式或斜体样式模拟粗体斜体样式。</span><span class="sxs-lookup"><span data-stu-id="22bc9-128">Similarly, GDI+ can simulate the bold italic style from either the bold style or the italic style.</span></span> <span data-ttu-id="22bc9-129">程序输出显示，"粗体" 斜体样式可用于 "时间" 系列，即使 "TimesBd" ("新罗马"，粗体) 是该集合中的唯一时间文件。</span><span class="sxs-lookup"><span data-stu-id="22bc9-129">The program output shows that the bold italic style is available for the Times family even though TimesBd.tff (Times New Roman, bold) is the only Times file in the collection.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="22bc9-130">编译代码</span><span class="sxs-lookup"><span data-stu-id="22bc9-130">Compiling the Code</span></span>  
 <span data-ttu-id="22bc9-131">前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="22bc9-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22bc9-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22bc9-132">See also</span></span>

- <xref:System.Drawing.Text.PrivateFontCollection>
- [<span data-ttu-id="22bc9-133">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="22bc9-133">Using Fonts and Text</span></span>](using-fonts-and-text.md)
