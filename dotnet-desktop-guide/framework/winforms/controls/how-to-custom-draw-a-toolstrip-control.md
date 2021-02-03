---
title: 如何：自定义绘制 ToolStrip 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], custom drawing
- drawing [Windows Forms], owner
- ProfessionalColorTable class [Windows Forms], overriding
- examples [Windows Forms], toolbars
- drawing [Windows Forms], custom
- toolbars [Windows Forms], changing colors
- ToolStrip control [Windows Forms], drawing
- ToolStrip control [Windows Forms], changing colors
- custom drawing
- owner drawing
ms.assetid: 94e7d7bd-a752-441c-b5b3-7acf98881163
ms.openlocfilehash: 9f34c0d62370b72de2c3ddf68fcc5fada918faa3
ms.sourcegitcommit: d7d89e96c827b6e20d9353d34c0aa329fdae0144
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506667"
---
# <a name="how-to-custom-draw-a-toolstrip-control"></a><span data-ttu-id="01a70-102">如何：自定义绘制 ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="01a70-102">How to: Custom Draw a ToolStrip Control</span></span>
<span data-ttu-id="01a70-103"><xref:System.Windows.Forms.ToolStrip> 控件具有以下关联的呈现（绘制）类：</span><span class="sxs-lookup"><span data-stu-id="01a70-103">The <xref:System.Windows.Forms.ToolStrip> controls have the following associated rendering (painting) classes:</span></span>  
  
- <span data-ttu-id="01a70-104"><xref:System.Windows.Forms.ToolStripSystemRenderer> 提供你使用的操作系统的外观和样式。</span><span class="sxs-lookup"><span data-stu-id="01a70-104"><xref:System.Windows.Forms.ToolStripSystemRenderer> provides the appearance and style of your operating system.</span></span>  
  
- <span data-ttu-id="01a70-105"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> 提供 Microsoft Office 的外观和样式。</span><span class="sxs-lookup"><span data-stu-id="01a70-105"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> provides the appearance and style of Microsoft Office.</span></span>  
  
- <span data-ttu-id="01a70-106"><xref:System.Windows.Forms.ToolStripRenderer> 是其他两个呈现类的抽象基类。</span><span class="sxs-lookup"><span data-stu-id="01a70-106"><xref:System.Windows.Forms.ToolStripRenderer> is the abstract base class for the other two rendering classes.</span></span>  
  
 <span data-ttu-id="01a70-107">若要对 <xref:System.Windows.Forms.ToolStrip> 进行自定义绘制（也称为所有者描述），可以重写其中一个呈现器类，并更改呈现逻辑的一个方面。</span><span class="sxs-lookup"><span data-stu-id="01a70-107">To custom draw (also known as owner draw) a <xref:System.Windows.Forms.ToolStrip>, you can override one of the renderer classes and change an aspect of the rendering logic.</span></span>  
  
 <span data-ttu-id="01a70-108">下面的过程描述自定义绘制的各个方面。</span><span class="sxs-lookup"><span data-stu-id="01a70-108">The following procedures describe various aspects of custom drawing.</span></span>  
  
## <a name="switch-between-the-provided-renderers"></a><span data-ttu-id="01a70-109">在提供的呈现器之间切换</span><span class="sxs-lookup"><span data-stu-id="01a70-109">Switch between the provided renderers</span></span>
  
- <span data-ttu-id="01a70-110">将 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 属性设置为所需的 <xref:System.Windows.Forms.ToolStripRenderMode> 值。</span><span class="sxs-lookup"><span data-stu-id="01a70-110">Set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to the <xref:System.Windows.Forms.ToolStripRenderMode> value you want.</span></span>  
  
     <span data-ttu-id="01a70-111">使用 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>，静态 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 为应用程序确定呈现器。</span><span class="sxs-lookup"><span data-stu-id="01a70-111">With <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>, the static <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> determines the renderer for your application.</span></span> <span data-ttu-id="01a70-112"><xref:System.Windows.Forms.ToolStripRenderMode> 的其他值为 <xref:System.Windows.Forms.ToolStripRenderMode.Custom>、<xref:System.Windows.Forms.ToolStripRenderMode.Professional> 和 <xref:System.Windows.Forms.ToolStripRenderMode.System>。</span><span class="sxs-lookup"><span data-stu-id="01a70-112">The other values of <xref:System.Windows.Forms.ToolStripRenderMode> are <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional>, and <xref:System.Windows.Forms.ToolStripRenderMode.System>.</span></span>  
  
## <a name="change-the-officestyle-borders"></a><span data-ttu-id="01a70-113">更改 Office 样式边框</span><span class="sxs-lookup"><span data-stu-id="01a70-113">Change the Office–style borders</span></span>
  
- <span data-ttu-id="01a70-114">重写 <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>，但不调用基类。</span><span class="sxs-lookup"><span data-stu-id="01a70-114">Override <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, but do not call the base class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01a70-115">此方法没有针对 <xref:System.Windows.Forms.ToolStripRenderer>、<xref:System.Windows.Forms.ToolStripSystemRenderer> 和 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 的版本。</span><span class="sxs-lookup"><span data-stu-id="01a70-115">There is a version of this method for <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer>, and <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span></span>  
  
## <a name="change-the-professionalcolortable"></a><span data-ttu-id="01a70-116">更改 ProfessionalColorTable</span><span class="sxs-lookup"><span data-stu-id="01a70-116">Change the ProfessionalColorTable</span></span>
  
