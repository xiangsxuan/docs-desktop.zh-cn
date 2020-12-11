---
title: 设计本地化友好布局
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: ae52669d2547532fcdaabab9aeb2cf40a4a6fa2d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971852"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a>如何：设计适合本地化的 Windows 窗体布局

创建可供进行本地化的窗体极大地加速了国际市场的开发。 可以使用 <xref:System.Windows.Forms.TableLayoutPanel> 控件实现在控件因 <xref:System.Windows.Forms.Control.Text%2A> 属性值更改而调整大小时正常响应的布局。

## <a name="example"></a>示例

 此窗体演示如何创建在将显示的字符串值翻译成其它语言时按比例进行调整的布局。 这一翻译过程称为 *本地化*。 有关详细信息，请参阅[本地化](/dotnet/standard/globalization-localization/localization)。

 Visual Studio 中对此任务提供广泛支持。  另请参阅[演练：创建可根据本地化需要调整比例的布局](/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100))。

 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]

## <a name="additional-resources"></a>其他资源

1. [如何：在 TableLayoutPanel 控件中对齐和拉伸控件](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)

2. [演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)

3. [如何：在 TableLayoutPanel 控件中跨行和跨列](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)

4. [如何：在 TableLayoutPanel 控件中编辑行和列](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)

5. [演练：使用设计操作执行常规任务](perform-common-tasks-design-actions.md)

6. [演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)

7. [演练：使用 Padding、Margins 和 AutoSize 属性对 Windows 窗体控件进行布局](windows-forms-controls-padding-autosize.md)

8. [如何：使用 AutoSize 属性和 TableLayoutPanel 控件支持对 Windows 窗体的本地化](/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))

9. [演练：创建可根据数据输入需要调整大小的 Windows 窗体](/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))

## <a name="compiling-the-code"></a>编译代码

 此示例需要：

- 对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [本地化](/dotnet/standard/globalization-localization/localization)
