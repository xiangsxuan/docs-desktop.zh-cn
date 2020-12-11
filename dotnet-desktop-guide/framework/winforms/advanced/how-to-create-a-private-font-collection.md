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
# <a name="how-to-create-a-private-font-collection"></a>如何：创建专用的字体集合
<xref:System.Drawing.Text.PrivateFontCollection>类继承自 <xref:System.Drawing.Text.FontCollection> 抽象基类。 可以使用 <xref:System.Drawing.Text.PrivateFontCollection> 对象为应用程序维护一组字体。 专用字体集合可以包含已安装的系统字体以及计算机上尚未安装的字体。 若要将字体文件添加到专用字体集合，请调用 <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> 对象的方法 <xref:System.Drawing.Text.PrivateFontCollection> 。  
  
 <xref:System.Drawing.Text.FontCollection.Families%2A>对象的属性 <xref:System.Drawing.Text.PrivateFontCollection> 包含对象的数组 <xref:System.Drawing.FontFamily> 。  
  
 专用字体集合中的字体系列数量不一定与已添加到集合中的字体文件的数目相同。 例如，假设将 tff、tff 和 TimesBd 等文件添加到集合。 由于 tff 和 TimesBd 属于同一系列，因此在集合中将有三个文件，但只包含两个系列。  
  
## <a name="example"></a>示例  
 下面的示例将以下三个字体文件添加到 <xref:System.Drawing.Text.PrivateFontCollection> 对象：  
  
- C： \\ *systemroot*\Fonts\Arial.tff (Arial，常规)   
  
- C： \\ *systemroot*\Fonts\CourBI.tff (宋体，黑体)   
  
- C： \\ *systemroot*\Fonts\TimesBd.tff (New 罗马，bold)   
  
 代码 <xref:System.Drawing.FontFamily> 从对象的属性中检索对象的数组 <xref:System.Drawing.Text.FontCollection.Families%2A> <xref:System.Drawing.Text.PrivateFontCollection> 。  
  
 对于集合中的每个 <xref:System.Drawing.FontFamily> 对象，代码会调用 <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> 方法，以确定是否有各种样式 (常规、粗体、斜体、粗体倾斜、下划线和删除线) 可用。 传递给方法的参数 <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> 是枚举的成员 <xref:System.Drawing.FontStyle> 。  
  
 如果给定的系列/样式组合可用， <xref:System.Drawing.Font> 则使用该系列和样式构造对象。 传递给构造函数的第一个自变量 <xref:System.Drawing.Font.%23ctor%2A> 是字体系列名称， (不是 <xref:System.Drawing.FontFamily> 对象，) 构造函数的其他变体的情况 <xref:System.Drawing.Font.%23ctor%2A> 。 <xref:System.Drawing.Font>构造对象后，它将传递给 <xref:System.Drawing.Graphics.DrawString%2A> 类的方法， <xref:System.Drawing.Graphics> 以显示系列名称以及样式的名称。  
  
 以下代码的输出类似于下图所示的输出：  
  
 ![显示各种字体文本的屏幕截图。](./media/how-to-create-a-private-font-collection/various-fonts-text-output.png)  
  
 在以下代码示例中，tff (已添加到专用字体集合中) 是 Arial 常规样式的字体文件。 但请注意，除 Arial 字体家族外，程序输出显示了几种不同的可用样式。 这是因为 GDI + 可以从常规样式模拟粗体、斜体和粗体斜体样式。 GDI + 还可以从常规样式生成下划线和 strikeouts。  
  
 同样，GDI + 可以从粗体样式或斜体样式模拟粗体斜体样式。 程序输出显示，"粗体" 斜体样式可用于 "时间" 系列，即使 "TimesBd" ("新罗马"，粗体) 是该集合中的唯一时间文件。  
  
 [!code-csharp[System.Drawing.FontsAndText#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Text.PrivateFontCollection>
- [使用字体和文本](using-fonts-and-text.md)
