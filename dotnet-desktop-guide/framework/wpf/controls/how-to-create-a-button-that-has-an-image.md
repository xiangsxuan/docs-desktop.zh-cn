---
title: 如何：创建包含图像的按钮
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: 5be928ac75ad727feabcde07ac0c6dc76ed130e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973982"
---
# <a name="how-to-create-a-button-that-has-an-image"></a>如何：创建包含图像的按钮
此示例演示如何在上包含图像 <xref:System.Windows.Controls.Button> 。  
  
## <a name="example"></a>示例  
 下面的示例创建两个 <xref:System.Windows.Controls.Button> 控件。 一个 <xref:System.Windows.Controls.Button> 包含文本，另一个包含图像。 图像位于名为 data 的文件夹中，该文件夹是该示例的项目文件夹的子文件夹。 用户单击 <xref:System.Windows.Controls.Button> 具有图像的时，背景和其他更改的文本 <xref:System.Windows.Controls.Button> 。  
  
 此示例 <xref:System.Windows.Controls.Button> 通过使用标记创建控件，但使用代码来编写 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件处理程序。  
  
 [!code-xaml[BtnColor#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a>另请参阅

- [控件](index.md)
- [控件库](control-library.md)
