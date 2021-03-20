---
title: 如何：在混合应用程序中启用视觉对象样式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: 37278005445d5574ba1d8ba927b672fe71699360
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "104665908"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a><span data-ttu-id="8c326-102">如何：在混合应用程序中启用视觉对象样式</span><span class="sxs-lookup"><span data-stu-id="8c326-102">How to: Enable Visual Styles in a Hybrid Application</span></span>

<span data-ttu-id="8c326-103">本主题演示如何对基于的应用程序中承载的 Windows 窗体控件启用视觉样式 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="8c326-103">This topic shows how to enable visual styles on a Windows Forms control hosted in a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
 <span data-ttu-id="8c326-104">如果你的应用程序调用 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 方法，则大部分 Windows 窗体控件将自动使用视觉样式。</span><span class="sxs-lookup"><span data-stu-id="8c326-104">If your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method, most of your Windows Forms controls will automatically use visual styles.</span></span> <span data-ttu-id="8c326-105">有关详细信息，请参阅 [用视觉样式呈现控件](/dotnet/framework/winforms/controls/rendering-controls-with-visual-styles)。</span><span class="sxs-lookup"><span data-stu-id="8c326-105">For more information, see [Rendering Controls with Visual Styles](/dotnet/framework/winforms/controls/rendering-controls-with-visual-styles).</span></span>  
  
 <span data-ttu-id="8c326-106">有关本主题中所述任务的完整代码列表，请参阅 [在混合应用程序示例中启用视觉样式](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfWithVisualStyles)。</span><span class="sxs-lookup"><span data-stu-id="8c326-106">For a complete code listing of the tasks illustrated in this topic, see [Enabling Visual Styles in a Hybrid Application Sample](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfWithVisualStyles).</span></span>  
  
## <a name="enabling-windows-forms-visual-styles"></a><span data-ttu-id="8c326-107">启用 Windows 窗体视觉样式</span><span class="sxs-lookup"><span data-stu-id="8c326-107">Enabling Windows Forms Visual Styles</span></span>  
  
#### <a name="to-enable-windows-forms-visual-styles"></a><span data-ttu-id="8c326-108">启用 Windows 窗体视觉样式</span><span class="sxs-lookup"><span data-stu-id="8c326-108">To enable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="8c326-109">创建一个 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 名为的应用程序项目 `HostingWfWithVisualStyles` 。</span><span class="sxs-lookup"><span data-stu-id="8c326-109">Create a [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Application project named `HostingWfWithVisualStyles`.</span></span>  
  
2. <span data-ttu-id="8c326-110">在解决方案资源管理器中，添加对下列程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="8c326-110">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="8c326-111">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="8c326-111">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="8c326-112">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="8c326-112">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="8c326-113">在 "工具箱" 中，双击该 <xref:System.Windows.Controls.Grid> 图标以将 <xref:System.Windows.Controls.Grid> 元素放在设计图面上。</span><span class="sxs-lookup"><span data-stu-id="8c326-113">In the Toolbox, double-click the <xref:System.Windows.Controls.Grid> icon to place a <xref:System.Windows.Controls.Grid> element on the design surface.</span></span>  
  
4. <span data-ttu-id="8c326-114">在属性窗口中，将和属性的值 <xref:System.Windows.FrameworkElement.Height%2A> 设置 <xref:System.Windows.FrameworkElement.Width%2A> 为 " **自动**"。</span><span class="sxs-lookup"><span data-stu-id="8c326-114">In the Properties window, set the values of the <xref:System.Windows.FrameworkElement.Height%2A> and <xref:System.Windows.FrameworkElement.Width%2A> properties to **Auto**.</span></span>  
  
5. <span data-ttu-id="8c326-115">在设计视图或 XAML 视图中，选择 <xref:System.Windows.Window> 。</span><span class="sxs-lookup"><span data-stu-id="8c326-115">In Design view or XAML view, select the <xref:System.Windows.Window>.</span></span>  
  
6. <span data-ttu-id="8c326-116">在属性窗口中，单击 " **事件** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="8c326-116">In the Properties window, click the **Events** tab.</span></span>  
  
7. <span data-ttu-id="8c326-117">双击该 <xref:System.Windows.FrameworkElement.Loaded> 事件。</span><span class="sxs-lookup"><span data-stu-id="8c326-117">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>
  
8. <span data-ttu-id="8c326-118">在 Mainwindow.xaml 或 Mainwindow.xaml 中，插入以下代码以处理 <xref:System.Windows.FrameworkElement.Loaded> 事件。</span><span class="sxs-lookup"><span data-stu-id="8c326-118">In MainWindow.xaml.vb or MainWindow.xaml.cs, insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. <span data-ttu-id="8c326-119">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="8c326-119">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="8c326-120">Windows 窗体控件用视觉样式绘制。</span><span class="sxs-lookup"><span data-stu-id="8c326-120">The Windows Forms control is painted with visual styles.</span></span>  
  
## <a name="disabling-windows-forms-visual-styles"></a><span data-ttu-id="8c326-121">禁用 Windows 窗体视觉样式</span><span class="sxs-lookup"><span data-stu-id="8c326-121">Disabling Windows Forms Visual Styles</span></span>  

 <span data-ttu-id="8c326-122">若要禁用视觉样式，只需移除对方法的调用 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 。</span><span class="sxs-lookup"><span data-stu-id="8c326-122">To disable visual styles, simply remove the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
#### <a name="to-disable-windows-forms-visual-styles"></a><span data-ttu-id="8c326-123">禁用 Windows 窗体视觉样式</span><span class="sxs-lookup"><span data-stu-id="8c326-123">To disable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="8c326-124">在代码编辑器中打开 MainWindow.xaml.vb 或 MainWindow.xaml.cs。</span><span class="sxs-lookup"><span data-stu-id="8c326-124">Open MainWindow.xaml.vb or MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2. <span data-ttu-id="8c326-125">注释掉对方法的调用 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 。</span><span class="sxs-lookup"><span data-stu-id="8c326-125">Comment out the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
3. <span data-ttu-id="8c326-126">按 F5 生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="8c326-126">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="8c326-127">Windows 窗体控件将用默认系统样式进行绘制。</span><span class="sxs-lookup"><span data-stu-id="8c326-127">The Windows Forms control is painted with the default system style.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c326-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c326-128">See also</span></span>

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="8c326-129">使用视觉样式呈现控件</span><span class="sxs-lookup"><span data-stu-id="8c326-129">Rendering Controls with Visual Styles</span></span>](/dotnet/framework/winforms/controls/rendering-controls-with-visual-styles)
- [<span data-ttu-id="8c326-130">演练：在 WPF 中承载 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="8c326-130">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
