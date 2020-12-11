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
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="66138-102">如何：在 Windows 窗体中为 ToolStrip 控件创建和设置自定义呈现器</span><span class="sxs-lookup"><span data-stu-id="66138-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="66138-103"><xref:System.Windows.Forms.ToolStrip> 控件提供对主题和样式的简单支持。</span><span class="sxs-lookup"><span data-stu-id="66138-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="66138-104">可以通过将 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 属性或 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 属性设置为自定义呈现器来实现完全自定义的外观和行为 (的外观) 。</span><span class="sxs-lookup"><span data-stu-id="66138-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="66138-105">可以向每个单独 <xref:System.Windows.Forms.ToolStrip> 的、或控件分配呈现器， <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.StatusStrip> 也可以 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> 通过将属性设置为来使用属性来影响所有对象 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="66138-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66138-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A><xref:System.Windows.Forms.ToolStripRenderMode.Custom>仅当的值 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 不为时返回 `null` 。</span><span class="sxs-lookup"><span data-stu-id="66138-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="66138-107">创建自定义呈现器</span><span class="sxs-lookup"><span data-stu-id="66138-107">To create a custom renderer</span></span>  
  
1. <span data-ttu-id="66138-108">扩展 <xref:System.Windows.Forms.ToolStripRenderer> 类。</span><span class="sxs-lookup"><span data-stu-id="66138-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2. <span data-ttu-id="66138-109">通过重写适当 *的* 来实现所需的自定义呈现</span><span class="sxs-lookup"><span data-stu-id="66138-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="66138-110">members</span><span class="sxs-lookup"><span data-stu-id="66138-110">members</span></span>  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="66138-111">将自定义呈现器设置为当前呈现器</span><span class="sxs-lookup"><span data-stu-id="66138-111">To set the custom renderer to be the current renderer</span></span>  
  
1. <span data-ttu-id="66138-112">若要设置一个自定义呈现器 <xref:System.Windows.Forms.ToolStrip> ，请将 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 属性设置为自定义呈现器。</span><span class="sxs-lookup"><span data-stu-id="66138-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. <span data-ttu-id="66138-113">或者，为应用程序中包含的所有类设置自定义呈现器 <xref:System.Windows.Forms.ToolStrip> ：将 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 属性设置为自定义呈现器并将 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 属性设置为 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> 。</span><span class="sxs-lookup"><span data-stu-id="66138-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="66138-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66138-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="66138-115">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="66138-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="66138-116">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="66138-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="66138-117">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="66138-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
