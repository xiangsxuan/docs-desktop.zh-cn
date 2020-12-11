---
title: 如何：定义拆分窗口中的大小调整和定位行为
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 8cdcfdfaa135a92ed6a6e96d4a72de2c97f2493d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971214"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a>如何：定义拆分窗口中的大小调整和定位行为
控件的面板 <xref:System.Windows.Forms.SplitContainer> 非常适合用户调整大小和操作。 但是，有时您需要以编程方式控制拆分器（它的位置和可移动的程度）。  
  
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>控件的属性和其他属性 <xref:System.Windows.Forms.SplitContainer> 使你能够精确地控制用户界面的行为以满足你的需求。 下表列出了这些属性。  
  
|名称|描述|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 属性|确定拆分器是否通过键盘或鼠标可移动。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 属性|确定从左边缘或上边缘到可移动拆分栏的距离（以像素为单位）。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 属性|确定用户可以移动拆分器的最小距离（以像素为单位）。|  
  
 下面的示例修改 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 属性以创建 "对齐拆分器" 效果; 当用户拖动拆分器时，它将以10个像素（而不是默认值1）递增。  
  
### <a name="to-define-splitcontainer-resize-behavior"></a>定义 SplitContainer 调整大小行为  
  
1. 在过程中，将 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 属性设置为所需的大小，以便实现拆分器的 "对齐" 行为。  
  
     在下面的代码示例中，在窗体的 <xref:System.Windows.Forms.Form.Load> 事件中，控件中的拆分器 <xref:System.Windows.Forms.SplitContainer> 设置为在拖动时跳过10像素。  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
      (Visual c # ) 将以下代码放在窗体的构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     稍微向左或向右移动拆分器将没有明显的效果;但是，当鼠标指针在任一方向上都为10个像素时，拆分器将对齐到新位置。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
