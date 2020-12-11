---
title: 如何：为 ToolStrip 控件创建和设置自定义呈现器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: 49db0d785155f19b7220ac64011eaf4253aaa7e9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96970165"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>如何：在 Windows 窗体中为 ToolStrip 控件创建和设置自定义呈现器
<xref:System.Windows.Forms.ToolStrip> 控件提供对主题和样式的简单支持。 可以通过将 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 属性或 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 属性设置为自定义呈现器来实现完全自定义的外观和行为 (的外观) 。  
  
 可以向每个单独 <xref:System.Windows.Forms.ToolStrip> 的、或控件分配呈现器， <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.StatusStrip> 也可以 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> 通过将属性设置为来使用属性来影响所有对象 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType> 。  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A><xref:System.Windows.Forms.ToolStripRenderMode.Custom>仅当的值 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 不为时返回 `null` 。  
  
### <a name="to-create-a-custom-renderer"></a>创建自定义呈现器  
  
1. 扩展 <xref:System.Windows.Forms.ToolStripRenderer> 类。  
  
2. 通过重写适当 *的* 来实现所需的自定义呈现 members  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>将自定义呈现器设置为当前呈现器  
  
1. 若要设置一个自定义呈现器 <xref:System.Windows.Forms.ToolStrip> ，请将 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 属性设置为自定义呈现器。  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. 或者，为应用程序中包含的所有类设置自定义呈现器 <xref:System.Windows.Forms.ToolStrip> ：将 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 属性设置为自定义呈现器并将 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 属性设置为 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> 。  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 控件体系结构](toolstrip-control-architecture.md)
- [ToolStrip 技术摘要](toolstrip-technology-summary.md)