- <span data-ttu-id="01a70-117">重写 <xref:System.Windows.Forms.ProfessionalColorTable> 并更改所需的颜色。</span><span class="sxs-lookup"><span data-stu-id="01a70-117">Override <xref:System.Windows.Forms.ProfessionalColorTable> and change the colors you want.</span></span>  

  ```csharp
  public partial class Form1 : Form
  {
      public Form1()
      {
          InitializeComponent();
      }
  
      private void Form1_Load(object sender, EventArgs e)
      {
          var colorTable = new MyColorTable();
          toolStrip1.Renderer = new ToolStripProfessionalRenderer(colorTable);
      }
  
      class MyColorTable: ProfessionalColorTable
      {
          public override System.Drawing.Color ButtonPressedGradientBegin => Color.Red;
          public override System.Drawing.Color ButtonPressedGradientMiddle => Color.Blue;
          public override System.Drawing.Color ButtonPressedGradientEnd => Color.Green;
          public override System.Drawing.Color ButtonSelectedGradientBegin => Color.Yellow;
          public override System.Drawing.Color ButtonSelectedGradientMiddle => Color.Orange;
          public override System.Drawing.Color ButtonSelectedGradientEnd => Color.Violet;
      }
  }
  ```

  ```vb
  Public Class Form1
      Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
          Dim colorTable As New MyColorTable
          ToolStrip1.Renderer = New ToolStripProfessionalRenderer(colorTable)
      End Sub
  
      Class MyColorTable
          Inherits ProfessionalColorTable
  
          Public Overrides ReadOnly Property ButtonPressedGradientBegin() As System.Drawing.Color
              Get
                  Return Color.Red
              End Get
          End Property
  
          Public Overrides ReadOnly Property ButtonPressedGradientMiddle() As System.Drawing.Color
              Get
                  Return Color.Blue
              End Get
          End Property
  
          Public Overrides ReadOnly Property ButtonPressedGradientEnd() As System.Drawing.Color
              Get
                  Return Color.Green
              End Get
          End Property
  
          Public Overrides ReadOnly Property ButtonSelectedGradientBegin() As System.Drawing.Color
              Get
                  Return Color.Yellow
              End Get
          End Property
  
          Public Overrides ReadOnly Property ButtonSelectedGradientMiddle() As System.Drawing.Color
              Get
                  Return Color.Orange
              End Get
          End Property
  
          Public Overrides ReadOnly Property ButtonSelectedGradientEnd() As System.Drawing.Color
              Get
                  Return Color.Violet
              End Get
          End Property
      End Class
  End Class
  ```
  
## <a name="change-rendering-for-all-toolstrips"></a><span data-ttu-id="01a70-118">更改所有 ToolStrips 的渲染</span><span class="sxs-lookup"><span data-stu-id="01a70-118">Change rendering for all ToolStrips</span></span>
  
1. <span data-ttu-id="01a70-119">使用 <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> 属性从提供的呈现器中选择一个。</span><span class="sxs-lookup"><span data-stu-id="01a70-119">Use the <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> property to choose one of the provided renderers.</span></span>  
  
2. <span data-ttu-id="01a70-120">使用 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 分配自定义呈现器。</span><span class="sxs-lookup"><span data-stu-id="01a70-120">Use <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> to assign a custom renderer.</span></span>  
  
3. <span data-ttu-id="01a70-121">确保 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> 已设置为默认值 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>。</span><span class="sxs-lookup"><span data-stu-id="01a70-121">Ensure that <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> is set to the default value of <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
## <a name="turn-off-the-office-colors"></a><span data-ttu-id="01a70-122">关闭办公室颜色</span><span class="sxs-lookup"><span data-stu-id="01a70-122">Turn off the Office colors</span></span>
  
- <span data-ttu-id="01a70-123">将 <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> 设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="01a70-123">Set <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> to `false`.</span></span>  
  
## <a name="turn-off-the-office-colors-for-one-toolstrip"></a><span data-ttu-id="01a70-124">关闭一个 ToolStrip 的办公室颜色</span><span class="sxs-lookup"><span data-stu-id="01a70-124">Turn off the Office colors for one ToolStrip</span></span>
  
- <span data-ttu-id="01a70-125">使用类似于以下代码示例的代码。</span><span class="sxs-lookup"><span data-stu-id="01a70-125">Use code similar to the following code example.</span></span>  

  ```csharp
  ProfessionalColorTable colorTable = new ProfessionalColorTable();
  colorTable.UseSystemColors = true;
  toolStrip1.Renderer = new ToolStripProfessionalRenderer(colorTable);
  ```
  
  ```vb
  Dim colorTable As New ProfessionalColorTable
  colorTable.UseSystemColors = True
  ToolStrip1.Renderer = new ToolStripProfessionalRenderer(colorTable)
  ```
  
## <a name="see-also"></a><span data-ttu-id="01a70-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01a70-126">See also</span></span>

- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripRenderer>
- [<span data-ttu-id="01a70-127">具有内置所有者描述支持的控件</span><span class="sxs-lookup"><span data-stu-id="01a70-127">Controls with Built-In Owner-Drawing Support</span></span>](controls-with-built-in-owner-drawing-support.md)
- [<span data-ttu-id="01a70-128">如何：在 Windows 窗体中为 ToolStrip 控件创建和设置自定义呈现器</span><span class="sxs-lookup"><span data-stu-id="01a70-128">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)
- [<span data-ttu-id="01a70-129">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="01a70-129">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
