---
title: 如何：水平拆分窗口
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], horizontal splitter
- splitter windows [Windows Forms], changing splitter orientation
- splitter windows [Windows Forms], horizontal
- windows [Windows Forms], splitting horizontally
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
ms.openlocfilehash: 7ef3fe1210ae42c52a4fd7f23633d6566bc102a5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96972544"
---
# <a name="how-to-split-a-window-horizontally"></a>如何：水平拆分窗口
下面的代码示例将使控件成为水平分隔的拆分器 <xref:System.Windows.Forms.SplitContainer> 。  
  
> [!NOTE]
> <xref:System.Windows.Forms.SplitContainer.Orientation%2A>控件的属性 <xref:System.Windows.Forms.SplitContainer> 决定拆分器的方向，而不是控件本身的方向。  
  
### <a name="to-split-a-window-horizontally"></a>水平拆分窗口  
  
1. 在过程中，将 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 控件的属性设置 <xref:System.Windows.Forms.SplitContainer> 为 <xref:System.Windows.Forms.Orientation.Horizontal> 。  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer 控件](splitcontainer-control-windows-forms.md)
