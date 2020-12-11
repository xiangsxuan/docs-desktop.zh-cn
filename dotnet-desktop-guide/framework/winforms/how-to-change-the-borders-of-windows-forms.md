---
title: 更改窗体边框
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: 8742f137b6dc53880b02d1cd667813aa728a6cfa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970270"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a>如何：更改 Windows 窗体的边框

当确定 Windows 窗体的外观和行为时，有几种边框样式可供选择。 通过更改 <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 属性，可控制窗体调整大小的行为。 此外，设置 <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 会影响标题栏的显示方式以及其上出现的按钮布局。 有关详细信息，请参阅 <xref:System.Windows.Forms.FormBorderStyle>。  
  
 Visual Studio 中对此任务提供广泛支持。  
  
 另请参阅 [如何：使用设计器更改 Windows 窗体的边框](/previous-versions/visualstudio/visual-studio-2010/yettzh3e(v=vs.100))。  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a>以编程方式设置 Windows 窗体的边框样式  
  
- 将 <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 属性设置为所需的样式。 下面的代码示例将窗体的边框样式设置 `DlgBx1` 为 <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> 。  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     另请参阅 [如何：在设计时创建对话框](/previous-versions/visualstudio/visual-studio-2010/55cz5x2c(v=vs.100))。  
  
     此外，如果为提供可选的 " **最小化** " 和 " **最大化** " 按钮的窗体选择了边框样式，则可以指定是要使这两个按钮中的一个或两个按钮都正常运行。 当想要密切控制用户体验时，这些按钮会非常有用。 默认情况下，" **最小化** " 和 " **最大化** " 按钮处于启用状态，并且通过 " **属性** " 窗口操作其功能。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.FormBorderStyle>
- <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>
- [入门与 Windows 窗体](getting-started-with-windows-forms.md)
