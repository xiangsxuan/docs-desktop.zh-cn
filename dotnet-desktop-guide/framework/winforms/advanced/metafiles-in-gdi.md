---
title: GDI+ 中的图元文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970802"
---
# <a name="metafiles-in-gdi"></a>GDI+ 中的图元文件
GDI + 提供 <xref:System.Drawing.Imaging.Metafile> 类，以便可以记录和显示图元文件。 图元文件（也称为矢量图像）是存储为一系列绘图命令和设置的图像。 在对象中记录的命令和设置 <xref:System.Drawing.Imaging.Metafile> 可以存储在内存中，也可以保存到文件或流中。  
  
## <a name="metafile-formats"></a>图元文件格式  
 GDI + 可以显示存储为以下格式的图元文件：  
  
- Windows 图元文件 (WMF)   
  
- 增强型图元文件 (EMF)  
  
- EMF +  
  
 GDI + 可以记录 EMF 和 EMF + 格式的图元文件，但不能以 WMF 格式记录。  
  
 EMF + 是 EMF 的扩展，它允许存储 GDI + 记录。 EMF + 格式有两种变体：仅限 EMF + 和 EMF + 双重。 仅限 EMF + 只包含 GDI + 记录的图元文件。 此类元文件可通过 GDI + 显示，但不能由 GDI 显示。 EMF + 双图元文件包含 GDI + 和 GDI 记录。 EMF + 双重图元文件中的每个 GDI + 记录都与备用的 GDI 记录配对。 此类元文件可通过 GDI + 或 GDI 来显示。  
  
 下面的示例显示之前保存为文件的图元文件。 图元文件的左上角显示 (100，100) 。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>另请参阅

- [图像、位图和图元文件](images-bitmaps-and-metafiles.md)
