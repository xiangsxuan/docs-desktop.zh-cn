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
# <a name="how-to-enumerate-installed-fonts"></a>如何：枚举已安装的字体
<xref:System.Drawing.Text.InstalledFontCollection>类继承自 <xref:System.Drawing.Text.FontCollection> 抽象基类。 可以使用 <xref:System.Drawing.Text.InstalledFontCollection> 对象枚举计算机上安装的字体。 <xref:System.Drawing.Text.FontCollection.Families%2A>对象的属性 <xref:System.Drawing.Text.InstalledFontCollection> 是对象的数组 <xref:System.Drawing.FontFamily> 。  
  
## <a name="example"></a>示例  
 以下示例列出了计算机上安装的所有字体系列的名称。 此代码检索 <xref:System.Drawing.FontFamily.Name%2A> <xref:System.Drawing.FontFamily> 由属性返回的数组中每个对象的属性 <xref:System.Drawing.Text.FontCollection.Families%2A> 。 检索系列名称后，它们会连接起来形成一个逗号分隔的列表。 然后， <xref:System.Drawing.Graphics.DrawString%2A> 类的方法 <xref:System.Drawing.Graphics> 在矩形中绘制以逗号分隔的列表。  
  
 如果运行示例代码，输出将类似于下图所示：  
  
 ![显示已安装字体系列的屏幕截图。](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例旨在与 Windows 窗体一起使用，并且它需要 <xref:System.Windows.Forms.PaintEventArgs> `e` ，这是的参数 <xref:System.Windows.Forms.PaintEventHandler> 。 此外，还应导入 <xref:System.Drawing.Text> 命名空间。  
  
## <a name="see-also"></a>另请参阅

- [使用字体和文本](using-fonts-and-text.md)
