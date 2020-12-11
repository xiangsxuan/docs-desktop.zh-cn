---
title: 在 Windows 窗体应用程序中响应字体方案更改
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: e3b96139a7cfd4b268d81b1da58229527e2beb87
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96973304"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a>如何：在 Windows 窗体应用程序中响应字体方案更改
在 Windows 操作系统中，用户可以更改系统范围的字体设置，使默认字体显得更大或更小。 更改这些字体设置对于视觉障碍的用户非常重要，需要更大的类型才能在屏幕上读取文本。 可以通过增加或减少窗体的大小和所有包含的文本，只要字体方案发生更改，就可以调整 Windows 窗体应用程序来做出这些更改。 如果希望窗体动态地适应字体大小的变化，则可以将代码添加到窗体中。  
  
 通常情况下，Windows 窗体使用的默认字体是由 <xref:Microsoft.Win32> 命名空间调用返回的字体 `GetStockObject(DEFAULT_GUI_FONT)` 。 此调用返回的字体仅在屏幕分辨率发生更改时才会更改。 如下面的过程所示，你的代码必须将默认字体更改为 <xref:System.Drawing.SystemFonts.IconTitleFont%2A> ，以响应字体大小的变化。  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a>使用桌面字体并响应字体方案更改  
  
1. 创建窗体，并向其添加所需的控件。 有关详细信息，请参阅 [如何：从命令行创建 Windows 窗体应用程序](how-to-create-a-windows-forms-application-from-the-command-line.md) 和 [要在 Windows 窗体上使用的控件](./controls/controls-to-use-on-windows-forms.md)。  
  
2. 向代码添加对 <xref:Microsoft.Win32> 命名空间的引用。  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3. 将以下代码添加到窗体的构造函数，以挂钩必需的事件处理程序，并更改窗体使用的默认字体。  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4. 实现事件的处理程序 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> ，该事件使窗体在类别更改时自动缩放 <xref:Microsoft.Win32.UserPreferenceCategory.Window> 。  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5. 最后，为 <xref:System.Windows.Forms.Form.FormClosing> 分离 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 事件处理程序的事件实现处理程序。  
  
     > [!IMPORTANT]
     > 如果不包含此代码，将导致应用程序泄漏内存。  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6. 编译并运行该代码。  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a>在 Windows XP 中手动更改字体方案  
  
1. 在 Windows 窗体应用程序运行时，右键单击 Windows 桌面并从快捷菜单中选择 " **属性** "。  
  
2. 在 " **显示属性** " 对话框中，单击 " **外观** " 选项卡。  
  
3. 从 " **字体大小** " 下拉列表框中，选择新字号。  
  
     你会注意到，窗体现在会对桌面字体方案中的运行时更改做出反应。 当用户在 **普通**、 **大型字体** 和 **超大字体** 之间更改时，窗体将更改字体并正确缩放。  
  
## <a name="example"></a>示例  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 此代码示例中的构造函数包含对的调用 `InitializeComponent` ，该调用是在 Visual Studio 中创建新 Windows 窗体项目时定义的。 如果要在命令行上生成应用程序，请删除此代码行。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [Windows 窗体中的自动缩放](automatic-scaling-in-windows-forms.md)
