---
title: 如何：枚举已安装的字体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 92f27399cce9e03a4679c8a34fbdafcf28c32252
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971706"
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="00c4e-102">如何：枚举已安装的字体</span><span class="sxs-lookup"><span data-stu-id="00c4e-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="00c4e-103"><xref:System.Drawing.Text.InstalledFontCollection>类继承自 <xref:System.Drawing.Text.FontCollection> 抽象基类。</span><span class="sxs-lookup"><span data-stu-id="00c4e-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="00c4e-104">可以使用 <xref:System.Drawing.Text.InstalledFontCollection> 对象枚举计算机上安装的字体。</span><span class="sxs-lookup"><span data-stu-id="00c4e-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="00c4e-105"><xref:System.Drawing.Text.FontCollection.Families%2A>对象的属性 <xref:System.Drawing.Text.InstalledFontCollection> 是对象的数组 <xref:System.Drawing.FontFamily> 。</span><span class="sxs-lookup"><span data-stu-id="00c4e-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00c4e-106">示例</span><span class="sxs-lookup"><span data-stu-id="00c4e-106">Example</span></span>  
 <span data-ttu-id="00c4e-107">以下示例列出了计算机上安装的所有字体系列的名称。</span><span class="sxs-lookup"><span data-stu-id="00c4e-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="00c4e-108">此代码检索 <xref:System.Drawing.FontFamily.Name%2A> <xref:System.Drawing.FontFamily> 由属性返回的数组中每个对象的属性 <xref:System.Drawing.Text.FontCollection.Families%2A> 。</span><span class="sxs-lookup"><span data-stu-id="00c4e-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="00c4e-109">检索系列名称后，它们会连接起来形成一个逗号分隔的列表。</span><span class="sxs-lookup"><span data-stu-id="00c4e-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="00c4e-110">然后， <xref:System.Drawing.Graphics.DrawString%2A> 类的方法 <xref:System.Drawing.Graphics> 在矩形中绘制以逗号分隔的列表。</span><span class="sxs-lookup"><span data-stu-id="00c4e-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="00c4e-111">如果运行示例代码，输出将类似于下图所示：</span><span class="sxs-lookup"><span data-stu-id="00c4e-111">If you run the example code, the output will be similar to that shown in the following illustration:</span></span>  
  
 ![显示已安装字体系列的屏幕截图。](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="00c4e-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="00c4e-113">Compiling the Code</span></span>  
 <span data-ttu-id="00c4e-114">前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="00c4e-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="00c4e-115">此外，还应导入 <xref:System.Drawing.Text> 命名空间。</span><span class="sxs-lookup"><span data-stu-id="00c4e-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00c4e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00c4e-116">See also</span></span>

- [<span data-ttu-id="00c4e-117">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="00c4e-117">Using Fonts and Text</span></span>](using-fonts-and-text.md)
